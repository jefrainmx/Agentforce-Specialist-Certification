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
An Agentforce Data Library is a library of content that can be used by an agent to answer questions. The source of a data library can be Salesforce Knowledge articles, uploaded files, web search, or a custom retriever.
#### GROUNDING
Agentforce uses the information in the assigned data library at run time to ground LLM prompts and produce better, more accurate, and relevant LLM responses. Grounding adds domain-specific knowledge or customer information to the prompt and provides context to the LLM.
#### CHUNKING
Data sources are broken down into smaller parts called chunks to make search more efficient and improve relevance. Chunking helps agents retrieve focused passages from sources such as Knowledge article text, uploaded files, and indexed web content. 
#### INDEXING
Data that is split into chunks is organized and categorized, which is called indexing. This process simplifies the search and retrieval of chunks. When information is required or a user asks a question, an agent searches through the chunks in the index.
#### SEARCH
When a search is performed by an agent, the user’s question is compared with indexed chunks. Chunks with high relevance or similarity are returned and added to the prompt because they point to relevant articles or sources. 
#### RETRIEVERS
A retriever connects an agent or prompt template to indexed content that can be searched for grounding. The retriever assigned to a data library determines which Data 360 data sources are available for AI responses.
#### AGENT ACTION
When a user asks a question, the AI agent uses the Answer Questions with Knowledge standard agent action to answer the query based on data in the corresponding Agentforce Data Library.
#### REQUIREMENTS
Using Agentforce Data Libraries require Data 360 setup, appropriate permissions, and available Data 360 credits for processing, indexing, and runtime retrieval. 
#### AUTOMATED CONFIGURATION
Creating a data library automates several configuration steps, such as processing the selected source in Data 360, creating a search index and retriever, and linking the agent to that data.
#### DATA SOURCE
A data library can use Knowledge articles, uploaded files, web search, or a custom retriever as its data source. A data library can’t support multiple data sources at the same time, and the selected source type can’t be changed later.
#### KNOWLEDGE FIELDS
A data library can be configured to use the Knowledge base as its data source by editing the Knowledge source settings for the data library and selecting the Knowledge fields for the library to index. Identifying fieldshelp agents locate the correct Knowledge articles. Content fields help agents enrich responses with relevant details.
#### KNOWLEDGE ARTICLES
Under Knowledge Settings, the Knowledge articles that should be included in the data library can be specified. Indexed articles can be restricted to use only publicly available articles in the Knowledge base. They can also be filtered by specific data categories.
#### FILES
A data library can use specific files as its data source by selecting the File Upload tab and uploading the files. Up to 4 MB of text or HTML files and 100 MB of PDF files can be uploaded, and adding files rebuilds the library’s search index.
#### ASSIGNMENT
Data libraries can be assigned to AI features, including Agentforce Agents, Agentforce Service Agent, and Einstein Service Replies. Each feature can use only one data library at a time. 
#### AGENTFORCE BUILDER
In Agentforce Builder, the data library that the agent uses to generate responses can be configured from the Data tab. An existing library can be selected, or a new library can be created. The selected library’s source settings determine what content is indexed and available for retrieval.
#### KNOWLEDGE RECORDS & FIELDS
Agent responses can be based on all Knowledge articles and fields by selecting All Knowledge records and fields.

### Creating an Agentforce Data Library
A data library can be created on the Agentforce Data Library page in Setup. After the library is saved, Data 360 creates or uses the supporting assets needed for indexing and retrieval. 


### Data Library Source
A data library can be configured to use Knowledge articles, uploadedfiles, web search, or a custom retriever as its data source. After a data source is selected, it can’t be changed later.
2

### Knowledge Fields
Identifying Fields and Content Fields can be selected to base a data library on the Knowledge base.
3

### Knowledge Settings
Indexed articles can be restricted to public articles and filtered by specific data categories.
4

### File Upload
Uploaded files can be used as a data source for a data library.
5

## References:
[Agentforce Data Library](https://help.salesforce.com/s/articleView?id=ai.data_library_parent.htm&type=5)
[Augment Agents and Prompts with Relevant Business Knowledge](https://trailhead.salesforce.com/content/learn/modules/retrieval-augmented-generation-quick-look/augment-prompts-with-relevant-knowledge)
[Use the Answer Questions with Knowledge Action](https://help.salesforce.com/s/articleView?id=ai.agent_setup_data_sources.htm&type=5)

# Explain foundational concepts of Data 360 such as chunking, indexing, and retrievers.


<!--stackedit_data:
eyJoaXN0b3J5IjpbMTc1ODE0NjE5Miw4NTg3NDc5OTQsLTE2Mj
E4NDg3XX0=
-->