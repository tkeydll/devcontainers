ARG VARIANT=${templateOption:imageVariant}
FROM mcr.microsoft.com/devcontainers/powershell:0-${VARIANT}

SHELL ["pwsh", "-Command", "$ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';"]

# Install Azure CLI
RUN Invoke-WebRequest -Uri https://aka.ms/InstallAzureCLIDeb -OutFile ./azurecli_install.sh
RUN bash ./azurecli_install.sh && Remove-Item ./azurecli_install.sh
RUN az bicep install

WORKDIR /app

EXPOSE 8080
