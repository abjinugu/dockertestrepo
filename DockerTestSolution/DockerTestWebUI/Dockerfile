# escape=`

FROM microsoft/aspnet
SHELL ["powershell", "-command"]

# Configure website
RUN md C:\inetpub\wwwroot\Application; `    
    New-WebApplication -Name 'DockerTestWebUI' `
				-Site 'Default Web Site' ` 
				-PhysicalPath 'C:\inetpub\wwwroot\Application' `
				-ApplicationPool '.NET v4.5';


# The final instruction copies the site you published earlier into the container.
COPY ./bin/Release/PublishOutput C:/inetpub/wwwroot/Application
COPY ./InitializeContainer.ps1 c:/

ENTRYPOINT powershell c:\InitializeContainer