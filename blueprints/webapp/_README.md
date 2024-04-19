This blueprint can be used to build and deploy any web-based .Net application to be deployed as an Azure App Service.

Proceed as follows:
1. Copy the azure-pipeline-webapp-start.yml file into the pipelines folder of your repository.
2. Set up the portfolioName and productName as usual. Set the publishFolder parameter to the relative path where your solution file is located.
3. Test your blueprint. At this point it will only do CI (build).
4. When you are ready to deploy, set the suppressCD parameter to false. Copy the azure-pipeline.webapp.config.yml fine into the AzureDevOps.Automation.Pipeline.Configuration.v2 repo in the appropriate folder for your application. You will need to set the variables in this file with the specific settings to deploy to your resource in Azure.
