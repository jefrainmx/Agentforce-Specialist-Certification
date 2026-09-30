# Given a scenario, test an agent using Testing Center.
## Introduction
The Agentforce Testing Center enables efficient testing of agents by allowing a large number of utterances to be evaluated in a single test. This reduces overall testing time and facilitates the quick activation of agents. Users can access the Testing Center in Agentforce Studio and leverage batch testing to execute multiple test cases simultaneously. The testing process involves creating a test suite, defining test conditions, selecting test data, and selecting scorers. The test results display both successful and failed utterances, which helps fine-tune instructions, subagents, and actions. Running tests consumes Einstein Requests and Data Cloud credits, and should be conducted in a sandbox to prevent unintended CRM data modifications. The Testing Center supports up to 10 tests in a 10-hour timeframe and 1,000 test cases per test.
### Agentforce Testing Center
#### Testing Process
The testing process involves creating a test suite, defining test conditions, selecting test data, and selecting scorers.
#### Considerations
Certain considerations and limitations apply to the use of the Testing Center. For example, running tests consumes Einstein Requests and Data Cloud credits.
#### Batch Testing
The Testing Center can be accessed in Agentforce Studio to quickly test a large number of utterances in a single test for a particular agent. 

## Agentforce Testing Center
The Testing Center can be utilized to test a large number of utterances in a single test, which reduces the testing time and allows the quick activation of agents.
### ACCESS
The Testing Center can be accessed by navigating to the Tests section in Agentforce Studio.
### BATCH TESTING
The Testing Center allows the use of batch testing to quickly test a large number of utterances in a single test.
### TESTING PROCESS
The testing process consists of the following steps:
1) Create a Test Suite with test cases using a template.
2) Define Test Conditions.
3) Select Test Data.
4) Select Scorers.
### SUBAGENTS & ACTIONS
Multiple subagents and actions can be tested at the same time. The subagent and action API names should be used for the expected values in the CSV file; they can be found in the Agentforce Builder.
### TEST RESULTS
The test results show which test casespassed and failed. A failed utterance can be retested in the Preview panel of Agentforce Builder to identify what caused the failure. The detailed data can be used to fine-tune the instructions, actions, or topics.
### EDITIONS & ADDONS
The Testing Center is available in Enterprise, Performance, Unlimited, and Developer Editions. The add-on licenses required for the Testing Center vary by agent type.
### LIMITATIONS
Up to 10 tests can be run at once in a 10-hour timeframe, and each test can have up to 1000 test cases.
### CONSIDERATIONS
Running tests consumes Einstein Requests and possibly Data Cloud credits. Tests should only be run in a  sandbox environment since testing agents can modify CRM data.

## Scenarios & Solutions
### Scenario 1
Cosmic Electronics is considering using the Agentforce Testing Center to test the behavior of certain AI agents in Salesforce. The company’s Agentforce Specialist needs to identify any considerations related to its usage for running tests.
### Solution 1
With regard to using the Agentforce Testing Center, it is important to consider that running tests consumes Einstein Requests and possibly Data Cloud credits. Tests should only be run in a  sandbox environment since testing agents can modify CRM data.

### Scenario 2
The Agentforce Specialist at Cosmic Computers is preparing a CSV file with test cases to test a large and repeatable number of utterances using the Agentforce Testing Center. They need to specify the expected output to ensure the testing accurately reflects the agent’s functionality.
### Solution 2
While a large number of utterances can be tested using the Agentforce Testing Center, it is important to note that the topic and action API names should be used for the expected values in the CSV file that contains test cases. These API names can be found in the Agent Builder.

