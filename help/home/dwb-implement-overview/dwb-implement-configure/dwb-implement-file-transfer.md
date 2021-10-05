---
description: 有关DWB中不同文件传输方法的快速指南。
title: 文件传输管理
uuid: a3e19f8a-1cc4-437c-9661-408f675109c0
exl-id: a0ecd8e1-6d6f-4811-9869-092837dc9e55
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 1%

---

# 文件传输管理{#file-transfer-governance}

有关DWB中不同文件传输方法的快速指南。

文件传输管理是将文件从内部目录传输到任何其他服务器或内部文件移动的标准过程。

## 不同的文件传输方法 {#section-972bb39ba1954c6ebd35f6d042593efe}

1. AWS(Amazon Web Services)

   1. 如果尚未安装，请举出票证在服务器上安装AWS命令行界面(请参阅[https://docs.aws.amazon.com/cli/latest/userguide/installing.html](https://docs.aws.amazon.com/cli/latest/userguide/installing.html))。
   1. 如何检查？ 尝试使用命令提示符配置AWS(请参阅[https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-getting-started.html](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-getting-started.html))。

1. 将文件从FTP服务器传输到NAS目录。

   1. FTP离线馈送从FTP服务器到NAS目录。 FTP需要以下详细信息。

      ftp_username

      ftp_password

      ftp_port

      ftp_address

      ftp_directory

      delete_ftp_files

      ftp_file_extension

      local_directory

      (FTP详细信息将在项目核对清单中提供。 使用外部ftp用户传输文件)

   1. 使用下面附加的ftp_winscp_get.pl脚本，并根据需要进行计划。

      ftp_winscp_get.pl

      此脚本应位于E:\scripts\Scripository\Library\Perl

      >[!NOTE]
      >
      >如果“Scripository”文件夹不可用，请参阅[Weekly Reprocess](../../../home/dwb-implement-overview/dwb-implement-configure/dwb-implement-reprocess-scripting.md#concept-60529e12d6d94386a02c1c6fdedf0295)以下载该文件夹。

   1. 根据ftp_address处的文件可用性计划脚本。
   1. 文件的命名约定应为YYYYMMDD-&lt;offline_feed_name>-00。*

1. 将文件从NAS目录传输到FTP服务器。

   1. 使用ftp_winscp_put.pl脚本并根据要求进行计划。

      此脚本应位于E:\scripts\Scripository\Library\Perl

      运行脚本时需要提供以下详细信息。

      ftp_username

      ftp_password

      ftp_port

      ftp_address

      ftp_directory

      delete_ftp_files

      ftp_file_extension

      local_directory

      ```
      #######################################################################################################################
      # PLUGIN NAME HERE
      my $pluginname = "FTP WinSCP";
      # 20140421 Script tp put files on the FTP
      #######################################################################################################################
      # INCLUDE SCRIPOSITORY CORE
      use FindBin;                 # locate this script
      BEGIN {push @INC, $FindBin::Bin}
      require 'core.pl';
      
         # check for the required parameters
       GetOptions('local_directory:s'     => \$local_directory,
                     'source_file_pattern:s' => \$source_file_pattern,
                     'ftp_file_extension:s' => \$ftp_file_extension,
                     'ftp_address=s'  => \$ftp_address,
                     'ftp_username=s'  => \$ftp_username,
                     'ftp_password:s'  => \$ftp_password,
                     'ftp_port:s'   => \$ftp_port,
                     'ftp_directory:s'     => \$ftp_directory,
           'log_directory:s'  => \$log_directory,
                     'error_directory:s'  => \$error_directory,
                     'mail_from:s'  => \$mail_from,
                     'mail_to:s'   => \$mail_to,
                     'host:s'   => \$host,
                     'trigger_directory:s' => \$trigger_directory,
                     'trigger_file_extension:s' => \$trigger_file_extension,
                     'delete_ftp_files:s'  => \$delete_ftp_files,);
      
       # FOR LEFT OVER PARAMS, WE CAN CHECK GLOBAL PARAMS
       check_parameters(@argv);
      
       my $ftp_winscp_script = "winscpscript.txt";
       if (index($trigger_file_extension, '.') != -1) {
        my @trigger_file_extension1=split(/\./,$trigger_file_extension,2);
        $trigger_file_extension =  $trigger_file_extension1[1];
       }
       if (index($ftp_file_extension, '.') != -1) {
        my @ftp_file_extension1=split(/\./,$ftp_file_extension,2);
        $ftp_file_extension =  $ftp_file_extension1[1];
       }
       if ($trigger_file_extension ne "_empty_" && $trigger_directory ne "_empty_") {
         print $trigger_file_extension;
        my $ftp_winscp_trigger_script = "winscpscript_trigger.txt";
        create_winscp_script($ftp_winscp_trigger_script,$ftp_port,$ftp_username,$ftp_password,$ftp_address,$trigger_directory,$ftp_directory,$delete_ftp_files,"*",$trigger_file_extension);
        sleep(10);
        system("\"E:\\Scripts\\Scripository\\Library\\WinSCP\\WinSCP.exe\" /console /script=$ftp_winscp_trigger_script /log=$logfile");
        $files = getFiles($trigger_directory,$trigger_file_extension,$days_ago,$months_ago);
        my $ftp_file_pattern="";
        my $numberoffiles = @$files;
        my $i=0;
        foreach my $trigger_file(@$files) {
         $i++;
         my $file_string=substr($trigger_file,length($trigger_directory), length($trigger_file)-length($trigger_directory));
         my @file_string1=split(/\./, $file_string, 2);
         if ($i == $numberoffiles) {
          $ftp_file_pattern.=$file_string1[0].".".$ftp_file_extension;
         }
         else {
          $ftp_file_pattern.=$file_string1[0].".".$ftp_file_extension.", ";
         }
      
        }
      
        #unlink($ftp_winscp_trigger_script);
        print $local_directory;
        print $trigger_directory;
        create_winscp_script($ftp_winscp_script,$ftp_port,$ftp_username,$ftp_password,$ftp_address,$local_directory,$ftp_directory,$delete_ftp_files,$ftp_file_pattern, "");
        runLogger("$pluginname: Sleeping for 10 sec to give enough time for the temp script to be available");
        sleep(10);
        runLogger("$pluginname: FTP started");
        system("\"E:\\Scripts\\Scripository\\Library\\WinSCP\\WinSCP.exe\" /console /script=$ftp_winscp_script /log=$logfile");
        runLogger("$pluginname: FTP ended");
      
       }
       else {
        if ($source_file_pattern eq "_empty_") {
         $source_file_pattern="*";
        }
        else {
         if (index($source_file_pattern, '.') != -1) {
          my @source_file=split(/\./,$source_file_pattern,2);
          $source_file_pattern =  $source_file[0];
         }
        }
        $ftp_file_extension=".".$ftp_file_extension;
      print $local_directory;
        create_winscp_script($ftp_winscp_script,$ftp_port,$ftp_username,$ftp_password,$ftp_address,$local_directory,$ftp_directory,$delete_ftp_files,$source_file_pattern,$ftp_file_extension);
        runLogger("$pluginname: Sleeping for 10 sec to give enough time for the temp script to be available");
        sleep(10);
        runLogger("$pluginname: FTP started");
        system("\"E:\\Scripts\\Scripository\\Library\\WinSCP\\WinSCP.exe\" /console /script=$ftp_winscp_script /log=$logfile");
        runLogger("$pluginname: FTP ended");
       }
       unlink($ftp_winscp_script);
      
      sub create_winscp_script() {
       my ($ftp_script,$ftp_port,$ftp_username,$ftp_password,$ftp_address,$local_directory,$ftp_directory,$delete_ftp_files,$file_pattern, $file_extension) = @_;
       open (FTP, "> $ftp_script") or die "Can't open log: $!";
       print FTP "\# Automatically answer all prompts negatively not to stall\n";
       print FTP "option batch on\n\n";
       print FTP "\# Disable overwrite confirmations that conflict with the previous\n";
       print FTP "option confirm off\n\n";
       print FTP "\# Connect using a password\n";
       if ($ftp_port eq "22") {
        print FTP "open sftp://$ftp_username:$ftp_password\@$ftp_address\n\n";
       }
       else {
        print FTP "open ftp://$ftp_username:$ftp_password\@$ftp_address\n\n";
       }
       print FTP "\# Change local directory\n";
       print FTP "lcd \"$local_directory\"\n\n";
       print FTP "\# Change remote directory\n";
       if ($ftp_directory eq "_empty_") {
       }
       else {
        print FTP "cd \"$ftp_directory\"\n\n";
       }
       print FTP "\# Force binary mode transfer\n";
       print FTP "option transfer binary\n\n";
       print FTP "\# Download the file to specified directory\n";
       my @get_files=split(/,/,$file_pattern);
       foreach my $file (@get_files){
        if ($delete_ftp_files eq "Y" || $delete_ftp_files eq "Yes") {
         print FTP "put -nopreservetime -nopermissions -delete $file$file_extension\n";
      
        }
        else {
         print FTP "put -nopreservetime -nopermissions $file$file_extension\n";
      
        }
      
       }
      
       print FTP "\n\n";
       print FTP "\# Disconnect\n";
       print FTP "close\n\n";
       print FTP "\# Exit WinSCP\n";
       print FTP "exit\n\n";
       close(FTP);
       runLogger("$pluginname: creating temporary winscp file");
      
      }
      ```

   1. 根据ftp_address处的文件可用性计划脚本。
   1. 文件的命名约定应为YYYYMMDD-&lt;offline_feed_name>-00。*

1. 将文件从一个NAS目录传输到其他NAS目录。

   1. 直接从其他NAS目录复制并粘贴文件。 请遵循以下流程：)

      登录到服务器 — >转到运行 — > \\server_name\E$ [新文件夹将打开并直接复制或移动文件]

   1. 使用“copy_files.pl”脚本将文件从一台服务器复制到其他服务器，或使用“move_files.pl”将文件从一台服务器移动到其他服务器。 (这些文件可在E:\scripts\Scripository中找到)
