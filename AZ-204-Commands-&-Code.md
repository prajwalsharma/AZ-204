##### 1. Configure logging for a web app

```powershell
az webapp log config --name "mywebapp" --resource-group "whizlab-rg" --docker-container-logging "filesystem"
```



##### 2. Download a web app's log history as a zip file 

```powershell
az webapp log download --ids "sdsd" --log-file "filename" --name "sds" --resource-group "rg"
```



##### 3. Get the details of a web app's logging configuration.

```powershell
az webapp log show --name "sds" --resource-group "myrg"
```



##### 4. Start live log tracing for a web app.

```powershell
az webapp log tail --name "mytail" --resource-group "myrg"
```



##### 5. Azure Functions Bindings

```javascript
{
    "bindings" : [
        {
            "type" : "queueTrigger",
            "direction" : "in",
            "name" : "neworder",
            "queueName" : "myQueue",
            "connection" : "STORAGE_CONNECTION_3000"
        },
        {
            "type" : "table",
            "direction" : "out",
            "name" : "$return",
            "tableName" : "myTable",
            "connection" : "MY_TABLE_STORAGE_ACCT_APP_SETTING"
        }
    ]
}
```



##### 6. A piece of software that provides reverse proxy, configurable traffic routing, and TLS termination for Kubernetes services?

```powershell
Answer: "Ingress Controller"
```



##### 7. Permission for "Microsoft Graph API" in storage account?

```powershell
Answer: "User.Read"
```



##### 8. Permission type for "Microsoft Graph API" in storage account?

```powershell
Answer: "Delegated"
```



##### 9. Permission name for "Azure Storage"?

```powershell
Answer: "user_impersonation"
```



##### 10. Permission type for "Azure Storage" in storage account?

```powershell
Answer: "Delegated"
```



##### 11. Application manifest file for Azure AD authentication?

```javascript
Answer: "oauth2AllowImplicitFlow"
```



##### 12. Which service is used to secure "Logic Apps"?

```javascript
Answer: "Integration Service Environment"
```



##### 13. Filter conditions in Service Bus?

```javascript
1. "Boolean Filters" : TrueFilter (accept all) or FalseFilter (reject all)

2. "SQL Filters" : SqlFilter (sql like expressions)

3. "Correlation Filters" : CorrelationFilter (condition matched against messages properties)
```



##### 14. Azure Kubernetes cluster with Azure AD

```powershell
# 1. Get the resource ID of your AKS cluster
az aks show --resource-group "myrg" --name "myAKSCluster" --query id -o tsv

#2. Create the first example group in Azure AD
az ad group create --display-name "appdev" --mail-nickname "appdev" --query objectId -o tsv

#3. Create an Azure role assignment for the appdev group
az role assignment create --assignee "appdev_ID" --role "Azure User Role" --scope "AKS_ID"
```



##### 15. Enable auto-scaling in Azure Web App?

```
1. Upgrade Web App to "Standard" plan.
2. Enable Auto-Scale
3. Add a scale rule
4. Configure a scale condition
```



##### 16. Code to implement push notifications

```c#
string connString = CloudConfigurationManager.GetSetting("Microsoft.NotificationHub.ConnectionString");

NotificationHubClient hub = NotificationHubClient.CreateClientFromConnectionString(connString, "myhub");

SubscriptionClient client = SubscriptionClient.CreateFromConnectionString(connString, myTopic, mySubscription);

await hub.SendWindowsNativeNotificationAsync(message);
```



##### 17. Code to upload images to Blob container?

```c#
CloudBlockBlob cloudBlockBlob = cloudBlobContainer.GetBlockBlobReference(localFileName);
await cloudBlockBlob.UploadFromFileAsync(sourceFile);
```



##### 18. Enable "Application Insights Profiler" for Web App?

```javascript
Answer: "Always On Setting"
```



##### 19. Can we recover Blobs & its snapshots if "Soft Delete" is enabled?

```javascript
Answer: "Yes"
```



##### 20. Code for Azure web service with Cosmos DB?

```javascript
function OrderTip(){
    
    // 1. Get context
    var context = getContext();
    
    // 2. Get Request
    var request = context.getRequest();
    
    // 3. Get item Body
    var item = request.getBody();
    
    // 4. Check if condition
    if(!("tip" in item)){
        item["tip"] = 0;
    }
    
    // 5. Set item in Cosmos DB
    request.setBody(item);
    
}
```



##### 21. Property to enable "web app personalization based on membership in AD groups"?

```javascript
Answer: "groupMembershipClaims" : "All"
```



##### 22. Property to enable "log in into web app using AD credentials"?

```javascript
Answer: "oauth2AllowImplicitFlow" : "true"
```



##### 23. What to do when you don't have any unique value in Azure Cosmos DB properties and you want to create a partitions?

```javascript
1. "Append a random suffix in property values"

2. "Using a hash suffix appended to property value"
```



##### 24. What to do when you get "No Access-Control-Allow-Origin header is present on the request header" error while accessing web app?

```javascript
Answer: "Enable CORS"
```



##### 25. What pricing tier to select while creating a web app when the requirement is "Azure resources must be located in Isolated network"?

```javascript
Answer: "Isolated"
```



