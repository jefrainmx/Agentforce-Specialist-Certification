# Given a scenario, determine whether a Multi Agent architecture is appropriate for scalability and control.
## Introduction
Single-agent architectures are often the starting point for Agentforce solutions because one agent can handle common use cases across a range of topics. As the solution grows, a single agent can become harder to govern, test, and maintain because too many unrelated topics, actions, and permissions are concentrated in one place. SOMA, or Single-Org Multi-Agent architecture, addresses this by using a primary or supervisor agent as the single front door while delegating work to specialist agents inside the same Salesforce org. This preserves one user experience while improving control, modularity, testing, permissions, and observability. SOMA is most appropriate when several related domains must collaborate within one Salesforce org and share the same governance and data boundary.
### SOMA Architecture
#### User
SOMA architecture keeps one user-facing conversation while routing specialized work to agents inside the same Salesforce org.
#### Primary / Supervisor Agent
The primary/supervisor agent acts as the single front door, interprets intent, and decides which specialist agent should handle the request. 
#### Task Routing
Task routing uses agent descriptions, instructions, and available actions to route the task to the best-fit specialist.
#### Specialist Agents
Specialist agents handle focused domains such as Cases, Orders, Benefits, Claims, Billing, or Knowledge using their own instructions and actions.
#### Consolidated Response
The specialist completes the task and returns the result through the primary agent so the user keeps one seamless conversation.

## Single-Agent vs SOMA Architecture 
### Single Agent vs SOMA
Single-agent and SOMA architectures solve different design problems and should not be treated as the same pattern.
#### SINGLE AGENT
In single-agent architecture, one Agentforce agent owns the conversation, topics, actions, instructions, and runtime behavior.
#### SOMA
In SOMA architecture, multiple agents collaborate within one Salesforce org through a primary or supervisor agent and specialist agents. 

### Single-Agent Architecture
A single agent works best when the use case is narrow, stable, and can be governed without splitting responsibilities across agents.
#### WHEN TO USE
A single agent should be used when topics are closely related and the action set is small enough to manage safely. 
#### BUILDING & MAINTENANCE
A single agent can be easier to build initially, but can become harder to maintain as scope expands. 

### SOMA Architecture
SOMA uses one front-door agent to route work to specialized agents inside the same Salesforce org. 
#### PRIMARY AGENT
A primary or supervisor agent receives the user request and routes it to the best-fit specialist. 
#### SECONDARY AGENTS
Specialist or secondary agents handle delegated tasks using focused instructions, data, and actions.

### Why SOMA Improves Scalability
SOMA improves scalability by decomposing a large agent workload into smaller, specialized agent responsibilities.
#### SPECIALIST AGENTS
Specialist agents reduce cognitive and instruction load by focusing on a specific business domain or capability. 
#### INDIVIDUAL AGENTS
Teams can add, replace, modify, and test individual agents more easily as the solution grows. 

### Why SOMA Improves Control
SOMA improves control by separating concerns and limiting each agent to the responsibilities, data, and actions it needs.
#### SPECIALIST
Each specialist agent can have a narrower scope, clearer instructions, and a more controlled action set. 
#### DOMAIN
Governance, troubleshooting, and accountability can be isolated to the agent responsible for a specific domain. 

## SOMA Architecture
### Primary and Specialist Agents
The primary agent owns the user experience, while specialist agents provide deep domain capability behind the scenes.
#### PRIMARY AGENT
The primary agent analyzes intent and routes work to the best-fit specialist agent.
#### SECONDARY AGENTS
Secondary agents use focused knowledge and actions, then return the result to the primary agent. 

### Task Orchestration
Task orchestration determines which specialist agent is best equipped to complete each request.
#### ATLAS REASONING ENGINE
Agentforce uses the Atlas Reasoning Engine to review agent descriptions, instructions, and actions for routing.
#### SOMA DESIGN
Effective SOMA design depends on clear specialist-agent boundaries and strong descriptions.

### Shared Governance Boundary
SOMA is appropriate when multiple agents can operate inside the same Salesforce org and governance boundary.
#### SHARING
Agents share the same org-level governance, identity, permissions, observability, and Salesforce data context. 
#### TRUST
Keeping orchestration in one org reduces cross-org trust complexitycompared with multi-org patterns. 

