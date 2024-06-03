# Azure Container Registry
---

# Table of Content
1. [Create Azure Container Registry](#create-azure-container-registry)
2. [Create a Docker Image](#create-a-docker-image)
3. [Create Azure Container App](#create-azure-container-app)
4. [Attach a custom domain with SSL to the Container App](#attach-a-custom-domain-with-ssl-to-the-container-app)

## Create Azure Container Registry
1. Login to the [Azure Portal](https://portal.azure.com/).
2. Click on  __+ Create a Resource__.

3. Select the __Container__ blade and click on the create icon below __Azure Conatainer Registry__.

4. On the __Basics__ tab, Select an Azure subscription and Resource Group in the project details section. 

5. In the Instance details section input a registry name, select region and a pricing plan.

6. Leaving every other fields as default, select __Review + Create__.

7. Once validation passes click __Create__

## Create a Docker Image
Once the ACR is created go to the resource.

1. Open up the Azure CLI

2. Login to the ACR; first get the access token using the command

```
az acr login --name acrname --expose-token
```
> Replace acrname with your registry name

Then use the command below to finally login

```
docker login acrServerName -u 00000000-0000-0000-00000000000 -p accessToken
```

3. Create a directory which the dockerfile would sit in and move into the directory

4. Create the dockerfile

5. You can confirm the docker image exists, by going to the ACR resource, Click on the repositories blade in the services tab.


## Create Azure Container App
1. Click on  __+ Create a Resource__.

2. Select the __Container__ blade and click on the create icon below __Container App__.

3. On the __Basics__ tab, Select an Azure subscription, Resource Group in the project details section also include a container app name, select deployment source to container image.

4. Leaving everything in the container app environment as default.

5. On the __Container__ tab, uncheck use quickstart image and fill the necessary deatails.

6. Click on __Review + Create__.

7. Once validation passes, click on __Create__.


## Attach a custom domain with SSL to the Container App
