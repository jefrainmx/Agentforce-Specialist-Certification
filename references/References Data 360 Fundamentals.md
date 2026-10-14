# Agentforce Data Library

Improve accuracy, add personalization, and build trust in gen AI responses when you assign data libraries to your Agentforce features. Agentforce Data Library uses grounding to index your knowledge articles and fields, your file uploads, or web sources, so that AI agents know which information to base responses on. With this index, AI agents can ensure the accuracy of LLM responses against your organization’s information so that you get the best results.

To use Agentforce Data Libraries, you must have [Data 360 set up](https://help.salesforce.com/s/articleView?id=data.c360_a_setup_provision.htm&language=en_US&type=5). Data libraries consume Data 360 credits.

To use Agentforce Data Library in a Data Cloud One companion org, use a custom retriever as the library's data source. Agentforce Data Library doesn't support Knowledge or Files as a data source in companion orgs.

<table class="slds-table slds-table_bordered slds-m-bottom_small"><colgroup><col style="width:6.5420560747663545%"><col style="width:93.45794392523365%"></colgroup><tbody><tr class=""><td style="text-align:left;vertical-align:top;" class="slds-cell-wrap"><a name="data_library_parent__image_nmk_32j_xdc"></a><span style="vertical-align:text-bottom;display:inline-block;"><img alt="../images/learning_minimap/help_minimap.png" src="https://sf-zdocs-cdn-prod.zoominsoftware.com/tdta-ai-generative_ai-264-0-0-production-enus/fc2f2f57-79fe-4598-a5e0-089f9b72c638/resources-global/_corporate/images/learning_minimap/help_minimap.png" id="data_library_parent__image_nmk_32j_xdc" style="width:35px;margin-bottom:0;"></span></td><td style="text-align:left;vertical-align:top;" class="slds-cell-wrap"><p>Dive deeper into Salesforce Help.</p><a name="data_library_parent__ul_omk_32j_xdc"></a><ul id="data_library_parent__ul_omk_32j_xdc"><li><a title="Agentforce Data Libraries enhance the accuracy of AI features like Agentforce Agents by connecting them to your trusted data sources. Data libraries use unstructured or semi-structured data so that they can take large sets of information that exist on the web, in documents, or as large text inputs in fields, and turn that into more useful, searchable information." href="https://help.salesforce.com/s/articleView?id=ai.data_library_concept.htm&amp;language=en_US&amp;type=5">What Are Data Libraries?</a></li><li><a href="https://help.salesforce.com/s/articleView?id=data.c360_a_rag_overview.htm&amp;language=en_US&amp;type=5"><u>Using Retrieval Augmented Generation</u></a></li></ul></td></tr><tr class=""><td style="text-align:left;vertical-align:top;" class="slds-cell-wrap"><a name="data_library_parent__image_rmk_32j_xdc"></a><span style="vertical-align:text-bottom;display:inline-block;"><img alt="Traihead resources. Icon." src="https://sf-zdocs-cdn-prod.zoominsoftware.com/tdta-ai-generative_ai-264-0-0-production-enus/fc2f2f57-79fe-4598-a5e0-089f9b72c638/resources-global/_corporate/images/learning_minimap/trailhead_minimap.png" id="data_library_parent__image_rmk_32j_xdc" style="width:35px;margin-bottom:0;"></span></td><td style="text-align:left;vertical-align:top;" class="slds-cell-wrap"><p>Use Trailhead to build and test your skills.</p><a name="data_library_parent__ul_smk_32j_xdc"></a><ul id="data_library_parent__ul_smk_32j_xdc"><li><a href="https://trailhead.salesforce.com/content/learn/modules/agentforce-data-library-basics">Agentforce Data Library Basics</a></li><li><a href="https://trailhead.salesforce.com/content/learn/modules/retrieval-augmented-generation-quick-look">Retrieval Augmented Generation: Quick Look</a></li></ul></td></tr><tr class=""><td style="text-align:left;vertical-align:top;" class="slds-cell-wrap"><a name="data_library_parent__image_p5k_x2j_xdc"></a><span style="vertical-align:text-bottom;display:inline-block;"><img alt="../images/learning_minimap/help_minimap.png" src="https://sf-zdocs-cdn-prod.zoominsoftware.com/tdta-ai-generative_ai-264-0-0-production-enus/fc2f2f57-79fe-4598-a5e0-089f9b72c638/resources-global/_corporate/images/learning_minimap/help_minimap.png" id="data_library_parent__image_p5k_x2j_xdc" style="width:35px;margin-bottom:0;"></span></td><td style="text-align:left;vertical-align:top;" class="slds-cell-wrap"><p>Get started with data library setup.</p><a name="data_library_parent__ul_wmk_32j_xdc"></a><ul id="data_library_parent__ul_wmk_32j_xdc"><li dir="ltr"><a href="https://help.salesforce.com/s/articleView?id=ai.data_library_setup.htm&amp;language=en_US&amp;type=5">Setting Up Data Libraries</a></li></ul></td></tr><tr class=""><td style="text-align:left;vertical-align:top;" class="slds-cell-wrap"><a name="data_library_parent__image_mzw_nfj_xdc"></a><span style="vertical-align:text-bottom;display:inline-block;"><img alt="../images/learning_minimap/help_minimap.png" src="https://sf-zdocs-cdn-prod.zoominsoftware.com/tdta-ai-generative_ai-264-0-0-production-enus/fc2f2f57-79fe-4598-a5e0-089f9b72c638/resources-global/_corporate/images/learning_minimap/help_minimap.png" id="data_library_parent__image_mzw_nfj_xdc" style="width:35px;margin-bottom:0;"></span></td><td style="text-align:left;vertical-align:top;" class="slds-cell-wrap"><p>Integrate data libraries with AI agents.</p><a name="data_library_parent__ul_ymk_32j_xdc"></a><ul id="data_library_parent__ul_ymk_32j_xdc"><li dir="ltr"><a title="Connect your agent to a data library for structured, citation-rich responses grounded in your indexed content." href="https://help.salesforce.com/s/articleView?id=ai.agent_setup_data_sources.htm&amp;language=en_US&amp;type=5">Use the Answer Questions with Knowledge Action</a></li><li dir="ltr"><a href="https://help.salesforce.com/s/articleView?id=ai.copilot_actions_ref_answer_questions_with_knowledge.htm&amp;language=en_US&amp;type=5"><u>Answer Questions with Knowledge</u></a></li><li dir="ltr"><a href="https://help.salesforce.com/s/articleView?id=ai.prompt_builder_answer_questions_with_knowledge.htm&amp;language=en_US&amp;type=5"><u>Customize the Knowledge Action prompt template in Prompt Builder</u></a></li></ul></td></tr><tr class=""><td style="text-align:left;vertical-align:top;" class="slds-cell-wrap"><a name="data_library_parent__image_jfv_pfj_xdc"></a><span style="vertical-align:text-bottom;display:inline-block;"><img alt="Diagram resources. Icon." src="https://sf-zdocs-cdn-prod.zoominsoftware.com/tdta-ai-generative_ai-264-0-0-production-enus/fc2f2f57-79fe-4598-a5e0-089f9b72c638/resources-global/_corporate/images/learning_minimap/architect_minimap.png" id="data_library_parent__image_jfv_pfj_xdc" style="width:35px;margin-bottom:0;"></span></td><td style="text-align:left;vertical-align:top;" class="slds-cell-wrap"><p>Explore all data library enabled features.</p><a name="data_library_parent__ul_ccp_lfj_xdc"></a><ul id="data_library_parent__ul_ccp_lfj_xdc"><li dir="ltr"><a href="https://help.salesforce.com/s/articleView?id=ai.agent_setup_data_sources.htm&amp;language=en_US&amp;type=5"><u>Agentforce Agents</u></a></li><li dir="ltr"><a href="https://help.salesforce.com/s/articleView?id=service.reply_recs_service_replies_chat_intro.htm&amp;language=en_US&amp;type=5"><u>Einstein Service Replies for Chat</u></a></li></ul></td></tr></tbody></table>

# Augment Agents and Prompts with Relevant Business Knowledge

## Learning Objectives

After completing this unit, you’ll be able to:

-   Explain why retrieval augmented generation (RAG) improves the accuracy and relevance of LLM responses in agents and prompt templates.  
    
-   Describe how to set up and use RAG in your Salesforce org.  
    

## What Is Retrieval Augmented Generation?

Retrieval augmented generation (RAG) is a popular way to ground prompt requests to large language models (LLMs). Grounding adds domain-specific knowledge or customer information to the prompt, giving the LLM context to respond more accurately to a question or task.

![RAG runtime flow: LLM prompt augmented with relevant information to instruct LLM response generation.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/retrieval-augmented-generation-quick-look/augment-prompts-with-relevant-knowledge/images/1c6bea0309f0497da032e820853bca5f_kix.pc023llbylg.png)

To break it down, RAG:

1.  _Retrieves_ relevant information from a knowledge store containing structured and unstructured content.  
    
2.  _Augments_ the prompt by combining this information with the original prompt.  
    
3.  With the augmented prompt, the LLM _generates_ a response.  
    

Many LLMs are trained generally across the Internet on static and publicly available content. RAG adds domain-specific information to help LLMs give you better responses to your prompts. With RAG, you can extract valuable information from all sorts of content, such as service replies, cases, knowledge articles, conversation transcripts, RFP (request for proposal) responses, emails, meeting notes, frequently asked questions (FAQs), and more.

## Quick-Start Agentforce Solutions With Agentforce Builder and Agentforce Data Library

Agentforce Builder allows you to seamlessly choose knowledge articles or upload files for retrieval by agents with just a few clicks. You can do this by selecting or creating an [Agentforce Data Library](https://help.salesforce.com/s/articleView?id=ai.data_library_parent.htm), which is a library of content the agent uses to answer questions. Select the source from which the data library pulls relevant information: Salesforce Knowledge base, files that you upload (text, HTML, and PDFs), or a web search. At run time, your agent uses this information to ground LLM prompts and produce better, more accurate, and relevant LLM responses.

When you add a data library, you automatically create all the elements needed for a working, RAG-powered solution. If you want, you can then customize these elements to fine-tune RAG solutions for your use cases. We’ll get to that later.

## Get Relevant Business Knowledge in Agents

Agents get relevant knowledge from a data library using the [Answer Questions with Knowledge](https://help.salesforce.com/s/articleView?id=sf.copilot_actions_ref_answer_questions_with_knowledge.htm) standard action. This action dynamically retrieves from the knowledge or file content you specified when you created or selected a library.

![RAG detailed runtime flow for agents: Answer Questions with Knowledge action, query request and response, augmented prompt, and LLM response forward to the agent.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/retrieval-augmented-generation-quick-look/augment-prompts-with-relevant-knowledge/images/d32a8f7490bb0fc5fbbf5ab09e38dd98_kix.xq4j81jzpuo1.png)

Each time the Answer Questions with Knowledge action is run:

1.  The action runs the associated prompt template. The retriever is invoked with a dynamic query.  
    
2.  The query searches the data library.  
    
3.  The query retrieves the relevant content.  
    
4.  The original prompt is populated with information retrieved from the data library, and then submitted to the LLM.  
    
5.  The LLM-generated response is forwarded to the agent.  
    

## Get Relevant Business Knowledge in Prompts

At run time, prompt templates pull relevant information from your data library to ground LLM prompts that result in more accurate LLM responses. If you’re using a custom prompt template, in Prompt Builder, simply embed a retriever that you select when inserting a resource. You can also use a custom retriever that fine-tunes search settings for any given prompt.

![RAG detailed runtime flow for prompts: query, vectorize, retrieve relevant content, augment, and submit to the LLM.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/retrieval-augmented-generation-quick-look/augment-prompts-with-relevant-knowledge/images/1a14376292ee9e05a1389558560e7294_kix.ur2xzk5e75xe.png)

Each time a prompt template with a retriever is run:

1.  The retriever is invoked with a dynamic query that’s initiated from the prompt template.  
    
2.  The query is vectorized (converted to numeric representations). Vectorization enables search to find semantic matches in the search index (which is already vectorized).  
    
3.  The query retrieves the relevant content from the indexed data in the search index.  
    
4.  The original prompt is populated with the information retrieved from the search index.  
    
5.  The prompt is submitted to the LLM, which generates and returns the prompt response.  
    

## Advanced Customization in Data 360

When you add a data library, either in Agentforce Builder or from Setup, Salesforce automatically builds a RAG-powered solution using default settings for all of the components: vector data store, search index, retriever, prompt template, and standard action. You can set up and customize these components individually.

![Data preparation steps: ingest, chunk, vectorize, and index.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/retrieval-augmented-generation-quick-look/augment-prompts-with-relevant-knowledge/images/2c2a876a132293ac5b8fb860930d2a18_kix.5gv0v4t35wbj.png)

Data preparation involves these tasks in Data 360.

1.  Connect (ingest) your unstructured data.  
    
2.  Create a search index configuration that chunks and vectorizes the content. Data 360 uses a search index to manage structured and unstructured content in a search-optimized way. You have two search options: vector search and hybrid search. Hybrid search combines vector + keyword search.  
    -   Chunking breaks the text into smaller units, reflecting passages of the original content, such as sentences or paragraphs.  
        
    -   Vectorization converts chunks into numeric representations of the text that capture semantic similarities.  
        
3.  Store and manage the search index.  
    

After a search index is created, create a retriever in AI Models (formerly Einstein Studio) to fetch relevant information from that search index for a specific use case. A retriever is a resource that you embed in a prompt template to search for, and return, relevant information from the knowledge store. To support a variety of use cases, you can create different retrievers that focus your search on just the relevant subset of information to add to the prompt. For a hands-on experience, take the [Advanced RAG with Data 360 and Agentforce](https://trailhead.salesforce.com/content/learn/modules/advanced-rag-with-data-360-and-agentforce) module.

## See RAG in Action

This video shows how easy it is to augment a prompt template using RAG.

## Conclusion

Agentforce Data Library and RAG in Data 360 are integrated with the Einstein generative AI platform. Natively incorporate RAG functionality into out-of-the-box apps like Agentforce Builder and Prompt Builder. With RAG, you can safely ground and improve your Agentforce solutions with proprietary data from a harmonized data model.

## Resources

-   [_Salesforce Help_: Unstructured Data in Data 360](https://help.salesforce.com/s/articleView?id=sf.c360_a_unstructured_data_about.htm&type=5)
-   [_Salesforce Help_: Data 360—Chunk and Vectorize Data](https://help.salesforce.com/s/articleView?id=sf.c360_a_search_index_grounding.htm&type=5)
-   [_Salesforce Help_: Data 360—Vector Search](https://help.salesforce.com/s/articleView?id=sf.c360_a_search_index_vector_index.htm&type=5)
-   [_Salesforce Help_: Data 360—Hybrid Search](https://help.salesforce.com/s/articleView?id=data.c360_a_hybridsearch_index.htm&type=5)
-   [_Salesforce Help_: Example: Agentic RAG with Advanced Data 360 Setup](https://help.salesforce.com/s/articleView?id=ai.generative_ai_rag_example.htm&type=5)
-   [_Trailhead_: Agentforce Data Library Basics](https://trailhead.salesforce.com/content/learn/modules/agentforce-data-library-basics)
-   [_Trailhead_: Unstructured Data in Data 360](https://trailhead.salesforce.com/content/learn/projects/unstructured-data-in-data-cloud)
-   [_Trailhead_: Search Index Types in Data 360: Quick Look](https://trailhead.salesforce.com/content/learn/modules/search-index-types-data-cloud-quick-look)
-   [_Trailhead_: Hybrid Search for RAG: Quick Look](https://trailhead.salesforce.com/content/learn/modules/hybrid-search-for-rag-quick-look)
-   [_Salesforce Blog_: RAG – The Hottest 3 Letters in Generative AI Right Now](https://www.salesforce.com/blog/what-is-retrieval-augmented-generation/)
-   [_Salesforce Blog_: Agentforce and RAG: Best Practices for Better Agents](https://www.salesforce.com/content/dam/web/en_us/www/documents/article/agentforce_and_rag_best_practices_for_better_agents.pdf)

# Use the Answer Questions with Knowledge Action

Connect your agent to a data library for structured, citation-rich responses grounded in your indexed content.

To use Agentforce Data Libraries, you must have Data 360 [set up](https://help.salesforce.com/s/articleView?id=data.c360_a_setup_provision.htm&language=en_US&type=5). Data libraries consume Data 360 credits.

Before you begin, make sure your agent has the Answer Questions with Knowledge action assigned and your data library status is Ready.

When you create and configure a data library, the Agentforce Data Library indexes your selected knowledge articles and uploaded files in Data 360. Data 360 creates a search index and retriever for your library that your agent can use via the Answer Questions with Knowledge action.

1.  Under Apps, open **Agentforce Studio** and select your target agent.
2.  Under the **Data** tab, use the dropdown menu to select an existing library. To create a new one, click **Go to Agentforce Data Library**. Ensure the library status is Ready.
    
    If you select or create a library, you can configure the [knowledge fields](https://help.salesforce.com/s/articleView?id=ai.data_library_select_fields.htm&language=en_US&type=5) or [file uploads](https://help.salesforce.com/s/articleView?id=ai.data_library_file_upload.htm&language=en_US&type=5) for your data library to index. If you create a library, it can take a few minutes for the preview conversation to update.
    
3.  To include citations in the agent's output, select **Show Sources**.
4.  Save your changes. To test out your changes, restart the preview conversation and then chat with your agent.

Use [Agentforce Testing Center](https://help.salesforce.com/s/articleView?id=ai.agent_studio_testing_center_knowledge_sources.htm&language=en_US&type=5) to generate and run tests from your knowledge sources at scale.

#### See Also

-   [Agentforce Platform | Answer Questions with Knowledge](https://help.salesforce.com/s/articleView?id=ai.copilot_actions_ref_answer_questions_with_knowledge.htm&language=en_US&type=5)
-   [_Trailhead_: Retrieval Augmented Generation: Quick Look](https://trailhead.salesforce.com/content/learn/modules/retrieval-augmented-generation-quick-look)
-   [Using Retrieval Augmented Generation](https://help.salesforce.com/s/articleView?id=data.c360_a_rag_overview.htm&language=en_US&type=5)

# Get Started with Unstructured Data in Data 360

## Learning Objectives

After this step, you’ll be able to:

-   Define unstructured data in Data 360.  
    
-   Explain how unstructured data enhances your AI and automation strategies.  
    
-   Describe how to connect data from an external blob store (‌such as Amazon S3).  
    

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

As of October 14, 2025, Data Cloud has been rebranded to Data 360. During this transition, you may see references to Data Cloud in our application and documentation. While the name is new, the functionality and content remains unchanged.

## What’s Unstructured Data?

The data your organization gathers generally takes three forms—structured, semistructured, and unstructured. Organizations collect an increasingly large portion of unstructured data, yet they effectively harness only a very small portion of it. Large amounts of data can be challenging to effectively integrate into workstreams, especially for search and retrieval purposes. With support for unstructured data in Data 360, it’s time to change that.

Unstructured data is data that doesn’t have a specific, consistent format and can’t be easily stored in a typical relational database. Its lack of structure makes it particularly challenging to search or analyze. However, AI technologies, such as large language models (LLMs), can process unstructured data effectively. This capability has many enterprises incorporating their increasingly vast reams of unstructured data into their data-driven strategies.

Common forms of unstructured data include chat transcripts, audio and video files, emails, legal documents, and other large texts, such as books. In Salesforce, examples of unstructured data are data from Knowledge articles or sales call transcripts.

## Use Unstructured Data to Enhance Your AI and Automation Strategies

When you connect your unstructured data in Data 360, you can create customer-centric results in yourgenerative AI (Prompt Builder and Agentforce); automation (Flow Builder); and analytics (Tableau and CRM Analytics) applications. For example, you can enhance service reply recommendations by generating responses to customers using Knowledge article data or create prompt templates that use prior emails to generate personalized messages. Or you can use Flow Builder and Agentforce to show service agents similar case data to help in case resolution or when they log new cases.

## Connect Unstructured Data from External Blob Stores

Data 360 can reference unstructured data in formats such as HTML, TXT, and PDF formats. For more information see, [Unstructured Data File Formats and Connectors](https://help.salesforce.com/s/articleView?id=data.c360_a_unstructured_data_connect.htm&type=5). And since Data 360 already supports connections from Amazon S3, Azure Blob Storage, and Google Cloud Storage, it takes just a few configuration clicks to bring in your unstructured data if you’ve already set up those connections.

After you create a connection between your external blob store and Data 360, you can reference unstructured data in Data 360 by creating an unstructured data lake object (UDLO) and mapping it to an unstructured data model object (UDMO).

Data 360 automatically creates ‌field level mappings between UDLOs and UDMOs because the schemas across the two objects are identical. You can read more about their schemas in [Salesforce Help](https://help.salesforce.com/s/articleView?id=data.c360_a_unstructured_data_about.htm&type=5).

The relationship between UDLOs and UDMOs can be 1:1 or N:1. This means, each UDLO can be mapped to at most one UDMO, while multiple UDLOs can be mapped to a single UDMO. Let’s look at an example.

Consider that you’re referencing case-recording data from multiple external blob stores. Three different UDLOs reference data from these three sources: CaseRecordingsFromAWSBucket1, CaseRecordingsFromAWSBucket2, and CaseRecordingsfromGCS. Because these sources are logically the same object, the individual UDLOs are mapped to one UDMO: CaseRecordings.

When you connect unstructured data from your external blob stores to Data 360, you give your admins and users more relevant content to help them resolve issues, manage cases, and build effective prompts for Einstein generative AI applications.

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

Data 360 doesn’t import unstructured data–the UDMOs reference it from the external blob store.

# Create an Unstructured Data Lake Object from a Data Kit

After you have deployed your data kit in Data 360, you can create an unstructured data lake object (UDLO). All fields are automatically mapped.

1.  From App Launcher, select **Data Cloud**.
2.  Click **Data Lake Objects** > **New**.
3.  From the New Data Lake Object menu, select **Create from a Data Kit**, and click **Next**.
4.  From your data kit, select one DLO, and click **Next**.
5.  From the Select Connection dropdown list, select a connection. Data 360 auto-populates the source based on the connection that you select.
6.  In the Directory field, point to a specific folder or an entire directory in your blob store. All folders and subfolders in a directory are included. Optionally, use wildcard characters to specify a file name pattern for multiple files.
7.  To add more directories, click **More Files**. You can include up to 5 directories.
8.  Click **Next**.
9.  Add an Object Name and an Object API Name for the UDLO. See Data Lake Object Naming Standards.
10.  From the Data Space dropdown list, select a data space in which to create the new unstructured data model object (UDMO) or a data space from which to select an existing UDMO.
11.  Map the UDLO to a UDMO.
     -   To create a new UDMO, click **New.**
     -   To use an existing UDMO, click **Existing**, and select a UDMO from the list.
12.  Optionally, leave the checkbox selected to create a search index configuration for the UDMO using system defaults that automatically selects text fields and a chunking strategy for each field.
     
     You can deselect the checkbox and create a search index configuration later if you choose not to do so now.
     
13.  Click **Next**, or if you created a search index configuration, review the details, and save your work.

# Chunking Strategies

Data 360 supports several chunking strategies. Data 360 automatically chooses the optimal chunking strategy based on the content type you're working with.

For example, consider the fields that provide the most relevant context and semantic meaning, how to break those fields up, and how you expect the retrieved results to be used in your Einstein Gen AI, automation, analytics application. For example, chunk the custom text fields of a Knowledge Article DMO using the Passage Extraction strategy to make it easier to return semantically similar results when you search across Knowledge objects.

-   [Section-Aware Chunking](https://help.salesforce.com/s/articleView?id=data.c360_a_search_index_supported_chunking_strategies.htm&language=en_US&type=5#c360_a_search_index_supported_chunking_strategies__section_tj2_dnz_rfc)
-   [Semantic-based passage extraction](https://help.salesforce.com/s/articleView?id=data.c360_a_search_index_supported_chunking_strategies.htm&language=en_US&type=5#c360_a_search_index_supported_chunking_strategies__section_pvt_jkq_c2c)
-   [Conversation-based chunking](https://help.salesforce.com/s/articleView?id=data.c360_a_search_index_supported_chunking_strategies.htm&language=en_US&type=5#c360_a_search_index_supported_chunking_strategies__section_q5y_tqx_jfc)
-   [Prepend field chunking](https://help.salesforce.com/s/articleView?id=data.c360_a_search_index_supported_chunking_strategies.htm&language=en_US&type=5#c360_a_search_index_supported_chunking_strategies__section_vsx_lkq_c2c)
-   [Code Extension](https://help.salesforce.com/s/articleView?id=data.c360_a_search_index_supported_chunking_strategies.htm&language=en_US&type=5#c360_a_search_index_supported_chunking_strategies__section_custom_function_chunking)

## Section-Aware Chunking

Section-aware chunking uses title and heading elements to chunk documents. All text under a section title or heading element is chunked together until Data 360 encounters a new section title or heading element. This allows you to chunk content in coherent sections based on the structure of a document.

Sections are never split arbitrarily—chunks always respect natural content boundaries, preserving readability and context. Sometimes short paragraphs or list items are misidentified as standalone sections This can lead to overly small chunks. To avoid this, use these settings when creating a search index.

-   Max Token: Combine adjacent small sections into a larger chunk, optimizing for chunk size without sacrificing coherence. See [How the Max Token Setting Affects Chunking](https://help.salesforce.com/s/articleView?id=data.c360_a_search_index_max_token_setting.htm&language=en_US&type=5).
-   Overlap Tokens: Only used when multiple chunks are created from a single section. Specify the number of tokens to add from the end of each chunk to the beginning of the next chunk. This creates contextual overlap between consecutive chunks, ensuring smooth transitions and better performance in tasks such as search and retrieval.

You can group multiple paragraphs into a single chunk if the combined content stays within the configured token limit.

When the token limit is reached, the chunking logic ensures clean breaks—it doesn’t split in the middle of a sentence or paragraph. Instead, it extends to the end of the paragraph, maintaining semantic and structural integrity across chunks.

For example, this text is divided into sections based on its title and following section headings.

![A text document annotated to show section-aware chunking.](https://sf-zdocs-cdn-prod.zoominsoftware.com/tdta-data-data_cloud-264-0-0-production-enus/9a804ab5-dba6-49d5-8077-820fbcc92ad9/data_cloud/images/section_aware_chunking.png)

An example portion of the resulting chunk data model object contains these records.

| Chunk Sequence Number | Chunk | Chunk DaTAsource Object | Datasource |
| --- | --- | --- | --- |
| 1 | `Retrievers A retriever returns relevant data from the vector database to augment a prompt. By augmenting prompts with accurate, current, and pertinent information, retrievers improve the value and relevance of LLM responses for users. . .` | `DataSourceObject__c` | `DataSource__c` |
| 2 | `Default and Custom Retrievers When a search index is created in Data Cloud, a default retriever is created automatically. You can't customize a default retriever. However, in AI Models, you can create and customize retrievers for search indexes.` | `DataSourceObject__c` | `DataSource__c` |
| 3 | `Dynamic Retrievers Some standard templates contain dynamic retrievers. A dynamic retriever is a placeholder for a retriever specified at runtime depending on the needs of the prompt template. To test a dynamic retriever, enter the retriever’s API name, which you can find in AI Models.` | `DataSourceObject__c` | `DataSource__c` |

When you create a search index configuration in the Data 360 advanced builder, section-aware chunking is the default chunking strategy for HTML and PDF files.

![Note](https://sf-zdocs-cdn-prod.zoominsoftware.com/tdta-data-data_cloud-264-0-0-production-enus/9a804ab5-dba6-49d5-8077-820fbcc92ad9/images/icon_note.png)

Note When you use the section-aware strategy for HTML documents, HTML tags are automatically stripped from the content before chunking.

## Semantic-based Passage Extraction

Semantic-based passage extraction uses the semantic meaning inherent in HTML tags to chunk a document into passages. These HTML elements are considered logical boundaries for chunks.

-   Heading levels 1-6 `<h1-h6>`
-   Thematic breaks `<hr>`
-   Bold `<b>`–Used when the tagged text is on its own line, or if it is used on text in a paragraph where the `font_weight` is set to 700 or higher or the `font_weight` is set to `bold`
-   Strong `<strong>`—Used when the tagged text is on its own line, or if it is used on text in a paragraph where the `font_weight` is set to 700 or higher or the `font_weight` is set to bold
-   Paragraph `<p>`—Used when the tagged text is on its own line
-   Line break `<br>`—Used when current chunk exceeds the token limit

![Note](https://sf-zdocs-cdn-prod.zoominsoftware.com/tdta-data-data_cloud-264-0-0-production-enus/9a804ab5-dba6-49d5-8077-820fbcc92ad9/images/icon_note.png)

Note When you use the passage extraction strategy for HTML documents, html tags are automatically stripped from before chunking. This is the default setting in the search index builder, but you can disable it if needed.

For example, this text includes several HTML elements.

![A text document annotated to show semantic based passage extraction.](https://sf-zdocs-cdn-prod.zoominsoftware.com/tdta-data-data_cloud-264-0-0-production-enus/9a804ab5-dba6-49d5-8077-820fbcc92ad9/data_cloud/images/semantic_based_passage_extraction2.png)

Here’s its HTML equivalent

```
<h1>Enable Custom Time Zones</h1>
<p>Time zone support lets you view time-specific data...</p>

<h4>REQUIRED EDITIONS</h4>
<p>Available in Salesforce Classic and Lightning Experience</p>
<p>...</p>

<h2>Enable Time Zone Support</h2>
<ul>...</ul>
```

An example portion of the resulting chunk data model object contains these records.

| ChunkSequenceNumber | Chunk | Datasource Object | Datasource |
| --- | --- | --- | --- |
| `1` | `Enable Custom Time Zones Time zone support lets you view time-specific data....` | `DataSourceObject__c` | `DataSource__c` |
| `2` | `REQUIRED EDITIONS Available in Salesforce Classic...` | `DataSourceObject__c` | `DataSource__c` |
| `3` | `Enable Time Zone Support From Setup, enter Analytics...` | `DataSourceObject__c` | `DataSource__c` |
| `4` | `Sync Connected Objects and Refresh Datasets Run a full Data Sync of your connected objects...` | `DataSourceObject__c` | `DataSource__c` |

If there is no content between two heading tags, those tags and subsequent content will appear in one chunk instead of two. Data 360 combines as many header tags as can fit into a single chunk if there is no content between the headings.

By default, Data 360 first uses the semantic-based method, but if some resulting passages are too long, they’re processed further using window-based passage extraction. Window-based extraction uses block-level elements such as `<div>` and `<p>` tags, or raw text separated by line breaks `<br>`, to chunk documents into passages. If a paragraph doesn’t contain HTML, the aggregation is done at the sentence level.

## Conversation-based Chunking

Conversation-based chunking segments transcribed data from audio and video files into chunks, typically separated when the voice changes.

During transcription, if there are multiple speakers, each chunk represents the speech of an individual speaker.

Here’s the first few lines of a transcript.

```
"Hello? Hi Alex, it's Sam from Bullseye. I didn't hear from you yesterday, so I wanted to check in. Hi Sam, sorry about that."
```

A portion of the resulting chunk data model object contains these records.

| ChunkSequenceNumber | Chunk | Start Timestamp | End Timestamp | Speaker |
| --- | --- | --- | --- | --- |
| `1` | `Hello?` | `1.051` | `1.253` | `SPEAKER_00` |
| `2` | `Hi Alex, it 's Sam from Bullseye. I didn't hear from you yesterday, so I wanted to check in.` | `3.203` | `8.418` | `SPEAKER_01` |
| `3` | `Hi Sam, sorry about that.` | `10.263` | `11.546` | `SPEAKER_00` |

## Prepend Field Chunking

When you need to add additional metadata to provide context for chunks generated from DMOs or UDMOs, prepend fields to chunks. For example, the `Description` field in a Knowledge article could exceed the optimal chunk size for prompt-based retrieval. By prepending the `Title` field to the chunk, you can provide more context in the prompt results.

This table provides some examples of useful metadata fields.

| Type | Metadata Field Examples |
| --- | --- |
| DMO (Knowledge Articles) | -   Title <br>-   Product Name|
| UDMO (External blob store connectors) | File Path |
| UDMO (Webcrawler or Sitemap connectors) | -   Labels<br>-   Title<br>-   URL|

Configure fields to prepend to chunks from DMOs or UDMOs in the search index advanced setup for vector or hybrid search.

The max token limit for a chunk is 512 so ensure that any fields you choose for prepending have values within that limit. Data 360 skips prepending fields if the length of the prepended fields is greater than 512 tokens.

## Code Extension

Use a custom chunking function when built-in chunking strategies don't meet your content or retrieval requirements. Custom functions are useful when chunk boundaries must follow domain-specific logic, such as preserving related sections from complex PDFs or applying prompt-driven chunking through LLM gateway calls.

By using code extension, deploy a custom function and select it as the chunking strategy in search index Advanced Setup. For the end-to-end workflow to author, validate, deploy, and use a custom chunking function, see [Use Custom Functions in Data 360](https://developer.salesforce.com/docs/data/data-cloud-code-ext/guide/function/use-custom-function.html).

#### See Also

-   [_Salesforce Help_: Create Vector Search Index Configurations](https://help.salesforce.com/s/articleView?id=data.c360_a_search_index_create_vector_index_config.htm&language=en_US&type=5)
-   [_Salesforce Developer_: Code Extension in Data 360](https://developer.salesforce.com/docs/data/data-cloud-code-ext/guide/use-custom-code.html)
-   [_Salesforce Help_: Govern Content for AI Consumption](https://help.salesforce.com/s/articleView?id=005460254&language=en_US&type=1)

# Rebuild a Search Index Configuration

If a Data 360 search index doesn't process properly, you can trigger a full rebuild of the index from the list page or the object record view.

The volume of data determines the time that it takes to rebuild a search index. The rebuild time can differ from the initial build because the amount of data in the data model object may have changed. This action reprocesses all data in the search index and can potentially consume a significant number of credits. Search indexes update continuously, so you don't have to rebuild them manually. If Data 360 dosen't process new content automatically, contact Salesforce Customer Support before rebuilding.

1.  From app Launcher, select **Data Cloud**.
2.  Click the search index configuration that you want to rebuild.
3.  On the details page, select **Rebuild**.
    
    The rebuild process happens in the background. You can continue to query the search index during this time without any interruptions. After a new version of the index is successfully built, the current version of the index is seamlessly replaced. See [View Search Index Status and Process History](https://help.salesforce.com/s/articleView?id=data.c360_a_search_index_view_search_index.htm&language=en_US&type=5) for an explanation of statuses.
    
    ![Note](https://sf-zdocs-cdn-prod.zoominsoftware.com/tdta-data-data_cloud-264-0-0-production-enus/9a804ab5-dba6-49d5-8077-820fbcc92ad9/images/icon_note.png)
    
    Note
    
    The Rebuild action isn't available for search indexes created by Agentforce Data Library (ADL) for file uploads. It's available only for search indexes created by Agentforce Data Library (ADL) for knowledge articles.
    
# Create a Hybrid Search Index with Advanced Setup

Configure a hybrid search index for a data model object (DMO) or an unstructured data model object (UDMO) to provide relevant information to generative AI applications. Data 360 breaks up the referenced data into semantically related chunks and generates searchable vectors, and then generates a vector index and a keyword index.

Before creating a search index, review the Unstructured Data and Search Index Guidelines and Limits in [Data 360 Limits and Guidelines](https://help.salesforce.com/s/articleView?id=data.c360_a_limits_and_guidelines.htm&language=en_US&type=5) and search index considerations in the [Search Reference.](https://help.salesforce.com/s/articleView?id=data.c360_a_search_index_reference.htm&language=en_US&type=5) Familiarize yourself with the concepts of chunking unstructured data, vectorization, and the chunk and index data model objects.

## Enable Agentforce for Generative AI Capabilities (Optional)

Some capabilities in search index, including image processing, enriched index, and LLM-based content processing and parsing require generative AI features available through Agentforce. If you want to use those capabilities, contact your admin to [enable Agentforce](https://help.salesforce.com/s/articleView?id=ai.agent_setup_enable.htm&language=en_US&type=5) in your org. Enable Amazon Bedrock Models (Amazon and Anthropic) in Einstein Setup to use enriched indexing.

## Select a Search Type and Source Object

To get started specify the type of search you want to perform and select a source DMO.

1.  From App Launcher, select **Data Cloud**.
2.  Click **Search Index** > **New**.
3.  Click **Advanced Setup** > **Next**.
4.  Select Hybrid Search for **Search Type**.
5.  Select a data space and a source object.
    
    ![Note](https://sf-zdocs-cdn-prod.zoominsoftware.com/tdta-data-data_cloud-264-0-0-production-enus/9a804ab5-dba6-49d5-8077-820fbcc92ad9/images/icon_note.png)
    
    Note A DMO that has mappings from one or more external DLOs can only be used as the data source if caching is enabled for all those external DLOs. For more information see, [Caching in Data Federation](https://help.salesforce.com/s/articleView?id=data.c360_a_accelerated_data_lake_objects.htm&language=en_US&type=5).
    
6.  Click **Next**.

## Set Up Parsing and Visual Data Preprocessing

Next, extract and prepare text, metadata, tables, and images from unstructured documents for chunking.

LLM-Parsing and preprocessing options are available for PDF, HTML, DOCX, and PPTX file types from UDMOs and files attached to DMO records. These options aren't available for use with DMO records.

You cannot select both LLM-based parsing and LLM-based Visual Data Preprocessing options for a single search index. See [LLM-based parsing and preprocessing](https://help.salesforce.com/s/articleView?id=data.c360_a_llm_parsing_preprocessing.htm&language=en_US&type=5) for more information about these options.

With LLM-based parsing and LLM-based Visual Data Preprocessing you can override the default GPT-4o model to use any supported LLM that best fits your business needs and your content. You can only select LLMs that are approved for use by your admin. If your org admin turns off a model that is currently in use, your previously processed content remains accessible. However, Search Index will fail to process any further content. For more more information supported models, see [Search Index Reference](https://help.salesforce.com/s/articleView?id=data.c360_a_search_index_reference.htm&language=en_US&type=5).

1.  On the Parsing page, choose one of these options.
    
    <table class="slds-table slds-table_bordered slds-m-bottom_small"><tbody><tr class=""><th id="d15801e252" headers="d15801e248-option" style="vertical-align:top;">Default Parser</th><td headers="d15801e248-desc d15801e252" style="vertical-align:top;">Extract text with built-in settings.</td></tr><tr class=""><th id="d15801e261" headers="d15801e248-option" style="vertical-align:top;">LLM-based Parser</th><td headers="d15801e248-desc d15801e261" style="vertical-align:top;">Extract all text, images, and other visual elements using an LLM.</td></tr><tr class=""><th id="d15801e270" headers="d15801e248-option" style="vertical-align:top;">Docling Parser</th><td headers="d15801e248-desc d15801e270" style="vertical-align:top;">Extract text from tables, spreadsheets, slide decks. Understand document layouts using Docling Parser.</td></tr></tbody></table>
    
2.  If you choose Default Parser, click **Next.**
3.  If you choose to parse your documents using an LLM, complete these steps.
    1.  From the dropdown list, select the appropriate model.
    2.  Use the default prompt as is, or edit it for your specific use case.
        
        It's highly recommended to customize the prompt for your use case and documents.
        
    3.  Click **Next**.
4.  If you choose the Docling parser, click **Next**.
    
    By default, additional pre-processing is turned-off. Optionally, enable image processing when you set up chunking strategies to parse images and complex tables.
    
5.  If you chose the default parser, on the Preprocessing page, choose one of these options.
    
    <table class="slds-table slds-table_bordered slds-m-bottom_small"><tbody><tr class=""><th id="d15801e342" headers="d15801e338-option" style="vertical-align:top;">No Preprocessing</th><td headers="d15801e338-desc d15801e342" style="vertical-align:top;">Use parsed text and visual data as is.</td></tr><tr class=""><th id="d15801e351" headers="d15801e338-option" style="vertical-align:top;">LLM-based Visual Data Preprocessing</th><td headers="d15801e338-desc d15801e351" style="vertical-align:top;">Capture context from visual data using an LLM. (Available only if you selected the default parser in the previous step.)</td></tr></tbody></table>
    
6.  If you choose No pre-processing, click **Next**.
7.  If you choose to pre-process your documents using an LLM, complete these steps.
    1.  From the dropdown list, select the appropriate model.
    2.  Use the default prompt as is, or edit it for your specific use case.
        
        It's highly recommended to customize the prompt for your use case and documents.
        
    3.  Click **Next**.

## Set Up Chunking and Vectorization

Next, set up chunking for your data and select an embedding model to create searchable vectors for each chunk.

1.  If your search index is on a DMO, on the Chunking page, select fields to chunk and the [chunking strategy](https://help.salesforce.com/s/articleView?id=data.c360_a_search_index_supported_chunking_strategies.htm&language=en_US&type=5).
    1.  To add or remove fields, click **Manage Fields** and save your work.
        
        Search Indexes don't support date and datetime fields for chunking. Only numerical and text fields are available for chunking data.
        
    2.  (Optional) Update the chunking strategy and modify the settings.
    3.  If your search index is on a DMO of a Salesforce object with file attachments that you want to include, click **Include Attachments** and select the ContentDocumentVersion UDMO.
    4.  Add a file extension or set a chunking strategy based on the file type. To add a file extension for a new file type, click **Add File Extension**, and then optionally update the chunking strategy and modify the settings for an existing file type.
    5.  (Optional) To add additional fields to a chunk, select the **Prepend fields to each chunk** toggle and select a field from the list. You can add a maximum of two fields.
    6.  To enrich generated chunks with additional metadata, turn on the **Enrich Content Chunks** toggle.
    7.  Click **Next**.
2.  If your search index is on a UDMO, add a file extension or set a [chunking strategy](https://help.salesforce.com/s/articleView?id=data.c360_a_search_index_supported_chunking_strategies.htm&language=en_US&type=5) based on the file type.
    1.  To add a file extension for a new file type, click **Add File Extension**. If you have images to process, add the JPEG, JPG, and PNG file extensions.
    2.  (Optional) Update the chunking strategy and modify the settings for an existing file type.
        
        For image files with extensions, such as JPEG, JPG, or PNG, image processing is enabled by default. To include image processing for PDF files, turn on image processing.
        
        If you selected LLM-based parsing or LLM-based visual data preprocessing in previous steps, image processing doesn't apply even if you turn it on.
        
    3.  (Optional) To add additional fields to a chunk, select the **Prepend fields to each chunk** toggle and select a field from the list. You can add a maximum of two fields.
    4.  To enrich generated chunks with additional metadata, turn on the **Enrich Content Chunks** toggle.
    5.  When you select the Docling parser, optionally, turn-on LLM-based image processing to parse images and complex tables using an LLM. For better data extraction with tables, select Section-Aware chunking. Section-Aware chunking processes tables optimally such as retaining the header information across table chunks. For more information on supported file formats see, [Docling Parser](https://help.salesforce.com/s/articleView?id=data.c360_a_docling_parser.htm&language=en_US&type=5).
3.  If you have audio or video files to transcribe, click **Configure**, and in the transcription window, select the following:
    1.  Select the default transcription model from the dropdown.
    2.  To add a timestamp to each speaker entry, select **Include timestamp**.
4.  Click **Next**.
5.  On the Vectorization page, from the dropdown list, select an embedding model. If your search index includes images to process, select the [appropriate embedding model (beta)](https://help.salesforce.com/s/articleView?id=data.c360_a_search_index_reference.htm&language=en_US&type=5#c360_a_search_index_reference__section_o34_jqz_wcc).
    
    The model determines how Data 360 measures your unstructured data objects for semantic relevance when building search results.
    
6.  Click **Next**.

## Configure Fields for Filtering and Ranking Factors

To enhance the precision and relevance of search results, specify fields that users can use to filter their searches.

1.  On the Fields for Filtering page, optionally add fields from the Source object or related objects to provide more ways to filter a search. You can select up to ten filter fields.
    
    Data 360 picks up the pre-filter fields when you generate vector embeddings. If you change the values in those pre-filter fields, Data 360 picks them up when you generate or refresh those vector embeddings. The cardinality of object relationship between the source object and the related object must be either 1:1 or N:1.
    
    For example, if the indexed unstructured data includes case conversation transcripts, filtering on the Status field in the Case object can improve the relevance of semantic search results when searching the conversation transcripts.
    
2.  Click **Next**.
3.  (Optional) To better rank the hybrid search results, click **Add Ranking Factor**.
    
    For example, you can select **RECENCY** as the ranking factor and choose the **LastModifiedDate** field in the DMO to rank the search results. For the object contributing to the ranking factor, you can select the object that the search index is built on or a related object. If you select a related object, select the field for the relationship.
    
    You can add up to two ranking factors, recency of records and popularity of records.
    

## Review and Build the Index

1.  Review the configuration and the target data model objects.
2.  Click **Save**.

When you build the search index, Data 360 creates a hybrid search index for the data. Next, create a Retriever in the **AI Models** tab. Agentforce agents can use the search index with Retrievers in prompt templates.

#### See Also

-   [_Salesforce Help_: Search Index Considerations](https://help.salesforce.com/s/articleView?id=data.c360_a_search_index_reference.htm&language=en_US&type=5)
-   [_Salesforce Help_: Search Index Grounding](https://help.salesforce.com/s/articleView?id=data.c360_a_search_index_grounding.htm&language=en_US&type=5)
-   [_Salesforce Help_: Manage Search Index](https://help.salesforce.com/s/articleView?id=data.c360_a_search_index_manage.htm&language=en_US&type=5)
-   [_Salesforce Help_: Ground with Retriever Augmented Generation (RAG)](https://help.salesforce.com/s/articleView?id=ai.prompt_builder_ground_rag.htm&language=en_US&type=5)

# Retrieve Data

Use a retriever to search and return relevant data from a search index. Create and customize retrievers in AI Models (formerly Einstein Studio) for Retrieval Augmented Generation (RAG) in Data 360. Retrievers augment prompt templates by providing relevant, specialized grounding information for prompts.

## Data Preparation

Data preparation for retrieval from a search index involves loading, chunking, vectorizing, and storing content in a search-optimized way. Data 360 uses a vector data store for unstructured data, such as documents and conversation histories. A search index stores chunked and vectorized data that can be searched and retrieved from other applications. You can create and manage search indexes in Data 360. They’re defined in a data space and associated with a data model object (DMO).

With advanced document processing and indexing capabilities in Data 360, retrievers can retrieve and ground agent responses by processing both text and images. Turn on image processing for the unstructured data model object search indexes to process documents with images and other visuals, such as tables and flow charts. For more information on advanced setup for search indexes, see [Use Search for AI, Automation, and Analytics](https://help.salesforce.com/s/articleView?id=data.c360_a_search_index_ground_ai.htm&language=en_US&type=5).

## Search and Retriever Configuration

Search indexes are often designed for general usage, such as indexing an entire knowledge base. You use retrievers to conduct specialized searches on search indexes and provide relevant results to agents, prompt templates, flows, and other features. Individual retrievers for search indexes apply the multi-purpose search index to a particular use case. For example, retrievers can return content that’s filtered based on a category of articles, the most recent information (such as the last 90 days), or geographical region.

You build retrievers in AI Models and then activate it to make it available to Prompt Builder users. In Prompt Builder, you ground a prompt template with knowledge by inserting and configuring a retriever. At run time, the retriever provides the LLM with accurate, current, and pertinent information to improve the relevance, accuracy, and value of LLM responses.

Retrievers adhere to the data governance policies set up for your data. Row-level access checks make sure that users have access to the data and knowledge returned by the retriever.

## Retrievers in Data Cloud One Configurations

When you create a retriever in a Data 360 home org, you can view it in the companion org and use it within Prompt Builder and Flow. You can also create and manage retrievers locally in a companion org. For more information see, [Retriever Support in Data Cloud One](https://help.salesforce.com/s/articleView?id=data.c360_a_ai_retriever_data_cloud_one.htm&language=en_US&type=5) and [Data Cloud One Companion Connections](https://help.salesforce.com/s/articleView?id=data.c360_a_companion_connections.htm&language=en_US&type=5).

## Individual Retrievers

Use individual retrievers to retrieve data from from a search index. To create an individual retriever in AI Models, you select its search index, define filters, and specify what information it returns. Filters narrow the search focus to more relevant data. The search index defines the fields that you can use for filtering. You also configure the data returned to the prompt, including the fields of data to return and the number of results. Each time you edit and save an individual retriever, another version is created in AI Models. Only one version of a retriever can be active.

Data 360 no longer creates default Retrievers automatically when you create a search index. Previously, when you created a search index in Data 360, a default retriever was created automatically. You can use existing default retrievers in apps, such as Prompt Builder or flow.

## Custom SQL Retrievers

Define, validate, and create retrievers with SQL queries directly in the retriever user interface (UI) without switching between the Query Editor, Apex, and Prompt Builder. Use parameterized queries to build reusable retrievers. Developers get a dedicated UI experience to programmatically build retrievers before deploying them in agents. You can also query other Data 360 objects such as data model objects (DMO), data lake objects (DLO), and calculated insights in the Custom SQL retriever UI.

## Ensemble Retrievers

An ensemble retriever is a collection of individual retrievers. When you run an ensemble retriever, it executes the individual retrievers, combines their results into a single list, reranks the list according to relevance to the search request, and returns just the most relevant information to apps.

Considerations for ensemble retrievers:

-   Ensemble retrievers don't support retrievers of type Code.
-   Individual retrievers with dynamic filters can’t be part of an ensemble retriever.
-   In the Retriever Playground, test and validate pre-filter conditions for individual retrievers only when you configure them separately. You can't edit or test individual retrievers directly within an ensemble retriever.
-   Ensemble retrievers with custom SQL retrievers can’t be tested in the playground.

## Dynamic Retrievers

Dynamic retrievers use placeholders that accept at run time values from prompt templates. A dynamic retriever has a placeholder for a value specified at runtime based on the needs of the prompt template.

-   **[Get Trusted AI Responses with Retriever Citations](https://help.salesforce.com/s/articleView?id=data.c360_a_ai_citations_retriever.htm&language=en_US&type=5)**  
    Citations link AI-generated responses to the source content relevant to each response. Citations allow users to compare the LLM response with the source data to verify the validity of the response and identify any potential inaccuracies or hallucinations. Enable citations in AI Models (formerly Einstein Studio) at the individual retriever level to give access to citations to solution components that call the retriever, such as a prompt template.
-   **[Manage Retrievers](https://help.salesforce.com/s/articleView?id=data.c360_a_ai_retriever_version.htm&language=en_US&type=5)**  
    Create and customize retrievers for Retrieval Augmented Generation (RAG) in Data 360. To see the list of retrievers, navigate to the Retrievers tab in AI Models (formerly Einstein Studio). To learn about a retriever, select View Details from the dropdown menu. Each time you edit a custom retriever and save the changes, a new version is created. You can create multiple versions, but you can have only one version active at a time.
-   **[Customize, Test, and Validate Retrievers with Retriever Playground](https://help.salesforce.com/s/articleView?id=data.c360_a_ai_retriever_test.htm&language=en_US&type=5)**  
    Fine-tune and validate retrieval logic for retrieval-augmented generation (RAG) systems by using retriever playground, reducing deployment risks, and verifying accurate AI outputs. Use AI Models (formerly Einstein Studio) retriever playground to configure pre-filters, select test data, and adjust result parameters to customize retrieval logic for domain-specific use cases, such as retrieving complaince documents or knowledge articles.
-   **[Retriever Filters Reference](https://help.salesforce.com/s/articleView?id=data.c360_a_retriever_filter_reference.htm&language=en_US&type=5)**  
    Configure filter conditions for retrieval accuracy when you create or test retrievers in AI Models (formerly Einstein Studio). Use filter conditions to filter records retrieved for search queries. You can configure up to ten filter conditions for an individual retriever.
-   **[Retriever Support in Data Cloud One](https://help.salesforce.com/s/articleView?id=data.c360_a_ai_retriever_data_cloud_one.htm&language=en_US&type=5)**  
    Learn about retriever capabilities and limitations when you work with Data Cloud One home and companion orgs.

#### See Also

-   [_Salesforce Help_: Retrieval Augmented Generation (RAG)](https://help.salesforce.com/s/articleView?id=ai.generative_ai_rag.htm&language=en_US&type=5)
-   [_Salesforce Help_:Ground with Knowledge Using Retrieval Augmented Generation](https://help.salesforce.com/s/articleView?id=ai.prompt_builder_ground_rag.htm&language=en_US&type=5)
-   [_Salesforce Help_: Search for AI, Automation, and Analytics](https://help.salesforce.com/s/articleView?id=data.c360_a_search_index_ground_ai.htm&language=en_US&type=5)
-   [_Salesforce Help_: Retriever Support in Data Cloud One](https://help.salesforce.com/s/articleView?id=data.c360_a_ai_retriever_data_cloud_one.htm&language=en_US&type=5)
-   [_Trailhead_: Retrieval Augmented Generation: Quick Look](https://trailhead.salesforce.com/content/learn/modules/retrieval-augmented-generation-quick-look)
-   [_Rag Best Practices White Paper_: Agentforce and RAG: Best Practices for Better Agents](https://view.salesforce.com/viewer/da54a79f51b5c2aa4002845258559687#1)
-   [_Salesforce Developer:_ Salesforce Data 360 Connect REST API: Retrievers Reference](https://developer.salesforce.com/docs/data/connectapi/references/spec#tag/Machine-Learning)

# Use Search for AI, Automation, and Analytics

Grounding Data 360 search on unstructured and structured data enhances your use of generative AI, analytics, and automation tools across Salesforce. Grounding brings customer-specific data, including diverse forms of unstructured data (such as text documents, multimedia files, social media content, web content, chat logs, sensor data, and customer feedback), into applications like Agentforce, Tableau, and Flow Builder. This alignment results in more accurate and relevant AI-generated content, deeper insights from analytics, and more efficient automation workflows for your teams and customers.

![Note](https://sf-zdocs-cdn-prod.zoominsoftware.com/tdta-data-data_cloud-264-0-0-production-enus/9a804ab5-dba6-49d5-8077-820fbcc92ad9/images/icon_note.png)

Note

As of October 14, 2025, Data Cloud has been rebranded to Data 360. During this transition, you may see references to Data Cloud in our application and documentation. While the name is new, the functionality and content remains unchanged.

In Data 360, you can create vector or hybrid search indexes depending on data and query needs.

## Vector Search

In Data 360, you can create searchable vector embeddings from your unstructured and structured data. A vector embedding is a numerical representation of a unit of text (an article or a passage from a larger document) that captures its semantic meaning. Large language models (LLMs) group embeddings with similar semantic meanings so that generative AI applications can effectively interpret their relationships and contextual relevance.

Use vector search when your data source and search queries benefit more from semantically aware matches within a large dataset. For example, if you send a query such as “What is Acme famous for?”, the LLM retrieves chunks that have the highest vector search score that relates to the closest semantic match with the search query.

Before you create a vector search index, unstructured data stored in data model objects (DMOs) or unstructured data model objects (UDMOs) are chunked into manageable, semantically meaningful units. These units are stored in [two objects](https://help.salesforce.com/s/articleView?id=data.c360_a_search_index_chunk_index_dmo.htm&language=en_US&type=5): a chunk data model object (CDMO) and an index data model object (IDMO). The CDMO is a Data 360 object that stores the actual content chunks, and the IDMO stores the vector embedding.

You can perform vector searches on that data from apps such as Prompt Builder, AI agents, or Tableau.

## Hybrid Search

To deliver relevant and accurate responses in generative AI applications, Large Language Models (LLMs) often require both vector and keyword search. While vector search excels at grasping semantic similarities, it can lack precision with specific domain vocabulary. Conversely, keyword search is excellent for lexical matches but doesn't understand semantic similarity. In Data 360, hybrid search combines these methods, using semantically aware vector search for contextual understanding and keyword search for precise lexical matching.

When your data source and search queries benefit from both semantically aware vector search and the precision of a keyword search, use hybrid search. For example, in the query “Does Acme motor XYZ123 use hydraulic pumps?” the addition of keyword search promotes higher-ranking positions for more relevant content, thus providing the results with better grounding.

After you create a hybrid search index on your DMOs or UDMOs, Data 360 generates content chunks and vector embeddings for a vector search index and a keyword search index. Hybrid search queries the vector search index to retrieve information based on semantic similarity, and it queries the keyword search index to retrieve information based on lexical similarity. Hybrid search then merges and ranks the results provided by both types of searches to generate the best response. You can also configure additional ranking factors, such as recency or popularity of records, to influence the search results returned.

## Key Use Cases for Data 360 Search

Key use cases for Data 360 search include:

-   In Retrieval Augmented Generation (RAG): Data 360 search is fundamental to RAG, grounding AI responses in relevant unstructured data. This directly leads to more accurate and contextually appropriate AI outputs that are based on your specific knowledge base.
-   In Service Cloud: AI agents use search to query for precise information within knowledge articles, emails, support tickets, and chat logs. This enables them to provide more accurate answers, craft better responses, and even proactively suggest solutions to customer issues.
-   In Sales Cloud: AI agents can query unstructured sales data—like emails, call transcripts, and notes—to generate highly relevant meeting briefings and summaries. This insight also fuels personalized content and customer-specific recommendations for new emails, significantly boosting customer engagement and sales team productivity.
-   In automation flows: AI agents can automatically identify semantically similar records, such as Cases, based on their descriptions. This capability is crucial for flagging duplicates, accelerating resolution times, and accurately classifying records by finding similar historical examples.
-   In analytics: Within Tableau, Data 360 search facilitates gaining deeper insights from unstructured data, notably through advanced topic classification. This enhances data analysis by revealing patterns and themes that traditional methods sometimes miss.

-   **[Chunk Data](https://help.salesforce.com/s/articleView?id=data.c360_a_search_index_grounding.htm&language=en_US&type=5)**  
    To add your data to Data 360’s search index, you must first chunk it. Chunking break your data into meaningful chunks, and Data 360 turns those chunks into machine-readable vector embeddings.
-   **[Vector Search](https://help.salesforce.com/s/articleView?id=data.c360_a_search_index_vector_index.htm&language=en_US&type=5)**  
    In Data 360, you can create searchable semantic vector embeddings from your unstructured and structured data. Vector search helps your generative AI, automation, and analytics applications understand semantic similarities and context between embeddings.
-   **[Hybrid Search](https://help.salesforce.com/s/articleView?id=data.c360_a_hybridsearch_index.htm&language=en_US&type=5)**  
    To provide relevant information to an LLM with gen AI applications and generate the correct response, requires both vector search and keyword search. Vector search understands semantic similarities and context, but lacks specific domain vocabulary. Keyword search excels at lexical similarity but not at semantic similarity. In Data 360, hybrid search combines the strengths of semantically aware vector search with the precision and speed of keyword search.
-   **[Manage Search Indexes](https://help.salesforce.com/s/articleView?id=data.c360_a_search_index_manage.htm&language=en_US&type=5)**  
    Create, view, edit, and delete search index configurations.
-   **[Optimizing Search Indexes: Field Selection and Chunking](https://help.salesforce.com/s/articleView?id=data.c360_a_search_index_optimize.htm&language=en_US&type=5)**  
    When you create a search index in the advanced builder, you can optimize your search index to deliver more accurate results by paying attention to the field selection and chunking strategies you use.
-   **[Search Index Reference](https://help.salesforce.com/s/articleView?id=data.c360_a_search_index_reference.htm&language=en_US&type=5)**  
    Data 360 search supports many different file formats with unstructured data, embedding models, and pre-filter operations on search results.
-   **[Using Retrieval Augmented Generation](https://help.salesforce.com/s/articleView?id=data.c360_a_rag_overview.htm&language=en_US&type=5)**  
    Retrieval Augmented Generation (RAG) in Data 360 is a framework for grounding large language model (LLM) prompts. By augmenting the prompt with accurate, current, and pertinent information, RAG improves the relevance and value of LLM responses for users.
-   **[Billing Considerations for Unstructured Data and Search Index](https://help.salesforce.com/s/articleView?id=data.c360_a_unstructured_data_billing_considerations.htm&language=en_US&type=5)**  
    When you use unstructured data and search index configurations, your data is stored and processed in Data 360. Use of unstructured data and search index in Data 360 impacts the consumption of credits in the following usage types.

#### See Also

-   [_Salesforce Help_: About Unstructured Data](https://help.salesforce.com/s/articleView?id=data.c360_a_unstructured_data_about.htm&language=en_US&type=5)
-   [_Salesforce Help_: Data 360 Limits and Guidelines](https://help.salesforce.com/s/articleView?id=data.c360_a_limits_and_guidelines.htm&language=en_US&type=5)
-   [_Salesforce Help_: Encrypt Data 360 with Customer-Managed Root Keys](https://help.salesforce.com/s/articleView?id=xcloud.security_pe_enable_pe_for_data_cloud.htm&language=en_US&type=5)
-   [_Trailhead_: Get to Know Search Index Types in Data 360](https://trailhead.salesforce.com/content/learn/modules/search-index-types-data-cloud-quick-look)

<!--stackedit_data:
eyJoaXN0b3J5IjpbOTQyMzU3OTAsLTM1NTkyOTYxN119
-->