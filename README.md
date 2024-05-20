# Fix Blank Icons in Windows 11
This is a set of PowerShell commands for rebuilding system icon cache in Windows 11 which fixes the problem of some shortcuts on desktop, start menu or taskbar appearing blank as on the screenshot bellow.

![blank-icon-windows-11](https://github.com/daniilpankrashin/Fix-Blank-Icons-in-Windows-11/assets/152285652/1abd8687-b858-4927-afaa-3f2b6dfdb53d)

### 1. Stop windows explorer task

```
taskkill /IM explorer.exe /F
```

### 2. Delete IconCache.db file

```
Remove-Item "C:\Users\YOUR_USERNAME\AppData\Local\IconCache.db" -Recurse -Force
```

### 3. Delete all files starting with iconcache

```
Remove-Item "C:\Users\YOUR_USERNAME\AppData\Local\Microsoft\Windows\Explorer\iconcache*" -Recurse -Force
```

### 4. Restart your system

```
Restart-Computer -Force
```


Windows 11 will rebuild icon cache during the boot process.
# Icon is still blank?
If rebuilding icon cache didn't solve the problem for you check if the path to your icon is valid, click "Browse..." than navigate manually to the needed icon -> Open -> Ok -> Apply. Than restart the explorer.exe task through task manager.
