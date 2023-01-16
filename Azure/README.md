### Install AZ CLI in PowerShell  
// Run PowerShell as administrator then run the command >>  

$ProgressPreference = 'SilentlyContinue'; Invoke-WebRequest -Uri https://aka.ms/installazurecliwindows -OutFile .\AzureCLI.msi; Start-Process msiexec.exe -Wait -ArgumentList '/I AzureCLI.msi /quiet'; rm .\AzureCLI.msi  

// restart PowerShell then run ***az version*** to verify installation  


---  
