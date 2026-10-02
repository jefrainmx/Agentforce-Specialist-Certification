# Explain the process for managing and monitoring agents.
## Introduction
Managing and monitoring agents is an ongoing lifecycle instead of a one-time setup task. After an agent is built and tested, admins must activate it, manage changes carefully, control access, maintain channel connections, and deactivate it when updates are needed. Once the agent is live, teams monitor how it performs by reviewing Agent Analytics, feedback, session data, performance trends, and optimization insights. Monitoring can reveal misrouted requests, low-quality responses, missing subagents, action failures, escalation issues, or trust and health concerns. The management process then continues through investigation, testing, updates, and reactivation.
### Managing and Monitoring Agent Lifecycle
#### Configure Agent
The agent is configured with subagents, actions, instructions, variables, filters, connections, and access settings. 
#### Test Agent
Builder preview and Testing Center validate expected subagent selection, action execution, and responses before activation.
#### Activate Agent
Activation makes the agent available in its connected channels or experiences. 
#### Monitor Behavior
Agent Analytics, feedback, session data, trace data, and optimization insights are reviewed after deployment.
#### Investigate Issues
Failed tests, unexpected subagent selection, missing actions, escalation patterns, poor feedback, and low-quality responses are analyzed. 
#### Update Agent
Subagents, actions, instructions, filters, grounding, connections, permissions, or escalation paths are adjusted. 
#### Retest and Reactivate
Changes are tested again before the updated agent is made available to users.

## Managing Agents
### Agent Management Surfaces
Agent management happens across Setup, Agentforce Builder, Agentforce Studio, and connected channel configuration.
#### AGENTFORCE BUILDER
Agentforce Builder is used to configure the agent’s subagents, actions, instructions, variables, filters, connections, preview conversations, and activation state.
#### AGENTFORCE STUDIO
Agentforce Studio provides access to agent-related work areas such as Agents, Tests, Prompt Templates, Data, AI Models, Agentforce DX, Analytics, Optimization, Scorers, and Alerts. 

### Activation and Deactivation
Activation controls whether an agent is available to users in its connected channels. 
#### ACTIVATION
Activating an agent makes the selected agent version available to users through configured channels and experiences.
#### DEACTIVATION
Deactivating an agent is required when changes must be made to live configuration such as subagents, actions, or instructions. 

### Agent Version Management
Agent versions help teams control which configuration is tested, activated, and changed. 
#### VERSION CONTROL
Agent versions provide a way to manage changes to subagents, actions, instructions, and configuration over time.
#### RELEASE CONTROL
Only a tested and approved version should be activated in productionafter changes are reviewed.

### Managing Subagents and Actions
Subagents and actions define what the agent can understand and what work it can perform. 
#### SUBAGENTS
Subagents define the jobs an agent can perform, including scope, instructions, and assigned actions. 
#### ACTIONS
Actions give the agent specific capabilities, such as retrieving data, calling automation, updating records, or escalating work. 

### Managing Connections and Access
Channel configuration and user access determine where the agent appears and what it can do. 
#### CONNECTIONS
Connections define how an agent is exposed through channels such as Lightning, Slack, Messaging, Email, or Voice.
#### ACCESS
Agent availability and action execution depend on user access, agent user permissions, runtime security context, and channel-specific setup.

## Monitoring Agents
### Builder Preview and Session Investigation
Builder-based tools helps admins inspect how an agent behaves during individual conversations. 
#### CONVERSATION PREVIEW
The Preview helps test real utterances and inspect which subagent, action, or response path the agent selected. 
#### SESSION INVESTIGATION
Session or trace details can help troubleshoot agent behavior by showing what happened during a conversation, including selected subagents, actions, errors, and responses. 

### Agent Analytics
Agent Analytics helps teams monitor broad trends across agent usage, performance, quality, and trust. 
#### AGENT ANALYTICS
Agent Analytics provides overview and performance views that can be filtered by agent type, agent, timeframe, and channel.
#### METRIC CATEGORIES
Agent Analytics organizes performance data into areas such as Effectiveness, Usage, User Satisfaction, Quality, Health, and Trust.

### Feedback and Performance Insights
Feedback and performance insights help teams understand whether users are getting useful, accurate, and trusted responses.
#### USER SATISFACTION
User satisfaction and feedback metrics help identify responses that users find helpful, unhelpful, incomplete, or misaligned with expectations.
#### INTERACTION PATTERNS
Performance insights and optimization data help identify repeated failure patterns, unresolved interactions, and areas where subagents, actions, or grounding may need improvement.

### Session and Trace Data
Session-level data provides deeper visibility into what happened during an agent interaction.
#### SESSION DATA
Session data captures conversation-level information such as user inputs, agent responses, selected subagents, actions, and outcomes. 
#### TRACE DATA
Trace data supports deeper troubleshooting through reasoning steps, action calls, errors, prompt inputs, and generated outputs when Session Tracing is enabled.

## Using Monitoring Data
### Investigating Issues
Monitoring data should be used to identify the likely cause of unexpected or low-quality agent behavior. 
#### ROUTING ISSUES
Routing issues can occur when the wrong subagent is selected, a request falls into a general fallback path, or instructions are unclear. 
#### EXECUTION ISSUES
Execution issues can occur when actions are missing, inputs are incomplete, permissions are insufficient, or the underlying Flow, Apex, API, or data source fails.

### Updating and Retesting Agents
Agent improvements should be tested before the updated agent is made available to users again. 
#### AGENT UPDATES
Updates can include changing subagent descriptions, instructions, actions, filters, variables, grounding, escalation rules, or channel configuration. 
#### RETESTING
Updated behavior should be tested in Agentforce Builder and Testing Center before the agent version is activated again.

###  Governance and Operational Review
Ongoing governance ensures that agents continue to meet business, security, compliance, and qualityexpectations.OPERATIONAL REVIEWTeams should regularly review usage, feedback, unresolved requests, failed tests, escalation trends, and action failures.❖CHANGE GOVERNANCEAgent updates should follow a controlled release process with documentation, testing evidence, approval, and rollback planning.




## References

# Explain agent analytics and agent optimization
## Introduction
## Agentforce Observability
## Agent Analytics
## Agent Optimization
## Continuous Optimization Cycle
## References
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTM1MDIzNTkzMCwtMjI1NTE0MDI0LC0xND
QwNTExMTUwXX0=
-->