##### 26. How many instances will you create if you have 3 customers requiring isolated Azure resources?

```javascript
Answer: "3"
```



##### 27. Create new VM using PowerShell script?

```powershell
New-AzVM --ResourceGroupName "myrg" --Name "myVM" --Location "EastUS" --VirtualNetworkName "newVN" --SubnetName "newSN" --SecurityGroupName "newSG" --PublicIpAddressName "myIP" --Credentials $cred
```



##### 28. Which service to use if you want to move your blobs into archive access tier after 7 days of inactivity?

```javascript
Answer: "Azure Logic Apps"
```



##### 29. How to enable RDP into your VM?

```javascript
Answer: "Create an Inbound Network Security Group rule to allow traffic on port 3389"
```



##### 30. Which Azure service to use to send notifications to devices?

```javascript
Answer: "Azure Notification Hubs"
```



##### 31. Which Azure service to use to work with events specifically?

```javascript
Answer: "Azure Event Grids"
```



##### 32. Which Azure service to use when millions of devices are sending data to storage account?

```javascript
Answer: "Azure Event Hub"
```



##### 33. How to execute a script when using Azure Web App with CD before the website starts?

```javascript
Answer: "Customize the deployment by creating a .deployment file at the root of github repository. This file will call the script"
```



##### 34. Which Azure Service to use to migrate data from On-premise DB to Azure?

```javascript
Answer: "Azure Database Migration Service"
```



##### 35. Which Azure service is a fully managed service designed to enable seamless migrations from multiple database sources to Azure with minimal downtime?

```javascript
Answer: "Azure Database Migration Service"
```



##### 36. What does "Azure Database Migration Service" uses to generate assessment reports that provides recommendations prior to performing a migration?

```javascript
Answer: "Data Migration Assistant"
```



##### 37. Which trigger to use to secure serverless "Functions App"?

```javascript
Answer: "HTTP"
```



##### 38. Which authorization level is required to secure "Functions App"?

```javascript
Answer: "Function"

// anonymous: No API key required
// function: API key is required
// admin: Master key is required
```



##### 39. CLI commands for CORS?

```powershell
# Add allowed origins
az webapp cors add --allowed-origins "https://myapps.com" --name "MyWebApp" --resource-group "MyRG"

# Remove allowed origins
az webapp cors remove --allowed-origins "https://myapps.com" -n "MyAppName" -g "MyRG" 

# Show allowed origins
az webapp cors show -n "MyWebApp" -g "MyRG"
```



##### 40. If you want "Headless authentication" & "Role based access" to Azure Container Registry, which service would you use?

```javascript
Answer: "Service Principal"
```



##### 41. If you want to provide single user access to Azure Container Registry, which service to use?

```javascript
Answer: "Admin Account"
```



##### 42. CLI script to create Azure Cosmos Table API account & table?

```powershell
# 1. Create a resource group
az group create -n "MyRG" -l "eastus"

# 2. Create Cosmos DB Account
az cosmosdb create -n "AccountName" -g "MyRG" --capabilities "EnableTable" --default-consistency-level "Eventual"

# 3. Create a Table API table
az cosmosdb table create -a "AccountName" -g "MyRG" -n "TableName" --throughput "400"
```



##### 43. Which feature to enable so that you can recover deleted blobs?

```javascript
Answer: "Soft Delete"
```



##### 44. Can we modify an existing Blob snapshot?

```javascript
Answer: "NO"
```



##### 45. Which Pricing Tier to use in Web Apps if you need auto-scaling feature?

```javascript
Answer: "Standard"
```



##### 46. Which "consistency level" is required for "The status should be most recent"?

```javascript
Answer: "Strong"
```



##### 47. Which "consistency level" is required for "Data must be either the current ***version*** or prior version"?

```javascript
Answer: "Bounded Staleness"

// version is the keyword here
```



##### 48. Which "consistency level" is required for "There is no ordering mentioned?

```javascript
Answer: "Eventual"
```



##### 49. Which property should be selected as "PartitionKey" while creating Cosmos DB - Table API?

```javascript
Answer: "The one which is used as load balancer in the question"

class Customer: TableEntity{
    public Customer(string Region, string Phone){
        PartitionKey = Region;
        RowKey = Phone;
    }
}

// Region was mentioned as a load balancer in the question
```



##### 50. Which property should be selected as "RowKey" while creating Cosmos DB - Table API?

```javascript
Answer: "The one whose value can never be blank"

class Customer: TableEntity{
    public Customer(string Region, string Phone){
        PartitionKey = Region;
        RowKey = Phone;
    }
}

// It was mentioned that emails can be blank, so only remaining property was "Phone"
```



##### 51. Which property to pass to "ReadCustomer_keys" method?

```c#
Answer: "CloudTable"

private static void ReadCustomer_keys(CloudTable myTable, string partitionKey, string rowKey){
    TableOperation query = TableOperation.Retrieve(partitionKey, rowKey);
    TableResult result = myTable.Execute(query);
}
```



##### 52. Which query to use to retrieve an entity based on partition key & row key?

