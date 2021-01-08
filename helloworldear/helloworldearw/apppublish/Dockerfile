FROM mcr.microsoft.com/dotnet/framework/aspnet:4.8-windowsservercore-ltsc2019
#ARG source
WORKDIR /inetpub/wwwroot
COPY . .
RUN C:\Windows\system32\inetsrv\appcmd.exe set config /section:directoryBrowse /enabled:true
EXPOSE 80
