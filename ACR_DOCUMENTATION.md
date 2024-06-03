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
![1](https://github.com/oputaolivia/AzureContainerRegistry/assets/72948572/f515a2d8-4922-4c21-9b81-a3dca43a6678)

3. Select the __Container__ blade and click on the create icon below __Azure Conatainer Registry__.
![2](https://github.com/oputaolivia/AzureContainerRegistry/assets/72948572/cdd266e3-3e99-415e-bc51-e63e873bfd2f)

4. On the __Basics__ tab, Select an Azure subscription and Resource Group in the project details section. 
![3](https://github.com/oputaolivia/AzureContainerRegistry/assets/72948572/e1964c8e-401e-4a39-b721-70c82d70ee67)

5. In the Instance details section input a registry name, select region and a pricing plan.
![4](https://github.com/oputaolivia/AzureContainerRegistry/assets/72948572/27f50f85-d978-426b-b6b7-6505571c224c)

6. Leaving every other fields as default, select __Review + Create__.
7. Once validation passes click __Create__
![5](https://github.com/oputaolivia/AzureContainerRegistry/assets/72948572/91b84776-fba0-48aa-b06a-09cabcdc44be)

## Create a Docker Image
Once the ACR is created go to the resource.

1. Open up the Azure CLI
![1](https://github.com/oputaolivia/AzureContainerRegistry/assets/72948572/b1345ffd-fc73-45cd-ad06-c4575378ba74)

2. Login to the ACR; first get the access token using the command

```
az acr login --name acrname --expose-token
```
> Replace acrname with your registry name

Then use the command below to finally login

```
docker login acrServerName -u 00000000-0000-0000-00000000000 -p accessToken
```
![2](https://github.com/oputaolivia/AzureContainerRegistry/assets/72948572/c0e98e1f-fb94-402d-9ac6-df41ce47f35c)

3. Create a dir![3](https://github.com/oputaolivia/AzureContainerRegistry/assets/72948572/178e8bd7-0c46-4bcd-93e4-3a8e01160fa7)
ectory which the dockerfile would sit in and move into the directory

4. Create the dockerfile
![5](https://github.com/oputaolivia/AzureContainerRegistry/assets/72948572/94eac788-510c-4434-8220-a947d627cca8)
![5a](https://github.com/oputaolivia/AzureContainerRegistry/assets/72948572/c7d2c040-d881-4901-9270-bfbf13ab1589)

5. You can confirm the docker image exists, by going to the ACR resource, Click on the repositories blade in the services tab.
![6](https://github.com/oputaolivia/AzureContainerRegistry/assets/72948572/8ecfafea-97b7-43cd-b968-618f3bebdb55)


## Create Azure Container App
1. Click on  __+ Create a Resource__.
![1](https://github.com/oputaolivia/AzureContainerRegistry/assets/72948572/beda680a-f99b-4998-b752-9cfdfbb53a2c)

2. Select the __Container__ blade and click on the create icon below __Container App__.
![2](https://github.com/oputaolivia/AzureContainerRegistry/assets/72948572/60da2d47-5a0c-4962-8cd9-0fd731d22100)

3. On the __Basics__ tab, Select an Azure subscription, Resource Group in the project details section also include a container app name, select deployment source to container image.
![3](https://github.com/oputaolivia/AzureContainerRegistry/assets/72948572/99eb1ec8-8248-4a91-b411-a42f8c0bf8fb)

4. Leaving everything in the container app environment as default.
![4](https://github.com/oputaolivia/AzureContainerRegistry/assets/72948572/5c963ac1-ae8a-4cba-9fc1-ccb181c51381)

5. On the __Container__ tab, uncheck use quickstart image and fill the necessary deatails.
![5](https://github.com/oputaolivia/AzureContainerRegistry/assets/72948572/4ee3ac98-be04-41d2-8162-ddffac2212ef)

6. Click on __Review + Create__.
7. Once validation passes, click on __Create__.
![6](https://github.com/oputaolivia/AzureContainerRegistry/assets/72948572/0bf4dc10-5b48-47a0-84c5-14b72c222f6a)


## Attach a custom domain with SSL to the Container App