```c#
Answer: "TableOperation query = TableOperation.Retrieve(partitionKey, rowKey);"

private static void ReadCustomer_keys(CloudTable myTable, string partitionKey, string rowKey){
    TableOperation query = TableOperation.Retrieve(partitionKey, rowKey);
    TableResult result = myTable.Execute(query);
}
```



##### 53. How CDN works?

```javascript
// 1. User requests an image from CDN URL.

// 2. If image is not there in the edge server, it will fetch from original server.

// 3. The edge server will cache the image received from origin server and return to user.

// 4. The subsequent requests will go to the edge server.

// Edge server is also known as "Point Of Presence"
```



##### 54. CLI commands to create a Web App?

```powershell
# Step 1: Create a Resource Group
az group create -n "MyRG" -l "eastus"

# Step 2: Create an App Service Plan
az appservice plan create -n "MyPlan" -g "MyRG" --sku "FREE"

# Step 3: Create a Web App
az webapp create -n "MyApp" -g "MyRG" --plan "MyPlan"

# Step 4: Deploy code from public GitHub repo
az webapp deployment source config -n "MyWebApp" -g "MyRG" --repo-url $gitrepourl --branch "master" --manual-integration

# Step 5: Access web app
echo http://MyApp.azurewebsites.net
```



##### 55. Which is the best way to auto-scale a website during high traffic which is also cost effective?

```javascript
Answer: "Azure App Service"
```



##### 56. PowerShell command to create "API Management Service"?

```powershell
NewAzApiManagement -ResourceGroupName "MyRg" -Location "EastUS" -Name "MyName" -Organization "MyOrg" -AdminEmail $adminCredentials
```



##### 57. Which feature of "Azure Event Hub" will persist the data in Azure Blob Storage?

```javascript
Answer: "Event Hubs Capture"
```



##### 58. When data is persisted in Azure Blob Storage from "Azure Event Hubs", in which format data is written?

```javascript
Answer: "Apache Avro"
```



##### 59. How can we ensure that stale keys are removed from "Azure Redis Cache"?

```javascript
// 1. Choose an eviction policy

// 2. Set a key expiration value
```



##### 60. How to process all sign-in & sign-out events by EventGridController?

```javascript
Answer: "Create separate Azure Event Grid topics & subscriptions for sign-in sign-out events."
```



##### 61. Write a query to fetch all customers with last name "Smith" from a given Azure Table Storage. Last name is also the partition key in this table?

```javascript
TableQuery.GenerateFilterCondition("PartitionKey", QueryComparisons.Equal, "Smith");

// Since we have to utilize partition key, we should use this query
```



##### 62. What to do when users report that anomaly detection emails sometimes arrive late after anomaly is detected?

```javascript
Answer: "Set Always on to true"

// This is due to that web app is stopped if not in use. By setting "Always On" to true we can ensure that our app won't be stopped
```



##### 63. Which "Application Insights data model" we can use to scale our website?

```javascript
Answer: "Application Insights Metric"

// We can use this to scale Web Apps.
```



##### 64. Which type of data should be stored in "Azure Cache for Redis"?

```javascript
Answer: "Sesion State/Data"
```



##### 65. CLI command to create a Keyvault in Azure?

```powershell
# Create a KeyVault
az keyvault create -n "MyKeyVault" -g "MyRG" -l "eastus"

# Add key in a KeyVault
az keyvault key create --vault-name "myvault" --name "myname" --protection "software"

# Add secret in a KeyVault
az keyvault secret set --vault-name "myvault" --name "SQLPassword" --value "Admin@123" 
```



##### 66. CLI commands to create a Web App using Docker Image?

```powershell
# Step 1: Create a Resource Group
az group create -n "myrg" -l "eastus"

# Step 2: Create an App Service Plan
az appservice plan create -n "myplan" -g "myrg" -l "eastus" --is-linux --sku "S1"

# Step 3: Create a Web App
az webapp create -n "myapp" -g "myrg" -l "eastus" --plan "myplan"

# Step 4: Configure Web App with a custom Docker container from Docker Hub
az webapp config container set --docker-custom-image-name $dockerHubContainerPath -n "myapp" -g "myrg"
```



##### 67. Code for notifications on windows devices?

```c#
NotificationHubClient hub = NotificationHubClient.CreateClientFromConnectionString();

await hub.SendWindowsNativeNotificationAsync(message);
```



##### 68. Which policy in API Management do you use in below scenario's?

```javascript
Scenario 1: "A set-variable policy to store user identity"
Answer: "Inbound"
Reason: "We need to set this in Request"

Scenario 2: "A cache-lookup-value policy"
Answer: "Inbound"
Reason: "This is also based on the request"

Scenario 3: "A cache store-value policy"
Answer: "Outbound"

Scenario 4: "Update response body"
Answer: "Outbound"
Reason: "Update the response, therefore outbound"
```



##### 69. If we have a scale-out rule based on number of items in "Azure Service Bus Queue", then what metric source should we select to "scale-down"?

```javascript
Answer: "Azure Service Bus Queue"

//Reason: Because we're already scaling out based on service bus queue, so similar metric should be used to scaling down as well
```



##### 70. If we have a scale-out rule based on number of items in "Active messages in a Service Bus Queue", then what metric source should we select to "scale-down"?

