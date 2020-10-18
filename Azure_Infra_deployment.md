## 1. Create regitry 

az login
az account set --subscription "your subscription id"
az group create --name "nj-d-rg" --location "North Europe" --sku premium

az acr create --name njdcr --resource-group nj-d-rg --sku premium --admin-enabled true

## Create App service plan

az login
az account set --subscription "your subscription id"

Now deploy the webapp

az group deployment create --resource-group nj-d-rj --template-file ./azuredeploy.json



