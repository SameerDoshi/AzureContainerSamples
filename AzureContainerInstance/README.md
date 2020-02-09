# Azure Container Instances

* [Link to Docs]

## Sample Code
Use the project to create and publish a container to an Azure Container Registry.
Use the code below (in Azure CloudShell, or CLI) to create an Azure Container Instance of the container you published above

$image="functionapp120200208051912.azurecr.io/functionapp1:20200209033849"
$RES_GROUP="rg-func-test"
$image="functionapp120200208051912.azurecr.io/functionapp1:20200209033849"
$ACR_LOGIN_SERVER="functionapp120200208051912.azurecr.io"
$ACR_User="FunctionApp120200208051912"
$ACR_Password="<replace>"
az container create --name aci-demo --resource-group $RES_GROUP --image $image --registry-login-server $ACR_LOGIN_SERVER --registry-username $ACR_User --registry-password $ACR_Password --dns-name-label sam33rsamp13-M --query ipAddress.fqdn --ports 80 8080