```javascript
Answer: "Active Messages Processed"

//Reason: Because we're already scaling out based on active messages count, so similar metric should be used to scaling down as well
```



##### 71. Which feature of "Azure AD Premium P1" license will help the support help desk team?

```javascript
Answer: "Self-Service Password Change for cloud users"

// Reason: keyword is help desk
```



##### 72. Which "Azure App Insights" feature you can use to monitor if your users are progressing through the entire process of your web app?

```javascript
Answer: "Funnel"
```



##### 73. Which "Azure App Insights" feature you can use to check if page load time is impacting the people convert in your web app?

```javascript
Answer: "Impact"
```



##### 74. Which "Azure App Insights" feature you can use to check how many users return to your app and how often they perform tasks or achieve goals?

```javascript
Answer: "Retention"
```



##### 75. Which "Azure App Insights" feature you can use to check how users are navigating between the pages in your web app?

```javascript
Answer: "User Flows"
```



##### 76. How to utilize "Azure Service Bus Queue" for a food ordering app?

```javascript
// 1. Create a single Service Bus Namespace

// 2. Create a single Service Bus Topic

// 3. Create a Service Bus Subscription for each reatraurant
```



##### 77. How to make sure that "cost of Application Insights does not exceed a pre-set budget"?

```javascript
Answer: "Implement Adaptive Sampling using the App Insights SDK"
```



##### 78. Code to connect to a Redis Cache and delete a key?

```javascript
void clearCustomerCache(string key){
    
    // 1. Establish a connection
    IDatabase cache = Connection.GetDatabase();
    
    // 2. Delete/Invalidate the cache based on key
    cahe.KeyDelete(key);
    
}
```



##### 79. PowerShell commands to create a "Service Bus Namespace"?

```powershell
New-AzServiceBusNamespace -ResourceGroupName "myrg" -Location "EastUS" -Name "myname" -SkuName "Standard"
```



##### 80. CLI commands to create "Azure Cosmos DB" in multiple regions?

```bash
az cosmosdb create --n "myDb" --g "myRg" --l "East US"=0 "West US"=1 "North US"=2
```



##### 81. Which feature to use in "Azure CDN" if you want "Point of Presence" to cache each unique URL with query string parameters?

```javascript
Answer: "Cache every unique URL"
```



##### 82. Different query strings based feature available in "Azure CDN"?

```javascript
1. "Ignore Query Strings" : serve same image to all requests from same origin but with different query strings.

2. "Bypass Caching for query strings" : bypass caching are request image directly from origin.

3. "Cache every unique URL" : cache each unique URL
```



##### 83. Which tool to use if you want to move blobs from one container to another container?

```javascript
Answer: "AzCopy Tool" or "Azure CLI" or "PowerShell"

// CLI: az storage blob copy start --destination-blob "" --destination-container ""

// PowerShell : Start AzStorageBlobCopy -SrcBlob "" -SrcContainer "" -DestContainer "" -DestBlob ""
```



##### 84. You want to provide access to an user only to publish images to "Azure Container Registry" with least privileges. Which role would you give?

```javascript
Answer: "AcrPush"

// AcrPush: 		Push/Pull images
// AcrPull: 		Pull images
// AcrDelete: 		Delete images
// AcrImageSigner: 	Sign images
// Reader:			Pull images/Access Resource Manager
// Contributor/Owner:	GOD
```



##### 85. Code to set/get objects to/from "Azure Redis Cache"?

```javascript
// Store .NET object to cache
cache.StringSet("ID1", JsonConvert.SerializaObject(myObj));

// Get .NET object from cache
var .netObj = JsonConvert.DeserializeObject<Employee>(cache.StringGet("ID1"));
```



##### 86. Copy a file from local system to "Azure  Storage Account" container named "demo"?

```bash
azcopy cp
	"Local file path"
	"Destination container full path"
	--recursive=true
```



##### 87. "Always On" feature of Web App is available in which tier?

```javascript
Answer: "Basic", "Standard", "Premium"

// Not available in "Shared" or "Free"
```



##### 88. Which parameter to add to this URL "https://prjwl4.blob.core.windows.net/demo/prjwl4common.json?" to implement "Blob Lease"?

```javascript
Answer: "comp=lease"
```



##### 89. CLI to get log stream from  a Web App?

```bash
az webapp log tail -n "mywebapp" -g "myrg" -filter "Error"
```



##### 90. Different type of filters in  "Azure Event Grid" service?

```javascript
1. "Event Type" : Get Success/Fail messages

2. "Subject Filtering" : Get messages that belongs to specific container (Starts with or Ends with)

3. "Advanced Filtering" : Get messaged based on condition in message properties
```



##### 91. CLI command to tag the docker images before publishing?

```bash
docker tag nginx myregistry.azurecr.io/samples/nginx
```

#####  

##### 92. What filter to add in "function.json" file in your Azure Function that should be triggered when a "".png" file is added to a container named "data"?

```javascript
Answer: "path" : "data/{name}.png"
```



##### 93. Code to create a document in Cosmos DB with SQL API?

```javascript
// 1. Get context
var context = getContext();

// 2. Get collection
var collection = context.getCollection();

// 3. Create a document
collection.createDocument();

// 4. Set created document in body
context.getResponse().setBody();
```



