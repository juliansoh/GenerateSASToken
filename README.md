# GenerateSASToken
Console application to generate SAS Token to be used in Azure Event Hubs (.NET CORE)

This simple console app will generate a SAS token that you can use in the auth header for Event Hubs API. Good for Postman testing.

### Usage
GenrateSASToken _ResourceURI_ _KeyName_ _Key_

1. Create a Shared Access Policy. Portal -> Event Hubs Namespace -> Event Hub - > Shared access policies -> Add.
1. Take note of the Policy Name (this is the KeyName). E.g. Receive
1. Click on newly created Shared Access Policy and retrieve the Primary Key
1. Also retrieve the Connection String-Primary Key (e.g. Endpoint=sb://mytest-eventhubs.servicebus.windows.net/;SharedAccessKeyName=Receive;SharedAccessKey=0uHWZ/gPKJtzTpG9qN4LCh6FNqsohKhksdhfke=;EntityPath=parking). Take note of the value for Endpoint and EntityPath.
1. Note that ResourceURI = Endpont + entityPath (e.g. mytest-eventhubs.servicebus.windows.net/parking)

Example: GenerateSaSToken mytest-eventhubs.servicebus.windows.net/parking Receive 0uHWZ/gPKJtzTpG9qN4LCh6FNqsohKhksdhfke=

Copy the entire  output from the console application and use it in the Authroization Header of the API.
