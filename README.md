# Description

This repo contains a code sample for the issue https://github.com/Azure/azure-functions-host/issues/3125.

# Setup

1. Create Azure Function App with runtime Python 3.9.
2. Create Azure Service Bus.
3. Add queue `outqueue` to service bus.
4. Deploy the code of this repository to the Azure Function App.
5. Add configuration `AzureServiceBusConnectionString` to the Azure Function App, containing the connection string to the service bus.

# Issue

1. Send a HTTP request to the Azure Function.
2. Look at the message that arrives in the queue `outqueue`. You will see, that instead of holding the expected bytes `Hello world!` (which is what should be returned by the Python code), it holds a string with the value `System.byte[]`. 