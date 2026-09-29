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
![Add a Data Library](https://raw.githubusercontent.com/jefrainmx/Agentforce-Specialist-Certification/refs/heads/main/images/Screenshot%202026-09-29%20132335.png)

### Data Library Source
A data library can be configured to use Knowledge articles, uploadedfiles, web search, or a custom retriever as its data source. After a data source is selected, it can’t be changed later.
![Data Library Source](https://raw.githubusercontent.com/jefrainmx/Agentforce-Specialist-Certification/refs/heads/main/images/Screenshot%202026-09-29%20132412.png)

### Knowledge Fields
Identifying Fields and Content Fields can be selected to base a data library on the Knowledge base.
![Add Knowledge Data](https://raw.githubusercontent.com/jefrainmx/Agentforce-Specialist-Certification/refs/heads/main/images/Screenshot%202026-09-29%20132509.png)

### Knowledge Settings
Indexed articles can be restricted to public articles and filtered by specific data categories.
![Knowledge Settings](https://raw.githubusercontent.com/jefrainmx/Agentforce-Specialist-Certification/refs/heads/main/images/Screenshot%202026-09-29%20132601.png)

### File Upload
Uploaded files can be used as a data source for a data library.
![Add files](https://raw.githubusercontent.com/jefrainmx/Agentforce-Specialist-Certification/refs/heads/main/images/Screenshot%202026-09-29%20132640.png)

## References:
[Agentforce Data Library](https://help.salesforce.com/s/articleView?id=ai.data_library_parent.htm&type=5)
[Augment Agents and Prompts with Relevant Business Knowledge](https://trailhead.salesforce.com/content/learn/modules/retrieval-augmented-generation-quick-look/augment-prompts-with-relevant-knowledge)
[Use the Answer Questions with Knowledge Action](https://help.salesforce.com/s/articleView?id=ai.agent_setup_data_sources.htm&type=5)

# Explain foundational concepts of Data 360 such as chunking, indexing, and retrievers.

## Introduction
Data 360 helps generative AI, automation, and analytics use trusted business data by making structured and unstructured content searchable. Data from Knowledge articles, documents, transcripts, DMOs, and UDMOs can be chunked into meaningful units, vectorized, and stored in search indexes. Search indexes support vector and hybrid search, while retrievers use those indexes to return relevant information at runtime. These foundational concepts allow Agentforce agents and prompt templates to ground responses in current, relevant, and governed enterprise data instead of relying only on general model knowledge. 

### Data 360 Concepts
#### Vectorization & Indexing
Chunks are converted into embeddings and stored in search indexes for retrieval. 
#### Search Type
Vector search retrieves semantically similar content, while hybrid search combines semantic and keyword matching.
#### Retriever
A retriever searches the index and returns relevant grounding content to prompts, agents, Flow, and other features.
#### Grounded Response
The LLM uses retrieved content to produce a more accurate and context-specific answer.
#### Data Sources
Structured and unstructured sources can include Knowledge articles, case notes, PDFs, transcripts, DMOs, and UDMOs.
#### Data Objects
Data is represented in Data 360 through DMOs, UDMOs, and related chunk and index model objects.
#### Chunking
Long text is divided into meaningful units that can be searched and inserted into prompts.

## Unstructured Data, Chunking, and Indexing
### Unstructured Data, Chunking, and Indexing
Unstructured data is data without a specific, consistent format that can’t be easily stored in a typical relational database.Examples include data from Knowledge articles and sales call transcripts.
#### ENHANCING AI RESPONSES
Unstructured data can be connected in Data 360 to create customer-centric results in Einstein generative AI (Prompt Builder and Agentforce). For example, responses to customers can be enhanced using Knowledge article data or prior emails.
#### DATA FORMATS & CONNECTIONS
Data 360 can reference unstructured data in HTML, TXT, and PDF formats and supports connections from Amazon S3, Azure Blob Storage, and Google Cloud Storage.
#### UNSTRUCTURED DATA OBJECTS
A connection can be created between an external blob store and Data 360. After creating the connection, the unstructured data can be referenced in Data 360 by creating an unstructured data lake object (UDLO) and mapping it to an unstructured data model object (UDMO).
#### RELATIONSHIPS & FIELD MAPPINGS
The relationship between UDLOs and UDMOs can be 1:1 or N:1, which means that each UDLO can be mapped to at most one UDMO, while multiple UDLOs can be mapped to a single UDMO. Field-level mappingsare automatically created between the two due to identical schemas.
#### KNOWLEDGE ARTICLE DATA
Knowledge articles contain both structured fields and unstructured text content. In Data 360, the Knowledge article bundle can be used to ingest Knowledge article data from the Salesforce org and includes default mappings to relevant data model objects (DMOs). 
#### SEARCH INDEX
Search Index Configurations can be utilized to ground search on unstructured and structured data and enhance the use of generative AI by bringing customer-specific data into applications like Agentforce.
#### CHUNKING
DMOs and UDMOs can be chunked with text fields, breaking them down into manageable, semantically meaningful chunks. These units of text are stored in chunk data model objects (CDMOs). When creating a search index configuration, the chunking strategy can be selected.
#### CHUNKING STRATEGIES
Data 360 supports these chunking strategies: Section-Aware Chunking, Semantic-Based Passage Extraction, Conversation-Based Chunking, and Prepend Field Chunking.
#### SECTION-AWARE CHUNKING
In section-aware chunking, title and heading elements are used to chunk documents. When creating a search index, Max Token and Overlap Tokens settings can be used to avoid misidentifying short paragraphs or list items as standalone sections, leading to overly small chunks.
#### SEMANTIC-BASED PASSAGE EXTRACTION
In semantic-based passage extraction, the semantic meaning inherent in HTML tags is used to chunk a document into passages. The HTML elements (e.g., heading levels 1-6 <h1-h6>, thematic breaks <hr>, bold <b>, etc.) are considered logical boundaries for chunks.
#### CONVERSATION-BASED CHUNKING
In conversation-based chunking, the transcribed data from audio and video files are segmented into chunks, typically separated when the voice changes. If there are multiple speakers, each chunk represents the speech of an individual speaker.
#### PREPEND FIELD CHUNKING
When creating a search index using the advanced builder, prepend fieldscan be configured when there’s a need to add additional fields or metadata to provide context for a chunk. For example, the Title field can be prepended to provide more context for the Description field in a Knowledge article, which could exceed the optimal chunk size for prompt-based retrieval.
#### SEARCH INDEX CREATION
Easy setup can be used to create a hybrid search index configuration for a data model object (DMO) or an unstructured data model object (UDMO). Data 360 automatically applies defaults for the chunking and vectorization strategies, and creates chunk and index model objects.
#### EDITING & REBUILDING A SEARCH INDEX
A search index configuration can be edited to add fields or file extensionsfor chunking. The search index can then be rebuilt to re-chunk and regenerate the embeddings.
#### ATTACHMENTS
If a search index is on a DMO of a Salesforce object with file attachments, the attachments can be included by clicking Include Attachments and selecting the ContentDocumentVersion UDMO.
#### FIELD SELECTION
Search index quality depends on selecting fields that contain meaningful, relevant text for the intended retrieval use case.

### Chunking Strategy
When creating a Search Index Configuration, the Chunking Strategy can be selected for each field.
![Search Index Configuration](https://raw.githubusercontent.com/jefrainmx/Agentforce-Specialist-Certification/refs/heads/main/images/Screenshot%202026-09-29%20145140.png)

### Editing & Rebuilding a Search Index
A Search Index can be edited and rebuilt.
![Edit and Rebuild Search Index](https://raw.githubusercontent.com/jefrainmx/Agentforce-Specialist-Certification/refs/heads/main/images/Screenshot%202026-09-29%20145202.png)

## Data 360 Search
### Data 360 Search
In Data 360, search indexes can be created for more accurate and relevant AI-generated content, deeper insights from analytics, and more efficient automation workflows.
#### GROUNDING
Data 360 search can be grounded on unstructured and structured data to enhance the use of generative AI, analytics, and automation toolsacross Salesforce. Grounding brings customer-specific data, including unstructured data like text documents and multimedia files, into applications like Agentforce, Tableau, and Flow Builder.
#### SEARCH INDEXES
In Data 360, vector or hybrid search indexes can be created depending on data and query needs. A search index configuration can be created to define a search index in Data 360.
#### VECTOR SEARCH
A vector search embedding is a numerical representation of a unit of text, such as an article or passage from a larger document, that is retrieved or used during a response generation. Vector search helps understand semantic similarities and context between embeddings. 
#### VECTOR SEARCH INDEX
A vector search index configuration can be created for a data model object. The referenced data is broken up into semantically related chunks to generate searchable vectors, which can then be used to find semantically similar items. 
#### HYBRID SEARCH
Hybrid search combines vector search for semantic similarity with keyword search for lexical similarity. It understands semantic similarities and context while focusing on specific domain vocabulary. 
#### HYBRID SEARCH INDEX
A hybrid search index configuration can be created for a data model object (DMO) or an unstructured data model object (UDMO) to provide relevant information to generative AI applications. Data 360 generates a vector index and a keyword index.
#### VECTOR SEARCH EXAMPLE
Vector search recognizes that How do I reset my password? and How can I change my login credentials? are semantically similar.
#### KEYWORD SEARCH EXAMPLE
Keyword search recognizes that Model X200 Printer and Model X210 Printer are lexically similar.

### Creating a Search Index Configuration
A Search Index Configuration can be created in Data 360 by selecting one of three options.
![New Search Index](https://raw.githubusercontent.com/jefrainmx/Agentforce-Specialist-Certification/refs/heads/main/images/Screenshot%202026-09-29%20151419.png)

A search type and data model object can be selected for a new search index configuration.
![Search Type and Source Object](https://raw.githubusercontent.com/jefrainmx/Agentforce-Specialist-Certification/refs/heads/main/images/Screenshot%202026-09-29%20151441.png)

The fields to chunk can be added, and the chunking strategy can be set for each field.
![Chunking](https://raw.githubusercontent.com/jefrainmx/Agentforce-Specialist-Certification/refs/heads/main/images/Screenshot%202026-09-29%20151504.png)

A vectorization strategy can be selected to measure the unstructured data for semantic relevance.
![Vectorizing](https://raw.githubusercontent.com/jefrainmx/Agentforce-Specialist-Certification/refs/heads/main/images/Screenshot%202026-09-29%20151526.png)

Related fields for search filtering can be selected.
![Fields for Filter](https://raw.githubusercontent.com/jefrainmx/Agentforce-Specialist-Certification/refs/heads/main/images/Screenshot%202026-09-29%20151717.png)



## Retrieval Augmented Generation (RAG)


<!--stackedit_data:
eyJoaXN0b3J5IjpbODI3Mjk2MjMxLC0yMDE2MzcxOTEzLC0xND
Y4NDczNTU5LDEwNzgxMDQ5OSwxODMxMzUyNjYsLTE0Njc5NTc4
NjMsLTIwMjA3MjU5NzYsLTQxMTk3MDI2NCw4NTg3NDc5OTQsLT
E2MjE4NDg3XX0=
-->