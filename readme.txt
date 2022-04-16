https://docs.microsoft.com/en-us/aspnet/core/host-and-deploy/iis/troubleshoot?view=aspnetcore-2.2:

If the app uses the 

#### in-process hosting model, run the script for w3wp.exe:
.\EnableDumps w3wp.exe c:\dumps

#### After the crash has occurred, run the DisableDumps PowerShell script:
.\DisableDumps w3wp.exe



If the app uses the 

#### out-of-process hosting model, run the script for dotnet.exe:
.\EnableDumps dotnet.exe c:\dumps

#### After the crash has occurred, run the DisableDumps PowerShell script:
.\DisableDumps dotnet.exe


NOTE:
Also procdump from sysinternals