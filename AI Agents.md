
# Explain how an agent works and its basic building blocks of agent script.

  

## Introduction

Agentforce agents use natural language, reasoning, business logic, and actions to help users complete tasks. When a user sends a request, the agent interprets the request, determines the most relevant subagent, evaluates available instructions and actions, runs the required actions, and generates a response. Agent Script defines this behavior in Agentforce Builder. It combines prompt instructions, which guide the LLM, with logic instructions, which execute deterministic rules such as conditions, variable updates, action calls, and transitions. This structure lets agents remain conversational while still following predictable business processes. Builders can work with Agent Script visually in Canvas View or directly in Script View, depending on how much control they need.

  

## Agent Execution and Agent Script Flow

An Agentforce agent uses Agent Script to turn a user request into a controlled sequence of reasoning, action execution, and response generation.

### User Request

The user asks a question or makes a request through a connected channel.

### Subagent Selection

The agent selects the best subagent based on the request, context, and available instructions.

### Agent Script Processing

The agent evaluates logic instructions and prompt instructions defined in Agent Script.

### Actions and Variables

Actions retrieve, update, or process data, while variables store state and action outputs for later use.

### LLM Reasoning

The LLM handles interpretation, ambiguity, and natural language generation where prompt instructions are used.

### Response

The agent returns an answer, asks a follow-up question, executes another action, or transitions to another subagent.

## How an Agent Works

### Agent Request Processing

Agentforce agents process user requests by combining intent interpretation, subagent selection, action execution, and response generation.

#### USER REQUEST

The agent interprets the user’s request and determines the best subagent or path for handling it.

#### PROCESSING

The agent evaluates instructions, runs actions when needed, and generates a response that continues or completes the conversation.

  

### Reasoning and Execution

Agentforce separates parts of the workflow that need LLM reasoning from parts that should execute as predictable logic

#### LLM REASONING

LLM reasoning is used for language understanding, ambiguity handling, summarization, and response generation.

#### DETERMINISTIC EXECUTION

Deterministic execution is used for business rules, action sequencing, variable updates, and conditional routing.

  

### Subagents and Actions

Subagents organize the agent’s responsibilities, while actions allow the agent to complete work.

#### SUBAGENTS

Subagents focus the agent’s behavior around a specific responsibility, such as billing, orders, returns, or escalation.

#### ACTIONS

Actions allow the agent to retrieve data, update records, call Flow or Apex, invoke prompt templates, or interact with external systems.

  
## Agent Script Building Blocks

### Agent Script

Agent Script is the language used in Agentforce Builder to define how an agent behaves.

#### AGENT BEHAVIOR

Agent Script defines the instructions, variables, actions, transitions, and business logic that control an agent’s behavior.

#### AUTHORING VIEWS

Canvas View and Script View provide different ways to create and editthe same underlying Agent Script.

  

### Instructions

Agent Script uses different instruction types to separate deterministic logic from LLM-based reasoning.

#### LOGIC INSTRUCTIONS

Logic instructions define deterministic rules for conditions, branching, variable updates, action execution, and routing.

#### PROMPT INSTRUCTIONS

Prompt instructions provide natural language guidance that the LLM interprets during reasoning and response generation.

  

### Variables and References

Variables and references help Agent Script store state and connect instructions to resources.

#### VARIABLES

Variables store values such as user inputs, action outputs, verification status, selected records, or workflow progress.

#### RESOURCE REFERENCES

Resource references connect script logic with actions, subagents, variables, outputs, and other agent resources.

### Conditions and Transitions

Conditions and transitions help agents follow controlled paths instead of relying only on conversational memory.

#### CONDITIONAL LOGIC

Conditional logic determines which path, prompt, or action should be used based on known values or business rules.

#### TRANSITIONS

Transitions move the conversation from one subagent to another when the user’s request changes or a task is complete.

 
### Execution and Debugging

Agent Script helps builders understand, test, and troubleshoot how an agent behaves at runtime.

#### RUNTIME EXECUTION

Runtime execution follows the compiled Agent Script structure while invoking LLM reasoning only where needed.

#### TROUBLESHOOTING

Canvas View, Script View, and preview tools help inspect subagent selection, action execution, variables, and responses.