##### 94. Which "least privilege" role to give if user want to use AzCopy tool to download blobs from container?

```javascript
Answer: "Storage Blob Data Reader"
```



##### 95. CLI command to get connection string from existing "Azure Event Hub"?

```bash
az eventhubs eventhub authorization-rule keys list -g "MyRG"
```



##### 96. How to get the secret version from "Azure KeyVault" REST API?

```javascript
Answer: "Query String Parameter"
```



##### 97. Which property to set if you want to "move messages to active state after certain period of time"?

```javascript
Answer: "ScheduledEnqueueTimeUtc" or "ScheduleMessageAsync API"
```



##### 98. Which Azure service to use to "listen to events emitted from the resource group that contain virtual machines"?

```javascript
Answer: "Azure Logic Apps" with "Azure Event Grid"
```



##### 99. What control to add in your "Azure Logic App" to send an email when "A deallocation activity occurs in VM"?

```javascript
Answer: "Condition"

// "If" deallocation happens "then" do something
```



##### 100. What "Data Object" to select in your "Azure Logic App" to send an email when "A deallocation activity occurs in VM"?

```javascript
Answer: "operationName = Microsoft.Compute/virtualMachines/write"
```



##### 101. In which file we can configure logging in "Azure Functions"?

```javascript
Answer: "host.json"
```



##### 102. What to do when you have large number of senders than receivers in "Azure Service Bus Queue" to increase the throughput?

```javascript
1. "If a sender resides in different process, use a single factory per process"

2. "Leave batched store access enabled"

3. "Use async operations to take advantage of client-side batching"

4. "Use default batching interval of 20ms"

5. "Set the prefetch count to 20 times"
```



##### 103. Which "Caching Behaviour" to use in "Azure CDN" if you want to expire image/video from cache after an hour?

```javascript
Answer: "Override"

1. "Override" : 		Set the cache duration
2. "Bypass Cache" : 	Do not cache
3. "Set if missing" : 	if duration not provided, then set the duration
```



##### 104. PowerShell command to "List a custom role definition"?

```javascript
Get-AzRoleDefinition "Reader" | ConvertTo-Json
```



##### 105. Add "Ability to raise support tickets in Azure subscription"?

```javascript
"*/read" & "Microsoft.Support/*"
```



##### 106. CLI command to create "Azure Container Instance" & also to view the logs?

```bash
# Create a Container Instance
az container create -g "myrg" -n "mycontainer" -image "nginx"

# View container logs
az container logs -g "myrg" -n "mycontainer"
```



##### 107. Which MIME types are supported by "Azure Front Door" service?

```javascript
"XML", "HTML", "javascript" & "json"
```



##### 108. Which compression types are supported in "Azure Front Door" service?

```javascript
"Gzip" & "Brotli"
```



##### 109. Which CLI command will provide diagnostic information during container start up?

```bash
az container attach -g "myrg" -n "mycontainer"
```



##### 110. Where to store end user agreements that are generated "millions per hour"?

```javascript
Answer: "Azure Event Hubs"
```



##### 111. Which .NET method to use to fetch blob properties?

```javascript
Answer: "FetchAttributesAsync()"
```



##### 112.  Which azure service to use if you want the messages to never expire?

```javascript
"Azure Service Bus Queue" & "Azure Service Bus Topic"

// "Azure Event Hubs" & "Azure Storage Queues" have max retention time of 7 days
```



##### 113. What to do if you get error message in your Azure Function "The timeout period elapsed prior to obtaining a connection from the pool"?

```javascript
Answer: "Edit the batchSize property in host.json file"
```



##### 114. Which Azure AD service to use if we need external authentication in our web app like Google, Facebook etc?

```javascript
Answer: "Azure Active Directory B2C"
```



##### 115. What is the most secure way to share SAS access for a file with Read only access?

```javascript
Answer: "User delegation SAS Key"
```



##### 116. Different type of SAS signatures?

```javascript
1. "User Delegation SAS" : Secured with Azure AD credentials. Applies to "Blob Storage" only.

2. "Service SAS" : Secured with "Storage Account Key". Applies to "Blob/Queue/Table/Azure Files"

3. "Account SAS" : Secure with "Storage Account Key". Applies to "Service Level Operations/Read,write,delete 					operations that are not permitted with SAS"
```



##### 117. PowerShell command to create a new "Azure Container Instance"?

```powershell
# Step 1: Create a resource group
New-AzResourceGroup -Name "rg" -Location "EastUS"

# Step 2: Create an Azure Container Instance
New-AzContainerGroup -ResourceGroupName "rg" -Name "instance"

# The "New-AzContainerService" command is deprecated.
```



##### 118. Can we store ASP.NET session data in Azure Cosmos DB?

```javascript
Answer: "NO"

// Azure Redis Cache is the answer to all questions related to session store
```



##### 119. PowerShell command to create ARM template from existing Resource Group?

```javascript
Answer: "Export-AzResourceGroup"
```



##### 120. Azure disk encryption is available on both "Gen 1" & "Gen 2" virtual machines?

```javascript
Answer: "YES"
```



##### 121. We should convert "VHDX" disk file to "VHD" before uploading?

