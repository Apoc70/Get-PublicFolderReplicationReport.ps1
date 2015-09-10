# Get-PublicFolderReplicationReport.ps1
Generates a report for Exchange 2010 Public Folder Replication.
    
This is an updated version of the Mike Walker (http://blog.mikewalker.me) to support non-ASCII environments.

##Description
This script will generate a report for Exchange 2010 Public Folder Replication. 

It returns general information, such as total number of public folders, total items in all public folders, total size of all items, the top 10 largest folders, and more. 

Additionally, it lists each Public Folder and the replication status on each server. 

By default, this script will scan the entire Exchange environment in the current domain and all public folders. 

This can be limited by using the -ComputerName and -FolderPath parameters.

##Inputs
ComputerName
This parameter specifies the Exchange 2010 server(s) to scan. If this is omitted, all Exchange servers with the Mailbox role in the current domain are scanned.

FolderPath
This parameter specifies the Public Folder(s) to scan. If this is omitted, all public folders are scanned.

Recurse
When used in conjunction with the FolderPath parameter, this will include all child Public Folders of the Folders listed in Folder Path.

AsHTML
Specifying this switch will have this script output HTML, rather than the result objects. This is independent of the Filename or SendEmail parameters and only controls the console output of the script.

Filename
Providing a Filename will save the HTML report to a file.

SendEmail
This switch will set the script to send an HTML email report. If this switch is specified, then the To, From and SmtpServers are required.

To
When SendEmail is used, this sets the recipients of the email report.

From
When SendEmail is used, this sets the sender of the email report.

SmtpServer
When SendEmail is used, this is the SMTP Server to send the report through.

Subject
When SendEmail is used, this sets the subject of the email report.

NoAttachment
When SendEmail is used, specifying this switch will set the email report to not include the HTML Report as an attachment. It will still be sent in the body of the email.

##Outputs
Generates an HTML report which can be stored in file system or send as an HTML email.

##Examples
```
$publicFolderPath = "\PF1\SUBPF1"
.\Get-PublicFolderReplicationReport.ps1 -ComputerName MXSRV01,MXSRV02,MXSRV03 -FolderPath $publicFolderPath -Recurse -Subject "Public Folder Environment Report [$($publicFolderPath)]" -AsHTML -To thomas@mcsmemail.de -From postmaster@mcsmemail.de -SmtpServer relay.mcsmemail.de -SendEmail
```

##TechNet Gallery
Find the script at TechNet Gallery
* https://gallery.technet.microsoft.com/Exchange-2010-Public-315ea9aa


##Credits
Written by: Thomas Stensitzki

Find me online:

* My Blog: https://www.granikos.eu/en/justcantgetenough
* Archived Blog:	http://www.sf-tools.net/
* Twitter:	https://twitter.com/apoc70
* LinkedIn:	http://de.linkedin.com/in/thomasstensitzki
* Github:	https://github.com/Apoc70

For more Office 365, Cloud Security and Exchange Server stuff checkout services provided by Granikos

* Blog:     http://blog.granikos.eu/
* Website:	https://www.granikos.eu/en/
* Twitter:	https://twitter.com/granikos_de

Additional Credits:
* 
