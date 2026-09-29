# Explain the considerations of Agentforce Data Library and its concepts.
## Introduction
A data library acts as a structured source of knowledge that an Agentforce agent can use to provide precise and contextually relevant answers. Data libraries can be sourced from Salesforce Knowledge articles, uploaded files, web search, or custom retrievers.Key features include grounding AI responses with domain-specific knowledge, chunking data for efficient retrieval, and indexing for organized searches. Data libraries also support retrievers, which fetch relevant information dynamically. A data library can be assigned to an agent in Agentforce Builder, but each AI feature can use only one data library at a time. Data libraries require Data 360 setup and consume Data 360 credits.

### Agentforce Data Library
#### Data Library & Source
A data library can be based on Knowledge articles, uploaded files, web search, or a custom retriever. It must be assigned to the AI feature or agent.
#### Search Index
The search index organizes chunks so relevant information can be found efficiently at runtime.
#### Retriever
The retriever connects the AI feature to the indexed content that should be searched.
#### Grounded Response
The agent uses retrieved content to ground the prompt and generate a more accurate answer.
#### Data 360 Processing
Data 360 processes the selected source through data objects, chunking, indexing, and retriever creation.

## Agentforce Data Library Concepts
### Agentforce Data Library
Data Libraries can be assigned to Agentforce features to improve accuracy, add personalization, and build trust in generative AI responses.
#### DATA LIBRARY
An Agentforce Data Library is a library of content that can be used by an agent to answer questions. The source of a data library can be Salesforce Knowledge articles, uploaded files, web search, or a custom retriever.❖GROUNDINGAgentforce uses the information in the assigned data library at run time to ground LLM prompts and produce better, more accurate, and relevant LLM responses. Grounding adds domain-specific knowledge or customer information to the prompt and provides context to the LLM.


# Explain foundational concepts of Data 360 such as chunking, indexing, and retrievers.


<!--stackedit_data:
eyJoaXN0b3J5IjpbMTM1Mjg5OTY2NCwtMTYyMTg0ODddfQ==
-->