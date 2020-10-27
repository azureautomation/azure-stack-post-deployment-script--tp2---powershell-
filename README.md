Azure Stack Post Deployment Script (TP2) (PowerShell)
=====================================================

            

***This script is for TP2 only. Follow me at [twitter](https://twitter.com/Ruud_Borst) for updates.***


**Blog:** [https://azurestack.blog/2017/01/azure-stack-post-deployment-script/](https://azurestack.blog/2017/01/azure-stack-post-deployment-script/)


Run this script after you deployed Azure Stack, it clears up space and improves the performance of your Azure Stack enviroment.


It cleans up winrm, tracing and diagnostic logfiles and disables the services and scheduled tasks generating them. Not clearing the WinRM log files is a well-known bug in TP2 and fills up the available space in increments of 4GB per day on every fabric VM
 and on the Host. Saving up space and gaining more performance on the host and its VMs, in particular, on the the MAS-XRP01. 'IE Enhanced Security' and 'User Account Control' will be disabled on the MAS-CON01, all for your management convenience. 


And last but not least it fixes, if necessary, the MAS-BGPNAT [Windows activation bug ](https://social.msdn.microsoft.com/Forums/azure/en-US/home?forum=AzureStack&announcementId=f35560ea-b0d2-4be0-b407-e20fe631d9fe )and the default domain[ password policy bug](https://docs.microsoft.com/en-us/azure/azure-stack/azure-stack-run-powershell-script#reset-the-password-expiration-to-180-days)so you can use the Azure Stack environment without being locked-out. Rerun the script if you experience the 'diagnostic profile' bug


        .EXAMPLE          .\PostDeployScript-AzureStack.ps1 -CheckLogsOnly
**        .EXAMPLE 
         .\PostDeployScript-AzureStack.ps1**


 


 


 

 

        
    
TechNet gallery is retiring! This script was migrated from TechNet script center to GitHub by Microsoft Azure Automation product group. All the Script Center fields like Rating, RatingCount and DownloadCount have been carried over to Github as-is for the migrated scripts only. Note : The Script Center fields will not be applicable for the new repositories created in Github & hence those fields will not show up for new Github repositories.
