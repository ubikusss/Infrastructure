# UiPathOrchestrator
[![HitCount](http://hits.dwyl.io/hteo1337/hteo1337/UiPathOrchestrator.svg)](http://hits.dwyl.io/hteo1337/hteo1337/UiPathOrchestrator)

[![Build Status](https://dev.azure.com/hteo-dev/Orchestrator/_apis/build/status/hteo1337.UiPathOrchestrator?branchName=master)](https://dev.azure.com/hteo-dev/Orchestrator/_build/latest?definitionId=4&branchName=master)

This ARM template will deploy UiPath Orchestrator (WebApp - single/multi node with scale out and scale in settings, depending on the number of instances) with following resources:</br>
-App Service with UiPath Orchestrator </br>
-App Service plan</br>
-Azure SQL Server with DB</br>
-Application Insights</br>
-Storage account</br>
-RedisCache (only if the parameter orchestratorInstances is greater than 1 and lower than 10)</br>
-Application Insights Rules (if the selected parameter orchestratorAlertRules is "yes" )</br>

Unlike the marketplace deployment this will:
- Not use unique strings
- Use download links directly from UiPath


Deployment steps:
1. Go to the Create UiDefinition [file](https://raw.githubusercontent.com/ubikusss/Infrastructure/master/Azure/Orchestrator/PaaS%26IaaS/Deploy/createUiDefinition.json)
2. Copy the contents and paste it [here](https://portal.azure.com/#blade/Microsoft_Azure_CreateUIDef/SandboxBlade)
3. Click Preview and fill in all the necessary fields according to the deployment type you need
4. In the last tab, `Review + Create` click on `View ouputs payload`
5. Copy the contents from the window that opened
6. Go here:

[![Deploy to Azure](https://azuredeploy.net/deploybutton.png)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fubikusss%2FInfrastructure%2Fmaster%2FAzure%2FOrchestrator%2FPaaS&IaaS%2FDeploy%2FmainTemplate.json)

7. Do not start filling in the parameters, but go to `Edit parameters`
8. Paste the parameters copied from the previous step:
- minimize the `parameters` entry
- select both brackets (`{...}`) for the parameters value
- paste the json copied from the outputs window
- click Save
9. Fill inthe Subscription, resource group and location.
10. Accept the terms if you will and click `Purchase`
11. ENJOY UiPath products!