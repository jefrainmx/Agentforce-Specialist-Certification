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
Testing Center helps validate Agentforce agents by running repeatable automated tests against many user inputs. A test casestarts with an utterance and includes one or more expected outcomes, such as the expected subagent, expected actions, or expected response. During a test run, the agent processes each utterance, and Testing Center compares the actual subagent, actions, and response against the expected values. Results are summarized as pass/fail evaluations, giving teams a structured way to identify routing issues, missing actions, incorrect expectations, or response-quality gaps before deployment. Testing should be performed in a sandbox because tests can consume requests and credits and may modify CRM data.

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

#

## Evaluation Execution and Results





## Evaluation Considerations




# Identify the considerations for deploying an agent from sandbox to production.









# Identify the considerations for deploying a template from sandbox to production.

<!--stackedit_data:
eyJoaXN0b3J5IjpbNTQxNTcwNjM1LDEyMDQ4NzI5OTMsLTk3OT
E4OTkwLC01NjU2NDc3ODksLTEyNjI4Nzk2NDYsMTY3Njc3ODkz
MiwtMTQ2OTY4NTk2MF19
-->