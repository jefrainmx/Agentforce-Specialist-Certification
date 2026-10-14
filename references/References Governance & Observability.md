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

## Monitoring in the Agent Development Lifecycle (ADLC)

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
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTYxNTg5MzU4OSw4ODE1MTA5OTEsNzMwOT
k4MTE2XX0=
-->