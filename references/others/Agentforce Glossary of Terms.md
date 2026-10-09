# Agentforce Glossary of Terms

Learn more about the terms used in Agentforce and generative AI at Salesforce.

[A](https://help.salesforce.com/s/articleView?id=ai.copilot_glossary.htm&language=en_US&type=5#copilot_glossary__a) | [B](https://help.salesforce.com/s/articleView?id=ai.copilot_glossary.htm&language=en_US&type=5#copilot_glossary__b) | [C](https://help.salesforce.com/s/articleView?id=ai.copilot_glossary.htm&language=en_US&type=5#copilot_glossary__c) | [D](https://help.salesforce.com/s/articleView?id=ai.copilot_glossary.htm&language=en_US&type=5#copilot_glossary__d) | [E](https://help.salesforce.com/s/articleView?id=ai.copilot_glossary.htm&language=en_US&type=5#copilot_glossary__e) | [F](https://help.salesforce.com/s/articleView?id=ai.copilot_glossary.htm&language=en_US&type=5#copilot_glossary__f) | [G](https://help.salesforce.com/s/articleView?id=ai.copilot_glossary.htm&language=en_US&type=5#copilot_glossary__g) | [H](https://help.salesforce.com/s/articleView?id=ai.copilot_glossary.htm&language=en_US&type=5#copilot_glossary__h) | [I](https://help.salesforce.com/s/articleView?id=ai.copilot_glossary.htm&language=en_US&type=5#copilot_glossary__i) | [L](https://help.salesforce.com/s/articleView?id=ai.copilot_glossary.htm&language=en_US&type=5#copilot_glossary__l) | [M](https://help.salesforce.com/s/articleView?id=ai.copilot_glossary.htm&language=en_US&type=5#copilot_glossary__m) | [N](https://help.salesforce.com/s/articleView?id=ai.copilot_glossary.htm&language=en_US&type=5#copilot_glossary__n) | [O](https://help.salesforce.com/s/articleView?id=ai.copilot_glossary.htm&language=en_US&type=5#copilot_glossary__o) | [P](https://help.salesforce.com/s/articleView?id=ai.copilot_glossary.htm&language=en_US&type=5#copilot_glossary__p) | [R](https://help.salesforce.com/s/articleView?id=ai.copilot_glossary.htm&language=en_US&type=5#copilot_glossary__r) | [S](https://help.salesforce.com/s/articleView?id=ai.copilot_glossary.htm&language=en_US&type=5#copilot_glossary__s) | [T](https://help.salesforce.com/s/articleView?id=ai.copilot_glossary.htm&language=en_US&type=5#copilot_glossary__t) | [U](https://help.salesforce.com/s/articleView?id=ai.copilot_glossary.htm&language=en_US&type=5#copilot_glossary__u) | [V](https://help.salesforce.com/s/articleView?id=ai.copilot_glossary.htm&language=en_US&type=5#copilot_glossary__v)

![Note](https://sf-zdocs-cdn-prod.zoominsoftware.com/tdta-ai-generative_ai-264-0-0-production-enus/8f79e91a-cacc-4a50-9604-d1286798b180/images/icon_note.png)

Note Beginning in April 2026, agent topics are now called subagents. There are no changes to functionality. During this transition, you may see a mix of the new and previous terms in our documentation.

## A

Action, agent action

A function your agent executes on the platform to get information and perform tasks. In other words, an action is how an agent gets things done in Salesforce. An agent action includes:

-   A natural language name and instructions that tells the agent how and when to use the action, how to retrieve required inputs, and how to format and use outputs.
-   The Salesforce functionality that the agent action calls to get information or perform a task, called a reference action. For example, an agent action can call an API to retrieve data, a flow to update a record, a prompt template to generate a response, an Apex class to run custom business logic, or a predictive model to make a recommendation.

Agent

Goal-oriented, autonomous AI that performs tasks and business interactions and provides relevant answers drawn from business data. An agent is more autonomous than other conversational AI solutions, so it can independently identify opportunities for action, anticipate next steps, and initiate tasks within the use cases and guardrails you specify. Some agents initiate and complete tasks on behalf of a user. Others assist users with tasks and questions in the user’s flow of work.

Agents can be deployed to customer or employee channels, depending on the associated agent type.

An agent can be created from a template or from scratch. An agent contains subagents and actions.

See [What Are Agents?](https://help.salesforce.com/s/articleView?id=ai.copilot_overview.htm&language=en_US&type=5)

Agent Router (formerly known as Topic Selector)

A special system subagent that helps you control subagent classification and routing in agents created in Agentforce Builder in Agentforce Studio.

When you create an agent, the Agent Router is added to your agent and is defined as the starting subagent for every agent conversation. By default, the agent uses this subagent for subagent classification, which is the process of selecting the most relevant subagent based on what the user wants to do and the jobs that the agent can do.

You can edit the Agent Router just like any other subagent, so you can customize its reasoning instructions and actions to set initial variables, add logic, and add or remove transitions to subagents to control your agent's routing behavior.

See [Subagent Classification and Routing](https://help.salesforce.com/s/articleView?id=ai.agent_topics_routing.htm&language=en_US&type=5).

Agent user, Agent’s user record

A Salesforce integration user with all the permissions that the agent needs to do its job. You can create an agent user in the Agent Creator guided setup when you create an agent that connects to customer channels.

An AI agent can interact with employees or customers. Most agents that interact with employees run in the context of the logged-in user. However, agents connected to customer channels chat with a broad set of users, including unverified users. To securely access data and perform actions that an end user doesn’t have access to, the agent operates as an agent user. The permissions that you give to an agent user determines the actions that the associated agent can take.

See [Best Practices for Agent User Permissions](https://help.salesforce.com/s/articleView?id=ai.agent_user.htm&language=en_US&type=5) and [Agent Execution Context and Data Access by Type](https://help.salesforce.com/s/articleView?id=ai.agent_execution_data.htm&language=en_US&type=5).

Agentforce Data Library

Agentforce Data Library provides grounding information for agents. Create a data library to index knowledge articles and fields, file uploads, or web sources. Indexes enable AI agents to retrieve and use relevant, accurate information for LLM prompts.

See [Agentforce Data Library](https://help.salesforce.com/s/articleView?id=ai.data_library_parent.htm&language=en_US&type=5).

Agentic feature, Agentforce feature

A generative AI solution that uses the LLM gateway and the reasoning engine (usually branded as “Agentforce.” An agentic feature is often a conversational experience with a chat UI, but others operate in the background.

Artificial intelligence (AI)

A branch of computer science in which computer systems use data to draw inferences, perform tasks, and solve problems with human-like reasoning.

Assets, agent assets

Refers to the subagents, actions, variables, surfaces, and default settings (such as system messages) assigned to an agent.

You can view assets available for your agents in the asset library. You can view and manage the assets assigned to your agent in Agentforce Builder.

## B

Bias

Systematic and repeatable errors in a computer system that create unfair outcomes, in ways different from the intended function of the system, due to inaccurate assumptions in the machine learning process.

## C

Channel

A messaging platform, app, or interface that you can deploy an agent to. Employees and other internal stakeholders can interact with agents in Salesforce, Slack, and other employee channels. Customer channels, such as messaging platforms and email, are where your customers can interact with an agent.

See [Deploy Your Agent to Channels](https://help.salesforce.com/s/articleView?id=ai.agent_parent_deploy.htm&language=en_US&type=5).

Chunking

The process of breaking unstructured data into manageable, semantically meaningful chunks that can then be turned into [vector embeddings](https://help.salesforce.com/s/articleView?id=ai.copilot_glossary.htm&language=en_US&type=5#copilot_glossary__vector_embedding). Chunking strategies vary depending on the context of the content being chunked.

See [Chunk Data](https://help.salesforce.com/s/articleView?id=data.c360_a_search_index_grounding.htm&language=en_US&type=5).

Citation

Citations link AI-generated responses to the grounding sources that are relevant to the response. Citations allow users to see what information the large language model (LLM) used to generate the response, and to verify the validity of the source data.

See [Build Trust in AI Responses with Citations](https://help.salesforce.com/s/articleView?id=ai.generative_ai_trust_citations.htm&language=en_US&type=5).

Connection

A connection includes all of the components and settings that help your agent connect to a specific channel, including adaptive response formats, and connection settings. You can also find the Omni-Channel flows that route conversations to and from an agent in your connection settings.

See [Deploy Your Agent to Channels](https://help.salesforce.com/s/articleView?id=ai.agent_parent_deploy.htm&language=en_US&type=5).

Conversation recommendations (Lightning Experience and mobile only)

Clickable suggested requests or questions that appear directly in the Agentforce conversation panel and persist even when the user moves to a new page. Formerly known as Recommended Actions. Supported for Agentforce Employee agents only.

## D

Digital Wallet

An account management tool that offers near real-time consumption data for enabled products across your active contracts. Use Digital Wallet to track your org’s Agentforce usage and credit consumption against generative AI usage types.

See [About Digital Wallet](https://help.salesforce.com/s/articleView?id=xcloud.wallet_about.htm&language=en_US&type=5) and [Generative AI Usage and Billing](https://help.salesforce.com/s/articleView?id=ai.generative_ai_usage.htm&language=en_US&type=5).

## E

Embedded feature, Einstein feature

A non-Agentforce feature (usually branded as “Einstein”) that uses AI. It can be a predictive AI solution, or it can be a generative AI solution that uses the LLM gateway and doesn’t use the reasoning engine.

## F

Filter

Limits access to subagents and actions based on conditions and variables you specify. When you apply a filter to a subagent or action, the agent can only use the asset when the filter conditions are met.

Fine-tuning, Tuning

The process of adapting a pre-trained language model for a specific task by training it on a smaller, task-specific dataset.

Fine-tuning can also more generally refer to the process of testing and refining instructions to improve prompt performance.

Follow-up actions (Lightning Experience only)

Context-sensitive actions that appear in the Agentforce conversation panel after a user completes a specific standard action. These actions guide users through a natural workflow by suggesting the next logical step based on the previous action's output. By definition, follow-up actions can’t be executed on their own. They can only follow a standard action (for example, you can’t ‘refine an email’ without first ‘drafting an email’).

## G

Generative AI gateway, Einstein gateway, the gateway

Exposes normalized APIs to interact with foundation models and services provided by different vendors, internally and from the partner ecosystem.

Generative pre-trained transformer (GPT)

A family of language models trained on a large body of text data so that they can generate human-like text.

Grounding

The process through which domain-specific knowledge and customer information is added to a prompt to give the model the context it needs to respond more accurately.

See [Ground Agentforce in Your Data](https://help.salesforce.com/s/articleView?id=ai.agent_parent_data.htm&language=en_US&type=5).

## H

Hallucination

A type of output where a model generates semantically correct text that is factually incorrect or makes little to no sense, given the context.

Human in the loop (HITL)

A model that requires human interaction.

Hyperparameter

A parameter used to control the training process. Hyperparameters sit outside the generated model.

## I

Instructions

Instructions describe a task to a LLM using natural language. Instructions are the basis of prompt templates. In Agentforce, instructions include instructions include agent-level instructions, subagent instructions (sometimes called reasoning instructions), and sometimes user input to the agent.

Intent

An end user’s goal for interacting with an AI agent.

## L

Large language model

A language model consisting of a neural network with many parameters trained on large quantities of text.

Agents harness the power of a large language model (LLM) to communicate with users and take action in your org. Agents make reasoning engine calls to the LLM at different times during a task or interaction with a user. The number and size of the LLM calls depends on the task and which subagents and actions are launched.

See [How Agentforce Works](https://help.salesforce.com/s/articleView?id=ai.agent_reasoning_engine.htm&language=en_US&type=5).

## M

Machine learning

A subfield of AI specializing in computer systems that are designed to learn, adapt, and improve based on feedback and inferences from data, rather than explicit instruction.

Model card

Documents details about the model’s performance as well as inputs, outputs, training method, conditions under which the model works best, and ethical considerations in use.

## N

Natural language processing (NLP)

A branch of AI that uses machine learning to understand language as written by people. Large language models are one of many approaches to NLP.

## O

Omni-Channel flow

A flow used to route conversations to or from an agent. Omni-Channel flows use the Route Work action to route conversations and their associated records, such as messaging session and email records. Agents that connect to customer channels have at least one inbound and outbound Omni-Channel flow.

See [Deploy Your Agent to Channels](https://help.salesforce.com/s/articleView?id=ai.agent_parent_deploy.htm&language=en_US&type=5).

## P

Parameter size

The number of parameters a model uses to process and generate data.

Prompt

A natural language description of the task to be accomplished. An input to the LLM.

Prompt design

Prompt design is the process of creating prompts that improve the quality and accuracy of a model’s responses.

Prompt engineering

An emerging discipline within AI focused on maximizing the performance and reliability of models by crafting prompts in a systematic and rigorous way.

Prompt injection

A method used to control or manipulate the model's output by giving it certain prompts. With this method, users and third parties attempt to get around restrictions and perform tasks that the model wasn't designed for.

Prompt resolution

The process of populating an LLM prompt at run time with additional information, such as values from structured data sources and knowledge retrieved from unstructured data sources. This process is sometimes referred to as dynamic grounding or hydrating a prompt. See [Prompt Template Run-time Execution](https://help.salesforce.com/s/articleView?id=ai.prompt_builder_runtime.htm&language=en_US&type=5).

Prompt template

A string with placeholders that are replaced with business data values to generate a final text instruction that is sent to the LLM.

## R

Reasoning engine, Atlas reasoning engine

Guides how an agent launches subagents and actions and generates responses during a conversation to accomplish a task for the user–in other words, how an agent reasons and takes action.

The Atlas reasoning engine is a graph-based reasoning engine. You can think of it like a flowchart with nodes, variables, and transitions, so agents follow specific, predictable paths. Unlike strictly prompt-based reasoning engines, Atlas separates an agent’s big-picture workflow from its conversational skills.

See [How Agents Work](https://help.salesforce.com/s/articleView?id=ai.agent_builder_reasoning_engine.htm&language=en_US&type=5).

Reference action

The Salesforce functionality that an agent action calls to get information or perform a task. For example, an agent action can call an API to retrieve data, a flow to update a record, a prompt template to generate a response, an Apex class to run custom business logic, or a predictive model to make a recommendation.

See [Create a Custom Action](https://help.salesforce.com/s/articleView?id=ai.agent_actions_custom.htm&language=en_US&type=5) to learn what reference action types are supported.

Retrieval-augmented generation (RAG)

A form of grounding that uses an information retrieval system like a knowledge base to enrich a prompt with relevant context, for inference or training.

See [Ground Agentforce in Your Data](https://help.salesforce.com/s/articleView?id=ai.agent_parent_data.htm&language=en_US&type=5).

Retriever

A logical layer between a search service and knowledge retrieval-powered solutions, such as [retrieval-augmented generation](https://help.salesforce.com/s/articleView?id=ai.copilot_glossary.htm&language=en_US&type=5#copilot_glossary__rag) (RAG) implementations. It defines the runtime search and retrieval configuration for an application, agent, prompt template, and other solution components. A retriever serves as a reusable, versioned, and packageable artifact that simplifies the setup of knowledge retrieval with search-based grounding for agents, data libraries, prompt templates, with Apex, or in Flow.

See [Retrieve Data](https://help.salesforce.com/s/articleView?id=data.c360_a_ai_retriever.htm&language=en_US&type=5).

## S

Search index

A Data 360 search index holds a collection of [content chunks](https://help.salesforce.com/s/articleView?id=ai.copilot_glossary.htm&language=en_US&type=5#copilot_glossary__chunking) and their respective [vector embeddings](https://help.salesforce.com/s/articleView?id=ai.copilot_glossary.htm&language=en_US&type=5#copilot_glossary__vector_embedding). The search index facilitates search for relevant vectors given a query vector. Depending on your data and query needs, you can create either a vector search index or a hybrid search index.

See [Use Search for AI, Automation, and Analytics](https://help.salesforce.com/s/articleView?id=data.c360_a_search_index_ground_ai.htm&language=en_US&type=5).

Semantic retrieval

A scenario that allows an LLM to use similar and relevant historical business data that exists in a customer's CRM data.

Subagent (fomerly known as topic)

A particular job an agent can do. A subagent contains actions, which are the tools available for the job, and instructions, which tell the agent how to make decisions. Collectively, the subagents assigned to your agent define the capabilities your agent can handle.

Subagents can be standard (Salesforce-provided) or custom. Standard subagents are available out of the box in the asset library or assigned to a new agent by default.

See [Subagents](https://help.salesforce.com/s/articleView?id=ai.agent_topics.htm&language=en_US&type=5).

Suggested actions (Lightning Experience only)

A set of three contextually relevant actions in the Agentforce conversation panel, based on the current page the user is viewing. These actions help users identify the most immediate step they can take to complete a task or learn more about a specific feature. Suggested actions consider page context only and are rules-based. The result of a suggested action is predefined, so it can differ from the result of entering a similar free text input in an agent conversation.

## T

Temperature

A parameter that controls how predictable and varied a model's outputs are. A model with a high temperature generates random and diverse responses. A model with a low temperature generates focused and more consistent responses.

Template, agent template

A blueprint for an individual agent designed for a particular use case. It contains subagents, actions, filters, variables, and system messages. When you create an agent from a template, you can choose which assets from the template to include.

An agent template is a child of an agent type. A type can be associated with many templates, but a template can only be associated with one type. For example, Agentforce Service Agent (ASA) is an agent type that connects to customer channels. To create an agent from a template of the ASA type, you need the required permissions for ASA and any permissions associated with the template.

See [Create an Agent](https://help.salesforce.com/s/articleView?id=ai.agent_setup_create.htm&language=en_US&type=5).

Token

To understand or generate text, a large language model (LLM) breaks the text into smaller units called tokens. A token can be as big as a single word or as small as a single character, depending on how the text is processed or generated.

Token size can affect agent billing and performance. In general, the greater the number of tokens in a prompt or response, the more complex the task and the slower the response of the LLM.

The maximum number of tokens that can be processed at a time is called a context window and varies by model. To learn more about context windows for supported models, see [_Agentforce Developer Guide_: Supported Models](https://developer.salesforce.com/docs/ai/agentforce/guide/supported-models.html#context-window).

Topic, agent topic

Topics are now called subagents. See [Subagent (fomerly known as topic)](https://help.salesforce.com/s/articleView?id=ai.copilot_glossary.htm&language=en_US&type=5#copilot_glossary__subagent).

Toxicity

Describes many types of discourse, including but not limited to offensive, unreasonable, disrespectful, unpleasant, harmful, abusive, or hateful language.

Trusted AI

Guidelines created by Salesforce that are focused on the responsible development and implementation of AI.

Type, agent type

A broad category of agents that share similar capabilities and constraints. A type controls permissions required to build or access an agent and the channels that an agent can be deployed to. For example, agents of the Agentforce Service Agent type can be deployed to customer channels, such as Enhanced Chat. Agents of the Agentforce Employee Agent type can be deployed to employee channels, such as Slack.

An agent type is a parent of an agent template. Each agent type is associated with a default template for that type (usually of the same name as the agent type), as well as other templates.

A type can be associated with many templates, but a template can only be associated with one type. For example, Agentforce Service Agent (ASA) is an agent type that connects to customer channels. To create an agent from a template of the ASA type, you need the required permissions for ASA and any permissions associated with the template.

See [Agent Types and Considerations](https://help.salesforce.com/s/articleView?id=ai.agent_setup_explore_types.htm&language=en_US&type=5).

## U

Unstructured data

Data that doesn’t have a specific, consistent format and can’t be easily stored in a typical relational database. Common forms of unstructured data include chat transcripts, audio files, websites, legal documents, and other large texts, such as books.

See [Unstructured Data in Data 360](https://help.salesforce.com/s/articleView?id=data.c360_a_unstructured_data_about.htm&language=en_US&type=5).

Usage type

Usage types are the different categories that classify how credits are consumed when using Agentforce and other generative AI features. Each usage type has its own multiplier rate as listed in the rate card that determines how many credits are charged per unit of use. You can track your org's usage of Agentforce features and the credit consumption in Digital Wallet.

See [Generative AI Usage and Billing](https://help.salesforce.com/s/articleView?id=ai.generative_ai_usage.htm&language=en_US&type=5) and [About Digital Wallet](https://help.salesforce.com/s/articleView?id=xcloud.wallet_about.htm&language=en_US&type=5).

User message, user utterance

Input from an end user to an agent, often a question or request. This can be free-text input entered into a chat UI or sent in an email, a selection from a predefined menu, or even voice input.

For agents that don’t directly interact with an end user, sometimes the admin or builder provides a string that’s treated as a user message in order to define the agent’s task.

## V

Variable

Stores contextual information about agent conversations. Variables can be used to personalize agent conversations, implement user verification, and ensure consistent agent behavior. Variables can be used in filters, instructions, and as input for actions.

Salesforce provides different types of variables. See [Agent Variables](https://help.salesforce.com/s/articleView?id=ai.agent_variables.htm&language=en_US&type=5).

Vector embedding

A numerical representation of [unstructured data](https://help.salesforce.com/s/articleView?id=ai.copilot_glossary.htm&language=en_US&type=5#copilot_glossary__unstructured_data) that machines can read. Vector embeddings measure the semantic similarity of different pieces of text, enabling accurate and relevant search results for generative AI prompts.

See [Vector Search](https://help.salesforce.com/s/articleView?id=data.c360_a_search_index_vector_index.htm&language=en_US&type=5).





<!--stackedit_data:
eyJoaXN0b3J5IjpbMzM4MjcyNjg5XX0=
-->