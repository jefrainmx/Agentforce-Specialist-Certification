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


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEwNDkxMDc0NzAsNzMwOTk4MTE2XX0=
-->