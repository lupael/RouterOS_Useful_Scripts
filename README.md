## RouterOS_Useful_Scripts
> MikroTik RouterOS Scripts for various use and shared among different projects. Repository contains ready to use scripts as well functions ready to use in larger projects. 
**Check also another repository with scripts related strictly to MikroTik CAPsMAN automation :link: [CAPsMAN Automation Scripts](https://github.com/lupael/MikroTik_CAPsMAN_Automation.git).**

![](https://img.shields.io/badge/scripting-routeros-important.svg)
![](https://img.shields.io/badge/mikrotik-routerBOARD-yellow)
![](https://img.shields.io/badge/network-automation-informational)

    
### Prerequisites

  -  :white_check_mark: RouterOS v6.40 or higher
  -  :white_check_mark: MikroTik CRS or CCR with LCD for RouterOS_LCD_Change.rsc
  
### How to use
> Use the following scripts to make your RouterOS management easier or use them in various larger scripts or projects 
:+1: 

#### FTP_Backup_Template.rsc
> This script creates two files via RouterOS scheduler as well creates FTP user and group: 
  - *.backup* file 
  - *.rsc* file 
  

#### RouterOS_All_Software_Download.rsc
> Automated download of all latest RouterOS standard packages. Tool recommended for CAPsMANs and DUDE servers

### RouterOS_Array_Append.rsc 
> Wrapper to append array elements

#### RouterOS_Auto_Firmware_Upgrade.rsc
> Checks if latest firmware is available. Installs it and sends email notification 

**Example**
```
$AutoFirmwareUpgrade smtpServer=smtpServer smtpPort=smtpPort domain=example.com \
recipient=recipient@example.com;
```

#### RouterOS_Auto_Software_Upgrade.rsc
> Checks if latest package is available. Downloads it, installs and sends email notification 

**Example** 
```
$PackageAutoDownload userName=userName password=password packagePath=path \
smtpServer=ipAddress smtpPort=poty domain=@example.com \
recipient=recipient@example.com;
```

#### RouterOS_Cloud_Backup.rsc
> Creates new backup file and uploads it to MikroTik Cloud

**Example**
```
$CloudBackup password=password;
```

#### RouterOS_Create_Directory.rsc
> RouterOS function that creates directory with defined name in the system. Can be used just to create directory or be a part of larger project. 

**Example**
 ```
 $CreateDirecotry userName=UserName password=Password directoryName=DirectoryName;
```

#### RouterOS_Dual_WAN_Failover.rsc
> Simple setup for DUAL WAN failover. Main WAN must be commented as WAN1. Secondary WAN must be commented as WAN2

#### RouterOS_Log_Filtering.rsc
> RouterOS function for log messages filtering based on message or time match stored in chosen output. 

**Example**
```
$LogFilter;
```

#### RouterOS_Log_To_Alert.rsc
 > RouterOS function sending mail alert if log entry matches message criteria.

**Example**
 ```
 $LogToAlert message="message" fileName="fileName" smtpServer=smtpServer smtpPort=smtpPort domain="@example.com" \ 
recipient="recipient@example.com";
 ```

#### RouterOS_Send_Email.rsc
> RouterOS function to send email via SMTP server. Function contains all common email fields like *to*, *cc*, *subject*, *body* and more. Function can be called itself in RouterOS or by other script.

**Example**
```
$SendEmail smtpServer=SMTPServer smtpPort=SMTPPort from=From to=To subject=Subject body=Body;
```

#### RouterOS_File_Logging.rsc
> RouterOS function adding log entry if file was added or removed.

**Example**
```
$FileToLog;
```

#### RouterOS_LCD_Change.rsc
> RouterOS function changing LCD mode from dark to light and vice versa based on schedule setup.

**Example**
```
$ChangeLcd lightModeStartTime="08:00:00" darkModeStartTime="17:00:00";
```

#### RouterOS_Low_Disk_Space.rsc
> RouterOS function generating mail alert if disk space is below defined treshhold.

**Example**
```
$LowDiskSpace treshhold=free_disk_space_in_%;
```

#### RouterOS_Mail_Backup.rsc
> Creates RouterOS backup and config file and sends them via email

**Example**
```
$MailBackup configName=configName backupName=backupName smtpServer=smtpServer smtpPort=smtpPort domain=@example.com \
recipient=recipient@example.com;
```

#### RouterOS_File_Screening.rsc
> Removes files by specific name or file extansion 

**Example**
```
$FileScreening keyWord=".txt";
```

#### RouterOS_Format_Drive.rsc
> Formats RouterOS additional drive

**Example**
```
$FormatDrive drive=0 fileSystem=ext3 label=data; 
```

#### RouterOS_Modulo.rsc
>Modulo function.

**Example**
```
$Modulo number=number_to_be_devided modulo=modulo_value;
```

#### RouterOS_Port_Knock.rsc
> Port Knock from RouterOS

**Example**
```
:global knockBase {"sourceIP1"="port23"; \
                   "sourceIP2"="port22"  \
                  };

$PortKnock base=$knockBase destinationAddress=destinationIP;
```

#### RouterOS_R_ARP.rsc
> ARP/RARP Function (shortange syntax) 

**Example**
```
$R_ARP mode=mode;
```

#### RouterOS_Radius_Monitor.rsc
> Sends Radius statistics via email

**Example**
```
$RadiusMonitor smtpServer=smtpServer smtpPort=smtpPort domain="@example.com" recipient="recipient@example.com";
```

#### RouterOS_Renew_License.rsc
> Renews RouterOS License 

**Example**
```
$RenewLicense account=account password=password level=level;
```

#### RouterOS_Load_Script.rsc
> Loads function to RouterOS environment

**Example**
```
$LoadScript scriptName=scriptName.rsc;
```

#### RouterOS_String_Generator.rsc
> Generates 6 char string based on dictionary 

**Example**
```
$GenerateString;
```

#### RouterOS_Reset_Interface.rsc
> Resets interface if particular IP does not respond 

**Example**
```
$ResetInterface ipAddress=ipAddress_To_Monitor interfaceName=interface_name;
```

#### RouterOS_Script_Fetch.rsc
> Fetches script from git to RouterOS directory

**Example**
```
$FetchScript url="https://example.repo.com" destinationPath="FolderName" destinationFileName="ScriptName" 

$FetchScript url="https://example.repo.com" destinationPath="FolderName" destinationFileName="ScriptName" isRun=true

$FetchScript url="https://example.repo.com" destinationPath="FolderName" destinationFileName="ScriptName" isSchedule=true\
interval="24" taskName="TaskName" startTime="startup"
```

#### RouterOS_Substring_Variable.rsc
> Substrings variable 

**Example**
```
$Substring findMode=true string="string" signA="A" signB "b";
```

#### RouterOS_User_alert.rsc
> After defined number of logon failure attempts in 1 hour sends email alert and blocks source IP on firewall

**Example**
```
$UserAlert message="message" treshhold=3 fileName="fileName" smtpServer=smtpServer smtpPort=smtpPort domain="@i4e.com.bd" \ 
recipient="recipient@i4e.com.bd";
```

#### RouterOS_FTP_Backup.rsc
> Creates backup files and sends them via FTP to FTP server

**Example**
```
$FTPBackup configName=configName backupName=backupName smtpServer=smtpServer smtpPort=smtpPort domain=@i4e.com.bd \
recipient=recipient@i4e.com.bd destPath=destPath ftpUser=user ftpPassword=password ftpServer=ftpserver;
```

#### RouterOS_Function_Template.rsc
> Function template that I use

#### RouterOS_PPP_Disconnect_Active_Sessions.rsc
> Disconnects all PPP active sessions at once

**Example**
```
$DisconnectPPPActveSessions;
```

#### RouterOS_Recreate_Bridge.rsc
> Recreates bridge if broken or misconfigured 

#### More scripts comming soon :) 

### Authors

  - Lupael
