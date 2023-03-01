# PowerShell files for capturing crash dumps from IIS and Kestrel webservers

It can be hard to debug crashes happening on live server running IIS or Kestrel.
This PowerShell utility allows you to capture memory debug files that you can later open in Visual Studio or your favorite debugger.

  ```w3wp.exe``` and ```dotnet.exe``` are supported.

There are two PowerShell files:
- ```EnableDumps.ps1  // Enable crash capturing```
- ```DisableDumps.ps1 // Disable crash capturing```

## Capture procedure
- The ```EnableDumps.ps1``` script will monitor your server in the background and wait for any crashes to occur. 
- Once a crash occur, the script will create a memory dump file in a folder of your choosing, e.g. ```c:\dumps```.
- The ```DisableDumps.ps1``` stops the monitoring process.

## How to use
1. Download both  ```.ps1```-files and store them in e.g. ```c:\dumps``` on your server.
2. Open PowerShell, and issue the commands specified below.

## in-process hosting model (w3wp.exe)
To enable monitoring:

```.\EnableDumps w3wp.exe c:\dumps```

To disable:

```.\DisableDumps w3wp.exe```

## out-of-process hosting model (dotnet.exe)
To enable monitoring:

```.\EnableDumps dotnet.exe c:\dumps```

To disable:

```.\DisableDumps dotnet.exe```


## Notes:
- Also see procdump: https://learn.microsoft.com/en-us/sysinternals/downloads/procdump
- https://learn.microsoft.com/en-us/aspnet/core/test/troubleshoot-azure-iis?view=aspnetcore-7.0
- Visual Studio can be used to open the crash dump files: https://visualstudio.microsoft.com/
