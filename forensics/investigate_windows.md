```
systeminfo
```

-- get system info

```PS
PS C:\Users\Administrator> Get-WinEvent -Computer $env:COMPUTERNAME -FilterHashtable @{Logname='Security';ID=4672} | where {$_.Properties[1].Value -notmatch "SYSTEM|Guest"} | select @{N='User'; E={$_.Properties[1].Value}}, TimeCreated
```

-- 4624 is the event ID of log in

```
net user <user>
```

-- get info about account

```PS
Get-Item "Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Run"
```

-- details of processess executed at system start

```
net localgroup administrators
```

-- get users with admin privileges

```PS
Get-ScheduledTask
```

-- list scheduled tasks

```PS
Get-ScheduledTaskInfo -TaskName "<scheduled_task_name>" | Select *
```
-- gen info about scheduled task

```PS
Get-EventLog -LogName Security -Index 151109 -InstanceId 4672 | select *
```

```ps
Get-ChildItem -Path C:\ -Include hosts -Recurse
```

-- find hosts file

```
C:\inetpub\wwwroot
```
--  files associated with a Web Server on a Windows server











