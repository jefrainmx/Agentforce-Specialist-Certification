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



## SOMA Architecture



## Scenarios & Solutions





# Explain the purpose of existing open standard multi-agent protocols such as MCP and A2A.

## Model Context Protocol (MCP)




## Agent-to-Agent Protocol (A2A)




## Use Cases


<!--stackedit_data:
eyJoaXN0b3J5IjpbMTI0MTM0MjU4NiwtMTc0NDQ5MDgzNSwtMj
k4NTE1NDIzLDczMDk5ODExNl19
-->