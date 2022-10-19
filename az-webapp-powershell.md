
***Command Reference***

**1. New-AzAppServicePlan**
https://docs.microsoft.com/en-us/powershell/module/az.websites/new-azappserviceplan?view=azps-7.3.0

**2. New-AzWebApp**
https://docs.microsoft.com/en-us/powershell/module/az.websites/new-azwebapp?view=azps-7.3.0

# Step#1 creating variables
```
$ResourceGroupName="powershell-grp"
$Location="North Europe"
$AppServicePlanName="companyplan"
$WebAppName="companyapp10000"
```

# Step#2 signing into the Azure portal
```
Connect-AzAccount
```

# Step#3 creating new azure resource group for logical separation of the services
```
New-AzResouceGroup -Name $ResourceGroupName `
                   -Location $Location
```

# Step#4 We first need to create an App Service Plan
```
New-AzAppServicePlan -ResourceGroupName $ResourceGroupName `
                     -Name $AppServicePlanName `
                     -Location $Location `
                     -Tier "B1" `
                     -NumberofWorkers 1
```

# Step#5 Then we can create the Azure Web App in AZURE-WebApp-Services
```
New-AzWebApp -ResourceGroupName $ResourceGroupName `
             -Name $WebAppName `
             -Location $Location -AppServicePlan $AppServicePlanName
```
