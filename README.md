# Azure OpenAI Integration for ServiceNow

This project provides a ServiceNow application to facilitate the integration between ServiceNow instances and Azure's OpenAI service. It enables the sending of prompts to Azure OpenAI and receiving responses, which can be utilized within ServiceNow for various purposes such as chatbots, automated customer support, and more.

## Features

- **Easy Configuration**: Set up your Azure OpenAI API key, endpoint, version, and deployment ID directly within the script.
- **Flexible Messaging**: Supports adding user, assistant, and system messages to the context sent to Azure OpenAI.
- **Customizable Parameters**: Adjust the behavior of the OpenAI model with parameters like `maxTokens`, `temperature`, `topP`, `frequencyPenalty`, and `presencePenalty`.
- **Context Management**: Maintain a conversation context to make interactions with the AI more coherent and contextually aware.

## Prerequisites

Before you can use this integration, you'll need:

- An Azure account with access to OpenAI services.
- A ServiceNow instance where you can create or modify Script Includes.

## Setup

1. **Azure OpenAI Configuration**: Ensure you have an Azure OpenAI API key, endpoint, API version, and deployment ID. These will be used to configure the script include to communicate with Azure OpenAI.

2. **Clone the repository**: Clone the repository to your own Github account.

3. **Link the repository to your SN instance**: Create a personal access token and store this in a SN credential record. More info from SN on this process [here](https://support.servicenow.com/kb?id=kb_article_view&sysparm_article=KB0870863).

4. **Pull the source code**: Once the connection is made you can pull the source code to your instance.

5. **System Properties**: Ensure you set the following global system properties according to the values in your Azure OpenAI environment.
   
   - `azure_openai.api_key`
   - `azure_openai.api_version`
   - `azure_openai.api_endpoint`
   - `azure_openai.deployment_id`

## Usage

After setting up the Script Include, you can use it in your ServiceNow applications to interact with Azure OpenAI. Here's a basic example of sending a prompt and receiving a response:

```javascript
var openAI = new x_bits2_az_openai.AzureOpenAI();
gs.info(openAI.prompt('hello world'));
// output: Hello there! How can I assist you today?
```
