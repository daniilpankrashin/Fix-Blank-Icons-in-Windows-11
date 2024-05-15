# Fix Blank Icons in Windows 11
This is a set of PowerShell commands for rebuilding system icon cache in Windows 11 which fixes the problem when some shortcuts on desktop, start menu or taskbar appear blank as on the screenshot bellow.

![blank-icon-windows-11](https://github.com/daniilpankrashin/Fix-Blank-Icons-in-Windows-11/assets/152285652/1abd8687-b858-4927-afaa-3f2b6dfdb53d)

### 1. Stop windows explorer task

```
taskkill /IM explorer.exe /F
```

### 2. Go to your %localdata% directory

```
cd C:\Users\your_username\AppData\Local
```

### 3. Delete IconCache.db file

```
rm IconCache.db
```

### 4. Go to your windows explorer directory

```
cd C:\Users\your_username\AppData\Local\Microsoft\Windows\Explorer
```

### 5. Delete all files starting with iconcache

```
rm iconcache*
```

### 6. Restart your system

```
Restart-Computer -Force
```


Windows 11 will rebuild icon cache during the boot process.
# Icon is still blank
If rebuilding icon cache didn't solve the problem check if the path to your icon is valid and navigate to the needed icon by clicking "Browse..." than open -> Ok -> Apply and restart the explorer.exe task through task manager.