```javascript
Answer: "YES"
```



##### 122. We should convert dynamic disk to fixed size disk before uploading disk image?

```javascript
Answer: "YES"
```



##### 123. CLI command to generate a container image in "Azure Container Registry"?

```bash
az acr build

# After the build, image is pushed to container registry

# "az acr cretae" - To create a new Container Registry
# "az acr update" - TO update parameters of Container Registry
# "az acr import" - To import from another registry
```



##### 124. How to enable the monitoring team to query logs generated by your Web App?

```javascript
Answer: "Enable AppServiceAppLogs under Diagnostics settings and set destination to Log Analytics"
```



##### 125. "Filesystem" & "Blob storage" are available for both windows & Linux?

```javascript
Answer: "NO"

// Only filesystem is available on Linux
```



##### 126. When using Blob Storage, the storage account must be in the same region as the App Service?

```javascript
Answer: "YES"
```



##### 127. Filesystem storage is for short term logging and turn itself off after 12 hours?

```javascript
Answer: "Yes"
```



##### 128. Where to store "Client Certificate" when using TLS mutual authentication for ASP.NET app?

```javascript
Answer: "HttpRequest.ClientCertificate property" 
```



##### 129. Which service to use when you want to "host a set of containers on the same host machine"?

```javascript
Answer: "ACI Container Groups"
```



##### 130. Code to put in Azure Durable Functions Fan in/fan out pattern to ensure that all functions are executed?

```javascript
Answer: "await Task.WhenAll(parallelTasks)"
```



##### 131. How can we edit the "host.json" file?

```javascript
Answer: "Azure Portal"
```



##### 132. A "host.json" file should always be located at the root of your Azure Functions app?

```javascript
Answer: "Yes"
```



##### 133. A "function.json" file should be in a folder with a name that matches the Azure Function name?

```javascript
Answer: "Yes"
```



##### 134. A custom handler executable should be located at the root of Azure Functions App?

```javascript
Answer: "NO"

Reason: "It can be placed anywhere but path should be mentioned in the host.json file"
```



##### 135. Code to get data from Azure Cosmos DB collection?

```javascript
// Step 1:
CreateDatabaseQuery();

// Step 2:
CreateDocumentCollectionQuery();

// Step 3:
CreateDoucumentQuery();
```



##### 136. Which consistency to use when you don't want Partial/Uncommitted data?

```javascript
Answer : "Strong"
```



##### 137. Can we write triggers, stored procedures, and user defined functions in Cosmos DB Table API?

```javascript
Answer: "NO"

// We can write custom business logic in JavaScript in SQL API only.
```



##### 138. Can we write stored procedures in Cosmos DB using C#?

```javascript
Answer: "NO"

// We can write only in JavaScript
```



##### 139. Which feature to use when you want to scale your database based on high traffic?

```javascript
Answer: "Autoscale throughput on Database"
```



##### 140. Which consistency provide "High Availability" & "Low Latency" for Data Reads?

```javascript
Answer: "Eventual"
```



##### 141. In which format Azure Cosmos DB SQL API returns data?

```javascript
Answer : "JSON"
```



##### 142. In which format Azure Cosmos DB Table API returns data?

```javascript
Answer: "Table with rows & columns"
```



##### 143. What statements are correct related to Cosmos DB?

```javascript
1. Chnage feed is enabled by default : "True"

2. Change feed captures delete : "False" (Only Inserts & Updates are allowed)

3. Change feed gurantees the order across the partition key values: "False"
```



##### 144. Which HTTP verb to use to add metadata to Containers & Blobs?

```javascript
Answer: "PUT"

// comp=metadata
```



##### 145. What is the most efficient way to move data from to "archive" in Azure Storage Account?

```javascript
// Step 1 : "Upgrade the account to Gen Purpose v2"

// Step 2: "Move the data using Blob dtorage lifecycle and access tiers"
```



##### 146. PowerShell command to configure access role as Contributor to team members?

```javascript
Answer: "New-AzRoleAssignment"
```



##### 147. How to enable MFA in Azure Ad?

```javascript
// Step 1: "Upgrade the AD account to Premium P1"

// Step 2: "Create a conditional access policy"
```



##### 148. Which Azure AD feature to use to provide secure access without passing credentials?

```javascript
Answer: "Managed Identity"
```



##### 149. What is "sr" & "sp" in a SAS signature?

```javascript
"sr" : Signed Resource (blob)

"sp" : Signed Permission (Read/Write)
```



##### 150. What's the URL to get your image from Microsoft graph api?

```javascript
GET https://graph.microsoft.com/v1.0/me/photo/$value
```



##### 151. Which command to use if you want to set cache in Redis along with it's duration?

```javascript
Answer: "SETEX"
```



##### 152. Different options to choose in Azure CDN?

```javascript
1. "General Web Delivery" : "Default - For static resources"

2. "Dynamic Site Acceleration(DSA)" : "Used in scenario where data is changing rapidly and cache no need"

3. "Video-on-demand" : "Used when you're using an endpoint for video streaming"

4. "General Media Streaming" : "Used when live streaming"
```



##### 153. Which eviction policy to use for "maxmemory-policy" directive?