### SOMA for Domain Specialization
SOMA is appropriate when one user journey spans several specialized business domains that should be controlled separately.
#### DIFFERENT DOMAINS
SOMA can be used when one conversation may require specialist agentsfor different domains, such as Claims, Billing, Orders, or Benefits. 
#### FOCUSED
SOMA lets each domain agent own a focused instruction set, data access pattern, and action library.

### SOMA for Scale and Maintainability
SOMA is appropriate when a single agent is becoming too large, brittle, or difficult to test. 
#### SCALABILITY
SOMA can be used when one agent has too many unrelated topics, actions, or decision paths.
#### MAINTAINABILITY
SOMA supports modular testing, clearer ownership, and easier updates to individual agents.

### SOMA for Control and Governance
SOMA is appropriate when different work domains require different permissions, policies, or operational ownership.
#### ISOLATION
SOMA can be used when actions should be isolated by business functionor risk level.
#### ACCOUNTABILITY
SOMA improves accountability because each specialist agent can be monitored and maintained separately.

### When a Single Agent Is Better
A single-agent architecture is usually better when the scope is small enough to govern, test, and maintain without orchestration. 
#### SIMPLICITY
A single agent should be used when the use case has a small number of related topics and a simple action set. 
#### COMPLEXITY
SOMA should be avoided when the added routing and orchestration complexity does not create meaningful control or scalability benefits. 

### When SOMA Is Not Enough
SOMA is limited to collaboration within one Salesforce org, so other patterns are needed when work crosses org or vendor boundaries. 
#### MOMA
MOMA (Multi-Org Multi-Agent) should be used when agents must collaborate across multiple Salesforce orgs.
#### A2A & MCP
A2A or MCP should be used when agents must coordinate with external agents, tools, APIs, or non-Salesforce systems.

## Scenarios & Solutions
### Scenario 1
Cosmic Health must decide whether one agent can support several member-service domains or whether SOMA is needed. The company uses one Salesforce org for member services and wants a single chat experience where authenticated members can ask about eligibility, benefits, claims, prior authorizations, and open cases. Each domain has different data sources, actions, compliance rules, and business owners. The existing single Service Agent has become difficult to test because updates to one area sometimes affect unrelated flows. Leadership wants one user-facing conversation, but separate control over each business domain.
### Solution 1
The Agentforce Specialist should recommend the SOMA architecture because the use case spans multiple specialized domains inside one Salesforce org. A primary agent should act as the single front door for members and route tasks to specialist agents for Eligibility, Benefits, Claims, Prior Authorization, and Cases. This keeps the member experience seamless while giving each domain a focused instruction set, scoped actions, and separate testing and governance. A single agent would concentrate too many unrelated topics and actions in one place, making the solution harder to scale and control.

### Scenario 2
Cosmic Retail must decide whether SOMA is necessary for a narrow internal support use case. The company wants an internal Agentforce agent for store employees who need answers about return policy exceptions. The agent will search a small set of approved Knowledge articles, answer return-policy questions, and create a simple escalation case when the situation falls outside policy. The agent uses one data domain, one support team owns the process, and the action set is limited. The company wants to avoid unnecessary architecture complexity.

### Solution 2
The Agentforce Specialist should recommend a single Agentforce agent rather than SOMA because the use case is narrow, stable, and easy to govern. Due to one policy domain, one owner, and a small action set, a single agent can be tested and governed effectively. SOMA would add routing and orchestration overhead without providing meaningful scalability or control benefits. If the agent later expands into inventory, loyalty, order management, and store operations, the architecture could be revisited.

### Scenario 3
Cosmic Manufacturing must determine whether SOMA is enough when agent collaboration spans multiple Salesforce orgs. The company has separate Salesforce orgs for Sales, Service, and Field Operations. It wants one agent conversation where a customer can ask about a warranty claim, schedule a technician, and check replacement-part inventory. Each org has its own data model, permissions, and operational ownership. The team wants unified orchestration, but the specialist agents do not all live in the same Salesforce org.

### Solution 3
The Agentforce Specialist should not select SOMA as the final architecture because the required specialist agents are spread across multiple Salesforce orgs and SOMA is intended for multiple agents collaborating within one Salesforce org. Since this scenario spans Sales, Service, and Field Operations orgs, a multi-org pattern such as MOMA is more appropriate. SOMA would be suitable only if the required specialist agents were all operating within the same Salesforce org and shared one governance and data boundary.