## References:
[Agentforce Testing Center](https://help.salesforce.com/s/articleView?id=ai.agent_testing_center.htm&type=5)
[Agentforce Testing Center](https://trailhead.salesforce.com/content/learn/modules/agentforce-agent-testing)

# Explain how Testing Center evaluations work.
## Introduction
Testing Center helps validate Agentforce agents by running repeatable automated tests against many user inputs. A test case starts with an utterance and includes one or more expected outcomes, such as the expected subagent, expected actions, or expected response. During a test run, the agent processes each utterance, and Testing Center compares the actual subagent, actions, and response against the expected values. Results are summarized as pass/fail evaluations, giving teams a structured way to identify routing issues, missing actions, incorrect expectations, or response-quality gaps before deployment. Testing should be performed in a sandbox because tests can consume requests and credits and may modify CRM data.

### Testing Center Evaluations
#### Test Suite
A test suite is a collection of test cases for a selected agent version.
#### Actual Results
Testing Center records the actual subagent, actual actions, and agent response.
#### Evaluation Results
Testing Center compares expected and actual outcomes and returns pass/fail results.
#### Troubleshooting
Failed tests are reviewed in Testing Center and retested in Agentforce Builder Conversation Preview.
#### Test Execution
During testing, the agent processes the utterance and chooses a subagent, actions, and response.
#### Test Case
A test case contains an utterance plus expected outcomes, such as expected subagent, actions, or response. 

## Testing Center Evaluation Fundamentals
### Testing Center
Testing Center provides a repeatable way to validate agent behavior at scale instead of relying only on manual conversation testing.
#### BATCH TESTING
Automated batch testing runs many utterances to verify how the agent behaves across expected, unexpected, and edge-case requests.
#### TEST SUITES
Test suites can be reused over time so agent changes can be checked repeatedly as subagents, actions, instructions, and guardrails evolve.

### Manual Testing vs Automated Testing
Manual testing is useful for troubleshooting, while automated testing is better for repeatable validation across many conversation variations.
#### MANUAL TESTING
Manual testing in Agentforce Builder Conversation Preview helps inspect a single utterance and see how the agent selected subagents, actions, and responses.
#### AUTOMATED TESTING
Automated testing in Testing Center runs many utterances in parallel and provides structured pass/fail results for evaluation.

### Test Case Structure
Each test case defines what the agent receives and what Testing Center should check after the agent responds.
#### TEST CASE
A test case includes an utterance, which is the user input or question the agent must handle. 
#### EXPECTED OUTCOMES
A test case can include expected outcomes, such as Expected Subagent, Expected Actions, and Expected Response.

### Expected Outcomes
Expected outcomes tell Testing Center which parts of the agent’s behavior should be evaluated for each utterance.
#### API NAMES
Expected Subagent and Expected Actions use API names instead of display labels. 
#### RESPONSE
Expected Response describes what the agent’s response should coveror accomplish. 

### Required Test Criteria
Testing Center test cases must include enough expected criteria for the platform to evaluate the utterance meaningfully.
#### REQUIRED COLUMNS
The Utterance column is required, along with at least one additional expected-outcome column.
#### FAILURES
Empty expected values are treated as failures, so test criteria should be completed intentionally.

### Test Suites
AI agents can be tested by creating test suites using the Testing Center in Agentforce Studio.
![TS1](https://raw.githubusercontent.com/jefrainmx/Agentforce-Specialist-Certification/refs/heads/main/images/Screenshot%202026-09-30%20141959.png)
![TS2](https://raw.githubusercontent.com/jefrainmx/Agentforce-Specialist-Certification/refs/heads/main/images/Screenshot%202026-09-30%20142022.png)
![TS3](https://raw.githubusercontent.com/jefrainmx/Agentforce-Specialist-Certification/refs/heads/main/images/Screenshot%202026-09-30%20142043.png)
![TS4](https://raw.githubusercontent.com/jefrainmx/Agentforce-Specialist-Certification/refs/heads/main/images/Screenshot%202026-09-30%20142103.png)
![TS5](https://raw.githubusercontent.com/jefrainmx/Agentforce-Specialist-Certification/refs/heads/main/images/Screenshot%202026-09-30%20142124.png)



## Evaluation Execution and Results
### Running Evaluations
A Testing Center evaluation runs test cases against one selected agent and records what the agent actually selected and returned. 
#### TEST SUITE
Each test suite runs against one agent version, and the agent processes each utterance as it would during a conversation.
#### ACTUAL OUTPUTS
Testing Center records actual outputs, including selected subagent, executed actions, and generated agent response.

### Evaluation Summary Metrics
Testing Center summarizes evaluation quality with pass percentages across the major parts of the agent’s behavior. 
#### SUBAGENT EVALUATION
Subagent Evaluation Pass % shows how often the agent selected the expected subagent. 
#### ACTION & RESPONSE EVALUATION
Action Evaluation Pass % and Response Evaluation Pass % show how often actions and responses matched expectations.

### Response Evaluation
Response evaluation checks whether the agent’s actual answer matches the expected response intent defined in the test case. 
#### EXPECTED RESPONSE
The expected response should describe the required outcome or content, not every possible wording variation.
#### RESPONSE FAILURE
A response can fail when the agent omits required information, asks for confirmation unexpectedly, or returns content that does not match the expected result. 

### Troubleshooting Failed Evaluations
Failed evaluations should be investigated by reviewing both the test criteria and the agent’s actual behavior.
#### RETESTING
Failed utterances can be retested in Agentforce Builder Conversation Preview to inspect the selected subagent, launched actions, and generated response.
#### FIXING THE ISSUE
The utterance, expected criteria, instructions, actions, filters, or guardrails can be updated, and then the test suite can be rerun. 

### Running Tests
A test can be run for the selected agent after generating test cases.
![*Running Test*](https://raw.githubusercontent.com/jefrainmx/Agentforce-Specialist-Certification/refs/heads/main/images/Screenshot%202026-09-30%20144832.png)


### Responses & Evaluations
After running a test, agent responses and evaluations can be checked.
![*Responses & Evaluations*](https://raw.githubusercontent.com/jefrainmx/Agentforce-Specialist-Certification/refs/heads/main/images/Screenshot%202026-09-30%20144857.png)


## Evaluation Considerations
### Test Coverage and Quality
Strong evaluation depends on a test set that covers the full range of expected and unexpected user behavior.
#### GOOD TEST DATASET
A good test dataset includes enough volume and diversity to cover common requests, edge cases, invalid inputs, and negative tests. 
#### USING AI
AI-generated test cases can help create many synthetic interactionsbased on the agent’s subagents and actions. 

### Sandbox, Data, and Credits
Testing Center evaluations should be run in a safe environment because they can consume usage and affect data.
#### CONSUMPTION
Running tests consumes requests and credits, even in sandbox environments.
#### DATA
Tests should be run in a sandbox because agent testing can modify CRM data.

### Limits and Parallel Runs
Testing Center supports scalable testing, but evaluation planning should account for platform limits. 
#### TEST JOBS
Up to 10 test jobs can run at once in a 10-hour time frame.
#### TEST CASES
A test can include up to 1,000 test cases, so large suites may need to be organized by feature, agent version, or release cycle. 

## References:
[Agentforce Testing Center](https://trailhead.salesforce.com/content/learn/modules/agentforce-agent-testing)
[Test Your Agent](https://help.salesforce.com/s/articleView?id=ai.agent_parent_test.htm&type=5)


# Identify the considerations for deploying an agent from sandbox to production.
## Introduction
Deploying an Agentforce agent from a sandbox to productionenvironment ensures its availability for end-users. This process involves metadata deployment using Change Sets or Metadata API. All the relevant metadata components, such as GenAiPlanner, Einstein Bot, and Bot Version, must be included in the deployment. Additionally, service agents typically require the Embedded Messaging component for deployment to an Experience Cloud site. After deployment, the agent must be activated in the Agent Builder to make it available to users. Finally, stakeholders and end-users must be informed, with proper training and documentation provided.
### Agent Deployment
#### Metadata Deployment
All the metadata components related to the agent, such as GenAiPlanner, Einstein Bot, and Bot Version, must be included in the deployment. An embedded service deployment is required for a service agent.
#### Activation
After deploying all the metadata components for an agent to the target production org, the agent must be activated in the Agent Builder to make it available to users.
#### Change Sets
Change Sets can be utilized to deploy an agent. An outbound change set can be created in a sandbox. An inbound change set can be validated and deployed in production.

## Agent Deployment
### Agent Deployment
Once an Agentforce agent has been created and thoroughly tested within a sandbox environment, it must be deployed to production to make it available to users.
#### CHANGE SETS
Change sets can be utilized for deploying an agent from sandbox to production. The process comprises the following steps:
1. Create an outbound change set in a sandbox. 
2. Add all the relevant metadata components.
3. Upload the outbound change set to the production org.
4. Validate and deploy the inbound change set in the production org.
#### METADATA COMPONENTS
All the metadata components related to the agent, such as the agent planner (GenAiPlanner), associated topics (GenAiPlugin), agent actions (GenAiFunction), prompt templates (GenAiPromptTemplate), flows, and Apex classes, must be identified and added to the deployment.
#### BOT METADATA
When deploying a new agent, the associated Einstein Bot and Bot Versionmust be deployed along with the GenAiPlanner.
#### METADATA API
Metadata API can also be used to retrieve agent metadata from a sandbox using a tool such as Salesforce CLI. The retrieved metadata can be deployed to the production org.
#### SERVICE AGENT DEPLOYMENT
An embedded service deployment must be created to deploy a service agent to an Experience Cloud site. The Embedded Messaging component must be added to the site in production, and the site must be published.
#### ACTIVATION
After deploying all the metadata components and confirming that the agent is working as expected in the production org, it must be activated in the Agent Builder to make it available to users.
#### COMMUNICATION
Stakeholders and end-users must be informed about the new agent deployment. Necessary training or documentation must be provided.

### Change Set for Agent Deployment
When deploying an agent using an Outbound Change Set, all the associated metadata componentsmust be added to the change set in the sandbox environment.
![Change Set for Agent Deployment](https://raw.githubusercontent.com/jefrainmx/Agentforce-Specialist-Certification/refs/heads/main/images/Screenshot%202026-09-30%20152235.png)

## References:
[How to deploy Agentforce AI Planner metadata](https://docs.gearset.com/en/articles/10406930-how-to-deploy-agentforce-ai-planner-metadata)
[Deploy change sets from sandbox to production](https://help.salesforce.com/s/articleView?id=000382677&type=1&utm_source=chatgpt.com)
[Activate or Deactivate Your Agent](https://help.salesforce.com/s/articleView?id=ai.copilot_setup_activate_deactivate.htm&type=5)
[Distribute a Service Agent](https://developer.salesforce.com/workshops/agentforce-workshop/service-agents/3-distribute-service-agent)
[GenAiPlanner](https://developer.salesforce.com/docs/atlas.en-us.api_meta.meta/api_meta/meta_genaiplanner.htm)

# Identify the considerations for deploying a template from sandbox to production.
## Introduction
Deploying a prompt template is not only about moving the prompt text. A prompt template can depend on template type settings, Salesforce objects and fields, flows, Apex classes, prompt templates, Data 360 resources, retrievers, model configurations, permissions, and the calling experience that executes it. Some of these assets can be moved through standard release processes, while others must be created or configured directly in the production org. After deployment, the intended template version, model configuration, grounding resources, permissions, and runtime execution path must be validated before users, agents, flows, apps, or APIs rely on the template in production.
### Deploying a Prompt Template from Sandbox to Production
#### Build in Sandbox
The template is created, grounded, previewed, revised, and tested with representative records or inputs.
#### Review Dependencies
Objects, fields, flows, Apex classes, retrievers, model configurations, permissions, and calling experiences are identified.
#### Prepare Production
Target-org features, licenses, model access, provider access, external credentials, and data resources are configured.
#### Deploy Supported Assets
Supported template metadata and dependencies are moved through the organization’s release process.Activate TemplateThe intended template version is activated after deployment and review. 
#### Complete Manual Setup
Unsupported or environment-specific dependencies are manually recreated or connected in production. 
#### Test Runtime Execution
The template is tested from the same experience that will execute it in production.

## Deployment Readiness
### Template Inventory
A deployment should begin by identifying exactly what the template uses and how it will run in production.
#### TEMPLATE DETAILS
Templatename, templatetype, activeversion, inputs, target object, target field, and model configuration should be documented before the deployment of the prompt template.
#### RUNTIME CALLER
The calling experience should be identified for the prompt template. This can be Prompt Builder, Field Generation, Sales Email, Flow, Apex, Connect API, or an Agentforce action.

### Template Type Considerations
The prompt template type affects what dependencies exist and how the template can be used after deployment.
#### TYPE-SPECIFIC DEPENDENCIES
Field Generation, Record Summary, Sales Email, and Flex templates can have different inputs, grounding resources, output behavior, and execution paths.
#### FLEX TEMPLATE LIMITS
Flex template metadata and related references require extra review because Salesforce documents import/export limitations for Flex templates and related artifacts.

### Grounding Dependencies
A prompt template must be deployed with or reconnected to the resources that ground the prompt.
#### SALESFORCE RESOURCES
Objects, fields, related lists, record snapshots, flows, Apex classes, and prompt-template resources must exist and be accessible in production. 
#### DATA & RETRIEVAL RESOURCES
Data 360 resources, Agentforce Data Libraries, search indexes, retrievers, and Knowledge settings may require separate setup.

### Flow and Apex Dependencies
Templates that use Flow or Apex require both deployment and runtime access validation. 
#### FLOW ACCESS
Referenced flows must exist in production, be activated when required, and be executable by the user or process that runs the template. 
#### APEX ACCESS
Apex classes must be deployed with required test coverage and granted to the correct users, profiles, permission sets, or runtime context.

### Model Configuration Dependencies
The selected model configuration must exist and be allowed in the production org. 
#### MODEL AVAILABILITY
The production org must have access to the model configuration referenced by the template. 
#### CUSTOM LLM MATCHING
When a template uses a custom or BYOLLM configuration, the matching model configuration must exist in production with the expected name.

### Permission and Access Dependencies
A template can deploy successfully but still fail if the running user or process lacks access at runtime. 
#### TEMPLATE EXECUTION ACCESS
Users, automations, agents, or integrations that execute the template need the appropriate permissions to run prompt templates. 
#### UNDERLYING RESOURCE ACCESS
The runtime context must also have access to the records, fields, flows, Apex, Knowledge, Data 360 assets, and external resources used by the prompt template. 

## Target Org Preparation
### Environment-Specific Setup
Some dependencies are environment-specific and should be configured directly in production before or after deployment.
#### ORG CONFIGURATION
Model provider access, model visibility, external credentials, named credentials, connected apps, Data 360 connections, and data librarie scan differ between sandbox and production.
#### RESOURCE AVAILABILITY
Newly created custom objects or fields may not appear immediately in Prompt Builder, so production verification may require refreshing the session or logging out and back in. 

### Retriever and Search Index Considerations
Retriever-backed templates require special planning because some retrieval assets are not moved automatically. 
#### RETRIEVER SETUP
If a template uses a retriever, the retriever and its search index should be verified or recreated in the production org before runtime testing.
#### DEPLOYMENT GAP
Salesforce notes that change sets and Metadata API deployments don’t include retriever or search index metadata for Einstein Search retrievers, so those assets must be manually created in the target org.

### Deployment Method
Supported template assets should move through the organization’s normal release process, while unsupported assets need manual setup. 
#### RELEASE PROCESS
Supported prompt template assets and dependencies should be moved through controlled release tools such as change sets, packages, Metadata API-based tools, or CI/CD. 
#### MANUAL CONFIGURATION
Environment-specific or unsupported dependencies should be listed in a deployment checklist so they are not missed in production. 

## Activation and Validation
### Activation and Versioning
Deployment does not automatically guarantee that the intended template version is active and ready for production use.
#### ACTIVE VERSION
The intended prompt template version should be activated in production before users, automations, apps, APIs, or agents execute it.
#### VERSION REVIEW
Only the reviewed and approved version should be active, and older versions should not remain active unintentionally. 

### Runtime Execution Testing
Testing should verify both Prompt Builder preview behavior and the real production execution path. 
#### PROMPT BUILDER PREVIEW
Preview testing confirms that production records, inputs, merge fields, grounding resources, and model configuration resolve as expected.
#### REAL CALLER TEST
The template should also be tested from the actual caller, which can be a Flow, Apex, Connect API, Agentforce, Field Generation, Sales Email, or Record Summary.

### Common Deployment Issues
Most deployment or runtime issues come from missing dependencies, inactive assets, model mismatches, or access gaps.
#### DEPLOYMENT FAILURES
Deployment can fail when the target org is missing referenced objects, fields, flows, Apex classes, prompt templates, retrievers, or model configurations.
#### RUNTIME FAILURES
Runtime execution can fail when the template is inactive, a flow is inactive, a model is unavailable, or the running context lacks access to data or automation.

### Governance Considerations
Prompt template deployment should be controlled through release governance because not all prompt-template changes are tracked in Setup Audit Trail.
#### CHANGE TRACKING
Template changes should be documented through release notes, source control, or deployment records because creating or updating prompt templates is not tracked in Setup Audit Trail.
#### PRODUCTION APPROVAL
The deployment should include evidence of preview testing, runtime testing, model review, grounding review, permission review, and business approval. 

## References:
[Packaging Considerations for Prompt Templates](https://help.salesforce.com/s/articleView?id=ai.prompt_builder_considerations_packaging.htm&type=5)
[Prompt Builder Limitations](https://help.salesforce.com/s/articleView?id=ai.prompt_builder_limitations.htm&type=5)
[enter link description here](https://help.salesforce.com/s/articleView?id=ai.prompt_builder_activate_deactivate_templates.htm&type=5)
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTY0MTYxOTc1NCwtMjIwMTc1MTU0LC03OD
M3NDIzMzAsLTI2OTUwMjcxOCw5OTY5MzU1OTUsMjEyMDE4MTcy
OSwtODE0MzQwMjYwLDE5MDA2NDAzNiwtMTI5ODIzMTAwOCwxNj
Y5MDY4OTkzLDYyNDY5OTUzMCwxODA0NzgyNjQ4LC0yOTI1OTky
NjcsMjA2MTgyOTIwLC0xMzEyNTQ2OTI2LC0xNDgzMTcyMTYwLD
EyMDQ4NzI5OTMsLTk3OTE4OTkwLC01NjU2NDc3ODksLTEyNjI4
Nzk2NDZdfQ==
-->