```javascript
Answer: "volatile-lru"
```



##### 154. PowerShell command to increase Redis cache size?

```javascript
Set-AzRedisCache -ResourceGroupName "RG1" -Name "RedisCache1" -Size "2.5GB"
```



##### 155. True or False regarding cache?

```javascript
1. Shared caching is faster than private caching: "False"

2. Shared cache is more scalable than private cache: "True"
```



##### 156. Which eviction policy to choose to ensure that cache evicts the oldest data first?

```javascript
Answer: "FIFO"
```



##### 157. Where the exceptions are logged?

```javascript
Answer: "Application Insights"

// TelemetryClass -> TrackException() - used to log exceptions
```



##### 158. What are the steps to take send verbose telemetry data to App Insights?

```javascript
// Step 1 : "Call the Info method of the TraceWriter class"

// Step 2 : "store instrumentation key in app settings named as APPINSIGHTS_INSTUMENTATIONKEY"
```



##### 159. What to do if you want to capture performance metrics from multiple geographies before moving app to prod server?

```javascript
Answer : "Create a URL ping test in App Insights"
```



##### 160. Which service allows us to see telemetry data using the "TelemetryClient" class?

```javascript
Answer : "App Insights"
```



##### 161. What is required for App Insights to capture page-view data?

```javascript
Answer : "Add App Insights JavaScript code in our pages"
```



##### 162. Different API Management services?

```javascript
1. "Revision" : "Used to add non-breaking changes in our web-app like addition of operations"

2. "Version" : "Used to add breaking changes in our web app using query strings"

3. "APIM Gateway" : "Used to change the endpoint of new API"

// Use version instead of revision if we don't want to change the URL at all

```



##### 163. Which interface to implement if you want to retrieve all events from a specific Event Hub partition?

```javascript
Answer: "IEventProcessor"
```



##### 164. CLI command to register "Azure Event Grid" with your subscription?

```javascript
az provider register --namespace Microsoft.EventGrid
```



##### 165. What to use if you want to ensure that all messages from the device are stored "in order" to the Event Hub?

```javascript
Answer: "Use the same partition key"
```



##### 166. Which Azure service to use if volume of data is < 80 GB?

```javascript
Answer: "Azure Service Bus"
```



##### 167. Which Azure service to use if volume of data is > 80 GB?

```javascript
Answer: "Azure Queue Storage"
```

------

# 									EXAMTOPICS



##### 1. How to configure your Web App to store Diagnostic Data that must be persisted?

```javascript
1. WEBSITES_ENABLE_APP_SERVICE_STORAGE = "true"

2. DIAGDATE = "/home"
```



##### 2. How to configure Application Gateway for the web app?

```javascript
1. "In the Azure Application Gateway's HTTP setting, enable the use for App Service Setting"

2. "In the Azure Application Gateway's HTTP setting, set the value of Override backedn path option to contoso22.azurewebsites.net"
```



##### 3. How to configure Kubernetes Custom Resource Definitions (CRD) for the Azure Function?

```javascript
"Azure Function Code" = "Deployment"

"Polling Interval" = "ScaledObject"

"Azure Storage Connection String" = "Secret"
```

#####  

##### 4. Can we use "Azure Blob storage events" to process the images once it is stored "under 1 minute"?

```javascript
Answer: "NO"

// It should be Azure Functions with Blob Trigger or Event Grid
```



##### 5. You need to ensure that scripts run and resources are available before a "Deployment Slot Swap" operation occurs. What will you do?

```javascript
Answer: "Update the web.config file to include applicationInitialization configuration"

OR

Answer: "WEBSITE_SWAP_WARMUP_PING_PATH" and "WEBSITE_SWAP_WARMUP_PING_STATUSES"
```



##### 6. What's the location of client certificates in TLS web app?

```javascript
Answer: "Http request header"
```



##### 7. What's the encoding type of the client certificates?

```javascript
Answer: "Base64"
```



##### 8. You need to provision a Web App to host a docker image and map the custom domain to the Web App?

```javascript
// 1. Declare Varibales
#/bin/bash appName="FourthCOffeePublicWeb$random"

// 2. Create a Web App
az webapp create

// 3. Set Container
az webapp config container set

// 4. Publish app to desired custom domain URL
az webapp config hostname add --webapp-name $appName
```



##### 9. Steps to provide "Azure KeyVault" access to an "Azure Function App"?

```javascript
1. "Create Azure Function with a Premium plan" (to avoid cold start)

2. "Create a system assigned Managed Identity" (when resource is deleted, it automatically deleted)

3. "Create an access policy in the KeyVault" (Enable the Get secret permission)
```



##### 10. Can we use "Azure Durable Functions" with "Async Pattern" for longer running tasks?

```javascript
Answer: "YES"

// Either use this or defer the actual work using Azure Service Bus Queue
```



##### 11. How to read the transaction logs of all the changes that occurs to blobs in the storage account?

```javascript
Answer: "Enable the change feed on the storage account and process all changes"

// Change Feeds are used to log all changes related to blobs & blobs metadata
```



##### 12. Commands to create a docker file document?

```
1. "FROM"
2. "WORKDIR"
3. "COPY"
4. "RUN"
5. "CMD"
```



