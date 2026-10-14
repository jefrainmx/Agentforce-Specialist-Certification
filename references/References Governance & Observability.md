# Monitor Your Agent

When you review and update your agentic solution, it has a higher chance of success. Review Agentforce analytics to report on key indicators such as performance, usage, quality, trust, cost, and ROI.

![Note](https://sf-zdocs-cdn-prod.zoominsoftware.com/tdta-ai-generative_ai-264-0-0-production-enus/fc2f2f57-79fe-4598-a5e0-089f9b72c638/images/icon_note.png)

Note Beginning in April 2026, agent topics are now called subagents. There are no changes to functionality. During this transition, you may see a mix of the new and previous terms in our documentation.

-   **[Agent Analytics](https://help.salesforce.com/s/articleView?id=ai.generative_ai_agent_analytics.htm&language=en_US&type=5)**  
    Analyze your AI agents’ performance within user and agent sessions. Agent Analytics is built on the unified Session Tracing Data Model (STDM), which captures every event and interaction within a session and logs it as individual events. You can query the logged ‌events to gain insights and optimize the Agent.
-   **[Agent Optimization](https://help.salesforce.com/s/articleView?id=ai.generative_ai_optimize.htm&language=en_US&type=5)**  
    Use Agent Optimization to inspect agent sessions from the initial user request to the agent’s resolution.
-   **[Monitor Agent Health](https://help.salesforce.com/s/articleView?id=ai.agent_monitor_health.htm&language=en_US&type=5)**  
    Agent Health Monitoring detects and notifies you of silent agent failures—like spiking error rates or high latency—in near-real time across your AI agents. Rapidly respond to agent performance issues to mitigate customer impact.
-   **[Legacy Agentforce Analytics](https://help.salesforce.com/s/articleView?id=ai.copilot_analytics.htm&language=en_US&type=5)**  
    Legacy Agentforce Analytics uses Data 360 to help you gain insights into how your agents are performing. The insights in your customizable dashboard and reports can help you determine whether you want to change anything to drive adoption or adjust subagents and actions to improve user satisfaction.
-   **[Monitor Your Voice-Enabled Agent](https://help.salesforce.com/s/articleView?id=ai.monitor_voice_enabled_agents.htm&language=en_US&type=5)**  
    To boost service quality, supervisors can monitor the voice-enabled agents on active calls by using Omni Supervisor. They can also monitor agent performance over time by using agent analytics reports and dashboards.
-   **[Agentforce Session Tracing](https://help.salesforce.com/s/articleView?id=ai.generative_ai_session_trace.htm&language=en_US&type=5)**  
    Agentforce session tracing captures detailed agent interaction data in a unified data model on Data 360. Build dashboards, reports, and queries on this data to derive insights into agent behavior and trends. Take data-driven action while testing, debugging, and monitoring agents in sandbox or production environments.
-   **[Monitor Agent Guardrails](https://help.salesforce.com/s/articleView?id=ai.agent_guardrails_monitor.htm&language=en_US&type=5)**  
    Monitor instruction adherence and task resolution for your agents.
-   **[Monitor Agentforce Session Log Events](https://help.salesforce.com/s/articleView?id=ai.agentforce_diagnostic_data_model.htm&language=en_US&type=5)**  
    Monitor log events captured during AI agent sessions in the AI Agent Session Log data model object (DMO).

# Agent Analytics

Analyze your AI agents’ performance within user and agent sessions. Agent Analytics is built on the unified Session Tracing Data Model (STDM), which captures every event and interaction within a session and logs it as individual events. You can query the logged ‌events to gain insights and optimize the Agent.

![Note](https://sf-zdocs-cdn-prod.zoominsoftware.com/tdta-ai-generative_ai-264-0-0-production-enus/fc2f2f57-79fe-4598-a5e0-089f9b72c638/images/icon_note.png)

Note Beginning in April 2026, agent topics are now called subagents. There are no changes to functionality. During this transition, you may see a mix of the new and previous terms in our documentation.

-   **[About Agent Analytics](https://help.salesforce.com/s/articleView?id=ai.generative_ai_agent_analytics_about.htm&language=en_US&type=5)**  
    Analyze the performance of your AI agents. Agent Analytics is a tool specifically designed for comprehensive session analysis. Built on the unified Session Tracing Data Model (STDM), it captures every turn and event occurring in and across all your agent sessions. You can then query the logged events to gain insights and optimize agent performance.
-   **[Set Up Agent Analytics](https://help.salesforce.com/s/articleView?id=ai.generative_ai_agent_analytics_setup.htm&language=en_US&type=5)**  
    Set up Agent Analytics to gain insights into agent performance, track conversation metrics, and optimize your agents with comprehensive dashboards and session insights.
-   **[Customize Agentforce Observability](https://help.salesforce.com/s/articleView?id=ai.generative_ai_agent_observability_customization.htm&language=en_US&type=5)**  
    Customize Agent Analytics when the standard metrics don't fully represent your business processes. Use scorer results and the analytics semantic data model to refine metrics and surface them in dashboards.
-   **[Data Model and Calculated Fields for Agent Analytics](https://help.salesforce.com/s/articleView?id=ai.generative_ai_agent_analytics_data_model.htm&language=en_US&type=5)**  
    The data model for Agent Analytics is based on Agent Session Tracing, which contains detailed session trace logs of agent behavior. The data model also includes references to every LLM call that the reasoning engine makes to support joins with feedback data or guardrails metrics. Extended Service Data Model DMOs, such as GenAiFeedback, GenAIContentCategory, and TenantEnrichedUsageEvent support feedback, Trust Layer, and flex credit analytics.
-   **[Get Insights with Agent Analytics](https://help.salesforce.com/s/articleView?id=ai.generative_ai_agent_analytics_use.htm&language=en_US&type=5)**  
    Monitor agent performance in Agentforce Studio with Agent Analytics dashboards, then open Sessions & Intents to audit transcripts, compare intents, and address low-quality sessions.
-   **[Improve Agent Performance with Agent Optimizer (Beta)](https://help.salesforce.com/s/articleView?id=ai.generative_ai_optimization_agent_use.htm&language=en_US&type=5)**  
    Understand agent performance, identify high-impact problems, investigate their causes, and get suggestions for improving sessions in Agentforce Studio.
-   **[Troubleshoot Agent Analytics](https://help.salesforce.com/s/articleView?id=ai.generative_ai_agent_analytics_troubleshoot.htm&language=en_US&type=5)**  
    If you’re unable to see the information, models, dashboards, or metrics that you expect, try these solutions.

# Agent Optimization

Use Agent Optimization to inspect agent sessions from the initial user request to the agent’s resolution.

Watch this video to learn how Agentforce Optimization and Agent Analytics work together to help you continuously refine and improve your AI agents.

[![Watch: Agentforce Optimization and Agent Analytics](https://sf-zdocs-cdn-prod.zoominsoftware.com/tdta-ai-generative_ai-264-0-0-production-enus/fc2f2f57-79fe-4598-a5e0-089f9b72c638/generative_ai/images/agentforce_optimization_analytics_video.png)](https://youtu.be/QgSfsD3qwXI?si=BMyIClrzau1-uLP6)

Here are the steps and information required to set up and use Agentforce Optimization.

-   **[About Agent Optimization](https://help.salesforce.com/s/articleView?id=ai.generative_ai_optimize_about.htm&language=en_US&type=5)**  
    Agent Optimization provides tools to dive deeper into unresolved interactions, identify knowledge gaps, and analyze agent sessions using the Session Tracing Data Model. Agent Optimization is a key component of Agentforce Observability, designed to help you understand how your AI agents perform in real-world scenarios. By analyzing user interactions and agent responses, you can identify areas for improvement and take action to enhance agent effectiveness.
-   **[Set Up Agent Optimization](https://help.salesforce.com/s/articleView?id=ai.generative_ai_optimize_setup.htm&language=en_US&type=5)**  
    To use Agent Optimization, turn it on in Einstein Setup. Analyze agent sessions, identify knowledge gaps, and explore unresolved interactions based on Agentforce Session Tracing data.
-   **[Scorers and Custom Scorers](https://help.salesforce.com/s/articleView?id=ai.generative_ai_optimize_scorers.htm&language=en_US&type=5)**  
    Scorers evaluate agent sessions for quality and business insights. You can score sessions with prompt templates that run automatically, by API, or manually in Agentforce Studio. Use out-of-the-box scorers, edit existing scorers, or create custom scorers with predefined or open-ended outputs.
-   **[Use Intents in Agent Optimization](https://help.salesforce.com/s/articleView?id=ai.generative_ai_optimize_intent_use.htm&language=en_US&type=5)**  
    Work with intents in Agent Optimization to understand user requests, analyze interaction patterns, and improve your agent's performance.
-   **[Troubleshoot Agent Optimization](https://help.salesforce.com/s/articleView?id=ai.generative_ai_optimize_troubleshoot.htm&language=en_US&type=5)**  
    Resolve common issues with Agent Optimization, including setup problems, data display issues, and performance concerns.
-   **[Data Model for Agent Optimization](https://help.salesforce.com/s/articleView?id=ai.generative_ai_optimize_data_model.htm&language=en_US&type=5)**  
    Agent Optimization extends Session Tracing Data Model (STDM) capabilities by provisioning additional data model elements that track session moments and user intent. An LLM identifies, clusters, and tags these moments. The resulting information enables targeted queries and insights into user engagement metrics, moment duration, and response relevance quality scores.
-   **[Analyze Data with Agent Optimization](https://help.salesforce.com/s/articleView?id=ai.generative_ai_optimize_use.htm&language=en_US&type=5)**  
    Use Agent Optimization to drill into sessions, analyze quality scores, and identify patterns to improve your agent's performance.

# Monitor Agent Health

Agent Health Monitoring detects and notifies you of silent agent failures—like spiking error rates or high latency—in near-real time across your AI agents. Rapidly respond to agent performance issues to mitigate customer impact.

## Manage the Health of Your Agents

Built on the data foundation of [Agentforce Session Tracing](https://help.salesforce.com/s/articleView?id=ai.generative_ai_session_trace.htm&language=en_US&type=5), Agent Health Monitoring gives your team visibility into agent performance.

-   Create alerts and get notified when agent performance breaches alert thresholds.
-   Observe agent health status and trends with Tableau Next visualizations.
-   Rapidly investigate and resolve agent performance issues.
-   Drill into detailed Agentforce session traces to debug conversation flows and identify root causes quickly.
-   Implement agent improvements as needed. Then test, deploy and continue to monitor your agent.

## Limitations and Considerations

-   Currently, the custom metric drill-down page supports only time-based filtering, lacking the specific criteria-based filters needed to isolate the sessions that triggered an alert.
-   Alerts created previously during the Agent Health Monitoring (Beta) program aren’t supported in this GA release. You must create new alerts by using the GA release.
-   By shifting the alert evaluation frequency from 1 to 10 minutes, we reduce infrastructure load while maintaining compliance with our service-level agreements. This change results in a slight increase in expected alert latency, with customer notifications now arriving between 3 and 7 minutes.

-   **[Set Up Agent Health Monitoring](https://help.salesforce.com/s/articleView?id=ai.agent_monitor_health_setup.htm&language=en_US&type=5)**  
    Set up Agent Health Monitoring so you can create alerts and get notified when agent performance breaches alert thresholds. Observe agent health status and trends. Rapidly investigate and resolve agent performance issues.
-   **[Manage Alerts for Agent Health Monitoring](https://help.salesforce.com/s/articleView?id=ai.agent_monitor_health_alert.htm&language=en_US&type=5)**  
    Set up an alert to monitor a metric for a particular agent. You receive an email notification when a performance data breaches an alert threshold.
-   **[Investigate Notifications](https://help.salesforce.com/s/articleView?id=ai.agent_monitor_health_notification.htm&language=en_US&type=5)**  
    Manage the notifications that you received from monitoring alerts that you created. The system sends a notification to your email inbox whenever agent data for a monitored metric breaches an alert threshold.
# Legacy Agentforce Analytics

Legacy Agentforce Analytics uses Data 360 to help you gain insights into how your agents are performing. The insights in your customizable dashboard and reports can help you determine whether you want to change anything to drive adoption or adjust subagents and actions to improve user satisfaction.

![Important](https://sf-zdocs-cdn-prod.zoominsoftware.com/tdta-ai-generative_ai-264-0-0-production-enus/fc2f2f57-79fe-4598-a5e0-089f9b72c638/images/icon_important.png)

Important Starting June 17, 2025, Agentforce (Default) will not include new features or improvements and isn’t available in new Salesforce environments. We recommend migrating to Agentforce Employee agent for continued enhancements and support. If you plan to transition to Agentforce Employee agent or make related license changes, complete the migration of your existing Agentforce (Default) agents in advance to avoid potential disruption in agent availability. If you can't complete the migration in advance, you can create new agents after the transition, which can involve some downtime. See [Migrate from Agentforce (Default) to Agentforce Employee Agent](https://help.salesforce.com/s/articleView?id=ai.migrate_agentforce_default_to_aea.htm&language=en_US&type=5).

![Note](https://sf-zdocs-cdn-prod.zoominsoftware.com/tdta-ai-generative_ai-264-0-0-production-enus/fc2f2f57-79fe-4598-a5e0-089f9b72c638/images/icon_note.png)

Note

-   Agentforce Analytics is **scheduled for retirement** starting May 2026. We recommend using [Agent Analytics instead](https://help.salesforce.com/s/articleView?id=ai.generative_ai_agent_analytics.htm&language=en_US&type=5).
-   Agentforce Analytics stores and processes data using Data 360. It consumes credits used for billing based on your usage of the feature. To stop processing Data 360 credits and unlock the Data 360 objects, turn off Agentforce Analytics in the Einstein Feedback and Monitoring Setup. You can then [remove the Data 360 objects](https://help.salesforce.com/s/articleView?id=data.c360_a_remove_data_lake_objects_from_data_spaces.htm&language=en_US&type=5).
-   Some Agentforce Analytics features include user feedback. To use all the features, turn on Feedback in the Einstein Feedback and Monitoring Setup.
-   Agentforce Analytics isn't available in **Data Cloud One companion orgs** or in **sandbox environments**.
-   Agentforce Analytics is not supported in **Government Cloud organizations**.
-   Make sure your org uses the [standard Salesforce CRM Connector](https://help.salesforce.com/s/articleView?id=data.c360_a_salesforce_crm_connector.htm&language=en_US&type=5) so Data 360 can ingest the data from your org.

Found in the Agentforce (Default) folder in the Dashboard tab, the reports on the dashboard provide a variety of data points, including adoption, feedback, and usage analysis. You can click the charts or linked reports to drill deeper into the results. You can modify the reports and dashboards or create your own to suit your org’s needs. But be sure to clone the report and modify the clone, not the original, to avoid breaking the analytics processes.

![Agentforce (Default) dashboard page with multiple charts displaying various agent analytics.](https://sf-zdocs-cdn-prod.zoominsoftware.com/tdta-ai-generative_ai-264-0-0-production-enus/fc2f2f57-79fe-4598-a5e0-089f9b72c638/generative_ai/images/agentforce_analytics_dashboard.png)

-   **[Utterance Analysis](https://help.salesforce.com/s/articleView?id=ai.copilot_utterance_analysis.htm&language=en_US&type=5)**  
    Utterance Analysis lets you quickly see how Agentforce (Default) users are using agents, what they’re requesting, and whether the agent was able to handle these requests. These customizable reports can help you refine your subagents and actions so that your agents respond more effectively and accurately.
-   **[Agentforce Analytics Reports](https://help.salesforce.com/s/articleView?id=ai.copilot_reports_dashboards.htm&language=en_US&type=5)**  
    Agentforce Analytics is based on Data 360 reports that can help you gain insight into the performance of your agents. The reports show you who’s using your agents, how successful they are, and what your adoption level is, among other things.
-   **[Legacy Agentforce Analytics Data Cloud Objects](https://help.salesforce.com/s/articleView?id=ai.copilot_analytics_data_cloud_objects.htm&language=en_US&type=5)**  
    Agentforce Analytics creates dashboards and reports built on Data Cloud objects.
-   **[Legacy Agentforce Analytics Troubleshooting](https://help.salesforce.com/s/articleView?id=ai.copilot_analytics_troubleshooting.htm&language=en_US&type=5)**  
    If you’re not seeing the information you expect in your reports and dashboards, check these possible solutions.

# Monitor Your Voice-Enabled Agent

To boost service quality, supervisors can monitor the voice-enabled agents on active calls by using Omni Supervisor. They can also monitor agent performance over time by using agent analytics reports and dashboards.

## Monitor Agents with Omni Supervisor

To make sure that your voice-enabled agent consistently delivers high-quality service to customers over the phone, supervisors can monitor the call transcripts in the Agentforce tab of Omni Supervisor. The Agentforce tab shows a list of agents on active calls. If you’re using a supervisor configuration, confirm that the Agentforce tab and the Agentforce Service agents are visible in Omni Supervisor.

![The Agentforce tab shows an agent on a call and the transcript](https://sf-zdocs-cdn-prod.zoominsoftware.com/tdta-ai-generative_ai-264-0-0-production-enus/fc2f2f57-79fe-4598-a5e0-089f9b72c638/generative_ai/images/agentforce_voice_omni_supervisor.png)

See [Monitor Agentforce Service Agents](https://help.salesforce.com/s/articleView?id=service.omnichannel_monitor_service_agents.htm&language=en_US&type=5).

## Monitor Agent Performance with Agentforce Analytics

Agent Analytics: Seeing the overall picture

The Agent Analytics tool records every step of an AI conversation from start to finish. It gathers all the details from your agent's sessions into one place so you can see exactly how they’re performing over time. By looking at these records, you can spot general trends and use the data to make sure that your agents stay helpful and efficient. See [Get Insights with Agent Analytics](https://help.salesforce.com/s/articleView?id=ai.generative_ai_agent_analytics_use.htm&language=en_US&type=5).

Agent Optimization: Fixing specific problems

The Agent optimization tool helps you improve how the agent talks to your customers. You can listen to the recordings of the voice calls, dive into the details of conversations, and review quality scores. You can find knowledge gaps where the AI didn't have the right answer. Review specific examples and quality scores to get insights for optimizing your voice-enabled agent. See [Use Agent Optimization](https://help.salesforce.com/s/articleView?id=ai.generative_ai_optimize_use.htm&language=en_US&type=5).

# Agentforce Session Tracing

Agentforce session tracing captures detailed agent interaction data in a unified data model on Data 360. Build dashboards, reports, and queries on this data to derive insights into agent behavior and trends. Take data-driven action while testing, debugging, and monitoring agents in sandbox or production environments.

-   **[About Agentforce Session Tracing](https://help.salesforce.com/s/articleView?id=ai.generative_ai_session_trace_about.htm&language=en_US&type=5)**  
    Agentforce session tracing captures details on agent interactions with users from start to finish. Agentforce session tracing ingests data from different sources (starting with reasoning engine logs) and combines everything under a session ID. The log provides detailed information into what happened during agent sessions: turn-by-turn interactions, reasoning engine executions, actions, prompt and gateway inputs/outputs, error messages, and final responses.
-   **[Set Up Agentforce Session Tracing](https://help.salesforce.com/s/articleView?id=ai.generative_ai_session_trace_setup.htm&language=en_US&type=5)**  
    Turn on Agentforce Session Tracing to collect and store, in Data 360, detailed data about agent sessions. By default, Agentforce Session Tracing is off. For orgs with only one dataspace, it’s turned on by default when Agentforce is turned on.
-   **[Data Model for Agentforce Session Tracing](https://help.salesforce.com/s/articleView?id=ai.generative_ai_session_trace_data_model.htm&language=en_US&type=5)**  
    Use the data model in Data 360 to build reports, dashboards, and queries that provide insights into agent behavior. The system streams data to data lake objects (DLOs) in Data 360 within minutes. Access the data via the standard data model objects (DMOs), which are mapped to the DLOs.
-   **[Get Insights from Agent Session Tracing Data](https://help.salesforce.com/s/articleView?id=ai.generative_ai_session_trace_use.htm&language=en_US&type=5)**  
    To analyze Agentforce session tracing data, you can use observability dashboards, run queries, and build Data 360 reports using the data model.
-   **[Billing Considerations for Agentforce Session Tracing](https://help.salesforce.com/s/articleView?id=ai.generative_ai_session_trace_usage_types.htm&language=en_US&type=5)**  
    Agentforce Session Tracing consumes Data 360 credits for storage used over the allocated amount.
-   **[Implement Data Governance Permissions for Agentforce Session Tracing Objects](https://help.salesforce.com/s/articleView?id=ai.generative_ai_session_trace_data_governance.htm&language=en_US&type=5)**  
    Use Data Cloud Data Governance to protect sensitive data by setting up dynamic data masking and field-specific data exclusion policies. Grant access to the impacted Data 360 objects according to an access policy.
-   **[Agent Platform Tracing](https://help.salesforce.com/s/articleView?id=ai.generative_ai_platform_trace.htm&language=en_US&type=5)**  
    This tracing capability provides comprehensive visibility into the actions and performance of Agentforce Agents, capturing crucial telemetry data across various services. By leveraging Data 360, users can unify this trace data with session information to create detailed reports. These reports are invaluable for monitoring Key Performance Indicators (KPIs), identifying performance bottlenecks, and quickly pinpointing the root cause of issues, ultimately enhancing the reliability and efficiency of Agent implementations.


# Monitor Agent Guardrails

Monitor instruction adherence and task resolution for your agents.

-   **[Instruction Adherence](https://help.salesforce.com/s/articleView?id=ai.agent_guardrails_instruction_adherence.htm&language=en_US&type=5)**  
    Instruction adherence is an agent guardrail that evaluates how well your agents interpret subagent instructions when generating responses.
-   **[Task Resolution](https://help.salesforce.com/s/articleView?id=ai.agent_guardrails_task_resolution.htm&language=en_US&type=5)**  
    Task resolution is an agent guardrail. It evaluates how well your agents interpret the user's intent, as expressed in a given conversation, and how well it resolves the task.


# Monitor Agentforce Session Log Events

Monitor log events captured during AI agent sessions in the AI Agent Session Log data model object (DMO).

## AI Agent Session Log DMO

[AiAgentSessionLog](https://developer.salesforce.com/docs/data/data-cloud-dmo-mapping/guide/c360dm-si-aiagentsessionlogdmo-dmo.html) is a Data 360 DMO that captures details about structured log events emitted during AI agent sessions. It captures informational, warning, debug, and error events. Use this data to analyze run-time behavior, troubleshoot failures, and trace issues across single-agent and multi-agent flows.

AiAgentSessionLog has these attributes.

Field Reference
| Field Label | Field DEVELOPER Name | Data Type | Description |
| --- | --- | --- | --- |
| `AI Agent Session Log Id` | `Id` | Text | Primary key |
| `AI Agent Session` | `AiAgentSessionId` | Foreign key | Foreign key to `AiAgentSession`. Required. |
| `AI Agent Interaction` | `AiAgentInteractionId` | Foreign key | Foreign key to `AiAgentInteraction`. Nullable. |
| `AI Agent Interaction Step` | `AiAgentInteractionStepId` | Foreign key | Foreign key to `AiAgentInteractionStep`. Nullable. |
| `Telemetry Trace` | `TelemetryTrace` | Text | Shared identifier used for implicit joins on TraceId among DMOs (`AiAgentInteraction`, `TelemetryTraceSpan`, `AiAgentSessionLog`). Nullable. |
| `Telemetry Trace Span` | `TelemetryTraceSpanId` | Foreign key | Foreign key to `TelementryTraceSpan`. Nullable. |
| `Cause Log` | `CauseLogId` | Foreign key | Self-FK. Immediate wrapped or underlying cause. Entries can reference a log entry in a different session. Populated only when `LogLevel` is `ERROR` or `FATAL`. |
| `Root Cause Log` | `RootCauseLogId` | Foreign key | Self-FK. Deepest known cause (denormalized). Entries can reference a log entry in a different session. Populated only when LogLevel is `ERROR` or `FATAL`. |
| `Log Date Time` | `LogDateTime` | Datetime | Timestamp of the log event. |
| `Log Level Type` | `LogLevelType` | Text | Log level. Values: `DEBUG` | `INFO` | `WARNING` | `ERROR` | `FATAL` |
| `Category` | `Category` | Text | Contextual domain of the log entry. Examples: Tool, LLM, Retrieval, Guardrail, Auth, HTTP, Delegation, Platform, Lifecycle, Performance |
| `Code` | `Code` | Text | Structured code for the event. For errors: user-facing error code (consistent with Salesforce existing codes). For non-errors: event type identifier (examples: `TOOL_INVOCATION_START`, `LLM_RESPONSE_RECEIVED`). |
| `Description` | `Description` | Text | Short, human-readable summary of the issue. |
| `Detailed Description` | `DetailedDescription` | Text | Structured JSON payload with diagnostics. Schema varies by `Category` and `LogLevelType`. |

## Error Codes for Agentforce Session Logs

The `Code` field in `AIAgentSessionLog` captures a standardized error code that identifies what happened when an Agentforce agent session encountered an issue during that session. This section describes valid values for `Code`, grouped by where it occurs in the agent's execution. Use this information to monitor, filter, and troubleshoot agent behavior.

![Note](https://sf-zdocs-cdn-prod.zoominsoftware.com/tdta-ai-generative_ai-264-0-0-production-enus/fc2f2f57-79fe-4598-a5e0-089f9b72c638/images/icon_note.png)

Note This list reflects the current error codes. Salesforce may add new codes as agent capabilities expand. Any changes to existing error codes (for example, if an error code is removed or repurposed) are documented.

**How Code Relates to Category and LogLevel**

Use `Code` with these fields on the same record:

-   `Category`—which part of the agent pipeline raised the issue (for example, planning, tool execution, or model gateway).
-   `LogLevel`—how severe the event is (`DEBUG`, `INFO`, `WARNING`, `ERROR`, `FATAL`).
-   `Code`—specifically what occurred.

**Agent Step Execution Errors**

| Code | Meaning | Typical Severity | Recommended Action |
| --- | --- | --- | --- |
| `ACTION_EXECUTION_FAILED` | An agent action (tool or flow invocation) failed to complete. | ERROR | Check the action's own logs or response for the underlying failure. Try again if transient. |
| `LLM_STEP_FAILED` | A model-reasoning step in the agent's plan failed. | ERROR | Review the prompt or step configuration. Check for model gateway issues in the same session. |
| `STEP_EXECUTION_FAILED` | A generic plan step failed outside of the other two categories. | ERROR | Inspect the session transcript for the failing step. |

**Agent-to-Agent (A2A) Delegation Errors**

| Code | Meaning | Typical Severity | Recommended Action |
| --- | --- | --- | --- |
| `A2A_BAD_REQUEST` | The delegating agent sent a malformed request to another agent. | ERROR | Check the calling agent's configuration or payload. |
| `A2A_UNAUTHORIZED` | The receiving agent rejected the request due to permissions. | ERROR | Verify permission sets and sharing between the delegating and receiving agents. |
| `A2A_TIMEOUT` | The receiving agent didn't respond in time. | WARNING | Try again. Check the load on the receiving agent. |
| `A2A_SYSTEM` | An internal system error occurred during delegation. | ERROR | Try again. Contact Salesforce Support if it doesn't resolve. |

**Planning Errors**

| Code | Meaning | Typical Severity | Recommended Action |
| --- | --- | --- | --- |
| `PLANNER_INVALID_AGENT_DSL` | The agent's plan definition was malformed. | ERROR | Review the agent's subagent and action configuration. |
| `PLANNER_AGENT_NOT_FOUND` | The plan referenced an agent that doesn't exist or isn't active. | ERROR | Confirm that the agent is active and correctly referenced. |
| `PLANNER_SESSION_NOT_FOUND` | The plan referenced a session that has expired or doesn't exist. | WARNING | Check session lifecycle and timeout settings. |

**Model (LLM) Gateway Errors**

| Code | Meaning | Typical Severity | Recommended Action |
| --- | --- | --- | --- |
| `PLANNER_LLM_GATEWAY_TIMEOUT` | The model gateway didn't respond in time. | WARNING | Try again. Check the model gateway status. |
| `PLANNER_LLM_GATEWAY_RATE_LIMIT` | The model gateway rejected the request due to rate limiting. | WARNING | Reduce the request volume or request a limit increase. |
| `PLANNER_LLM_GATEWAY_SERVICE_UNAVAILABLE` | The model gateway service was unavailable. | ERROR | Try again. Check for a service-wide incident. |

**Cross-functional / System Errors**

| Code | Meaning | Typical Severity | Recommended Action |
| --- | --- | --- | --- |
| `CIRCUIT_BREAKER_OPEN` | A downstream dependency is failing repeatedly. Short circuits requests to protect the system. | WARNING | Wait and try again. Check the status of the dependent service. |
| `RATE_LIMIT_EXCEEDED` | The session exceeded an allowed request rate. | WARNING | Reduce request volume. |
| `UNEXPECTED_ERROR` | An unclassified internal error occurred. | ERROR | Try again. Contact Support with the session ID if it recurs. |

# Get Started with Agent Monitoring

## Learning Objectives

After completing this unit, you’ll be able to:

-   Explain how you can use agent activity observations and measurements to improve agent outcomes.  
    
-   Describe the range of agent metrics you can use to quantify agent activity.  
    

## Before You Start

Before you start this module, consider completing this recommended content.

-   [Introduction to Agentforce Builder](https://trailhead.salesforce.com/content/learn/modules/introduction-to-agent-builder)  
    
-   [Agentforce Testing Tools and Strategies](https://trailhead.salesforce.com/content/learn/modules/agentforce-testing-tools-and-strategies)  
    

## Measure and Improve Outcomes with Agent Monitoring

Agentforce Monitoring is the suite of tools that gives you deep visibility into AI agent interactions.

-   **Agent Analytics:** A broad view of agent sessions with insights into how the agent is behaving in production. Agent Analytics reveals agent performance by showing you interaction latency, usage patterns, and performance metrics such as overall quality scores and success rates. Analytics helps answer questions like, “Is my agent working as expected?” and “Where and how can I improve it?”  
    
-   **Sessions & Intents:** Intent-level details for closer inspection. An LLM groups similar user goals across sessions into intents. Move beyond whole-session summaries and find cases where the agent was inaccurate, misleading, or off-topic, or where configured actions did not run as expected.  
    

When your agents are active, comprehensive information is collected about what they’re doing and how well they’re doing it. Use these tools with this data to:

-   Spot agent trends and patterns.  
    
-   Filter and drill into sessions, including sessions that led to underperforming outcomes.  
    
-   Audit and debug agents’ behavior.  
    
-   Uncover and classify reasons for underperforming outcomes.  
    
-   Identify action items to address underlying causes.  
    

After you implement and test your improvements, you deploy and monitor an improved version of your agent that delivers better outcomes with higher user satisfaction.

# Monitoring in the Agent Development Lifecycle (ADLC)

The ADLC moves through the Ideate, Build, Test, Deploy, and Monitor phases in an iterative cycle of continuous agent improvement.

![Agent Development Life Cycle (ADLC).](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/agent-analytics-and-monitoring/get-started-with-agent-monitoring/images/41825d57e487591f6f6a7e64d0691448_kix.htlep7mn96wv.png)

A successful AI solution starts in the Ideate phase with establishing measurable, outcome-based goals (also known as KPIs) by which to measure success. For example, for a service agent, your business goals could be to maximize case deflections (exceed 80%), minimize escalations to humans (below 25%), and minimize abandonment (users giving up on the agent, below 5%). Your business goals inform all phases in the ADLC: how you design and build your AI solution, what and how you test it before deployment, and how you monitor it after it’s launched.

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

For an end-to-end walkthrough of the steps to design and implement an agent according to the ADLC framework, see the [Agentforce Implementation Guide for Customer-Facing Agents](https://help.salesforce.com/s/articleView?id=ai.agent_resources.htm&type=5).

## Agent Observability Drives Continuous Improvement

Observability is the practice of measuring and understanding your agent’s behavior in action. Observability particularly applies in the Test and Monitor phases. In both phases you:

-   Observe your agent in action.  
    
-   Measure outcomes as defined by your goals.  
    
-   Compare the results with your goals.  
    
-   Take action to improve the agent as needed.  
    

These phases differ in important ways.

-   Testing helps you observe your agent in the lab. You subject it to well-designed test cases and test data. You preview and bulk test it at scale so that you can detect, diagnose, and fix issues before you release it to production. For more information, check out [Agentforce Testing Tools and Strategies](https://trailhead.salesforce.com/content/learn/modules/agentforce-testing-tools-and-strategies).  
    
-   Monitoring exposes your agent to real-world conditions that can exercise it in diverse and unexpected ways. You observe your agent over time to detect trends and meaningful patterns. The insights you gain from monitoring your agent in the field can show you where to make your agent more resilient, reliable, and effective in producing the results you want.  
    

## Measurement Categories in the Monitor Phase

In the Monitor phase, agent activity is observed, measured, and calculated across many dimensions, including:

-   **Effectiveness**, such as rates (%) of case deflections  
    
-   **Usage**, such as the number of unique sessions  
    
-   **Quality**, such as knowledge retrieval scores  
    
-   **Health**, such as error rates  
    
-   **Trust**, such as instruction adherence rates  
    
-   **User satisfaction**, such as thumbs up/down (Employee Agent only)  
    
-   **Voice**, such as interruption rates  
    

## How Agent Data Is Collected and Stored

Data collection begins when you turn on Agentforce Session Tracing, Audit and Feedback, and Knowledge/RAG Quality Data and Metrics in your org. You also need to install analytics apps for individual agent types. For prerequisites and instructions, review [Set Up Agent Analytics](https://help.salesforce.com/s/articleView?id=ai.generative_ai_agent_analytics_setup.htm&type=5).

Activity logs are captured for every turn and event across all your agent sessions. Measurements and scoring data are collected, calculated, and aggregated in a unified Data 360 data model. Analytics data flows from multiple sources:

-   **Session tracing**, which captures a step-by-step view of what happened during a conversation—inputs, decisions, actions taken, and outputs. These details show you why your agent behaved a certain way.  
    
-   **Audit and feedback data**, such as knowledge retrieval scores.  
    
-   **Trust Layer scores**, such as toxicity and instruction adherence.  
    

## Improve Customer Service for Excursion Bookings

Like many boutique resorts, Coral Cloud Resorts offers a full range of excursions for guests who want to explore fun activities during their stay. Water activities like snorkeling and scuba diving are the most popular, along with land-based adventures like cycle and culture tours. Excursions at Coral Cloud Resorts have proven to be so popular—and profitable—that the excursion staff is swamped and unable to keep up with demand.

Director of Business Intelligence at Coral Cloud Resorts, Alex Wu, helped drive the decision to add agents to his company. Using the agent development lifecycle (ADLC) framework, Alex planned, designed, built, tested, and deployed a new Excursion Booking agent to help improve and scale customer service for excursions. The agent handles information requests and manages reservations.

In the planning phase, Alex established the top goals for evaluating the new agent.

-   Deflect information inquiries and booking requests by 50%.  
    
-   Reduce the escalation rate from 100% (no agent) to 50%.  
    

By providing an easy-to-use system with a conversational interface, Alex hopes to deliver better outcomes for guests and increase bookings for the resort. Now that it’s running in production, he’s eager to monitor how well the agent performs with users. We follow Alex to see how he uses analytics to monitor his agent and combine that information with other tools to improve agent performance.

## Up Next

In the next unit, you explore the Agent Analytics dashboards and learn how to filter sessions, drill into quality scores, spot trends, and identify where your agent needs improvement.

## Resources

-   [_Salesforce Help_: Agent Analytics](https://help.salesforce.com/s/articleView?id=ai.generative_ai_agent_analytics.htm&type=5)
-   [_Salesforce Help_: Agent Optimization](https://help.salesforce.com/s/articleView?id=ai.generative_ai_optimize.htm&language=en_US&type=5)
-   [_Salesforce Help_: Agentforce Session Tracing](https://help.salesforce.com/s/articleView?id=ai.generative_ai_session_trace.htm&type=5)
-   [_Salesforce Help_: Einstein Audit and Feedback Data](https://help.salesforce.com/s/articleView?id=ai.generative_ai_feedback.htm&type=5)
-   [_Salesforce Help_: Einstein Trust Layer: Designed for Trust](https://help.salesforce.com/s/articleView?id=ai.generative_ai_trust_arch.htm&type=5)

# Monitor Agent Metrics and Scores

## Learning Objectives

After completing this unit, you’ll be able to:

-   Navigate to Agent Analytics in Agentforce Studio.  
    
-   Identify the dashboards, tabs, filters, and dimension views available in Agent Analytics.  
    
-   Interpret metrics on the Overview and Performance Insights tabs.  
    

## What’s Agent Analytics?

Agent Analytics provides visualization and drill-down tools that help you identify and investigate meaningful trends and patterns across all your agent sessions. Explore different levels of detail, from highly granular data to aggregated insights and trend analysis of agent performance over time.

## Launch Agent Analytics in Agentforce Studio

Director of Business Intelligence at Coral Cloud Resorts, Alex Wu, is eager to check up on his newly deployed Excursion Booking agent in Agent Analytics. He decides to learn how to use the app so that he’s prepared to investigate the results as the data is collected.

1.  From the App Launcher, search for and select **Agentforce Studio**.  
    
2.  Select **Agents**.  
    
3.  In the Explorer, under **Observe & Optimize**, select **Analytics**.  
    

![Explorer in Agentforce Studio with Analytics selected under Observe & Optimize.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/agent-analytics-and-monitoring/monitor-agent-metrics-and-scores/images/7a17f65e4f27382415a2c470ea1b7225_kix.pjc1sd5m6pq5.png)

The Observe & Optimize section includes:

-   **Analytics:** Opens the performance dashboards for the selected agent app.  
    
-   **Sessions & Intents** (expand **Optimization**): Opens a table of individual sessions for transcript auditing, intent comparison, and tagging.  
    

## Navigate the Agent Analytics Dashboard

After you select the agent type, the Agent Analytics dashboard displays metrics for that agent type. Dashboards are powered by Tableau Next. Metrics can vary by agent type. Here’s an example dashboard for a Service Agent.

![Agent Analytics dashboard showing metrics for the Service Agent.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/agent-analytics-and-monitoring/monitor-agent-metrics-and-scores/images/5975c5783539b9679a71f4b064f4cc8d_kix.ncnzcdmu5pw3.png)

### Filter the Dashboard Data

The filter bar scopes the data that’s displayed on the dashboard. Filtering focuses your visualization on just the area you want to explore: all agents or a specific one, the time window to display, channels, and modality (for example, text, voice, or both).

![Filter Bar to focus data on the Agent Performance dashboard by agent, timeframe, channel, and modality.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/agent-analytics-and-monitoring/monitor-agent-metrics-and-scores/images/15b195c884a22a8ffb71b50408aa2be8_kix.5352hcglz8oq.png)

## Explore Agent Performance

The Overview tab shows you headline KPIs, period-over-period trend cards, and outcome charts. Start here to get a high-level picture and aggregated agent performance metrics at a glance.

![Overview tab shows headline metrics with trend charts and a line chart of outcomes over time.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/agent-analytics-and-monitoring/monitor-agent-metrics-and-scores/images/19df4f77f1efe8f30dfce0a3b133270b_kix.a8zt5susm6gc.png)

### Dimension Tabs

Analytics data are categorized by dimension. Select a dimension tab, such as Quality or Health, to view its KPI set and charts.

### Explore Effectiveness Metrics

Select the Effectiveness tab to see KPI cards with period-over-period change indicators. You’ll see a multi-agent trend line chart and a Session Outcome stack bar chart.

-   **Deflection Rate****:** Share of sessions that ended without escalation to a support representative or another agent  
    
-   **Escalation Rate****:** Share of sessions that escalated to a support representative or another agent  
    
-   **Abandonment Rate****:** Share of sessions that timed out or ended without engagement (default timeout: 2 hours)  
    
-   **Engagement Rate****:** Share of sessions in which the user received a reply tied to an agent-triggered action. A session is counted as engaged only when at least one action was triggered  
    
-   **Success Rate****:** Share of interactions that included action steps and completed without errors  
    
-   **Task Resolution Rate****:** Share of sessions evaluated as fully resolved by the Trust Layer Task Resolution detector  
    

Further down the page, notice the aggregated statistics for session outcomes in a stacked bar chart.

![Session outcomes by time period: deflected, escalated, abandoned, and ambiguous.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/agent-analytics-and-monitoring/monitor-agent-metrics-and-scores/images/4a863078974e96cef8bf12ec6e137a36_kix.wa0xoeptf8kk.png)

-   **Deflected****:** Ended at user’s request (user resolved)  
    
-   **Escalated****:** Transferred to a customer service representative or a different agent  
    
-   **Abandoned****:** Timed out or dropped  
    
-   **Ambiguous****:** Could not be classified clearly  
    

### Toggle Between the Metric Card and Table View

Select **Metric Card** to view the tile layout (large cards with graphics and details). Select the metric to change the graph.

![The Metric Card view follows performance for the selected metric over time.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/agent-analytics-and-monitoring/monitor-agent-metrics-and-scores/images/cdbb1a2c986c3624d0fe115f03fb4923_kix.u651q9do9gd.png)

Select **Table View** to explore a compact table layout, which shows all metrics at once.

![Table View shows all metrics at one across the selected time frequency.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/agent-analytics-and-monitoring/monitor-agent-metrics-and-scores/images/041053fb538da2900636696eed304451_kix.urg4944amvdk.png)

### Change Trend Chart Granularity

The Date Filter changes the granularity (Day/Week/Month) of the charts.

### Explore Usage Metrics

Select the Usage tab to see usage metrics.

-   **Unique Sessions:** The number of distinct sessions recorded within a defined timeframe. A session includes the entire exchange between a user and an agent.  
    
-   **Unique Interactions:** The number of distinct user and agent interactions recorded within a defined timeframe. One interaction is considered as a user’s request plus an agent’s response.  
    
-   **Unique Users:** The number of distinct users interacting with the agent within a defined timeframe.  
    
-   **Average Interactions Per Session:** The average number of interactions per session.  
    

### Explore Quality Scores

Select the Quality Scores tab to see dimension scores generated by an external LLM evaluator.
|**Score** |**Scale** |**What It Measures** |
| --- | --- | --- |
| Quality Score | 1–5|Overall relevance of the agent’s response to the user’s request|
|Answer Faithfulness\*|0–1|How closely the response adheres to grounded source data (knowledge base articles)|
|Answer Relevance\*|0–1|Relevance of the response to the user’s question|
|Context Relevance\*|0–1|Whether the agent retrieved the correct data source to answer the question|

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

These scores require Audit and Feedback, and Knowledge/RAG Quality Data and Metrics, to be turned on in Setup.

### Explore Health Metrics

Select the Health tab to review agent health metrics.

-   **Error Rate****:** Percentage of interactions in which the agent encounters an error in processing or responding  
    
-   **Session Duration (seconds)****:** The session duration in seconds  
    
-   **Agent Interaction Duration (seconds)****:** The time it takes the agent to respond to the user’s request  
    

### Explore Trust Metrics

Select the Trust tab to explore evaluations in the Einstein Trust Layer.

-   **Adherence Response Rate****:** Percentage of responses where instruction adherence meets the high-adherence threshold.  
    
-   **Average Agent Toxicity Score (0–1)****:** Average toxicity detector score for agent output—lower is better.  
    

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

Trust metrics require that these features are turned on: Audit and Feedback and related Trust Layer features.

### Voice Metrics

Select the Voice tab to see voice metrics.

-   **Interruption Rate****:** Percentage of interactions with interruptions.  
    

## Explore Performance Insights (Breakdowns)

The Performance Insights tab lets you compare performance across segments—which subagents, intents, or actions are driving good or bad outcomes. Use this tab to investigate which segments are underperforming.

1.  Select the **Performance Insights** tab.  
    
2.  In the Breakdowns panel, choose a segment type: Subagents, Intents, or Actions.  
    
3.  Use **Select Subagent** (or the equivalent selector) to filter to a specific segment, or leave it set to **All**.  
    
4.  In **Select Metric**, choose the measure you want to compare.  
    
5.  Review the horizontal bar chart. Each row represents a segment (for example, a subagent like Billing & Payments or Order Status), with the bar length representing the metric value and color coding indicating performance level (green=favorable, orange/red=needs attention).  
    

This example shows subagents grouped by Unique Sessions, with Average Quality Score selected as the comparison metric. Each agent lists its subagents (Billing & Payments, Order Status, Returns & Refunds, and so on) alongside bar charts showing both session volume (blue bars) and quality score (green/orange bars).

![The Performance Insights tab breaks the data down into subagents, intents, and actions for the selected metric.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/agent-analytics-and-monitoring/monitor-agent-metrics-and-scores/images/3d72d12e6671b15b242493c2615db2cc_kix.jr2w11o1vtfa.png)

## Explore User Sentiment in the Employee Agent Dashboard

In the Employee Agent dashboard, choose User Satisfaction to see counts of positive user feedback (thumbs up) and negative user feedback (thumbs down). Both metrics show multi-agent trend lines so you can track sentiment over time across agents.

## Alex Investigates Agent Performance in Agent Analytics

Two weeks after deploying the Excursion Booking Agent, Alex Wu opens Agent Analytics to check progress toward his goals of deflecting 50% of inquiries and reducing escalations to 50%. He wants to get a baseline understanding of how the agent is performing in production.

1.  Alex logs in to **Agentforce Studio**.  
    
2.  He navigates to **Observe & Optimize** | **Analytics**.  
    
3.  He selects the **Service Agent** type and changes the Timeframe in the Filter Bar to the Last 30 Days.  
    

On the **Agent Performance** tab, he immediately reviews the **Effectiveness** dimension tab.

-   **Deflection Rate:** 38% (below the 50% goal)  
    
-   **Escalation Rate:** 42% (close to target but needs improvement)  
    
-   **Abandonment Rate:** 27% (concerning - this means over 1 in 4 users are giving up)  
    
-   **Engagement Rate:** 58%  
    
-   **Success Rate:** 71%  
    

Alex studies the Aggregated Effectiveness Metrics trend chart, which shows all four metrics over the 30-day period. He notices the abandonment rate (orange line) has been climbing steadily during the past 2 weeks, while the deflection rate (blue line) has plateaued. The Session Outcome stacked bar chart at the bottom reveals that abandoned sessions (red segments) increased significantly during weekends, particularly showing spikes on March 15–16 and March 22–23.

### Drilling into Performance Insights

Alex switches to the Performance Insights tab to identify which parts of the agent are causing abandonments. In the Breakdowns panel, he selects:

-   **Segment type:** Subagents  
    
-   **Metric:** Deflection Rate  
    

The horizontal bar chart displays performance for each subagent:

-   General FAQ: **Green bar** (deflection rate ~65%)  
    
-   Water Activities Booking: **Orange bar** (deflection rate ~32%)  
    
-   Land Tours Booking: **Green bar** (deflection rate ~58%)  
    
-   Pricing Information: **Yellow bar** (deflection rate ~45%)  
    

Alex changes the metric to **Abandonment Rate** and sees:

-   Water Activities Booking: **Red bar** (abandonment rate ~38%)  
    
-   General FAQ: **Green bar** (abandonment rate ~8%)  
    
-   Land Tours Booking: **Yellow bar** (abandonment rate ~15%)  
    

### What Has Alex Learned?

The Water Activities Booking subagent is significantly underperforming. It has:

-   The lowest deflection rate among all subagents  
    
-   The highest abandonment rate (38% versus average of 27%)  
    

This subagent handles scuba diving and snorkeling bookings—the resort's most popular and profitable excursions. The high abandonment rate means potential revenue is being lost.

From here, Alex writes a list of things to do.

-   Investigate the instructions in the Water Activities Booking subagent. Identify possible improvements that could result in better outcomes.  
    
-   Look at Quality scores for this subagent to understand response relevance. How well does the agent understand the user’s intent? How well does it return relevant results?  
    
-   Check Health metrics (latency) to see whether slow response times are contributing to abandonment.  
    
-   Schedule a meeting with the excursion desk manager to discuss what common questions guests ask that might not be getting answered by the Excursion Booking Agent.  
    

Alex discovers and fixes an ambiguous instruction in the Water Activities Booking subagent. Then he tests a new version of the agent in Agentforce Testing Center, deploys it, and monitors its performance for the next few weeks. He’s rewarded for his efforts with higher deflection rates and lower abandonment rates that align with his business goals.

## Up Next

What if the numbers underperform his goals? Alex can drill deeper into the data. Using Sessions & Intents, he can examine individual Water Activities conversations and investigate other possible patterns and causes. On to the next unit!

## Resources

-   [_Salesforce Help_: Agent Analytics](https://help.salesforce.com/s/articleView?id=ai.generative_ai_agent_analytics.htm&type=5)

# Investigate Agent Sessions and Intents

## Learning Objectives

After completing this unit, you’ll be able to:

-   Navigate the Sessions & Intents page.  
    
-   Distinguish between processed and unprocessed sessions.  
    
-   Explain the intent pipeline process.  
    
-   Filter and analyze individual agent-user conversations using session metadata.  
    
-   Interpret session details.  
    
-   Use the Session Page trace to debug agent behavior step by step.  
    

## Launch Sessions & Intents

In Sessions & Intents, you drill down into individual sessions and agent-user interactions at the intent level.

1.  From the App Launcher, find and select **Agentforce Studio**.  
    
2.  Select **Agents**.  
    
3.  In the Explorer, under Observe & Optimize, select **Sessions & Intents**.  
    

![The Session & Intents page shows processed and unprocessed sessions.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/agent-analytics-and-monitoring/investigate-agent-sessions-and-intents/images/006117c7be6358acb42749b4a8e84fbf_kix.i4ksiylsg20s.png)

## Filter the Session & Intents Page

Just as you learned in Agent Analytics, use the filter bar to scope the data you see on the Session & Intents page.

![Filter Bar to Focus Data on the Session & Intents Page](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/agent-analytics-and-monitoring/investigate-agent-sessions-and-intents/images/7b502ff052595ebcdbca784413377c07_kix.frruk6f7rv7r.png)

## Navigate Processed and Unprocessed Sessions

The Sessions & Intents page has two tabs: Processed Sessions and Unprocessed Sessions.

### Processed Sessions

Sessions that the system has completely processed using two sequential pipelines:

-   **Intent Pipeline**: Analyzes closed sessions and extracts intents—what the user was trying to accomplish within a set of turns. Intent generation typically takes 4–5 hours after a session closes.  
    
-   **Clustering Pipeline**: Groups similar intents across sessions, assigns cluster tags, and makes tagged intents visible in the session trace. Clustering runs weekly. New intent tags for a new topic area won't appear until the weekly clustering run.  
    

Processed sessions are ready for analysis. The system has extracted user intents, assigned cluster tags, and calculated quality scores. Click on any intent in the trace to open its Interaction Summary with performance metrics, triggered subagents and actions, and Quality Score Reasoning.

**Note:** Some intents don’t get tagged. The clustering pipeline creates a cluster tag only when it finds at least 10 semantically similar intents.

### Unprocessed Sessions

These are sessions that are still active, recently closed, or haven’t been completely processed. A blue banner indicates when session processing is in progress. Use the Trace tab to investigate a session immediately without waiting for processing to complete.

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

If you can’t find a session in Processed Sessions, check Unprocessed Sessions—it may still be processing.

## Explore the Sessions Table

The Session table shows information about agent-user sessions. Each row represents an individual session.

![Sessions table for processed and unprocessed user sessions.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/agent-analytics-and-monitoring/investigate-agent-sessions-and-intents/images/d89a250cff1921be055fcb6b6a9752fb_kix.gpvjraqr367s.png)

-   **Session ID / Timestamp:** Unique identifier and time the session started.  
    
-   **Session Duration:** Total session duration.  
    
-   **Session Outcome:** Outcome of the session.  
    
-   **Custom Scorers** (Beta): Custom scorer labels and scores associated with the session.  
    
-   **Intent Summary:** LLM-generated summary of what the user was trying to accomplish.  
    
-   **Response Summary:** Summary of how the agent responded to the user’s request.  
    
-   **Subagents:** Which subagents were invoked during the session.  
    
-   **Actions:** Specific actions the agent ran (for example, Retrieve Knowledge, Get User, Authenticate User).  
    
-   **Intent Tag:** Cluster tag assigned to the intent (for example, Cancellation Request, Order Status); only tagged intents appear here. Untagged intents are blank.  
    
-   **Quality Score:** Color-coded score (High / Medium / Low) with a numeric value.  
    

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

Sessions created via email in real time are not reflected in the Sessions & Intents table

### Duration Metrics (Chat Only)

For Chat sessions only, the log shows:

-   Total session duration at the top of the transcript  
    
-   Per-response duration for each agent reply  
    
-   Processing time breakdown—time spent reasoning (understanding intent, planning next steps) versus taking actions (executing configured actions)  
    

## Explore Individual Conversations

Click the Session ID of the conversation you want to investigate.

![The Session Details page shows the chat session log on the left and the session overview on the right.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/agent-analytics-and-monitoring/investigate-agent-sessions-and-intents/images/b58aa9a1f70e6f5c4f7cf43a272fd068_kix.n6wm34g63tlc.png)

The top of the session page includes the session start timestamp, the unique Session ID, and a download transcript button.

### Explore the Chat Session Log (Left Panel)

The left panel shows the full conversation log between user and agent, with:

-   Timestamps on every message  
    
-   Color-coded bubbles—user messages on the right, agent messages on the left  
    
-   Quality badge on agent responses once processed (for example, Quality: High or Quality: Low in color)  
    
-   Agent completion time for each response (for example, Agent (Complete: 1 sec))  
    

For voice sessions, the left panel shows the voice session transcript alongside an integrated audio player with playback controls. Click play to listen to the recorded conversation while reading the transcript.

### Explore the Interaction Summary and Trace Tabs (Right Panel)

The right panel has two tabs: Interaction Summary and Trace.

The Interaction Summary provides a structured breakdown of what happened in a selected intent (moment).

-   **Agent Name:** The agent that handled this interaction.  
    
-   **Average Agent Latency:** Average response time for this intent (in milliseconds).  
    
-   **Total Interactions:** Number of turns in this intent.  
    
-   **Intent Duration:** How long this intent lasted (example: “1 min, 12 sec”).  
    
-   **Topics Triggered:** Subagents invoked (color-coded icons, example: “Order Management”).  
    
-   **Intent Tag:** Cluster tag for this intent (example: “Cancellation Request”).  
    
-   **Actions Triggered:** Specific actions executed (example: “Retrieve Knowledge”).  
    
-   **Quality Score:** Score badge—color-coded High/Medium/Low.  
    
-   **Quality Score Reasoning:** LLM explanation of why the score was assigned. For example: “The agent did not provide the user a detailed response about the Cancellation Policy.” This is the most actionable field for knowing exactly what to fix.  
    

The Trace tab shows a time-ordered record of every processing step the agent took, with the duration for each step. Use the trace to:

-   Follow the exact sequence of steps from user input to final response.  
    
-   See where time was spent (intent recognition, subagent routing, retrievals, variable updates, action execution).  
    
-   Identify where behavior diverged from what you configured in Agentforce Builder.  
    
-   Expand nested trace steps to drill into subagent delegation.  
    

Steps visible in the trace include:

-   Topic (subagent) identification  
    
-   Actions (labeled with action type and icon)  
    
-   Agent routing steps  
    
-   Variable updates  
    
-   Retrieval steps  
    
-   Response generation  
    

Each step shows a status indicator (green check=success) and timing.

## Alex Drills Deeper Into Agent Performance with Sessions & Intents

At Coral Cloud Resorts, Alex received feedback from guest services that visitors are confused by the agent’s cancellation policy answers.

### What Agent Analytics Reveals

Agent Analytics shows the Cancellation & Rescheduling subagent has a quality score of 2.8/5 and a 67% escalation rate across 423 sessions—the highest escalation rate of any subagent.

Alex navigates to the **Overview** | **Quality** dimension:

-   Overall Average Quality Score: 3.4/5  
    
-   Cancellation & Rescheduling: 2.8/5 (lowest)  
    

**Performance Insights** | **Subagents** (Escalation Rate metric):

-   Cancellation & Rescheduling: 67%  
    
-   Other subagents: 28–42% range  
    

**Quality sub-scores for Cancellation & Rescheduling:**

-   Answer Faithfulness: 0.54  
    
-   Answer Relevance: 0.68  
    
-   Context Relevance: 0.71  
    

The low Answer Faithfulness (0.54) suggests the agent is providing information that doesn't align with the actual knowledge base content.

### Deep Dive with Sessions & Intents

Alex navigates to **Sessions & Intents** and filters:

-   **Subagent:** Cancellation & Rescheduling  
    
-   **Session Outcome:** Escalated  
    
-   **Quality Score:** Low (1.0–3.0)  
    

He opens the top 10 escalated sessions.

#### Session #1—Quality Score: 2.2

**Chat Session Log:**

-   **User:** “If there's a hurricane warning, can I cancel my excursion?”  
    
-   **Agent:** “Our cancellation policy allows for free cancellation up to 48 hours before your scheduled excursion. After that, a 50% fee applies.”  
    
-   **User:** “But what about weather emergencies?”  
    
-   **Agent:** “You can reschedule your excursion up to 24 hours in advance for a $25 fee.”  
    
-   **User:** “That doesn’t answer my question about hurricanes.”  
    
-   **Agent:** “Let me connect you with our guest services team who can help with your specific situation.”  
    

**Interaction Summary tab:**

-   Answer Faithfulness: 0.42  
    
-   Quality score reasoning: _“_Agent provided generic policy information that did not address the weather emergency exception. The responses about 48-hour and 24-hour windows appear inconsistent.”  
    

**Trace tab shows:**

-   Action Retrieve Knowledge → Retrieved article: Excursion Cancellation Policy  
    
-   Agent generated response about 48-hour policy  
    
-   Action Retrieve Knowledge → Retrieved article: Rescheduling Guidelines  
    
-   Agent generated response about 24-hour rescheduling  
    
-   Agent escalated to a support representative  
    

**Session #2**—**Quality Score: 1.9**

Chat shows:

1.  User asks about canceling due to illness.  
    
2.  Agent provides the standard 48-hour cancellation policy.  
    
3.  User asks if there’s an exception for medical reasons.  
    
4.  Agent repeats the same policy.  
    
5.  User requests a support representative.  
    

The Trace tab shows the agent only retrieved the basic Excursion Cancellation Policy article and never searched for medical exception information.

**Session #3**—**Quality Score: 2.5**

-   User purchased travel insurance and wants to know how it affects cancellations.  
    
-   Agent describes the standard cancellation fees.  
    
-   User frustrated that insurance wasn't considered.  
    
-   Escalated.  
    

### Investigating the Knowledge Base

Alex clicks through to read the actual knowledge articles referenced in the traces. He notices there are two separate articles, but neither adequately covers:

-   What happens if there’s a hurricane warning but the resort hasn’t officially canceled.  
    
-   Medical emergency cancellations.  
    
-   How travel insurance affects cancellations (only mentioned for rescheduling).  
    

The knowledge base has fragmented and incomplete information.

-   **Multiple overlapping articles** create confusion (cancellation versus rescheduling policies separated).  
    
-   **Missing exception scenarios** (guest illness, family emergencies, travel insurance coverage for cancellations).  
    
-   **Ambiguous weather policy** (only covers resort-initiated cancellations, not guest-initiated due to weather concerns).  
    

The agent’s low Answer Faithfulness score (0.54) occurs because it's synthesizing responses from multiple incomplete articles, creating inconsistent answers.

### Implementing the Fixes

Alex works with the legal and guest services teams to create a single, comprehensive article: Complete Excursion Cancellation & Rescheduling Policy that addresses the issues in the knowledge base. Alex archives the old fragmented articles to ensure the agent retrieves only the new comprehensive article, preventing conflicting information.

He also updates the Cancellation & Rescheduling subagent instructions to ask users about travel insurance, their reason for canceling, and to ground answers in the complete policy document. He tests a new version of the agent in Agentforce Testing Center and deploys it into production. Three weeks later, Alex checks the metrics.

**Agent Analytics–Cancellation & Rescheduling**

-   Quality Score: 4.3/5 (up from 2.8)  
    
-   Answer Faithfulness: 0.91 (up from 0.54)  
    
-   Escalation Rate: 28% (down from 67%)  
    
-   423 sessions in previous 30 days → 447 sessions (volume increased as users trust the agent more)  
    

**Sessions & Intents Validation**

Alex samples 15 recent cancellation sessions and finds:

-   The Trace tab shows consistent retrieval of the single comprehensive article.  
    
-   Weather-related questions are answered correctly with specific policy details.  
    
-   Medical and insurance questions are handled appropriately.  
    
-   Quality score reasoning notes: Agent provided accurate, complete information directly addressing the user's specific cancellation scenario.  
    

The consolidated knowledge base eliminated contradictions and filled coverage gaps, dramatically improving both deflection rates and quality.

## Wrap It Up

You learned how to use Agentforce Monitoring tools—including Agent Analytics dashboards and Sessions & Intents—to observe, measure, and understand your agents' real-world performance across multiple dimensions like effectiveness, quality, and health. You explored how to filter data, interpret metrics, investigate individual sessions, and trace agent behavior step-by-step to identify underperforming areas. Now you can apply these monitoring skills to detect trends, uncover root causes of issues, and continuously improve your agents to deliver better outcomes aligned with your business goals.

## Resources

-   [_Salesforce Help_: Analyze Data with Agent Optimization](https://help.salesforce.com/s/articleView?id=ai.generative_ai_optimize_use.htm&type=5)


# Monitor Agent Health

## Learning Objectives

After completing this unit, you'll be able to:

-   Explain the value of proactive, automated health monitoring for AI agents.  
    
-   Create alerts with practical thresholds for standard metrics and custom scores.  
    
-   Investigate alert notifications by drilling into associated sessions and conversations.  
    
-   Use findings from alerts to prioritize and implement targeted agent improvements.  
    

Alex Wu has already used Agent Analytics and Sessions & Intents to improve the Excursion Booking agent at Coral Cloud Resorts. Deflection rates are up, and escalations are down. But as usage keeps climbing, Alex knows that point-in-time analysis is no longer enough.

He now needs an early-warning system that can flag performance problems before guests notice them. That means moving from reactive troubleshooting to proactive health monitoring.

## Why Monitor Agent Health Proactively?

As AI agents handle more real customer traffic, failures can spread quickly. A latency spike during peak booking hours can increase abandonment in minutes. A sudden jump in errors can affect multiple subagents before anyone opens a dashboard.

Agent Health Monitoring helps teams detect these silent failures in near real time so they can act fast.

With health monitoring in place, Alex and his team can:

-   Catch emerging issues before they become guest-facing incidents.  
    
-   Reduce mean time to detection by using automated notifications.  
    
-   Focus investigations on the exact sessions that triggered concern.  
    
-   Prioritize fixes using measurable signals instead of assumptions.  
    
-   Build confidence that the agent stays within acceptable service levels over time.  
    

This workflow supports the monitor phase of the agent development lifecycle (ADLC): observe, investigate, improve, and then monitor again.

## Set Up Alerting for Agent Health

Alex opens Agentforce Studio and navigates to **Observe & Optimize** to configure alerts for the Excursion Booking agent.

From there, he can monitor both:

-   **Standard metrics**, such as error rate and interaction duration (latency)  
    
-   **Custom metrics**, such as a resort guest user satisfaction rate that’s based on a custom user sentiment score  
    

## What an Alert Includes

Each alert is tied to:

-   A selected standard or custom metric  
    
-   A specific AI agent  
    
-   A threshold condition (for example, at or above, or at or below)  
    
-   A threshold value that represents the boundary of acceptable performance  
    

When monitored data breaches the threshold, the system sends a notification so Alex can investigate quickly.

## Start with Baselines, Then Set Thresholds

Alex doesn't pick threshold values at random. He uses a repeatable process.

-   Review at least 30 days of historical data for the selected metric.  
    
-   Identify the normal operating range.  
    
-   Define what is acceptable for guest experience with business stakeholders.  
    
-   Set a threshold where normal variation ends and action should begin.  
    
-   Revisit and tune the threshold as agent behavior changes.  
    

For example, if the Excursion Booking agent’s interaction duration usually ranges from 1.8 to 4.6 seconds, and guest services reports that delays above 5 seconds feel disruptive, Alex can set an alert threshold at **5 seconds (at or above)**, as shown in the orange horizontal line.

![Threshold of 5 (orange line) as upper bound for agent interaction duration.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/agent-analytics-and-monitoring/monitor-agent-health/images/fa32e43b587ee04a026bb75aafb781f9_kix.1x5nriw49bur.png)

He repeats this logic for other health-sensitive measures. The result is a practical alert set that reduces noise while still surfacing meaningful risk.

## Example Alert Plan for Alex

Alex creates two starter alerts.

![Create Alert modal with selections for metric, agent, condition operator, and threshold value.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/agent-analytics-and-monitoring/monitor-agent-health/images/a980efd4c78d1a2ce32ea0528b06ab29_kix.qdhmsbmfkzqp.png)

-   **Agent Interaction Duration:** Triggers when average interaction duration exceeds his service target.  
    
-   **Elevated Error Rate:** Triggers when response processing errors rise above normal range.  
    

Together, these alerts cover speed and reliability.

## Investigate Notifications and Find Root Cause Fast

Two weeks later, Alex gets an alert notification: **Agent Interaction Duration** exceeded threshold for the Excursion Booking agent.

He follows a simple investigation path.

## Step 1: Open the Notification

In **Observe & Optimize | Alerts**, Alex opens the notification list, which arrived via email or an in-app notification. For Metric, he filters by **Agent** **Interaction Duration**.

![Notifications subtab that shows a list of notifications that the user received via email.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/agent-analytics-and-monitoring/monitor-agent-health/images/ab14e3d65561361ab0359244a15275a5_kix.jt2cyalkxm9u.png)

Each notification provides key context.

-   Alert name  
    
-   Metric or score involved  
    
-   Agent  
    
-   Trigger timestamp  
    

He then selects the triggered alert he wants to investigate. This immediately narrows his scope to the interactions linked to the alert condition.

![Selected notification that shows a list of sessions associated with the notification condition.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/agent-analytics-and-monitoring/monitor-agent-health/images/337e74a6c6454d8fd7d1549ef7cd08ec_kix.x49lrgudmorh.png)

## Step 2: Drill into Associated Sessions

Alex scans for patterns across session rows, such as:

-   Repeated subagent involvement  
    
-   Similar user intents  
    
-   Shared session outcomes (for example, abandonment or escalation)  
    
-   Time clustering that suggests incident windows  
    

## Step 3: Open Individual Conversations

Alex opens several session IDs and reviews the conversation flow.

![Conversation associated with the selected session.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/agent-analytics-and-monitoring/monitor-agent-health/images/deabfabcb18377bee83057db52f5dbca_kix.l6c6zndkur4y.png)

On each session page, he checks:

-   Turn-by-turn exchange between guest and AI agent  
    
-   Agent response timing  
    
-   Trace details for where processing slowed down or failed  
    
-   Subagent routing and Agent action execution patterns  
    

This lets him separate symptoms from causes.

## From Alert to Action

The latency alert is concentrated in sessions that involve the Water Activities Booking subagent, especially during weekend spikes.

By reviewing conversations and traces, Alex finds a repeatable pattern.

-   Guests ask for availability and pricing in one request.  
    
-   The subagent invokes multiple Agent actions in sequence.  
    
-   One retrieval step often times out, delaying the full response.  
    
-   Delays lead to drop-offs before booking is completed.  
    

Alex now has enough evidence to prioritize fixes.

-   Simplify the subagent's decision path for combined availability-plus-pricing requests.  
    
-   Update instructions so the subagent asks one clarifying question before triggering multiple actions.  
    
-   Add fallback behavior when retrieval latency crosses an internal limit.  
    
-   Retest the updated behavior in Agentforce Testing Center, deploy, and continue monitoring.  
    

After deployment, Alex watches the same latency and abandonment alerts. Over the next few weeks, notifications decrease, response times stabilize, and weekend booking completion improves.

That's proactive observability in practice: detect early, investigate quickly, improve continuously.

## Best Practices for Health Monitoring

-   Start with a small, high-value alert set and expand gradually.  
    
-   Use historical data plus business thresholds, not guesses.  
    
-   Review alert signal quality often; tune thresholds to reduce noisy notifications.  
    
-   Pair each alert with a clear owner and response playbook.  
    
-   Investigate sessions and conversations before changing Prompt templates, subagents, or Agent actions.  
    
-   Track post-fix metrics to validate that changes improved outcomes.  
    

## Wrap Up

You learned how to monitor AI agent health proactively with automated alerts, threshold-based detection, and focused investigation workflows. You saw how Alex Wu used notifications to pinpoint problematic sessions, drill into conversation-level behavior, and implement targeted improvements that reduced customer impact.

With Agent Health Monitoring, you can move from reactive debugging to continuous, data-driven reliability management for your AI agents.

## Resources

-   [_Salesforce Help_: Monitor Agent Health](https://help.salesforce.com/s/articleView?id=ai.agent_monitor_health.htm&type=5)
-   [_Salesforce Help_: Agent Analytics](https://help.salesforce.com/s/articleView?id=ai.generative_ai_agent_analytics.htm&type=5)
-   [_Salesforce Help_: Customize Agentforce Observability](https://help.salesforce.com/s/articleView?id=ai.generative_ai_agent_observability_customization.htm&type=5)
-   [_Salesforce Help_: Agentforce Session Tracing](https://help.salesforce.com/s/articleView?id=ai.generative_ai_session_trace.htm&type=5)
-   [_Salesforce Help_: Analyze Data with Agent Optimization](https://help.salesforce.com/s/articleView?id=ai.generative_ai_optimize_use.htm&type=5)
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTgxMTA1MjYyOSw4ODE1MTA5OTEsNzMwOT
k4MTE2XX0=
-->