## References:
[Multi-Agent Orchestration](https://www.salesforce.com/agentforce/multi-agent-orchestration/)
[Seven Requirements for Effective Agents](https://www.salesforce.com/agentforce/effective-ai-agent-checklist/)
[Learn about Agentforce SOMA(Single Org, Multi Agent) Orchestration and MCP](https://help.salesforce.com/s/articleView?id=005317683&type=1)


# Explain the purpose of existing open standard multi-agent protocols such as MCP and A2A.
## Introduction
Model Context Protocol (MCP) is an open standard that defines how AI models connect with external tools, systems, and data. Originally developed by Anthropic, MCP enables Agentforce agents to perform real-world tasks by securely integrating with external applications through standardized interfaces known as MCP servers.The Agent-to-Agent Protocol (A2A) defines how AI agents within and across organizations communicate, coordinate, and collaborate securely. It provides a standardized and interoperable framework that allows diverse agents, such as sales, service, or partner agents, to exchange messages, delegate tasks, and share results regardless of platform or vendor.
### Model Context Protocol (MCP)
#### Open Standard
Model Context Protocol (MCP), is an open standard originally developed by Anthropic that enables connecting AI applications like agents to external systems.
#### MCP Servers
MCP servers found on AgentExchange provide the tools that enable AI agents to perform specific tasks. Agents can be connected to MCP servers in Agentforce Builder.
#### Context
MCP provides a universal standard that enables Agentforce to engage with an external server to receive the context of the functionality needed to deliver accurate, effective results. 
#### Use Cases
Use cases of MCP include data retrieval, record management, workflow automation, document and file access, system-to-system integration, and tool discovery.

### Agent-to-Agent Protocol (A2A)
#### Platform Events
Platform Events act as the transport layer for A2A communication in the Agentforce ecosystem. Agents publish, subscribe, and react to contextual events to trigger actions or escalate tasks asynchronously.
#### Open Standard
Agent-to-Agent Protocol (A2A) is an open standard that complements MCP and provides standardized and secure agent-to-agent messaging, delegation, and result handoff. 
#### Features
A2A offers features such as seamless communication, interoperability, scalable collaboration, and governance. Agents can publish their capabilities via Agent Cards and exchange structured tasks and messages using standard web technologies (HTTP, JSON).
#### Use Cases
A2A has various use cases relevant for Agentforce, such as cross-domain handoff, specialist handoff, swarming and triage, partner collaboration, multi-step planning, and escalation.

## Model Context Protocol (MCP)
### Model Context Protocol (MCP)
Model Context Protocol (MCP) is an open standard that describes how AI models can connect with external tools, systems, and data.
#### OPEN SOURCE
Model Context Protocol (MCP), originally developed and open-sourced by Anthropic, enables connecting AI applications to external systems.
#### BENEFITS
Model Context Protocol (MCP) reduces integration effort and complexity while enforcing consistent enterprise-grade trust, security, and compliance across all agent interactions.
#### CONTEXT
MCP provides a universal standard that enables Agentforce to engage with an external server to receive the context of the functionality needed to deliver accurate, effective results. The context fits into the agent’s system of topics, prompts and instructions.
#### MCP SERVERS
AI agents can be connected to MCP servers in Agentforce Builder. These servers can be found on AgentExchange. For example, a service agent can retrieve location data from a shipping and logistics provider’s MCP server to provide an accurate delivery window to a customer. 
#### TOOLS & PROMPTS
MCP servers provide the tools that enable AI agents to perform tasks. These are functions or actions that AI agents can take. MCP partners can also share useful prompts for recurring or common tasks with AI agents to ensure they quickly get the information they need to help customers.
#### MCP PARTNERS
Some examples of AgentExchange partners that offer MCP servers are AWS, Cisco, PayPal, Box, IBM, Zoom, etc.

### MCP Partners
Various AgentExchange partners offer MCP servers that enable agents to connect to external systems.


## Agent-to-Agent Protocol (A2A)
Agent-to-Agent Protocol (also called A2A) is an open standard that lets AI agents from different vendors or stacks communicate, coordinate, and collaborate securely.
### STANDARDIZED & SECURE
The Agent-to-Agent Protocol (A2A) complements MCP (which connects a single agent to tools/data) and provides standardized and secure agent-to-agent messaging, delegation, and result handoff. 
### SEAMLESS
A2A enables seamless communication and collaboration between diverse agents, regardless of their underlying platform or developer.
### INTEROPERABILITY
A2A allows heterogeneous agents (e.g., sales, service, employee, partner, etc.) to exchange tasks and context across platforms.
### SCALABLE COLLABORATION
A2A allows agents to seamlessly communicate and orchestrate complex tasks directly with external agents, fostering truly collaborative AI workflows while ensuring secure, scalable interoperability and an enhanced digital workforce across all ecosystems.
### TRUST & GOVERNANCE
A2A enforces org-level permissions, context propagation, and auditability across A2A exchanges through the Einstein Trust Layer.
### HOW IT WORKS
A2A focuses on horizontal agent communication. Agents can publish their capabilities via Agent Cards so others know what they can do. They can exchange structured tasks and messages using standard web technologies (HTTP, JSON).
### BENEFITS
A2A offers various benefits, such as faster solution building, better accuracy & resilience, and enterprise-grade trust & compliance.
### PLATFORM EVENTS
Platform Events act as the nervous system for proactive and collaborative agents, serving as the transport layer for A2A communication in the Agentforce ecosystem.
### EVENT-DRIVEN COLLABORATION
Agents publish, subscribe, and react to contextual events to trigger actions or escalate tasks asynchronously.
### COMPOSABLE AGENT MESH
A2A supports distributed orchestration, allowing specialized agents (sales, service, employee, etc.) to coordinate dynamically.

## Use Cases
### Use Cases of Model Context Protocol (MCP)
MCP has various practical use cases and empowers AI agents to execute real-world tasks.
#### DATA RETRIEVAL
Agents can access live CRM, ERP, or Knowledge data to provide contextually accurate responses.
#### RECORD MANAGEMENT
Agents can create, update, or close records (e.g., cases, leads, opportunities) through standardized MCP tool calls.
#### WORKFLOW AUTOMATION
Agents can coordinate multi-step processes like order fulfillment or employee onboarding across connected systems.
#### DOCUMENT AND FILE ACCESS
Agents can retrieve, summarize, or analyze documents from systems like SharePoint or Google Drive.
#### INTEGRATION
Agents can perform actions that span multiple platforms, such as syncing billing data or triggering approvals in an ERP.
#### TOOL DISCOVERY
Agents can dynamically identify or add new tools exposed via MCP servers, expanding their capabilities.

### Use Cases of Agent-to-Agent Protocol (A2A)
A2A has various use cases that are relevant for Agentforce.
#### CROSS-DOMAIN HANDOFF
A Service agent can escalate to a Billing agent (collections policy), which can send a response with a structured resolution.
#### SPECIALIST DELEGATION
A Sales agent can delegate pricing to a CPQ agent and contract language to a Legal agent, and then compose the final offer.
#### SWARMING & TRIAGE
Multiple agents (Knowledge, Case, Logistics) can collaborate on an incident, each providing results to a coordinator agent.
#### PARTNER COLLABORATION
An in-org Agentforce agent can collaborate with a partner’s fulfillment agent across company boundaries.
#### MULTI-STEP PLANNING
A coordinator agent can plan a task, assign subtasks to domain agents, merge outputs, and report status.
#### ESCALATION
When an agent cannot resolve a request or policy conflict, it can delegate to a specialized escalation agent.

## References:
[Agentforce MCP Support](https://www.salesforce.com/agentforce/mcp-support/)
[What Is MCP? A Simple Guide to Model Context Protocol for Salesforce Admins](https://admin.salesforce.com/blog/2025/what-is-mcp-a-simple-guide-to-model-context-protocol-for-salesforce-admins)
[Introducing the Model Context Protocol](https://www.anthropic.com/news/model-context-protocol)
[A Comprehensive Overview of the Model Context Protocol (MCP)](https://medium.com/@astropomeai/a-comprehensive-overview-of-the-model-context-protocol-mcp-f65150da0aa0)
[What is the Model Context Protocol (MCP)?](https://modelcontextprotocol.io/docs/2026-07-28/getting-started/intro)
[Unleashing the Power of Connected Agents with the Newly Expanded AgentExchange](https://www.salesforce.com/blog/connected-agents-agentexchange/?utm_source=chatgpt.com)



<!--stackedit_data:
eyJoaXN0b3J5IjpbLTc2MTc2NjYxMCw0MTk0MzA2MDksLTE3ND
Q0OTA4MzUsLTI5ODUxNTQyMyw3MzA5OTgxMTZdfQ==
-->