DuoPutty

-------------------------------------------------------------------------------------------------------------------------------------------------

DuoPutty is a tool that used to quick connect to multiple UNIX servers (even cisco devices), you can run commands/scripts on selected remote servers (revoke psftp, plink, putty, ftp, scopy). i.e, sftp files to selected unix server and run command to change owner, took off ctrm for text file.  Scopy files to selected server and change mode of files, then run the scripts. (scopy will took of ctrm automatically) 

ID/password stored locally (AES256 encrypted).

Common operations

1.Run any commands or scripts and return result for selected server. 
2.(s)ftp files to servers first and run command in remote servers or vice versa
3. scp file (same as sftp) to servers, took out ^M for text after Ascii file transferred, then run commands or vice versa.
4.Open putty login with stored id/password
 
-------------------------------------------------------------------------------------------------------------------------------------------------

Basic step

1. Select servers from predefined list in various domain or groups, you can edit server list.
   you also can input server name manually in "Input Host" combo box, it will store latest servers you recently login. You can just input server name and select radio button to add suffix.
2. Input your ID/Password. Password / ID can be saved and auto load for next time 
3. Select action: Login, ping or remote Exec command (or combine with scp, sftp  etc.)..

In Server list, you can put # after each server name as comments. Chars after # will treat as comments.

-------------------------------------------------------------------------------------------------------------------------------------------------

Find result

Find keyword in result is very useful, search result will show which servers include key words. i.e , you ping 200 servers and search “could not find host” to get dead server list
Or you run “lsuser -a id ALL | grep 269” and will get AIX server list that contain or not contain id 269 to determine 269 is used.   Or cat /etc/syslog.conf| grep @nykcon01.google to find which servers did not set up forward logs to company logs servers

sample_unix_cmds.txt include sample command I used, add yours as a cheatsheet.
  
-------------------------------------------------------------------------------------------------------------------------------------------------

Configuration Screen

You can set up 8 Domain / server Group. Domain Suffix and Domain login in id must accurate, login id should come with your actually id, include domain if required (mostly no domain required in UNIX LDAP /AD environment)

-------------------------------------------------------------------------------------------------------------------------------------------------

I have managed hundreds of UNIX servers in various domains (AIX, Redhat in LDAP, redhat in AD, and even Cisco), I use this tool to add /remove local users, deploy syslog.conf, email configure, inventory app installed on servers, check compliance settings,   generate result request by auditor and mostly, quick putty login.

(I use this tool to deploy a uniform sudoers from laptop to various servers, sample_deploysudo_ftp.txt contain ftp command used in deploy, sample_deploysudo_exec.txt contain scripts to backup/replace sudoers, it’s only take less 10 mins to deploy sudoers to hundreds of unix servers with one click)

It does save plenty of time for daily operations, hope you can enjoy it, any issues:
 Contact: duoputty@hotmail.com  ( will not check frequently)

-------------------------------------------------------------------------------------------------------------------------------------------------

PuTTY (Plink/Psftp/Pscopy) is an SSH and telnet client, developed originally by Simon Tatham. you can copy these tools to application folder if new version published (Plink is a little different, my version can auto store cached SSH key, Symantec (?) modified it? ). ftp is owned by Microsoft. Somw codes are copy/paste from internet (Thanks for everyone).
 

