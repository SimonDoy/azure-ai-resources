# Introduction

This folder holds Postman resources to create Azure AI Search Indexes using the Azure AI Search Index Api.
This is in particularly useful for setting up SharePoint Indexing with Azure AI Search.

## Getting started

To get started open Postman.
- Click on the file menu and choose import.
- Provide the following URL to download the Postman collection from GitHub and install into your Postman application.
    -- https://github.com/SimonDoy/azure-ai-resources/blob/main/azure-ai-search-postman/Azure%20AI%20Search.postman_collection.json

## Steps to setting up the Azure AI Search Index

Use the [Microsoft Learn instructions - Index data from SharePoint document libraries](https://learn.microsoft.com/en-us/azure/search/search-howto-index-sharepoint-online) inconjunction with these Postman requests.

You will need to setup an Microsoft Entra ID application first.

If you look at the variables tab within the collection, you can see there are a lot of variables which need configuring.
For the SharePoint Indexer you will need to configure the following:
- aisearch-instance-name - this is the name of your Azure AI Search service. e.g. i365-aisearch-copilot-dev
- aisearch-index-name - this is the name that you want to call your search index within Azure AI Search. e.g. sharepoint-index
- aisearch-indexer-name - this is the name that you want to call your indexer within Azure AI Search. e.g. sharepoint-indexer
- aisearch-datasource-name - this is the name that you want to give your datasource within Azure AI Search. e.g. sharepoint-demo-datasource
- aisearch-apikey - this is the api key that is used to authenticate with Azure AI Search. 
- SharePointOnlineEndpoint - this is the connection string that the Azure AI Search will use to connect to your data using the Microsoft Entra ID application. e.g. [SharePoint site url];ApplicationId=[Azure AD App ID];TenantId=[SharePoint site tenant id]
- aisearch-blob-storageaccountname - this is used for the Azure Blob Storage Indexing to tell the indexer which storage account your files are.
- aisearch-blob-storagecontainername - this is used for the Azure Blob Storage to point to where the files are stored in your Azure Storage account.
- aisearch-blob-storageaccountkey - this is used for the Azure Blog Storage Indexing to be able to authenticate with the Azure Blob Storage account.

Fill out this variables with the appropriate values.

Then run the requests in this order, following [Microsoft Learn instructions - Index data from SharePoint document libraries](https://learn.microsoft.com/en-us/azure/search/search-howto-index-sharepoint-online).
- Setup SharePoint Search Datasource
- Create Search Index for SharePoint Data
- Create Indexer for SharePoint Search
- Get Indexer Status
- Run Indexer
- Get Indexer Status (check for authentication issues)

