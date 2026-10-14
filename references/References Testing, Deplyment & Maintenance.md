# Agentforce Testing Center

Build confidence in your AI agents and deliver seamless, effective interactions with thorough testing. Easily generate custom test scenarios and leverage our expert evaluation tools to assess response accuracy, conversation quality, subagent recognition, action execution, and knowledge retrieval. Identify issues early and fine-tune your agent’s behavior with precision.

![Important](https://sf-zdocs-cdn-prod.zoominsoftware.com/tdta-ai-generative_ai-264-0-0-production-enus/fc2f2f57-79fe-4598-a5e0-089f9b72c638/images/icon_important.png)

Important

-   Running tests consumes requests and credits. See [Considerations for Testing Center](https://help.salesforce.com/s/articleView?id=ai.agent_testing_center_considerations.htm&language=en_US&type=5).
-   Testing agents can modify CRM data. To avoid issues, be sure to use Testing Center only in your sandbox environment.

With Testing Center, you can quickly generate test cases from your agent’s core subagents and actions, create Q&A style tests from your knowledge content, or upload custom scenarios tailored to your specific needs. Because AI agents are non-deterministic, it's essential to test them across a wide range of scenarios to ensure consistent and accurate performance.

Testing Center supports large-scale batch testing through a range of evaluations. These include response accuracy, subagent and action validation, and key quality metrics such as completeness, coherence, conciseness, latency, and instruction adherence. By surfacing patterns and edge cases often missed in smaller-scale testing, you’ll get a fuller picture of your agent’s performance. With these insights, you can close performance gaps, refine subagent instructions, and continuously improve your AI agent’s responses.

-   **[Set Up and Run Tests in Agentforce Studio (Beta)](https://help.salesforce.com/s/articleView?id=ai.agent_studio_testing_center_setup_tests.htm&language=en_US&type=5)**  
    Use Testing Center in Agentforce Studio (Beta) to test AI agents or prompt templates at scale. Test agents by simulating conversations across many scenarios at once. Or, test prompt templates by running batch evaluations across many inputs. Apply scorers to quickly evaluate responses and identify quality issues.
-   **[Set Up and Run Tests in Setup (Legacy)](https://help.salesforce.com/s/articleView?id=ai.agent_testing_center_setup_tests.htm&language=en_US&type=5)**  
    Efficiently validate your agent’s performance at scale, whether you want to fast-track testing with AI-generated scenarios or manually craft and upload your own. You can generate realistic test cases for specific subagents and actions, or data linked through the Agentforce Data Library.
-   **[Use Test Results](https://help.salesforce.com/s/articleView?id=ai.agent_testing_center_use_test_results.htm&language=en_US&type=5)**  
    After a test run completes, review evaluation scores to identify where your agent or prompt template is falling short. Understand what each scorer measures, how scores are calculated, and what to do when results are low .
-   **[Considerations for Testing Center](https://help.salesforce.com/s/articleView?id=ai.agent_testing_center_considerations.htm&language=en_US&type=5)**  
    To use Testing Center, consider supported functionality, usage, limitations and allowances, limits, and other issues.

## See Also

-   [_Trailhead_: Agentforce Testing Tools and Strategies](https://trailhead.salesforce.com/en/content/learn/modules/agentforce-testing-tools-and-strategies)
-   [_Trailhead_: Agentforce Testing Center](https://trailhead.salesforce.com/en/content/learn/modules/agentforce-agent-testing)
-   [Agentforce Testing Center Considerations](https://help.salesforce.com/s/articleView?id=ai.agent_testing_center_considerations.htm&language=en_US&type=5)

# Trust Your Agents

## Learning Objectives

After completing this unit, you’ll be able to:

-   Explain the benefits of different types of testing.  
    
-   Describe how automated tests build confidence in your agents.  
    
-   Explain the difference between manual and automated testing.  
    

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

**New Agentforce Builder Generally Available!**

Agentforce has gotten an upgrade! In February 2026, the new agent building experience became generally available. **There is also a new Testing Center that is currently in Beta.** This badge uses the legacy builder for the second unit and the new builder for the third and fourth unit. To get started with the new builder now, complete the [Take a Tour of the New Agentforce Builder](https://trailhead.salesforce.com/content/learn/trails/get-ready-for-the-new-agentforce-builder) trail or read more in the [Agentforce documentation](https://help.salesforce.com/s/articleView?id=ai.agent_builder_intro.htm&type=5).

## Before You Start

If you’re new to Agentforce agents, we recommend taking these other badges first so you’ll be familiar with the terms in this badge.

-   [Agentforce Key Components: Quick Look](https://trailhead.salesforce.com/content/learn/modules/agentforce-agents-quick-look)  
    
-   [Agentforce Basics](https://trailhead.salesforce.com/content/learn/modules/einstein-copilot-basics)  
    
-   [Trusted Agentic AI](https://trailhead.salesforce.com/content/learn/modules/trusted-agentic-ai)  
    
-   [Agentforce Testing Tools & Strategies](https://trailhead.salesforce.com/content/learn/modules/agentforce-testing-tools-and-strategies)  
    

## Trust Is Our Number One Value

At Salesforce, trust is deeply rooted in everything we do. That’s why we rely heavily on testing. Apex tests are automatically run with every new deployment. Unit tests make sure each unit works as expected. Flows are tested to verify that everything functions as expected. To put it simply, testing is one of the best ways to ensure trust in our products and processes.

As a Salesforce admin, testing should also be a cornerstone to make sure everything runs smoothly in your org. You can test new processes in a dedicated sandbox. You can perform user acceptance tests (UAT) with large groups of users. And once you’ve verified everything through tests, you can deploy the new process to a production environment and monitor it to make sure everything is running smoothly.

## Test Agents for Trust

But what about the agents you’re creating with Agentforce? How do you make sure they’re as trustworthy and reliable as the rest of your Salesforce org?

The answer, again, is testing.

You learn a bit more about testing agents later in the module, but first take a look at some of the challenges you might encounter when testing agentic AI.

| **Challenge** |**What this sounds like** |
| --- | --- |
| Gen AI is nondeterministic producing different outputs for the same input on different runs|“Gen AI is so nondeterministic that I don’t have the right answer to test against.”|
|Manual testing is not scalable|“Given the subjective nature of Gen AI, I need to rely on manual testing that is not scalable.”|
|Safety and ethical concerns|“Generative AI can produce harmful or unintended outputs.”|
|Lack of standards|“Generative AI is still new, and there are no existing standards to follow.”|

If you start encountering these types of challenges, fear not. The Agentforce Testing Center is here to help.

## Say Hello to the Agentforce Testing Center

The Agentforce Testing Center is designed to help overcome the challenges you might encounter when building out your Agentforce, and helps you roll out trusted AI agents in a secure, repeatable way. Testing your agents in the Agentforce Testing Center is a critical step in creating trust in your AI agents.

The Agentforce Testing Center is designed with no-code testing tools to help you easily deploy trusted agents. The testing takes place in properly configured sandboxes to isolate testing from the production environment. You can also add more tests over time as your agents get updated or are given more actions. This means your agents continue to work as your business changes and grows.

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

Sandboxes now have access to Data 360 and Agentforce to allow for agentic testing.

## Testing Methods

There are two testing methods that are used to troubleshoot, verify, and maintain Agentforce agents: manual testing and automated testing.

### Manual Testing

Agentforce Builder allows for manual testing and troubleshooting while you build and update the agent. Simply use the Conversation Preview while in the builder to ask the agent a question. You can then view the response and see how it was created. This is a great way to troubleshoot your agents and verify that the correct processes are being called based on the questions. But testing this way takes a long time, and it’s challenging to test all the possible scenarios manually. It’s also difficult and time-consuming to repeat these tests when needed. This is where the Agentforce Testing Center really shines.

### Automated Testing

The Agentforce Testing Center lets you perform automated batch testing, which reduces the amount of testing time. Batch processing also lets ‌you test large numbers of user inputs. These inputs, or questions, are called utterances. An utterance might be something like, “Show me all the open opportunities for the ACME account.” There’s one utterance for every test execution. Combining multiple utterances with expected responses lets you build a batch of tests. You can use the tests over and over, adding to them as needed to ensure the agent continues to be trustworthy.

The Agentforce Testing Center also helps you do performance testing by running through a large series of tests at one time in a test environment. The Agentforce Testing Center can also use AI to generate hundreds of dynamic interactions. The Agentforce Testing Center runs tests automatically and in parallel to see what subagents and actions the agents choose. After looking at the test results, you manually test and troubleshoot in Agentforce Builder to adjust instructions and guardrails as needed. Automated testing saves time that would have been lost on manually testing many different variations of a conversation.

## Deploy with Confidence

Once testing is done, you can confidently deploy the agent to production without concerns of disrupting your business or corrupting your customers’ data. And you can deploy the changes by migrating them to your production environment with whatever tool you’re currently using, such as Change Sets, DevOps Center, and the Salesforce CLI that now supports Data 360 and Agentforce.

## Concerns and Limits

There are a few things to keep in mind when building and testing agents.

### Cost

Running tests, manually or automatically, consumes requests and credits the same as your customers using the agent. This is true even when done in a sandbox environment. Although testing itself has a cost, the cost of not testing can be much higher. To learn more, see [Agentforce and Generative AI Usage and Billing](https://help.salesforce.com/s/articleView?id=ai.generative_ai_usage.htm&type=5).

### Security

Testing agents can modify CRM data. To avoid modifying data unnecessarily, be sure to use the Agentforce Testing Center and Agentforce Builder tests only in your sandbox environment.

### Limits

Currently you can run up to 10 test jobs at once in a 10-hour time frame and have up to 1000 test cases per test.

Ready to take a closer look at testing and using test cases? Get hands-on practice in the next unit.

## Resources

-   [_Trailhead_: Explore Software Testing](https://trailhead.salesforce.com/content/learn/trails/explore-software-testing)
-   [_Salesforce Admins_: Ensuring AI Accuracy: 5 Steps to Test Agentforce](https://admin.salesforce.com/blog/2025/ensuring-ai-accuracy-5-steps-to-test-agentforce)
-   [_Trailhead_: Explore the Software Development Lifecycle for Salesforce Admins](https://trailhead.salesforce.com/content/learn/trails/explore-the-software-development-lifecycle-for-salesforce-admins)
-   [_Salesforce Help_: Data 360 in a Sandbox](https://help.salesforce.com/s/articleView?id=sf.c360_a_data_cloud_sandbox.htm&type=5)
-   [_Salesforce YouTube_: How to Test Agentforce](https://www.youtube.com/watch?v=HkTGrCmTISM)
-   [_Salesforce Help_: Agentforce and Generative AI Usage and Billing](https://help.salesforce.com/s/articleView?id=sf.generative_ai_usage.htm&type=5)
-   [_Video_: Test an AI Agent in Agentforce Testing Center](https://salesforce.vidyard.com/watch/UAtqTg67xRFS6jeAuZHt8w)



<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE5ODg3NzMwNjgsNzMwOTk4MTE2XX0=
-->