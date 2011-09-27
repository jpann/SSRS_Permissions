SSRS_SetPermissions
========

This is a script for Microsoft SQL Report Server rs.exe that can be used to add a user or group as a certain role to folders in SSRS.

To run the script, you must specify the global variables ParentPath, UserGroup and UserRole as an argument to rs.exe by using the -v switch. See usage for more details.

Usage
-----

```
rs -i SetPermissions.rss -s http://localhost:8080/ReportServer -v ParentPath="/" -v UserGroup="domain\user" -v UserRole="Content Manager" 
```

* ParentPath	Set this to the parent folder in SSRS that you wish to apply the permissions to. 
			For example, setting this to "/" will set the user or group to have the specified role permissions in all sub folders.

* UserGroup	Set this to the domain user account or group you wish to give permissions to. 
			For example, it would be domain\user or computername\user.

* UserRole		Set this to the SSRS role you wish to use. You can also set this to "*" to use all catalog roles.

Logging
-----

Errors are logged to the file SSRS_SetPermissions_Error.log.

I'll be adding debug logging in the future.