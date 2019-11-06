# AdobeCCKiller
Kill all Adobe Creative Cloud processes when Adobe product is not running!

Create .bat file like this:

@echo off
set EXE=adobeprocessname.exe
FOR /F %%x IN ('tasklist /NH /FI "IMAGENAME eq %EXE%"') DO IF %%x == %EXE% goto FOUND
taskkill /F /IM "Adobe Desktop Process.exe" & taskkill /F /IM "Adobe Desktop Service.exe" & taskkill /F /IM AdobeIPCBroker.exe & taskkill /F /IM AdobeUpdateService.exe & taskkill /F /IM CCXProcess.exe & taskkill /F /IM CCLibrary.exe & taskkill /F /IM AdobeNotificationClient.exe & taskkill /F /IM armsvc.exe & taskkill /F /IM AGSService.exe & taskkill /F /IM CoreSync.exe & taskkill /F /IM "Adobe Installer.exe" & taskkill /F /IM CreativeSDKAppServiceClient.exe & taskkill /F /IM backgroundTaskHost.exe & taskkill /F /IM RuntimeBroker.exe & taskkill /F /IM Node.exe
goto FIN
:FOUND
:FIN
exit
