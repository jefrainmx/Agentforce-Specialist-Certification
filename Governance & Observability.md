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
Ongoing governance ensures that agents continue to meet business, security, compliance, and qualityexpectations.
#### OPERATIONAL REVIEW
Teams should regularly review usage, feedback, unresolved requests, failed tests, escalation trends, and action failures.
#### CHANGE GOVERNANCE
Agent updates should follow a controlled release process with documentation, testing evidence, approval, and rollback planning.

### Agent Analytics
The Agent Analytics page in Agentforce Studio shows analytics and performance metrics related to categories such as Effectiveness, Usage, User Satisfaction, Quality, Health, and Trust. 
![Agent Analytics 1](https://raw.githubusercontent.com/jefrainmx/Agentforce-Specialist-Certification/refs/heads/main/images/Screenshot%202026-10-02%20103550.png)

### Agent Analytics
The Optimization section in Agentforce Studio allows viewing performance-related insights.
![Agent Analytics 2](https://raw.githubusercontent.com/jefrainmx/Agentforce-Specialist-Certification/refs/heads/main/images/Screenshot%202026-10-02%20103615.png)

### Agent Preview
The Preview button in Agentforce Builder allows manual testing of utterances.
![Agent Preview](https://raw.githubusercontent.com/jefrainmx/Agentforce-Specialist-Certification/refs/heads/main/images/Screenshot%202026-10-02%20103635.png)


## References
[Monitor Your Agent](https://help.salesforce.com/s/articleView?id=ai.agent_parent_monitor.htm&type=5&utm_source=chatgpt.com)
[Agent Analytics and Monitoring](https://trailhead.salesforce.com/content/learn/modules/agent-analytics-and-monitoring)

# Explain agent analytics and agent optimization
## Introduction
Agent analytics and optimization help organizations monitor, understand, and improve Agentforce agents after they are deployed. Agent Analytics provides dashboards and metrics that show how agents are being used, how effectively they resolve conversations, and where users escalate, abandon, or disengage. Agent Optimization provides deeper analysis of sessions, intents, quality scores, unresolved interactions, and knowledge gaps. Both capabilities rely on session-level data captured through Agentforce Session Tracing, which records agent interactions, reasoning steps, actions, prompt and gateway inputs/outputs, errors, and final responses. Together, analytics and optimization support an ongoing improvement cycle: measure agent performance, investigate weak areas, update subagents or actions, test changes, and monitor results.
### Agent Analytics and Optimization
#### Agent Conversations
Users interact with agents across supported channels such as messaging, Slack, email, voice, or embedded experiences.
#### Session Tracing Data
Agentforce Session Tracing captures detailed session data, including interactions, reasoning executions, actions, prompts, gateway inputs/outputs, errors, and final responses. 
#### Agent Analytics
Dashboards and metrics show usage, engagement, effectiveness, escalation, deflection, abandonment, feedback, and error patterns.
#### Agent Optimization
Optimization tools help inspect sessions, identify unresolved interactions, group intents, review quality scores, and find knowledge or configuration gaps.
#### Agent Updates
Builders improve subagents, instructions, actions, grounding, knowledge, filters, or escalation paths based on observed issues.
#### Testing & Monitoring
Changes are tested in Builder or Testing Center, then monitored again using analytics and optimization insights. 


## Agentforce Observability
### Agentforce Observability
Agentforce Observability provides tools for measuring, analyzing, and improvingagent behavior across real conversations.
#### AGENT ANALYTICS
Agent Analytics focuses on performance, usage, effectiveness, feedback, escalation, deflection, and abandonment metrics. 
#### AGENT OPTIMIZATION
Agent Optimization focuses on unresolved interactions, knowledge gaps, session inspection, intents, and response-quality trends.

### Session Tracing Foundation
Agent Analytics and Agent Optimization rely on session-level data captured through Agentforce Session Tracing.
#### SESSION TRACING
Agentforce Session Tracing captures turn-by-turn interactions, reasoning executions, actions, prompt and gateway inputs/outputs, error messages, and final responses. 
#### SESSION DATA
Session data is stored in Data 360 DLOs and DMOs so it can be queried, reported on, and used for dashboards. 

### Session Tracing Data Model
The Session Tracing Data Model organizes agent behavior into sessions, participants, interactions, messages, and steps.
#### SESSION
AIAgentSession represents the overall session, while AIAgentInteraction represents a turn or segment inside the session.
#### OPERATIONS
AIAgentInteractionStep captures discrete operations such as LLM execution, action execution, errors, inputs, and outputs. 

## Agent Analytics
### What Agent Analytics Measures
Agent Analytics helps teams understand how agents perform across users, sessions, channels, and business outcomes.
#### PERFORMANCE
It analyzes agent performance within user and agent sessions using data from the unified Session Tracing Data Model. 
#### METRICS
It supports insights into engagement, escalation, deflection, abandonment, feedback, errors, and agent effectiveness. 

### Key Agent Analytics Metrics
Agent Analytics metrics help teams understand whether agents are being used successfully and where users need additional support. 
#### ENGAGEMENT & DEFLECTION
Engagement and deflection metrics show whether users are interacting with agents and resolvingissues without escalation.
#### ESCALATION, ABANDONMENT & ERROR
Escalation, abandonment, and error metrics show where conversationsfail, transfer, time out, or encounter technical issues.

### Analytics Dashboards
Dashboards turn session data into visual summaries that help teams monitor usage, quality, performance, and trends.
#### DASHBOARDS
Dashboards can show adoption, conversation volume, session outcomes, user feedback, and agent effectiveness across time. 
#### ANALYTICS
Analytics can help identify subagents, actions, channels, or conversation types that require deeper investigation. 

### Agent Analytics
Agent Analytics can be accessed in Agentforce Studio to understand agent performance through various types of metrics.
Agent Analytics 1

## Agent Optimization
### What Agent Optimization Does
Agent Optimization helps builders move from dashboard trends to deeper diagnosis and improvement actions.
#### INSPECTION
It provides tools to inspect sessions, review unresolved interactions, identify knowledge gaps, and analyze real-world agent behavior.
#### UNDERSTANDING
It helps teams understand why agentsfail, go off topic, misinterpretintent, or return low-quality responses.

### Intents and Clustering
Agent Optimization groups related interactions so teams can see what users are asking and where patterns emerge.
#### INTENTS
Intents represent sets of interactions within a session that address a specific user request.
#### CLUSTERING
Intents are generated and clustered to help identify common issues, unmet requests, and improvement opportunities.

### Quality Scores
Quality scores help prioritize which interactions need attention by showing how relevant the agent’s response was to the user request.
#### LOW-QUALITY SCORES
Low-quality scores can highlight weak instructions, missing knowledge, incorrect action selection, or poor response grounding.
#### QUALITY TRENDS
Quality trends can help teams decide which subagents, topics, instructions, or knowledge sources should be updated first.

### Session Analysis
Session analysis provides a detailed view of what happened from the initial user request to the final outcome.
#### ANALYSIS
Session analysis allows builders to inspect how the agent interpretedthe request, which subagentwas selected, and which actions or LLM stepswere executed.
#### DETAILS
Session details can reveal misrouted requests, missing actions, grounding failures, prompt issues, or escalation problems.



## Continuous Optimization Cycle
## References
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTA1MDY2MDgwMiwxMzQ0MzA5ODU2LC0yMj
U1MTQwMjQsLTE0NDA1MTExNTBdfQ==
-->