## References:
[Get Started with Agent Script](https://developer.salesforce.com/docs/ai/agentforce/guide/agent-script.html)
[Agent Script Language Characteristics](https://developer.salesforce.com/docs/ai/agentforce/guide/ascript-lang.html)
[Agent Script Blocks](https://developer.salesforce.com/docs/ai/agentforce/guide/ascript-blocks.html)
[Agent Script Flow of Control](https://developer.salesforce.com/docs/ai/agentforce/guide/ascript-flow.html)


# Explain the components and benefits of hybrid reasoning, including how Agent Script functions in Canvas and Script View.

## Introduction
Hybrid reasoning allows Agentforce agents to combine the flexibility of large language models with the predictability of structured business logic. In Salesforce, this capability is powered by Agent Script and the Atlas Reasoning Engine. Agent Script defines an agent’s behavior using both natural language prompt instructions and deterministic logic instructions. Canvas View gives builders a visual, document-style way to configure agents, while Script View gives advanced users direct access to the underlying Agent Script. Together, these tools help teams design agents that can interpret user requests, follow business rules, run actions in controlled sequences, transition between subagents, and maintain reliable context throughout a conversation.

### Hybrid Reasoning
Hybrid reasoning balances AI flexibility with enterprise workflow rigor, enabling agents to be both conversational and predictable.
### Agent Script
Agent Script defines an agent’s configuration, business logic, prompting, actions, variables, and transitions.
### Canvas View
Canvas View presents Agent Script as understandable blocks and provides shortcuts that help builders configure agents without directly writing code.
### Script View
Script View exposes the underlying Agent Script so advanced users can make precise edits and inspect how the agent is defined. 
### Design Considerations
There are several design considerations related to Hybrid Reasoning and Agent Script, such as the choice between deterministic logic and LLM reasoning.



## Hybrid Reasoning
Hybrid reasoning balances AI flexibility with enterprise workflow rigor so agents can be both conversational and predictable.
### HYBRID REASONING
Hybrid reasoning separates the parts of an agent that require deterministic control from the parts that benefit from LLM interpretation.
### LLM REASONING
LLM reasoning handles interpretation, judgment, ambiguity, and natural language generation. 
### DETERMINISTIC LOGIC
Deterministic logic handles business rules, conditions, action sequencing, and controlled transitions.

### Benefits of Hybrid Reasoning
Hybrid reasoning improves reliability by making the boundary between probabilistic reasoning and fixed execution explicit.
#### WORKFLOWS
Hybrid reasoning helps agents follow strict, sequential workflows for tasks such as refunds, identity checks, and approvals.
#### LLM CALLS
It improves control, auditability, latency management, and reliability by limiting LLM calls to the places where reasoning is needed.

### Hybrid Reasoning Execution Pipeline
Agentforce uses a three-stage pipeline that turns human-readable agent instructions into an executable plan for the reasoning engine.
#### Authoring Layer
Agent Script in Canvas View or Script View 
#### Compilation Layer
Agent Script is compiled into an Agent Graph 
#### Runtime Execution Layer
Atlas Reasoning Engine executes logic or invokes the LLM

### Atlas Reasoning Engine
The Atlas Reasoning Engine executes the compiled Agent Graph and determines when to run deterministic logic or invoke the LLM.
#### LLM INVOCATION
Nodes with prompt instructions trigger LLM reasoning for interpretation or natural language response generation.
#### DETERMINISTIC LOGIC
Logic-only nodes can execute deterministically without sending instructions to the LLM.

## Agent Script Fundamentals
### Agent Script
Agent Script is a language with elements of both declarative and procedural languages that defines an agent’s configuration, business logic, prompting, actions, variables, and transitions.
#### INSTRUCTIONS
Agent Script combines natural language instructions with programmatic expressions, which help build predictable, context-aware workflows that don’t rely only on LLM interpretation. 
#### DETERMINISTIC LOGIC
Deterministic logic instructions represent conditions and action sequences that are executed as code without LLM involvement.
#### NATURAL LANGUAGE
Prompt instructions represent natural language guidance interpreted by the LLM at runtime.

### Logic Instructions and Prompt Instructions
Agent Script uses different instruction types to separate deterministic execution from LLM-based reasoning.
#### LOGIC INSTRUCTIONS
Logic instructions run deterministically and are used for rules, branching, variables, and action execution. The agent follows a fixed sequence every time certain conditions are met regardless of how the user phrases their input. 
#### PROMPT INSTRUCTIONS
Prompt instructions are natural language instructions that the LLM interprets at runtime. They handle everything that requires judgment, interpretation, or natural language generation.

### Agent Script Blocks and Resources
Agent Script is organized into blocks and can reference resources such as subagents, actions, variables, and outputs.
#### SCRIPT BLOCKS
Script blocks describe agent configuration, system messages, subagent behavior, actions, and routing.
#### RESOURCES
Resources can be referenced with @, such as @actions, @subagent, @variables, and @outputs.

### Variables, Actions, and Transitions
Agent Script gives builders deterministic ways to store state, run actions, and control movement between subagents.
#### VARIABLES
Variables help agents remember information, track progress, and maintain context across conversation turns.
#### ACTIONS & TRANSITIONS
Actions can be run with defined inputs and outputs, while transition scan route the conversation to another subagent

### Agent Script
Agent Script can be used to build predictable, context-aware workflows using natural language instructions and programmatic expressions. Agent Script combines deterministic logic with prompt instructions.

Agent Script consists of deterministic logic code that can reference resources such as subagents, actions, variables, and outputs. Resources can be referenced with @, such as @actions, @subagent, @variables, and @outputs.

## Canvas View and Script View
### Canvas View
Canvas View presents Agent Script as understandable blocks and provides shortcuts that help builders configure agents without directly writing code.
#### BLOCKS
Canvas View summarizes Agent Script into easily understandable blocks that can be expanded to view the underlying script. The agent can be edited with the help of quick action shortcuts. 
#### SHORTCUTS
Builders can use / to add common expressions, such as if/else conditions. They can use @ to add resources such as subagents, actions, and variables.

### Canvas View
Canvas View can be used to configure agents without writing code. Canvas View comprises easily understandable blocks that can be expanded to view the underlying script.

### Script View
Script View exposes the underlying Agent Script so advanced users can make precise edits and inspect how the agent is defined. Canvas View comprises easily understandable blocks that can be expanded to view the underlying script.

Script View shows the underlying script and can be used to configure agents by making precise edits. Script View can be used for direct script editing with aids such as syntax highlighting, autocompletion, and validation
#### EDITING
Script View supports direct script editing with aids such as syntax highlighting, autocompletion, and validation.
#### BENEFITS
Script View is useful for precise control, troubleshooting, reuse, and developer-focused changes. 
#### CONSISTENCY
Canvas View and Script View represent the same agent configuration, so changes remain consistent across both experiences
## Design Considerations
### Logic vs LLM Reasoning
The most important design choice is deciding what should run as fixed logic and what should be left to LLM reasoning.
#### DETERMINISTIC LOGIC
Deterministic logic should be used for decisions that can be expressed as code, such as eligibility checks, required steps, or action order. 
#### LLM REASONING
LLM reasoning should be used for interpretation, summarization, ambiguity handling, and natural language generation.

### Reliability and Context
Agent Script strengthens reliability by letting the agent store and evaluate state instead of relying only on conversational memory. 
#### VARIABLES
Variables can store information across turns, such as verification status, selected product, or workflow progress.
#### CONDITIONS
Conditional expressions can control what the agent says, which action runs, or when the agent transitions to another subagent.

### Testing and Debugging
Agentforce Builder helps preview agent behavior and inspect how the agent processes requests.
#### PREVIEW
Preview tools can show how the agent reasons through a user request and executes actions.
#### DIAGNOSIS
Script View can help diagnose validation errors and make fast, precise corrections.

### Terminology Considerations
#### NOTES
1. Salesforce documentation is transitioning from topics to subagents, but the underlying functionality is unchanged. Older materials and UI labels may still refer to topics. 
2. Newer Agent Script documentation commonly uses subagents to describe the same functional layer.

## References:
[Get Started with Agent Script](https://developer.salesforce.com/docs/ai/agentforce/guide/agent-script.html)
[Hybrid Reasoning with New Agentforce Builder and Agent Script](https://architect.salesforce.com/docs/architect/fundamentals/guide/hybrid-reasoning-agentforce-builder-agent-script?utm_source=chatgpt.com)
[Agent Script Language Characteristics](https://developer.salesforce.com/docs/ai/agentforce/guide/ascript-lang.html?utm_source=chatgpt.com)
[Agent Script Blocks](https://developer.salesforce.com/docs/ai/agentforce/guide/ascript-blocks.html?utm_source=chatgpt.com)
[Agent Script Variables](https://developer.salesforce.com/docs/ai/agentforce/guide/ascript-ref-variables.html?utm_source=chatgpt.com)
[Build With Confidence: Inside the New Agentforce Builder](https://admin.salesforce.com/blog/2026/build-with-confidence-inside-the-new-agentforce-builder?utm_source=chatgpt.com)

# Given a use case, manage deterministic behavior for the agent using mechanisms like filters, variables, and template expressions.
## Introduction
Agentforce agents use LLM reasoning, but deterministic behavior is needed when business rules must be applied consistently. Variables, filters, and template expressions help control how an agent selects subagents, runs actions, stores state, and generates responses. Variables can store session state, user inputs, action outputs, and values needed by later actions. Filters can limit which subagents or actions are available when specific conditions are met. Template expressions can insert variable values, evaluate conditions, and customize prompt text before the LLM responds. Together, these mechanisms reduce reliance on prompt wording alone and help the agent follow required business processes more predictably.
### Variables
Variables store values such as user inputs, action outputs, verification status, selected records, or workflow progress.
### Filters
Filters make subagents or actions available only when specific variable-based conditions are met. 
### Template Expressions
Template expressions insert values, calculations, or conditional text into prompt instructions at runtime.
### Actions
Actions can use variables as inputs and store outputs in variables for later deterministic checks.
### Instructions
Instructions can reference variables and template expressions so the LLM receives only the relevant context.
### Deterministic Behavior
Deterministic controls reduce reliance on LLM interpretation alone.

## Agent Variables, Filters & Template Expressions
### Variables
Variables and filters can be used within Agentforce to ensure deterministic logic, protect private data, and streamline agent orchestration.
#### VARIABLES
Variables store and reuse values that help an agent reason, make decisions, pass data to actions, and maintain state across turns or subagents. These include Custom Variables and Messaging Session Variables.
####  SYSTEM VARIABLES
Predefined, prepopulated system variables can be accessed using @system_variables.<variable_name>. For example, @system_variables.user_input can be used to access the customer’s most recent utterance.

### Custom Variables
Variables and filters can be used within Agentforce to ensure deterministic logic, protect private data, and streamline agent orchestration.
#### CUSTOM VARIABLES
Custom variables store values created or updated during a conversation, such as troubleshooting steps, verification status, selected products, or user preferences. 
#### USING VARIABLES
Variables can be used as action inputs, mapped from action outputs, referenced in instructions, evaluated by filters, passed through Agent API, and used in template expressions.

### Variable Format
Variables and filters can be used within Agentforce to ensure deterministic logic, protect private data, and streamline agent orchestration.
#### LEGACY
In legacy builder instructions, variables use syntax such as {!$Context.VariableAPIName} or {!VariableAPIName}.
#### AGENT SCRIPT
 In Agent Script, variables are referenced as @variables.variable_name and inserted into prompt text with {!@variables.variable_name}.

### Variable Format Examples
Variables and filters can be used within Agentforce to ensure deterministic logic, protect private data, and streamline agent orchestration.

#### MESSAGING SESSION VARIABLE
A messaging session variable can personalize responses with session information, such as: “Always respond in @MessagingSession.EndUserLanguage when this value is available.”
#### CUSTOM VARIABLE
A custom variable can guide later instructions, such as: “Use these troubleshooting steps when helping the customer: {!@variables.TroubleshootingSteps}.”

### Creating and Using Custom Variables
Variables and filters can be used within Agentforce to ensure deterministic logic, protect private data, and streamline agent orchestration.

#### CREATING CUSTOM VARIABLES
Custom variables can be created in Agentforce Builder from the Variables section. In legacy builder experiences, variables are created from the Context panel.
#### USING VARIABLES
A variable can be mapped to an action input or populated from an action output so later actions, filters, and instructions can reuse the same value.

### Filters
Variables and filters can be used within Agentforce to ensure deterministic logic, protect private data, and streamline agent orchestration.
#### FILTER
Filters can be created for subagents and actions so the agent can use them only when specific variable-based conditions are met.
#### FILTER EXAMPLE
Filters can require authentication, verification, case status, order eligibility, or other required conditions before an agent can use a sensitive subagent or action.

### Creating Filters
Variables and filters can be used within Agentforce to ensure deterministic logic, protect private data, and streamline agent orchestration.
#### LEGACY BUILDER
In the legacy builder, filters are created from the Filters tab of the Context panel. A filter can include one or more conditions based on context, conversation, or custom variables. 
#### AGENT SCRIPT
In Agent Script, available when is used to control which subagents or actions are available to the LLM. A filter can applied to one or more subagents or actions.
### Template Expressions
Template expressions make prompt instructions dynamic by inserting variables, calculations, and conditional content before the LLM responds.
#### DYNAMIC VALUES
Template expressions use the {!expression} syntax to insert variable values into prompt text so the LLM receives concrete context instead of variable names.
#### RUNTIME LOGIC
Template expressions can include conditions, comparisons, and simple calculations to customize prompt content at runtime.

### Conditionals and Available Logic
Conditional expressions help make agent behavior deterministic because they are evaluated before the prompt reaches the LLM.
#### CONDITIONAL EXPRESSIONS
Conditional expressions determine which instructions are included, which actions run, or which subagent transitions are allowed.
#### AVAILABILITY CONTROLS
Availability conditions can make actions, subagents, or prompts available only when variable values meet defined criteria

### Custom Variables
Custom variables can be created in Agentforce Builder and used to store conversation state, action outputs, and values needed for filters, instructions, or later action inputs.
![Create Custom Variable](https://raw.githubusercontent.com/jefrainmx/Agentforce-Specialist-Certification/refs/heads/main/images/Screenshot%202026-09-22%20120850.png)

###  Using Variables
Variables can be referenced in instructions, mapped to action inputs, populated from action outputs, and inserted into Agent Script prompt text with {!@variables.variable_name}.
![Using variable](https://raw.githubusercontent.com/jefrainmx/Agentforce-Specialist-Certification/refs/heads/main/images/Screenshot%202026-09-22%20120927.png)

### Using Filters
Filters can be created to control when a subagent or action is available based on variable conditions.
![Using filter](https://raw.githubusercontent.com/jefrainmx/Agentforce-Specialist-Certification/refs/heads/main/images/Screenshot%202026-09-22%20120950.png)

### Using Conditionals
Conditionals are used to deterministically control agent behavior based on variable values.
![Using conditionals](https://raw.githubusercontent.com/jefrainmx/Agentforce-Specialist-Certification/refs/heads/main/images/Screenshot%202026-09-22%20121009.png)

## Scenarios & Solutions
### Scenario 1
Cosmic Retail uses an Agentforce Employee agent to help its warehouse team manage order fulfillment. The company wants to ensure that only orders marked as ‘Ready for Dispatch’ can trigger the ‘Generate Shipping Label’ action. Orders still in processing or awaiting payment should be excluded to avoid errors and unnecessary label generation. The Agentforce Specialist must configure the agent to apply this condition deterministically
### Solution 1
The Agentforce Specialist should store the order status in a custom variable, such as OrderStatus, by mapping it from the current record context or from an action output that retrieves the order. Then, a filter should be applied to the Generate Shipping Label action so the action is available only when OrderStatus = "Ready for Dispatch". This deterministic rule would prevent the agent from generating shipping labels for orders that are still processing, awaiting payment, or otherwise ineligible.

### Scenario 2
Cosmic Hospitality uses an Agentforce Service agent on its Experience Cloud site to help guests with booking issues. Leadership wants a deterministic rule: chats marked ‘Critical’ (for example, payment failure or account lockout) must be routed immediately to a human, while all other chats should create a support case and continue with guided self-service. The Agentforce Specialist must ensure the agent enforces this rule without relying on prompt wording
### Solution 2
The Agentforce Specialist should create a custom field (for example, SessionPriority__c) on the Messaging Session object and add it as a Messaging Session Variable to the agent. Then apply conditionalfiltersto the actions so that Route to Live Agent runs only when SessionPriority = "Critical", and Create Support Case runs only when SessionPriority <> "Critical". This approach would make the actions available only when the session meets the required condition, ensuring deterministic behavior and preventing unpredictable LLM decisions.

### Scenario 3
Cosmic Adventures uses an Agentforce agent to help customers plan guided tours. During chats, travelers often share their language preference and mobility assistance requirements, which are needed throughout the booking process. However, the company noticed that the agent forgets these details when customers switch subagents or return later in the same session. The Agentforce Specialist must ensure these preferences persist reliably across the entire interaction.
### Solution 3
The Agentforce Specialist should define custom variables, such as PreferredLanguage and MobilityAssistance, and map them to the outputs of an action that captures traveler preferences. These variables can then be reused as inputs to later actions and referenced in subagent instructions so the agent consistently honors the same language and assistance requirements across subagents during a single session, without repeatedly asking for the same details.

### Scenario 4
Cosmic Financial runs multiple Salesforce orgs. A KYC Verification agent in the Auth org verifies a customer and must hand the verified Customer GUID to a downstream Account Servicing agent in another org to perform updates. The identifier must be immutable, hidden from the LLM, and persist across the handoff.
### Solution 4
The Agentforce Specialist should use the Agent API to start the downstream agent’s session and pass the verified Customer GUID as a read-only messaging session variable to the Account Servicing agent. This approach would keep the GUID secure and unaltered by the LLM, while ensuring a reliable, deterministic handoff across agents and orgs.

### Scenario 5
Cosmic Retail uses an Agentforce agent to help loyalty members place orders. The agent stores CustomerName, MembershipTier, CartTotal, and CreditLimit in variables during the session. Leadership wants the agent to greet members personally, mention VIP benefits only for Platinum members, and warn the customer when the cart total exceeds the credit limit. The Specialist must make the response behavior consistent without relying only on natural-language instructions.
### Solution 5
The Agentforce Specialist should use template expressions and conditional logic in Agent Script instructions. Template expressions such as {!@variables.CustomerName} can personalize the response with stored variable values, while conditional expressions can include VIP benefit text only when MembershipTier = "Platinum" and include a warning only when CartTotal > CreditLimit. This approach would make the prompt content dynamic and deterministic because only the relevant instruction text would be assembled before the response of the LLM.

References:
[Variables](https://help.salesforce.com/s/articleView?id=ai.agent_parent_variables.htm&language=en_US)
[Create Variables in Agentforce Builder](https://help.salesforce.com/s/articleView?id=ai.agent_builder_variables_create.htm&language=en_US&type=5)
[Create a Filter to Control Access to Subagents and Actions in the Legacy Builder](https://help.salesforce.com/s/articleView?id=ai.agent_asset_filters.htm&type=5)
[Example: Improve Your Agent's Memory with Filters and Variables](https://help.salesforce.com/s/articleView?id=ai.agent_custom_variables_filters_example.htm&type=5)
[Agent Script Reference: Variables (Custom and Linked)](https://developer.salesforce.com/docs/ai/agentforce/guide/ascript-ref-variables.html)
[Agent Script Reference: Conditional Expressions](https://developer.salesforce.com/docs/ai/agentforce/guide/ascript-ref-expressions.html)
[Agent Script Language Characteristics](https://developer.salesforce.com/docs/ai/agentforce/guide/ascript-lang.html)

# Given a scenario, select and configure standard topics, custom topics, standard Agent actions, and custom Agent actions.
## Introduction
Agentforce agents use subagents and actions to understand what a user wants and determine what work the agent can perform. A subagent represents a particular job the agent can do, such as answering questions, managing orders, verifying identity, or creating a case. Each subagent includes instructions and assigned actions that guide how the agent should behave.Actions are the tools an agent uses to retrieve information, call automation, generate content, update data, or complete tasks. Salesforce provides standard subagents and standard actions for common use cases, and custom subagents and custom actions can be created for business-specific requirements. When selecting or configuring these assets, an Agentforce Specialist should consider the agent type, required permissions, data access, channel, and whether a standard asset already meets the requirement.

### Subagents
A subagent is a job an agent can perform, and the subagents assigned to an agent define the agent’s overall capabilities.
### Standard Subagents
Standard subagents provide prebuilt starting points for common business use cases and can be added from the Agentforce Asset Library.
### Custom Subagents
Custom subagents are created when a business requirement needs its own scope, instructions, and action set
### Actions
Actions are tools a subagent can use to get information, call automation, update data, or complete tasks.
### Standard Actions
Standard actions are Salesforce-provided actions, and availability can vary by product, license, permission, and agent type.
### Custom Actions
Custom actions can call supported functionality such as autolaunched flows, Apex, external services, MuleSoft APIs, or prompt templates.

## Subagents and Actions
### Agent Actions
Actions give a subagent the tools it needs to retrieve information or perform tasks.
#### STANDARD ACTIONS
Standard actions are Salesforce-provided actions that support common agent capabilities, but availability can vary by license, permission, cloud, and agent type. 
#### CUSTOM ACTIONS
Custom actions extend an agent with business-specific capabilities by referencing supported Salesforce functionality such as Flow, Apex, APIs, MuleSoft APIs, or prompt templates.

### Action Assignment and Management
Actions must be assigned to subagents before the agent can use them.
#### ACTION ASSIGNMENT
A subagent can use only the actions assigned to it, and each imported action becomes an independent copy for that subagent.
#### ACTION MANAGEMENT
Actions can be reviewed in the Agentforce Asset Library and assigned or configured in Agentforce Builder.

### Managing Agent Actions
Actions assigned to a subagent can be managed in Agentforce Builder. Available standard, managed, and custom actions can be reviewed in the Agentforce Asset Library.
![enter image description here](https://raw.githubusercontent.com/jefrainmx/Agentforce-Specialist-Certification/refs/heads/main/images/Screenshot%202026-09-22%20121105.png)

### Creating Custom Actions
Custom actions can be created from the Asset Library for reuse or from inside an agent for a single agent version. 
#### REUSABLE CUSTOM ACTIONS
A custom action created in the Agentforce Asset Library is available to add to multiple agents, versions, and subagents.
####  AGENT-SPECIFIC CUSTOM ACTIONS
A custom action created inside an agent in Agentforce Builder is available only to that agent version.

### Creating a Custom Action
A custom action can be created from the Agentforce Asset Library or from within an agent in Agentforce Builder. The custom action references underlying Salesforce functionality, such as an autolaunched flow, invocable Apex, ApexREST, external service, MuleSoft API, or prompt template.
![Create Custom Action](https://raw.githubusercontent.com/jefrainmx/Agentforce-Specialist-Certification/refs/heads/main/images/Screenshot%202026-09-22%20121137.png)

### Action Instructions
Action instructions help the agent understand when and how to use an action.
#### ACTION INSTRUCTIONS
Action instructions describe what the action does, when the agent should use it, how required inputs are collected, and how outputs should be handled.
#### INSTRUCTION QUALITY
Strong instructions include clear use conditions, required inputs, expected outputs, dependencies, and examples of when the action should or should not run.

### Action Inputs
Action inputs control what data the agent needs before it can run an action.
#### REQUIRED INPUTS
A required input must have a value before the action can execute, and inputs required by the underlying reference action remain required.
#### COLLECT DATA FROM USER
Collect data from user should be enabled when the agent must ask the user for a missing input value during the conversation.

### Action Outputs
Action outputs determine what information is available after the action runs. 
#### FILTER OUTPUTS
Filtered outputs are excluded from the agent action when they should not be used by the agent. 
#### SHOW IN CONVERSATION
Outputs marked to show in conversation can be used in the agent’s response to the user.

### Custom Action Instructions
Custom action instructions define the action’s purpose, when it should run, how the agent should collect inputs, and how outputs should be used in the conversation.
![Custom Action Instructions](https://raw.githubusercontent.com/jefrainmx/Agentforce-Specialist-Certification/refs/heads/main/images/Screenshot%202026-09-22%20121221.png)

### Testing Agent Actions
Agentforce Builder can be used to test whether the agent selects the correct subagent and action. 
#### CONVERSATION PREVIEW
Conversation Preview helps confirm that realistic user utterances route to the correct subagent and trigger the expected action.
#### AGENT SCOPE
An agent can perform a task only when the required action is assigned and the running user or agent user has the required access.

### Subagents
A subagent represents a job an agent can do. It defines the capabilities an agent can handle. Subagents help define an agent’s range of capabilities, classify user requests, determine the scope of work, make decisions, and perform actions.Each subagent contains instructions and actions. Standard subagents can be added from the Agentforce Asset Library to support common use cases, and custom subagents can be created when the business needs a purpose-built job. Salesforce documentation now uses subagents instead of topics, although older UI labels and screenshots may still show “topics” during the transition.

### Subagent Details
A subagent includes a name, description, reasoning instructions, reasoning actions, and agent actions. These define when the subagent should be used and how it should handle the user’s request.

### Managing Subagents
Standard or custom subagents can be added to an agent from the Agentforce Asset Library. Standard subagents are available in the Agentforce Asset Library and provide prebuilt starting points for common use cases. Availability can vary by edition, cloud, license, permission, and agent type.

### Standard Actions
Some standard actions available for Agentforce agents include the following. Availability varies by edition, license, permission, cloud, and agent type.

ACTION | DESCRIPTION | EXAMPLE
------------------------- | -------------------------------------------------- | -------------------------------
Answer Questions with Knowledge | This action answers user questions using relevant content from the configured Agentforce Data Library, such as Knowledge articles and uploaded files. | Examples of utterances:1)What is the warranty period for this product?2)How do I reset my device?
Create Close Plan | This action generates a sales close plan to help a sales rep work toward an opportunity’s target close date. | Examples of utterances:1)Create a close plan for this opportunity.2)How should I move this deal forward?
Draft or Revise Email | This action creates or revises an email draft based on the user’s request and available email types. The draft includes a recipient, subject, and body. | Examples of utterances:1)Draft a follow-up email for this prospect.2)Make this email more formal.
Find Similar Opportunities | This action finds opportunities similar to a specified opportunity and explains why the opportunities are similar. | Examples of utterances:1)Find deals like this one. 2)How did we win similar opportunities?
Query Records | This action retrieves records that match the user’s request and can help the agent answer questions about Salesforce data.| Examples of utterances:1)Show my open cases.2)Find accounts in healthcare.
Summarize Record | This action generates a summary of a record using the prompt template associated with that record’s object type.|Examples of utterances:1)Summarize this account.2)Summarize this case.


## Scenarios & Solutions
### Scenario 1
An Agentforce Specialist at Cosmic Software Solutions is building a custom agent that answers questions based on Knowledge articles about the services offered by the company. They need to assign a standard subagent to the agent for this use case.
### Solution 1
The Agentforce Specialist can assign the standard subagent called General FAQ. It includes the Answer Questions with Knowledge standard action, which helps answer questions by searching through available Knowledge articles and providing information from those articles.

### Scenario 2
The sales reps at Cosmic Electronics frequently send follow-up emails to prospects and existing customers. They currently spend a significant amount of time manually crafting these emails to align with prior successful communications. The company wants to streamline this process using an AI-driven solution that suggests well-structured email drafts based on historical interactions.
### Solution 2
The Draft or Revise Email standard agent action can be assigned to an agent for the given use case. It allows users to create or revise a draft of an email to a recipient based on the user's request and available email types. An email draft includes a recipient, subject, and body. It can be sent through the Salesforce email composer or copied to another email client.

### Scenario 3
The Agentforce Specialist at Cosmic Software Solutions has built an Agentforce Employee agent for the company’s sales reps. The sales director wants to ensure that they can identify similar opportunities by entering utterances like this: "How did we win deals like this one in the past?"
### Solution 3
The Agentforce Specialist can assign the standard agent action called Find Similar Opportunities to the Agentforce Employee agent. When a sales rep enters an utterance like "How did we win deals like this one in the past?". This action allows users to find opportunities with similar characteristics. It searches for and returns a list of opportunities that are similar to, but not duplicates of, a specified opportunity.

### Scenario 4
Cosmic Innovation wants to enable its support reps to query an order's current shipment status using natural language in a custom Agentforce agent. An existing auto-launched flow retrieves this data from a third-party system that handles shipping details.
### Solution 4
A custom agent action can be created and assigned to the agent to meet the requirement. It can launch the existing auto-launched flow, enabling the company's support reps to query the shipment status using natural language.

## References:
[Agentforce Glossary of Terms](https://help.salesforce.com/s/articleView?id=ai.copilot_glossary.htm&type=5)
[Subagents](https://help.salesforce.com/s/articleView?id=ai.agent_topics_parent.htm&type=5)
[Agent Actions](https://help.salesforce.com/s/articleView?id=ai.copilot_actions.htm&type=5)

# Explain the process for connecting agents to various channels such as digital experience, email, voice, and Slack.
## Introduction
Agentforce agents can be deployed to multiple channels so customers and employees can interact with agents where they already work. A connection defines the channel-specific settings, instructions, adaptive response formats, and routing behavior that allow an agent to respond appropriately in that channel. Service Agents can be connected to customer-facing channels such as Messaging for In-App and Web, Email, and Voice, while Employee Agents can be made available in workforce channels such as Lightning Experience, the Salesforce mobile app, and Slack.Channel setup varies by destination. Digital experience deployments use Messaging, Embedded Service Deployment, and Omni-Channel flows. Email deployments use Email-to-Case, email templates, routing, and an Email Configuration. Voice deployments use a telephony connection, voice settings, and routing to the Service Agent. Slack deployments require a Salesforce-Slack connection, an Agentforce connection, installation in Slack, and user access management.

### Connecting Agents to Channels
#### Connection
A connection contains the channel-specific settings that let an agent operate in a supported channel, including instructions, adaptive response formats, and routing configuration.
#### Email, Messaging & Voice
Service Agents can be connected to customer channels such as Messaging for In-App and Web, Email, and Voice by configuring the required channel setup and routing.
#### Adaptive Responsive Formats
Adaptive response formats help the agent structure responses for the channel, such as text, links, buttons, images, or other supported message formats.
#### Slack Connection
Slack connections require Salesforce and Slack to be connected, an agent connection to be added in Agentforce Builder, and the agent to be installed and managed in Slack.

### Connecting a Service Agent to a Customer Channel
#### Omni-Channel Flows
Omni-Channel flows route conversations to and from a Service Agent. Inbound flows route work to the agent, while outbound flows transfer work to another destination.
#### Email Configuration
An Email Configuration connects Agentforce Service Agent on Email to the required email template, routing, and email channel setup.
#### Telephony Connection
A telephony connection connects voice calls to an Agentforce Service Agent and supports voice-specific routing and transfer behavior. 
#### Embedded Service Deployment
An Embedded Service Deployment exposes Messaging for In-App and Web on a website or Experience Cloud site.
#### Messaging Channel
A Messaging channel handles customer messages from channels such as Messaging for In-App and Web and routes them through Omni-Channel.

## Connecting Agents to Channels
An Agentforceagent can be deployed to multiple supported channels.
### Connecting Agents to Channels
#### CONNECTION
A connection includes the settings that help an agent connect to a channel. These settings can include instructions, adaptive response formats, and Omni-Channel flows.
#### CHANNEL-SPECIFIC BEHAVIOR
A connection helps the agent adapt its reasoning and response format for the channel where the user is interacting, such as Messaging, Email, Slack, or Voice.
#### INSTRUCTIONS & FORMATS
Connection settings can include behind-the-scenes instructions and adaptive response formats that help the agent reason and respond appropriately for each channel.
#### CHANNEL
Channels are the platforms and interfaces where users interact with agents, such as Lightning Experience, Salesforce mobile, Slack, Messaging, Email, and Voice.
#### OMNI-CHANNEL FLOWS
Inbound Omni-Channel flows route conversations from a channel to an agent. Outbound Omni-Channel flows route conversations from an agentto a queue, service rep, or another destination.
#### ESCALATION
When a conversation becomes complex or sensitive, the agent can use the Escalation subagent to transfer the conversation through an outbound Omni-Channel flow.
#### SETUP
A channel connection can be added in Agentforce Builder from the Connections area. Additional setup depends on the channel, such as Messaging, Email, Voice, or Slack configuration.
#### LIGHTNING EXPERIENCE & MOBILE
An Agentforce Employee Agent can be made available in Lightning Experience and the Salesforce mobile app by activating the agent and ensuring users have the required access.

### Connecting an Agent to Slack
The diagram below illustrates how an Agentforce Employee agent can be connected to Slack.

![Connecting an Agent to Slack](https://raw.githubusercontent.com/jefrainmx/Agentforce-Specialist-Certification/98091e55c3501e05fab28c960f30ce521b03c12e/images/Screenshot%202026-09-22%20113402.png)

### Connecting an Agent to Email
The diagram below illustrates how an Agentforce Service agent can be connected to Email, allowing it to autonomously respond to customer email inquiries.
![Connecting an Agent to Email](https://raw.githubusercontent.com/jefrainmx/Agentforce-Specialist-Certification/refs/heads/main/images/Screenshot%202026-09-22%20122821.png)

### Connecting a Service Agent to Voice
Voice connections allow customers to interact with an Agentforce Service Agent through a telephony channel.
#### TELEPHONY CONNECTION
A telephony connection connects voice conversations to the Service Agent and defines how calls enter the agent experience.
#### VOICE MODE SETTINGS
Voice mode settings control the voice interaction experience, including how the agent listens, responds, and handles the call flow.

### Voice Routing and Escalation
Voice setup must route calls to the Service Agent and define what happens when the agent needs to transfer the call.
#### VOICE ROUTING
Voice routing determines how incoming calls are sent to the Service Agent and what fallback destination is used when needed.
#### HUMAN TRANSFER
Escalation or transfer behavior should be configured so the agent can hand off complex or sensitive calls to a queue or service rep.

### Connections in Agentforce Builder
The Connections section in Agentforce Builder is used to add and manage channel connections such as Messaging, Email, Voice, and Slack.
![Connection in Agentforce Builder](https://raw.githubusercontent.com/jefrainmx/Agentforce-Specialist-Certification/refs/heads/main/images/Screenshot%202026-09-22%20124118.png)

### Connection Settings
Connection settings define channel-specific behavior, such as adaptive response formats, routing flows, and other settings required for the selected channel.
![Connecting Settings](https://raw.githubusercontent.com/jefrainmx/Agentforce-Specialist-Certification/refs/heads/main/images/Screenshot%202026-09-22%20124359.png)

## Connecting a Service Agent to Digital Experience
### Connecting a Service Agent to Experience Cloud
An AgentforceService Agent can be connected to a customer channel, such as a digital experience.
#### SERVICE CLOUD CONFIGURATION
A Service Agent can be exposed to customers through Messaging for In-App and Web after the required Service Cloud, Messaging, and routing setup is complete. 
#### OMNI-CHANNEL SETUP
Omni-Channel must be enabled so Messaging conversations can be routed to the Service Agent and fallback destinations.
#### MESSAGING
Messaging must be enabled and configured to create the customer-facing channel that receives messages from the Experience Cloud site.
#### INBOUND FLOW
An inbound Omni-Channel Flow must be created to route Messaging requests to the Service Agent. The Route Work action must be added to the flow, and it must be configured by selecting the Service Channel, Service Agent, and Fallback Queue.
#### MESSAGING CHANNEL
A Messaging Channel must be created on the Messaging Settings page in Setup by selecting the Messaging for In-App and Web type. The Omni-Channel Flow and Fallback Queue must be added for routing.
#### OUTBOUND FLOW
An outbound Omni-Channel Flow must be created to enable the agent to transfer conversations to a queue. The flow must be added to the agent by navigating to the Connections tab of its details page in Setup.
#### EMBEDDED SERVICE DEPLOYMENT
An Embedded Service Deployment must be configured in Setup to add the agent to the messaging interface of the channel.
#### EXPERIENCE CLOUD
The agent can be deployed to a customer-facing Experience Cloud site by adding the Embedded Messaging component to a site page.
#### CONTEXT VARIABLES 
In Agentforce Builder, context variables can be used to map Messaging Session object fields to a customer channel to save the agent from having to ask for common information conversationally.
#### PROGRESS INDICATORS
Progress indicators can be used to alert customers to agent activity during a messaging session. They can be enabled and customized by editing the Embedded Service Deployment Settings.
#### TESTING
To preserve message formatting during testing, Salesforce recommends chatting with the agent in a test channel.

### Connecting a Service Agent to Experience Cloud
The diagram below illustrates how a Service Agent can be connected to a Messaging Channel on an Experience Cloud site.
![Connecting a Service Agent to Experience Cloud](https://raw.githubusercontent.com/jefrainmx/Agentforce-Specialist-Certification/refs/heads/main/images/Screenshot%202026-09-22%20130355.png)
#### Inbound Omni-Channel Flow
An Inbound Omni-Channel Flow can be created to route messaging requests to a Service Agent.
![Inbound](https://raw.githubusercontent.com/jefrainmx/Agentforce-Specialist-Certification/refs/heads/main/images/Screenshot%202026-09-22%20130436.png)
#### Outbound Omni-Channel Flow
An Outbound Omni-Channel Flow can be created to enable routing conversations to a queue.
![Outbound](https://raw.githubusercontent.com/jefrainmx/Agentforce-Specialist-Certification/refs/heads/main/images/Screenshot%202026-09-22%20130503.png)
#### Messaging Channel
A Messaging Channel must be created for a digital customer channel in Setup.
![Messaging Channel](https://raw.githubusercontent.com/jefrainmx/Agentforce-Specialist-Certification/refs/heads/main/images/Screenshot%202026-09-22%20130530.png)
#### Embedded Service Deployment
An Embedded Service Deployment must be configured and published to deploy a Service Agent.
![Embedded Service](https://raw.githubusercontent.com/jefrainmx/Agentforce-Specialist-Certification/refs/heads/main/images/Screenshot%202026-09-22%20130550.png)
#### Embedded Messaging Component
The Embedded Messaging component can be added to a page of an Experience Cloud site.
![Embedded Message Component](https://raw.githubusercontent.com/jefrainmx/Agentforce-Specialist-Certification/refs/heads/main/images/Screenshot%202026-09-22%20130613.png)

## References:
[Deploy Your Agent to Channels](https://help.salesforce.com/s/articleView?id=ai.agent_parent_deploy.htm&type=5)
[Get Hands on with Agentforce Service Agents](https://developer.salesforce.com/workshops/agentforce-workshop/service-agents/overview)
[Agentforce Service for Slack](https://trailhead.salesforce.com/content/learn/trails/service-cloud-for-slack)
[Connect a Service Agent to Partner Telephony](https://help.salesforce.com/s/articleView?id=ai.agent_connect_telephony_parent.htm&type=5)

# Explain the security context in which the agent is actually running, and how it impacts agent action execution.
## Introduction
Agentforce agents execute actions in a specific security context. In employee-facing experiences, an agent often runs in the context of the logged-in user, so the user’s license, permissions, field-level security, and sharing determine what data and actions are available. In unauthenticatedor customer-facing channels, the agent often runs as an agent user, which is a Salesforce integration user with the permissions the agent needs to complete its work.This runtime context directly affects action execution. Even if an action is assigned to the agent, the action can succeed only when the running context has access to the required records, objects, fields, flows, Apex classes, prompt templates, Knowledge, Data 360 assets, or external services. Following the principle of least privilege, admins should grant only the minimum required access and use filters, variables, and authentication to control sensitive actions.

### Logged-In User Context
Some employee or authenticated experiences run in the context of the logged-in user, so the user’s Salesforce access controls determine what the agent can access.
### Agent User Context
Customer-facing or unauthenticated experiences often run as an agent user, which is assigned the permissions the agent needs to perform its work. 
### Action Assignment
An agent can execute only actions that are assigned to the relevant subagent or agent configuration.
### Resource Access
The running context must have access to the underlying resources used by the action, such as Flow, Apex, prompt templates, objects, fields, Knowledge, and Data 360.
### Record Access
Organization-wide defaults, sharing, roles, and field-level security determine which records and fields the running context can view or update. 
### Least Privilege
Agent users and human users should receive only the minimum access required for the agent’s intended tasks.

## Agent Runtime Security Context
### Logged-In User Context
In authenticated employee experiences, the agent runs in the context of the user who interacts with it.
#### EMPLOYEE EXPERIENCES
Employee-facing agents in logged-in Salesforce experiences typically use the logged-in user’s existing Salesforce access controls.
#### ACCESS IMPACT
The logged-in user’s license, object permissions, field permissions, sharing, and record access determine what the agent can read, update, or execute.

### Agent User Context
In unauthenticated or customer-facing channels, the agent runs as a dedicated agent user.
#### AGENT USER
An agent user is a Salesforce integration user that provides the runtime access an agent needs when the end user is not directly authorized in Salesforce. 
### ACCESS IMPACT
The agent user’s role, permission sets, object access, field access, sharing access, and feature permissions determine which actions can run successfully.

### Agent User
The agent user should start with minimal access and then receive only the additional permissions required for the agent’s assigned actions.
#### NEW AGENT USER
Creating a new agent user gives the agent a secure baseline with the Einstein Agent license, Einstein Agent User profile, and default permission set assignments.
#### ADDITIONAL ACCESS
Additional permissions should be granted through targeted permission sets for the specific objects, fields, flows, Apex classes, prompt templates, Knowledge, or Data 360 assets the agent uses.

### Agent User
When creating an agent that needs an agent user, the specialist can create a new agent user or select an existing one. The agent user should be reviewed after creation to ensure it has only the permissions required for the agent’s assigned actions.
![Agent User](https://raw.githubusercontent.com/jefrainmx/Agentforce-Specialist-Certification/refs/heads/main/images/Screenshot%202026-09-22%20140038.png)

### Agentforce Permission Sets for Sales & Service
Agentforce permission sets can assigned to users based on their persona and responsibilities.
PERMISSION SET | AGENT TYPE| DESCRIPTION
-------------- |-------------- | -------------- | 
Use Agentforce Sales Coach | Agentforce Sales Coach | Allows users to access and utilize Agentforce Sales Coach.
Manage Agentforce Sales Coach | Agentforce Sales Coach | Allows an admin to enable and configure Agentforce Sales Coach. 
Agentforce Sales Coach | Agentforce Sales Coach | Needs to be assigned to the Agentforce Sales Coach user record.
Use Agentforce SDR Agent | Agentforce SDR | Allows users to access and interact with Agentforce Lead Nurturing.
Configure Agentforce SDR Agent | Agentforce SDR | Allows an admin to manage and monitor Agentforce Lead Nurturing.
Agentforce SDR Agent | Agentforce SDR | Needs to be assigned to the Lead Nurturing agent user record.
Manage Agentforce Service Agent | Agentforce Service Agent | Allows an admin to build and manage Service Agents.
AgentforceServiceAgentUserPsg | Agentforce Service Agent | Permission Set Group that is assigned to the Agentforce Service Agent user record.
Service Planner User | Agentforce Service Planner | Allows service reps to draft service plans using Agentforce Service Planner.
Service Planner Builder | Agentforce Service Planner | Allows an admin to set up and manage Agentforce Service Planner.

### Considerations for Setting Up Agent Permissions
Certain considerations apply to setting up permissions for an Agentforce agent.
Most agent users require a role that lets the agent view or edit the records that it interacts with. In addition, the agent requires access to the relevant objects referenced in each action. The principle of least privilege should be followed to grant the permissions, which means that only the minimum necessary permissions should be granted.

Access to additional features, such as prompt templates, should be granted by creating and assigning a permission set or permission set group. Flows require the Run Flows permission. Features and actions that leverage Knowledge and Data Cloud require the Allow View Knowledge and Access Conversation Entriespermissions.

Organization-wide defaults (OWD) determine access to records. An agent session with an authenticated user runs in the end user’s context and OWD depend on whether the user is external or internal. An agent session with an unauthenticated user runs in the agent user’s context and OWD for internal users apply.

## References:
[Configure Service Agent Access](https://help.salesforce.com/s/articleView?id=ai.agent_user.htm&type=5&utm_source=chatgpt.com)
[Maintain Trust with Agentforce Actions in the Legacy Builder](https://help.salesforce.com/s/articleView?id=ai.service_agent_secure_actions.htm&type=5)
[Create an Agent](https://help.salesforce.com/s/articleView?id=ai.agent_setup_create.htm&type=5)
[Agent Types and Considerations](https://help.salesforce.com/s/articleView?id=ai.agent_setup_explore_types.htm&type=5)


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTgxMDMwNDgxMywtMjI4NDg1NzE1LDE4NT
M0NzIxMDMsMzAzMzQ4NzE5LDM1Mzg3MjI2MSwtMTcwNzQ1OTY3
MSwtMTExNzA5NjE2NCwtMTQ3NDI1MDg5MCwtNzgyNTU4ODIsMT
Q3MTA2NTY0LDIwMDQwODY1MTMsMTczMzQ2MDMyOSw5MDM2ODg2
ODgsLTM5MDAzMjI5NCwxMzcwOTAzNTcyLC0xOTkxNDQ3ODY3LD
EwMzU0MDcyMDMsMTA4NjY1MDM4MSw2OTcwNTEzNjcsMTAwNjA1
NDQ2NF19
-->