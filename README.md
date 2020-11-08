# az-func-cli-example
Create an Azure Function only using the command line

```
func init FuncCliProj --dotnet

cd FuncCliProj

func new --name HttpExample --template "HTTP trigger" --authlevel "anonymous"

func start

az group create --name funcclirg --location westeurope

az storage account create --name funcclisa --location westeurope --resource-group funcclirg --sku Standard_LRS

az functionapp create --resource-group funcclirg --consumption-plan-location westeurope --runtime dotnet --name funcclifa --storage-account funcclisa --functions-version 3

func azure functionapp publish funcclifa
```