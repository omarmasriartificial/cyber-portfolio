## Overview:
This tutorial guides you through creating an automated Windows shutdown task using PowerShell to interact with Task Scheduler.
## Use Case:
In a scenario where a company's IT department wants to reduce energy costs and improve security by ensuring all office computers are automatically shut down every evening. Many employees forget to turn off their machines, leading to power waste and potential security risks.
## Steps:
### 1. Run and Understand the command you want to automate.

The shutdown command is:

 ```shutdown.exe /s /f /t 0```

**Explanation:**
- /s -Shutdown the computer
- /f -Force close all running applications.
- /t -Time delay before shutdown (0 seconds).

### 2. Define the scheduled task with action, trigger, principal, and settings.
```powershell
$Action = New-ScheduledTaskAction -Execute "shutdown.exe" -Argument "/s /f /t 0"
$Trigger = New-ScheduledTaskTrigger -Daily -At 11:00PM
$Principal = New-ScheduledTaskPrincipal -UserId "SYSTEM" -LogonType ServiceAccount -RunLevel Highest
$Settings = New-ScheduledTaskSettingsSet -AllowStartIfOnBatteries -DontStopIfGoingOnBatteries -StartWhenAvailable

Register-ScheduledTask -TaskName "Daily_Shutdown" -Action $Action -Trigger $Trigger -Principal $Principal -Settings $Settings
```
**Explanation:**
- UserId "SYSTEM": runs the task as the system user (no login needed).
- RunLevel Highest: ensures admin privileges.
- The task runs daily at (example, 11:00 PM) and shuts down the machine immediately.

### 3. To verify task, run:

  ```Get-ScheduledTask -TaskName "Daily_Shutdown"```
### 4. (Optional) To delete task, run:

```Unregister-ScheduledTask -TaskName "Daily_Shutdown" -Confirm:$false```

### Why use powershell instead of task scheduler gui:
- Consistency: Ensures shutdown occurs regardless of who is logged in.
- Automation: Great for environments with regular maintenance or energy-saving policies.
- Scalability: Deploy the script across many machines easily