##### 13. What to use if you want to process an image "as quickly as possible" once uploaded?

```javascript
Answer: "Use an App Service Plan. Configure the FUnction App to use an Azure Blob Storage trigger"

// With consumption plan, we can have a 10 min delay
```



##### 14. ARM template to configure Virtual Machine Scale Sets (VMSS)?

```javascript
1. "CopyIndex"

2. "Copy"

3. "DependsOn"
```



##### 15. True/False statements related to processing orders in Azure Function App in Visual Studio?

```javascript
1. The code will log the time that the order was processed from the queue : "False"

2. When order function fails, function will retry upto 5 times including the first try. : "True"

3. When there are multiple orders in the queue, a batch of orders are processed concurrently : "True"

4. The processorders function will output the order to an orders table in Azure Table Storage : "True"
```



##### 16. Process to generalize the VM & store the image?

```javascript
1. VM will be generalized : "Azure PowerShell" (Sysprep cmd will be executed in powershell)

2. Image will be stored in : "Azure Blob Storage" (Standard)
```



##### 17. Process to create a copy of the storage account in another region and copy the data?

```javascript
1. Export
2. Create
3. Modify
4. Deploy
5. AzCopy
```



##### 18. Features to use in Azure VM?

```javascript
1. "Firewall configuration" : "Run command"

2. "Supporting services script" : "Custom Script Extension"
```



##### 19. PowerShell command to enable managed Identity for VM?

```javascript
-IdentityType "SystemAssigned"
```



##### 20. Features to use to deploy microservice to a multinode Azure Kubernetes Service (AKS)?

```javascript
1. Deploy Solution : "Helm"

2. View cluster and external IP addressing : "KubeCtl"

3. Implement single, public IP endpoint routed: "Ingress Controller"

// Helm is used to install Ingress
// To get IP address of Kubernetes pod, use Kubectl command
// Ingress controller is the answer
```



##### 21. Steps to update blob metadata?

```javascript
// 1. Fetch the metadata
"FetchAttributesAsync"

// 2. Update the metadata
"Metadata.Add"

// 3. Set the metadata
"SetMetadataAsync"
```



##### 22. Move files 

```
1. Upgrade the storage account to GPv2

2. Create a new GPV2 standard with cool tier

3. Copy the data to be archived to a standard Gpv2 storage and delete the data from original.
```



##### 23. Command to provide VM access to specific resource groups in Azure Resource Manager?

```javascript
Answer: "Run the Invoke-RestMethod command"
```



##### 24. What to do if you want to copy blobs from one container to another container when a new blob is uploaded?

```javascript
Answer: "Create an Event Grid topic that uses the Start-AzureStorageBlobCopy"
```



##### 25. Which purge type to use when we need to purge individual assets from the Front Door cache?

```javascript
Answer: "Single Path"

// Single Path Purge : Purge individual assets
// Wildcard Purge: Purge all folders under an endpoint
// Root domain Purge: purge the root of the endpoint
```



##### 26. Questions with OpenID API?

```javascript
Answer: "validate-jwt"
```



##### 27. How to register the application with an active Azure Active Directory(Azure AD) tenant?

```javascript
1. Select to Azure AD instance.

2. In App Registeration, select New registeration.

3. Create a new application and provide the name, account type and redirect URI.
```



##### 28. Which is the feature used for RBAC in Azure Cosmos DB?

```javascript
Answer: "Consmos DB Operator"
```



##### 29. You plan to assign users one of the following permission levels for the website: admin, normal and reader. A users Azure AD group membership must be used to determine the permission level?

```javascript
Answer: "Set groupMembershipClaims = All"
```



##### 30. What are the 2 policies to configure API Management with an authentication policy?

```javascript
1. Certificate Authentication

2. Basic Authentication
```



##### 31. What is the code for ASP.NET Core?

```javascript
1. app.UseAuthentication();

2. app.Authorization();

3. app.UseAzureAppConfiguration();
```



##### 32. How to secure the contents of the forms?

```javascript
1. Create an Azure Key Vault.

2. Encrypt the form using key.

3. Store the encrypted data in Azure Blob Storage.
```



##### 33. Implement Azure CDN rule that ensures iPhone users are redirected to the app store?

```
1. "name - IsDevice": "iOS";

2. DeliveryRulesDeviceConditionParameters

3. "name - RequestHeader" : DeliveryRuleRequestHeaderConditionParameters
```



##### 34. Which two telemetry properties should you use to ensure that dependency tracking works for cals to the third-party database?

```javascript
"Telemetry.Id" & "Telemetry.Context.Operation.Id"
```



##### 35. Temperature question?

```
1. Create 
```



##### 36. Which two action should you perform to implement  a reply trail auditing solution?

```javascript
1. "Assign value of SessionID to ReplyToSessionId property"

2. "Assign value of MessageId to CorrelationId property"
```



##### 37. Which two steps to configure a test for your app in App Insights:

```javascript
1. URL ping
2. multi-step web

// There are 3 tests:
	// URL Ping : "A simple test"
	// Multi-step web : "A recording of web request sequence"
	// Custom track availability tests: "custom app to run , TrackAvailability() fn is used"
```







































































































