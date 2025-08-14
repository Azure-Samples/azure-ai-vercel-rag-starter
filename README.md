# Azure AI + Vercel AI SDK RAG Template

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https%3A%2F%2Fgithub.com%2FAzure-Samples%2Fazure-ai-vercel-rag-starter&env=AZURE_SEARCH_ENDPOINT%2CAZURE_SEARCH_KEY%2CAZURE_SEARCH_INDEX_NAME%2CAZURE_SEARCH_CONTENT_FIELD%2CAZURE_SEARCH_VECTOR_FIELD%2CAZURE_SEARCH_SEMANTIC_CONFIGURATION_NAME%2CAZURE_OPENAI_API_ENDPOINT%2CAZURE_RESOURCE_NAME%2CAZURE_DEPLOYMENT_NAME%2CAZURE_EMBEDDING_DEPLOYMENT_NAME%2CAZURE_API_KEY)

Live sample: https://vercelazurerag.azurewebsites.net/

A [Next.js](https://nextjs.org/) application, powered by the Vercel AI SDK, that uses retrieval-augmented generation (RAG) to reason and respond with information outside of the model's training data.

![vercel-start3](https://github.com/user-attachments/assets/103d912e-652a-4bf2-b220-2cdf5f758deb)

## Features

- Information retrieval and addition through tool calls using the [`streamText`](https://sdk.vercel.ai/docs/reference/ai-sdk-core/stream-text) function
- Real-time streaming of model responses to the frontend using the [`useChat`](https://sdk.vercel.ai/docs/reference/ai-sdk-ui/use-chat) hook
- Vector embedding retrieval with [Azure AI Search](https://learn.microsoft.com/en-us/azure/search/search-what-is-azure-search) using embeddings from [Azure OpenAI](https://learn.microsoft.com/en-us/azure/ai-services/openai/overview)
- Generative text streaming with [Azure OpenAI](https://learn.microsoft.com/en-us/azure/ai-services/openai/overview)
- Animated UI with [Framer Motion](https://www.framer.com/motion/)

## Getting Started

To get the project up and running, follow these steps:

1. Install dependencies:

   ```bash
   npm install
   ```

2. Copy the example environment file:

   ```bash
   cp .env.example .env
   ```

3. Create prerequisite resources in Azure AI:
- Azure AI Search index
  - Optionally create a semantic search configuration and include vector fields in the index

_Note: create a vector search index via [REST API](https://learn.microsoft.com/azure/search/search-get-started-vector) or within [Azure Portal](https://learn.microsoft.com/en-us/azure/search/search-get-started-portal-import-vectors?tabs=sample-data-storage%2Cmodel-aoai%2Cconnect-data-storage))_
- Azure OpenAI Chat model
- Azure OpenAI Embedding model, if using vector search

_Note: see available Azure OpenAI models [here](https://learn.microsoft.com/en-us/azure/ai-services/openai/concepts/models) and deploy them using this [guide](https://learn.microsoft.com/en-us/azure/ai-services/openai/chatgpt-quickstart)_


4. Add your Azure OpenAI and Azure AI Search variables to the `.env` file:

   ```
   AZURE_SEARCH_ENDPOINT=your_azure_search_endpoint_here
   AZURE_SEARCH_KEY=your_azure_search_key_here
   AZURE_SEARCH_INDEX_NAME=your_azure_search_index_name_here
   AZURE_SEARCH_CONTENT_FIELD=your_azure_search_content_field_here
   AZURE_SEARCH_VECTOR_FIELD=your_azure_search_vector_field_here # include if using vector search
   AZURE_SEARCH_SEMANTIC_CONFIGURATION_NAME=your_azure_search_semantic_configuration_name_here # include if using semantic search

   AZURE_OPENAI_API_ENDPOINT=your_azure_openai_api_endpoint_here
   AZURE_RESOURCE_NAME=your_azure_resource_name_here
   AZURE_DEPLOYMENT_NAME=your_azure_deployment_name_here # chat model deployment name
   AZURE_EMBEDDING_DEPLOYMENT_NAME=your_azure_embedding_deployment_name_here # embedding model deployment name
   AZURE_API_KEY=your_azure_api_key_here
   ```

5. Start the development server:
   ```bash
   npm run dev
   ```

Your project should now be running on [http://localhost:3000](http://localhost:3000).

### Virtual Dev Environments

[![Open in GitHub Codespaces](https://img.shields.io/static/v1?style=for-the-badge&label=GitHub+Codespaces&message=Open&color=brightgreen&logo=github)](https://github.com/codespaces/new?hide_repo_select=true&ref=main&skip_quickstart=true&machine=basicLinux32gb&repo=902638490&devcontainer_path=.devcontainer%2Fdevcontainer.json&geo=WestUs2)

[![Open in Dev Containers](https://img.shields.io/static/v1?style=for-the-badge&label=Dev%20Containers&message=Open&color=blue&logo=visualstudiocode)](https://vscode.dev/redirect?url=vscode://ms-vscode-remote.remote-containers/cloneInVolume?url=https://github.com/Azure-Samples/azure-ai-vercel-rag-starter)

# Appendix

This template includes code from Vercel's [AI SDK RAG Template](https://github.com/vercel-labs/ai-sdk-preview-rag), which is licensed under the MIT license.

## Trademarks
This project may contain trademarks or logos for projects, products, or services. Authorized use of Microsoft trademarks or logos is subject to and must follow Microsoft’s Trademark & Brand Guidelines. Use of Microsoft trademarks or logos in modified versions of this project must not cause confusion or imply Microsoft sponsorship. Any use of third-party trademarks or logos are subject to those third-party’s policies.
