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


# Set Up Testing Criteria

## Learning Objectives

After completing this unit, you’ll be able to:

-   Explain how to get the testing template.  
    
-   Describe the different parts of test criteria.  
    

## What to Test

Testing is all about making sure you achieve an acceptable level of risk for your agent. After testing and troubleshooting your agent manually in Agentforce Builder, you’ve updated the instructions, subagents, actions, filters, and guardrails based on those test results. Now, you can use the Agentforce Testing Center to store those tests and run them over and over again.

Your customers put your agents to the test because they want answers to their every question. Hackers, and sometimes even employees, might try to get around restrictions and attempt to perform tasks or manipulate the model’s output in ways that the model wasn’t designed‌ for. These scenarios get added to the tests in the Agentforce Testing Center.

The trick is to try and predict the types of questions they’re going to ask. You should try to cover every angle, every possibility. That’s what you’re designing your tests to cover.

You can expect to find errors or at least issues as you start testing. Test for positive, expected results. Then test for negative, unexpected, or even invalid results. You want to be sure the agent responds correctly to even the most wrong requests. This is called positive and negative testing. It makes for a more robust test suite.

Here's an example: While testing an agent email input, test for the correct email response. This is testing the positive, valid, and expected behavior. But don’t stop there. Test for an incorrect email input to the agent, and be sure the correct response for that scenario is returned. This is testing the negative, invalid, and unexpected behavior.

While this can sound like a daunting task, doing your due diligence pays off in the end. Ready to get started?

## Sign Up for a Developer Edition Org with Agentforce Testing Center

To complete this module, you need a special Developer Edition org that contains Agentforce Testing Center and our sample data. Get the free Developer Edition and connect it to Trailhead now so you can complete the challenges in this module. Note that this Developer Edition is designed to work with the challenges in this badge, and might not work for other badges. Always check that you’re using the Trailhead Playground or special Developer Edition org that we recommend.

When you’re finished completing the step-by-step instructions, click **Check Challenge to Earn 500 Points** at the bottom of the page.

1.  Sign up for a free [Developer Edition org with Agentforce Testing Center](https://trailhead.salesforce.com/promo/orgs/agentforce-with-testing-center-for-trailhead).  
    
2.  Fill out the form:  
    -   For Email, enter an active email address.  
        
    -   For Username, enter a username that looks like an email address and is unique, but it doesn't need to be a valid email account (for example, yourname@example.com).  
        
3.  After you fill out the form, click **Sign me up**. A confirmation message appears.  
    
4.  When you receive the activation email (this might take a few minutes), open it and click **Verify Account**.  
    
5.  Complete your registration by setting your password and challenge question. Tip: Save your username, password, and login URL in a secure place—such as a password manager—for easy access later.  
    
6.  You are logged in to your Developer Edition.  
    

Now connect your new Developer Edition org to Trailhead.

1.  Make sure you're logged in to your Trailhead account.  
    
2.  In the Challenge section at the bottom of this page, click the org name and then click **Connect Org**.  
    
3.  On the login screen, enter the username and password for the Developer Edition you just set up.  
    
4.  On the Allow Access? screen, click **Allow**.  
    
5.  On the Want to connect this org for hands-on challenges? screen, click **Yes! Save it**. You are redirected back to the challenge page and ready to use your new Developer Edition to earn this badge.  
    

## Turn on Agentforce

1.  Click the **Setup** icon ![Setup icon](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/agentforce-agent-testing/set-up-testing-criteria/images/867ab858d6d60b2a0c069cd6a4bd0412_kix.nug2m8xjpv8.png) , then click **Setup**.  
    
2.  In the Quick Find box, search for and select **Einstein Setup**.  
    
3.  Verify Einstein is turned On. If it is already On, then turn it **Off** and then back **On** again.  
      
    ![Enable Einstein toggle.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/agentforce-agent-testing/set-up-testing-criteria/images/e68b4c5f319a831a01a9df1044cb6bef_kix.7rix2poun8mb.png)  
    

4.  Refresh your browser.  
    
5.  In the Setup Quick Find, search for and select **Salesforce Go**.  
    
6.  In the Search features... textbox, enter and select **Agentforce (Default)**.  
      
    ![Agentforce (Default) selected.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/agentforce-agent-testing/set-up-testing-criteria/images/86728a466857df76babf0706828f46da_kix.l401uwcbntn0.png)  
    

7.  Click **Get Started**.  
    
8.  Click **Turn On**.  
    
9.  Click **Turn On**.  
    

Agentforce is now enabled and the Agentforce Testing Center is available. But before we begin testing agents, let’s talk about permissions.

## Got Permissions?

The Developer Edition that you’re using for this badge already has the correct permissions set up, but what if they weren’t set up?

Part of creating trust is making sure only the right access is given. Working with Agentforce requires certain permissions. Not only for the Agentforce tools but also for the automations that agents might use. Like access to data, apps, and Apex. Let's start with getting access to Agentforce.

Control access to the Agentforce (Default) agent with type-specific permissions. To use Agentforce (Default), users must have the Access Agentforce Default Agent permission set group or be an admin with the Customize Application permission.

### Legacy Testing Center (Setup)

To work with the legacy Agentforce Testing Center in Setup, these permissions are needed:

-   Manage AI Agents AND the required permissions for your agent type AND System Admin profile  
    

_Or_

-   Customize Application AND System Admin profile  
    

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

Users who previously accessed Agentforce (Default) with only the Modify Metadata permission no longer have access.

### New Testing Center in Agentforce Studio (Beta)

The new Testing Center supports non-admin users. Add these permissions to an existing permission set — no System Administrator profile required:

-   Manage Agentforce Grids AND Manage Agentforce Testing  
    

## Create Test Cases

To start crafting the test cases, you need a place to store them so you can upload them into the Agentforce Testing Center. The Agentforce Testing Center has a template you can use to help get you on your way, so let’s start with that. Here’s how you get the testing template.

1.  From Setup, in the Quick Find box, search for and select **Testing Center**.  
    
2.  Click **New Test Suite**.  
    
3.  For Test Name, enter `templateCopy`.  
    
4.  For Select an Agent, select **Einstein Copilot** or **Agentforce (Default)** as the agent to test.  
    
5.  Click **Next**.  
    
6.  Click **Next**.  
    
7.  Click the **Upload Test Cases** tab.  
    
8.  Click the **Template** link.  
      
    ![](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/agentforce-agent-testing/set-up-testing-criteria/images/275d3db85d5a309e96a8a691c83a9648_kix.vzyn7vubqi5m.png)  
      
    This downloads a testing\_template.csv file to your device.  
    

9.  Close the New Test without saving. We were just looking for the testing template.  
    
10.  Open the file in a text editor to see the comma-separated values.  
     

![Example of the testing template file opened in an editor.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/agentforce-agent-testing/set-up-testing-criteria/images/75b1effa30e65ceafd7b141604415f28_kix.kwh6k0ggw364.png)

CSV files are one of the most common ways to store tabular data. Each value is separated with a comma, and each line is a data record, or a test case. The top row is the header designating what each column is used for by the Agentforce Testing Center. Each question or utterance and its expected outcomes are on a separate line.

Here’s a closer look at the first example from the testing\_template.csv file.

| **Utterance** |**Expected Subagent**|**Expected Actions** |**Expected Response**|
| --- | --- | --- | --- |
|Summarize account Acme| OOTBSingleRecordSummary| \['IdentifyRecordByName', 'SummarizeRecord'\] |summary of Account details are shown|

The _utterance_ is “Summarize account Acme” and is looking for the _expected subagent_ to be OOTBSingleRecordSummary. Notice that the subagent is the API name and not the Label for the subagent. Utterances are the questions or inquiries that the agent can get. Since an agent can have multiple subagents, the Expected Subagent is the subagent that the utterance should trigger to run.

Then it looks for the _expected actions_ from that subagent to be more than just a single action. There can be one or more actions used in generating a response. In this case the expected actions are set in a list denoted with brackets `[]Copy` and each action is separated with single quotes `‘’Copy` and a comma. The actions for this test case are 'IdentifyRecordByName' and 'SummarizeRecord'. Notice again that the actions in the list are the API names and not the Labels for the actions.

The last column is for the _expected response_ to the actions and is set as a description of what the response should cover.

Now let’s look at another example from the testing template file. The last line is similar to the first, but covers more data since it is looking for all open cases and activities of the Acme account in a certain data range.

| **Utterance** | **Expected Subagent**| **Expected Actions**| **Expected Response**|
| --- | --- | --- | --- |
| Summarize the open cases and Activities of Acme from sep to nov 2024| GeneralCRM| \['IdentifyRecordByName','QueryRecords','GetActivitiesTimeline'\]|summary of open cases and activities associated with timeline |

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

When creating your own test criteria, be sure to add utterances for positive and negative results and appropriate subagents, actions, and responses. Also, the only required columns are Utterance and at least one other column. Empty values are treated as failures.

## Run Your Tests

Once you have created your own test cases in a CSV file, you’re ready to initiate the test. Let’s see how to do that.

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

**Important!**

-   Running tests consumes requests and credits. See [Considerations for Testing Center](https://help.salesforce.com/s/articleView?id=ai.agent_testing_center_considerations.htm&type=5).  
    
-   Testing agents can modify CRM data. To avoid issues, be sure to use the Agentforce Testing Center only in your sandbox environment.  
    

1.  From Setup, in the Quick Find box, search for and select **Testing Center**.  
    
2.  Select **New Test Suite**.  
    
3.  For Test Name, enter `Test Agentforce v1Copy`. Note: When you create your own tests, use versions and be specific with the test name so they are easy to discern from other tests and versions.  
    
4.  For Description, enter `Test cases for Agentforce to verify account summaries and details.Copy`  
    Descriptions should be natural language describing the types of test cases being run.  
    
5.  For Select an Agent, select **Einstein Copilot** or **Agentforce (Default)**.  
    You can have more than one agent to select from. Each test only runs against one agent.  
    
6.  Click **Next**.  
    
7.  Test Conditions allows you to specify Context Variables that are used in your tests by the agents when they need input values. For this test, we won’t need to use them. Click **Next**.  
    
8.  Click the **Upload Test Cases** tab.  
    
9.  Click **Upload Files** and select the **testing\_template.csv** test file.  
      
    ![Screen shot of Upload Files window with testing\_template.csv file uploaded successfully.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/agentforce-agent-testing/set-up-testing-criteria/images/18aed6d29f750cf694757650806f7020_kix.mlbnz6oeutfn.png)  
    

10.  Click **Done**.  
     
11.  Click **Next**.  
     
12.  Click **Save**.  
     

Way to go! You created your first test in the Agentforce Testing Center. You also gained an insight into the working of the test file and test parameters. In the next unit, you take a look at using AI to generate your tests.

Make sure to click **Check Challenge to Earn 500 Points** before moving on to the next unit.

## Resources

-   [_Salesforce News & Insights_: Salesforce Introduces Agentforce Testing Center](https://www.salesforce.com/news/press-releases/2024/11/20/agentforce-testing-center-announcement/)
-   [_Trailhead_: The Einstein Trust Layer](https://trailhead.salesforce.com/content/learn/modules/the-einstein-trust-layer)
-   [_Salesforce Help_: Agentforce Testing Center Create a Test](https://help.salesforce.com/s/articleView?id=ai.agent_testing_center_create.htm&type=5)

# Use AI to Generate Tests

## Learning Objectives

After completing this unit, you’ll be able to:

-   Use AI to generate test cases.  
    
-   Execute batch testing in Agentforce Studio Tests.  
    

## Let AI Generate Your Tests

Manually creating a diverse and scalable set of test scenarios is time-consuming and complex. The Agentforce Studio Tests has the solution. You can now use AI to effortlessly generate hundreds of synthetic interactions based on the agent’s subagents and actions to be used as test cases. This helps ensure that your agents handle various customer interactions accurately.

Then you run those tests automatically in parallel to see what subagents and actions the agent chooses. From there, you can iterate by adjusting agent instructions and guardrails as needed—saving time that would have been lost on manually testing many different variations of a conversation. The result is a faster time to testing and a faster time to a more trusted agent that you feel confident deploying.

A good-quality test case dataset has three quality attributes.

-   **Volume:** A sufficient number of test cases to ensure comprehensive coverage of different scenarios and edge cases.  
    
-   **Diversity:** A wide range of inputs, contexts, and variations to test the AI agent’s adaptability across real-world use cases.  
    
-   **Quality:** Well-defined, accurate, and relevant test cases aligned with the AI agent’s objectives.  
    

To complete this unit, you’ll need to use the special Developer Edition org you created in the last unit. When you’re finished following the step-by-step instructions, click **Check Challenge to Earn 500 Points** at the bottom of the page.

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

**Important!**

-   Running tests consumes requests and credits. See [Considerations for Testing Center](https://help.salesforce.com/s/articleView?id=ai.agent_testing_center_considerations.htm&type=5).  
    
-   Testing agents can modify CRM data. To avoid issues, be sure to use the Agentforce Testing Center only in your sandbox environment.  
    

## Batch Testing

In the last unit you used the Agentforce Testing Center. In this unit you’ll use Agentforce Studio to generate tests with AI.

1.  From the **App Launcher** ![App Launcher icon](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/agentforce-agent-testing/use-ai-to-generate-tests/images/cd26518777b955132939a15a69512fe5_kix.4pytu4sp2xnx.png), search for and select **Agentforce Studio**.  
    
2.  Click **Tests**.  
    
3.  Click **New Test Suite** and select **Agent**.  
    
4.  For Test Name, enter `Generated Test Agentforce v1Copy`.  
    
5.  For Description, enter `Test cases for Agentforce to verify account summaries and details.Copy`  
    
6.  Select **Einstein Copilot** or **Agentforce (Default)**.  
    
7.  Click **Next**.  
    
8.  Click **Next**.  
    
9.  Select **Generate Test Cases**.  
    
10.  For Number of test cases, leave it at 20.  
     
11.  For Test Objective, enter `Generate realistic inquiries that customers might ask about their user account, orders, and other general questions about products.Copy` This is also where you can define the number of these test cases that are positive and negative to create diversity in your test cases.  
     
12.  For Generate Test Cases From, select the **Subagents and Actions assigned to the agent**.  
     
13.  Click **Next**.  
     
14.  Click **Generate Test Cases**.  
     Wait for the test to be generated. You may have to refresh your browser as it may take a bit to generate the tests.  
       
     ![Agentforce Studio with Test cases and Run Test button.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/agentforce-agent-testing/use-ai-to-generate-tests/images/cc22f20f6301f3622620ce0a260d4139_kix.u677rctdu051.png)  
     

15.  Click **Run Test**.  
       
     ![Tests with Agent Response showing Generating.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/agentforce-agent-testing/use-ai-to-generate-tests/images/5b7883778f3c7cdd64ee23098573cd2d_kix.n7bjftcb2n5l.png)  
     

Once the tests are created, you can download them to make sure the agent is doing what you want it to do. You can also fine-tune the agent as needed. In the next unit, you take a closer look at the test results and use Agentforce Builder to troubleshoot a test.

Make sure to click **Check Challenge to Earn 500 Points** before moving on to the next unit.

## Resources

-   [_Salesforce YouTube_: Tools to Build, Test, and Release Agentforce | TDX 2025](https://www.youtube.com/watch?v=L0MlGxPWyCM)
-   [_Salesforce YouTube_: Agentforce Testing Center | TDX 2025](https://www.youtube.com/watch?v=TrEH6YRCde4)


# View Test Results

## Learning Objectives

After completing this unit, you’ll be able to:

-   Describe Agentforce Studio test results.  
    
-   Troubleshoot tests in Agentforce Builder.  
    

## Working with Test Results

Once the tests are completed, you can view the results and see what worked well and what didn’t work as well as you hoped. Take a look at the results for the test you ran in the last unit.

1.  From the **App Launcher** ![App Launcher icon](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/agentforce-agent-testing/view-test-results/images/cd26518777b955132939a15a69512fe5_kix.kzpm9btpyqkl.png), search for and select **Agentforce Studio**.  
    
2.  Click **Tests**.  
    
3.  Select the Test Suite **Generated Test Agentforce v1**.  
    
4.  Click **Run history**.  
    Run history shows the Status, Results, and Run By for each time the test suite is run.  
    
5.  Select the Start Time for the test suite that you just ran.  
    

At the top you see the following: Subagent Evaluation Pass %, Action Evaluation Pass %, and Response Evaluation Pass %. This gives you a quick overview of how the different parts of the tests are completed.![“Agentforce Studio with Generated Test Agentforce v1 test statuses and Details and Download Results buttons.”](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/agentforce-agent-testing/view-test-results/images/be579127d622fca001e72b5268862cf9_kix.qur4vd1swb9d.png)

The Test Results section displays several columns. Let’s look at the first line in more detail. Your results might be different.

| **Utterance** | Please update the email address for Ilsa Galgey to new\_email@example.com.|
| --- | --- |
| **Expected Subagent**| MigrationDefaultTopic |
|**Expected Actions**| \['IdentifyRecordByName', 'ExtractFieldsAndValuesFromUserInput', 'UpdateRecordFields'\]|
|**Expected Response**| The email address for Ilsa Galgey has been updated to new\_email@example.com.|
|**Agent Response**|Can I proceed with updating Ilsa Galgey's email address to new\_email@example.com?|
|**Response Evaluation**| Pass|
|**Subagent Evaluation**| Pass|
|**Actual Subagent**| MigrationDefaultTopic|
|**Action Evaluation**| Fail|
|**Actual Actions**| \['IdentifyRecordByName', 'ExtractFieldsAndValuesFromUserInput'\]|

You probably recognize Utterance, Expected Subagent, Expected Actions, and Expected Response from the test file. The new information are the actual responses and results from running the tests.

-   **Agent Response** shows the actual response from the agent.  
    
-   **Response Evaluation** shows Pass or Fail if the actual outcome matches the expected response.  
    
-   **Subagent Evaluation** shows Pass or Fail if the actual subagent matches the expected subagent.  
    
-   **Actual Subagent** shows which subagent was chosen for the utterance.  
    
-   **Action Evaluation** shows Pass or Fail if the actual action matches the expected actions.  
    
-   **Actual Actions** shows which actions the agent ran from the subagent.  
    

It looks like the above example test had a fail for Actual Actions. The Expected Actions has IdentifyRecordByName and QueryRecords and the Actual Actions has only QueryRecords. You use the Agentforce Builder for the Agentforce (Default) agent to troubleshoot the utterance of this test to get a better idea of what the agent is doing.

## Troubleshoot with Agentforce Builder

Switch to the Agentforce Builder and manually test the utterance in the Conversation Preview. Using Agentforce Builder in this way is a form of manual testing and lets you dig into the utterance to see the subagents, actions, and responses the agent chooses. Then try changing the utterance to test getting different results.

1.  From Setup, in the Quick Find box, search for and select **Agentforce Agents**.  
    
2.  Select the drop down for the Agent Name you want to open and select **Open in Builder**. We’ll continue to look at the Einstein Copilot or Agentforce (Default) agent.  
      
    ![Agentforce agent list with the Agentforce (Default) dropdown showing Open in Builder highlighted.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/agentforce-agent-testing/view-test-results/images/684b30388258fc54196fc4725a9451fb_kix.ax0dbfazpfp0.png)  
    

3.  In the Conversation Preview, enter the utterance `Please update the email address for Ilsa Galgey to new_email@example.com.Copy` and click **Enter**. The agent might ask you to confirm, click **Confirm** or enter `YesCopy`.  
    

The Agentforce Builder center screen shows the results, including Session Started, User Prompt, Subagent Selected , and so on.

![](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/agentforce-agent-testing/view-test-results/images/9f81681a809d1b9075b4dfcc8477443d_kix.q4rq65ujec4n.png)

You also see Action Launched, which shows the Identify Record by Name (IdentifyRecordByName) action was called.

![](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/agentforce-agent-testing/view-test-results/images/85e5bb5c00b1f41bb9565ee61467d945_kix.ayg3cep4zky8.png)

The Expected Action test criteria was expecting three actions. The failure is due to the wrong expectation.

At this point there are a few options.

-   The first one is to change the test Expected Action to just have the IdentifyRecordByName and ExtractFieldsAndValuesFromUserInput. But there is also the option to change the test Utterance if it was supposed to invoke both actions.  
    
-   Changing the utterance and checking the Actual Actions in the testing results allows you to reiterate over the tests, make changes, and verify that the agent is doing what is expected. The more tests and different test criteria you have, the higher the confidence and trust in the agent there is.  
    
-   Or this could be used as a negative test. Just add another test with the positive test criteria so that the criteria is covered.  
    

## Agentforce Testing Benefits

Testing is an essential part of building Agentforce agents. By creating and maintaining detailed positive and negative test criteria, you’re building and maintaining the confidence and trust that your Agentforce agents are bringing to your users and customers.

Agentforce Testing allows for repeated test runs that give you the ability to quickly determine if changes to your agents are having a negative impact on outcomes. You can even create the testing criteria first, run the tests, and then build the new functionality into the agents to get those tests to pass. This is known as test-driven development (TDD) in the coding community, and is a great way to build out new functionality with agents.

You now have a better idea of what the Agentforce Testing can do for you and the different ways you can work with test criteria to ensure your new agents are a sure way to interact with your users and customers. Now, go forth and create some tests!

## Resources

-   [_Salesforce Help_: Batch Test with Agentforce Testing Center](https://help.salesforce.com/s/articleView?id=release-notes.rn_einstein_copilot_testing_center.htm&release=254&type=5)

# Test Your Agent

Testing begins with single-session testing in Agentforce Builder, where you can manually validate agent behavior and troubleshoot issues in detail. When the agent performs reliably in individual scenarios, testing can scale by using batch tests in Agentforce Testing Center. Batch testing provides a broader view of performance across diverse scenarios, helping identify patterns, edge cases, and gaps that didn’t surface during manual testing. Together, these approaches make sure that the agent is well-tested, consistent, and ready for real-world use.

![Note](https://sf-zdocs-cdn-prod.zoominsoftware.com/tdta-ai-generative_ai-264-0-0-production-enus/fc2f2f57-79fe-4598-a5e0-089f9b72c638/images/icon_note.png)

Note Beginning in April 2026, agent topics are now called subagents. There are no changes to functionality. During this transition, you may see a mix of the new and previous terms in our documentation.

-   **[Agent Testing Strategy](https://help.salesforce.com/s/articleView?id=ai.agent_test_strategy.htm&language=en_US&type=5)**  
    Define what your agent is built to achieve, map the observability tools that measure it, and build the plan that connects your KPIs to testing and monitoring before your agent goes live.
-   **[Agentforce Builder Testing](https://help.salesforce.com/s/articleView?id=ai.agent_preview_and_test.htm&language=en_US&type=5)**  
    Manual testing, like you do in Agentforce Builder, is the starting point for validating your agent’s performance. It offers a detailed, step-by-step evaluation of your agent's interactions and utterances and is especially effective for confirming configurations and exploring how the agent responds to different inputs. Throughout the agent lifecycle, plan to revisit manual testing in Agentforce Builder, especially after making changes to your agent.
-   **[Agentforce Testing Center](https://help.salesforce.com/s/articleView?id=ai.agent_testing_center.htm&language=en_US&type=5)**  
    Build confidence in your AI agents and deliver seamless, effective interactions with thorough testing. Easily generate custom test scenarios and leverage our expert evaluation tools to assess response accuracy, conversation quality, subagent recognition, action execution, and knowledge retrieval. Identify issues early and fine-tune your agent’s behavior with precision.
-   **[Troubleshooting Agents in the Legacy Builder](https://help.salesforce.com/s/articleView?id=ai.copilot_troubleshoot.htm&language=en_US&type=5)**  
    Solve common agent issues.
-   **[Enable Enhanced Event Logs](https://help.salesforce.com/s/articleView?id=ai.copilot_setup_enhanced_event_logs.htm&language=en_US&type=5)**  
    Event logs capture the events and user messages in an agent session to help you test and troubleshoot your agent. In supported agent types, enable enhanced event logs to store conversation data and view all session activity in one place. When enhanced event logs aren't enabled, events associated with agent and user messages (such as Message sent: and User response:) are logged, but the messages themselves aren't included in the event.


# How to deploy Agentforce AI Planner metadata

A walkthrough on how to deploy Agentforce AI Planner metadata via GenAiPlannerBundle (API v 64 and above) or GenAiPlanner (API v 60 to 63)

Written by Vincent Maltby

September 10, 2026

Table of contents

[Prerequisites](#h_06af2dbc19)

[What metadata is needed in the filter?](#h_0da9f5301d)

[How to deploy GenAiPlannerBundle metadata with Gearset?](#h_5a4c92f97c)

**Important to note:** _GenAiPlanner_ components are available in API versions 60 to 63. In API version 64.0 and later, _GenAiPlanner_ is deprecated and replaced entirely by _GenAiPlannerBundle_.

Gearset's [Agentforce metadata deployment solution](https://gearset.com/solutions/agentforce/) streamlines the process of deploying AI-powered configurations in Salesforce, including the Agent Planner metadata (_[GenAiPlanner](https://GenAiPlanner)_ & _[GenAiPlannerBundle](https://developer.salesforce.com/docs/atlas.en-us.api_meta.meta/api_meta/meta_genaiplannerbundle.htm)_).

Agentforce **AI Agents** engage customers autonomously across channels in natural language.

This guide will explain how to successfully deploy **Agent Planner** metadata with Gearset.

## Prerequisites

Make sure to use at least API version 60 for the comparison. Read the prerequisite section of the [How to deploy GenAi metadata](https://docs.gearset.com/en/articles/10406855-how-to-deploy-genai-metadata-types) guide to find out how to do this.

The `Einstein bot` and `botVersion` associated to the Agent that you want to deploy must exist on the target org — otherwise the agent will not be visible.

## What metadata is needed in the filter?

You'll need to include `Einstein bot`, `botVersion` & `GenAiPlanner` (for API versions 60-63) or `GenAiPlannerBundle` (for API version 64 and above) in your metadata filter.  
​

[![](https://downloads.intercomcdn.com/i/o/h0kayiwv/1350276782/d86bc87463f41bd2906e56a4569c/image.png?expires=1792019700&signature=18f19ec39c39d0bdb34dfecee3346be6c218ae3323ed61dca7fa4dcee156091e&req=dSMiFst5m4ZXW%2FMW1HO4zd29j9s3odp98hjsfZFhSepjkw3mFXjQgWdk%2BLY3%0A66F9vtWNVnzrc3E2sl8%3D%0A)](https://downloads.intercomcdn.com/i/o/h0kayiwv/1350276782/d86bc87463f41bd2906e56a4569c/image.png?expires=1792019700&signature=18f19ec39c39d0bdb34dfecee3346be6c218ae3323ed61dca7fa4dcee156091e&req=dSMiFst5m4ZXW%2FMW1HO4zd29j9s3odp98hjsfZFhSepjkw3mFXjQgWdk%2BLY3%0A66F9vtWNVnzrc3E2sl8%3D%0A)

## How to deploy GenAiPlannerBundle metadata with Gearset?

If the agent was created using the **Agent Script** editor, you need to select the `Agent Script (AiAuthoringBundle)` metadata type in the filter. Check out this [document](https://docs.gearset.com/en/articles/13452227-how-to-deploy-agent-scripts-aiauthoringbundle-metadata) on how to deploy Agent Scripts.

To deploy the `GenAiPlannerBundle` metadata type, you need to make sure that all the `GenAiFunction` and `GenAiPlugin` dependencies exist on the target environment. If they don't, then you'll need to deploy them alongside the `GenAiPlannerBundle` for the validation/deployment to be successful.

**Note:** If the `GenAiPlanner` is `New` (in the source), then the associated `Einstein bot` and `botVersion` will also need to be deployed to the target org. Otherwise the deployed `GenAiPlanner` will not be visible on the target org. It's recommended to always deploy any changes to the `Einstein bot` and `botVersion` alongside the `GenAiPlanner` (or alongside `GenAiPlannerBundle` if deploying via APi version 64 and above).

Example:

[![](https://downloads.intercomcdn.com/i/o/h0kayiwv/1336798680/7a8523e491ee375a56dbdde08355/image.png?expires=1792019700&signature=2c086e14eabb1a897b6130389cec9f72c213c73d85e024415fb898fb62b90f38&req=dSMkEM53lYdXWfMW1HO4zd1CYh7vb4OV94OCT8tQjD8fqxJji01tjcYwVaZV%0AcSSW6SpPY7ani%2BGKGS0%3D%0A)](https://downloads.intercomcdn.com/i/o/h0kayiwv/1336798680/7a8523e491ee375a56dbdde08355/image.png?expires=1792019700&signature=2c086e14eabb1a897b6130389cec9f72c213c73d85e024415fb898fb62b90f38&req=dSMkEM53lYdXWfMW1HO4zd1CYh7vb4OV94OCT8tQjD8fqxJji01tjcYwVaZV%0AcSSW6SpPY7ani%2BGKGS0%3D%0A)

This `GenAiPlannerBundle` is dependent on the following `GenAiFunction`:

-   EmployeeCopilot\_AnswerQuestionsWithKnowledge
    

It's also dependent on the following `GenAiPlugins`:

-   EmployeeCopilot\_GeneralCRM
    
-   SvcCopilotTmpl\_OrderInquiries
    
-   SvcCopilotTmpl\_GeneralFAQ
    
-   Customer\_Service\_Assistant
    

If any of these `GenAiFunctions` or `GenAiPlugins` aren't already in the org, or being deployed to the org alongsidethe `GenAiPlannerBundle`, then the validation/deployment will fail.  
​  
We will be adding more problem analyzers over time to help highlight any missing `GenAiFunction` or `GenAiPlugin` dependencies before you validate or deploy your Agentforce agents.

* * *

Related Articles

-   [How to deploy Agentforce (GenAi & Ai) metadata types](https://docs.gearset.com/en/articles/10406855-how-to-deploy-agentforce-genai-ai-metadata-types)
-   [How to deploy Agentforce Subagent AKA Topic (GenAiPlugin) metadata](https://docs.gearset.com/en/articles/10406889-how-to-deploy-agentforce-subagent-aka-topic-genaiplugin-metadata)
-   ["Default Agentforce comparison" metadata filter](https://docs.gearset.com/en/articles/10572042-default-agentforce-comparison-metadata-filter)
-   [How to Deploy Agent Script (AiAuthoringBundle) metadata](https://docs.gearset.com/en/articles/13452227-how-to-deploy-agent-script-aiauthoringbundle-metadata)
-   [How to deploy Agentforce Agents](https://docs.gearset.com/en/articles/13700779-how-to-deploy-agentforce-agents)

# Deploy change sets from sandbox to production

Publish Date: Jun 25, 2026

Description

  
A change set in Salesforce is a collection of components and customizations — such as Apex classes, Apex Triggers, and page layouts — that can be deployed between connected Salesforce orgs. This article describes how to deploy a change set from a sandbox environment to a production organization.

**Note:** An administrator must first connect the source and target organizations before deployment is possible.

Resolution

Follow these two stages to deploy a change set: first upload it from your sandbox, then deploy it in your production org.

### **Create and upload a change set in your source sandbox organization**

1.  Log in to your sandbox.
2.  Navigate to **Setup** and enter c_hange set_ into the Quick Find box.
3.  Click **Outbound Change Set**
4.  Click **New**.
5.  Enter the new Change Set name and description, then click **Save**.
6.  From the "Change Set Components" related list, click **Add**.
7.  Add profiles to the Change Set for the Users you'd like to grant access.
8.  Select the "Component Type" for the component you want to deploy (for example, Apex class, Apex Trigger).
9.  Select the specific class or trigger name, then click **Add to Change Set**.
10.  From the "Change Set Detail" related list, click **Upload**, then select the target organization as **Production**.
11.  Click **Upload**.

After your upload has completed, you'll receive an email to confirm completion of your Change Set upload.To complete the migration, an inbound change administrator can deploy the Change Set in the destination production organization.  
 

### **Complete the deployment in your target production organization**

1.  Login to the target organization.
2.  Navigate to **Setup** and enter _Change Set_ into the Quick Find box.
3.  Click **Inbound Change Sets**.
4.  Under "Change Sets Awaiting Deployment," click your Change Set's name.
5.  Click **Validate** to validate the components. 
6.  Click **Deploy**.

Once you have a successful validation, repeat the above steps and choose **Deploy** on step 5 to complete the deployment of your Change Set. 

### Code Coverage Requirement

For a successful deployment, your Apex code must have at least 75% test coverage. Run Validate before deploying to confirm code coverage requirements are met. If coverage is below 75%, update your Apex test classes before proceeding.

Additional Resources

  
[Change Sets Implementation Tips](https://help.salesforce.com/s/articleView?id=platform.changesets_implementation_notes.htm&type=5&language=en_US)   
[Monitor Deployments](https://help.salesforce.com/s/articleView?id=platform.deploy_monitoring.htm&type=5&language=en_US)   
[Components Available in Change Sets](https://help.salesforce.com/s/articleView?id=platform.changesets_about_components.htm&type=5&language=en_US)  
[Deploy profiles via change sets](https://help.salesforce.com/s/articleView?id=000386377&type=1&language=en_US)  
[**Connect Organizations for Deployment**](https://help.salesforce.com/s/articleView?id=platform.deploy_connection_parent.htm&type=5&language=en_US)  
  
**Video guide to deploy change sets**  
[Release Management: Deploying Changes Using Change Sets](https://www.youtube.com/watch?v=Ix_LFFdck-E)  
[How to Add Components to a Change Set and Upload](https://youtu.be/AFezX6KWaFg)  
[How to Create a Deployment Connection for a Change Set](https://www.youtube.com/watch?v=vJm3rsFts8U)

# Activate or Deactivate Your Agent

Activate your agent to make it available to your customers or employees. When an agent is deployed to one or more channels, including the Agentforce panel, activating the agent makes it immediately available to your users.

Only one version of an agent can be active at a time. You can have up to 100 concurrently active agents. When you activate a version of an agent that already has an active version, the currently active version is automatically deactivated.

Deactivating an agent interrupts any ongoing user conversations. Users aren’t notified that an agent is deactivated. The agent sends the system error message as a response to any messages.

-   If the agent uses the Agentforce panel, the panel is available until the user closes it, and it can’t be reopened until the agent is active.
-   If the agent is connected to an active Enhanced Chat deployment, the chat window appears, but the agent doesn't join the conversation.

## Activate or Deactivate an Agent

1.  From the Agents page of the Agentforce Studio app, open the agent you want to activate or deactivate.
2.  If there are multiple versions of your agent, from the header in Agentforce Builder, select the agent version you want to activate or deactivate.
3.  Click **Activate** to make your agent live or **Deactivate** to remove it from service.

After you activate a version, you can no longer make changes to it, even after you deactivate it. To make changes, [create another version.](https://help.salesforce.com/s/articleView?id=ai.agent_versions_draft.htm&language=en_US&type=5)

## Activate or Deactivate an Agent in the Legacy Builder

To make and test changes to your agent without taking the active version out of production, [create multiple versions of an agent](https://help.salesforce.com/s/articleView?id=ai.agent_versions.htm&language=en_US&type=5).

1.  From Setup, in the Quick Find box, enter Agent, and then select **Agentforce Agents**.
2.  Click the name of the agent you want to activate or deactivate.
3.  Click **Open in Builder**.
4.  Click **Activate** to make your agent live or **Deactivate** to remove it from service.

# Exercise 3: Distribute a Service Agent ​

In this exercise, you will add the Coral Cloud Agent to an Experience Cloud site.

![](https://developer.salesforce.com/workshops/assets/service-agent-architecture_experience-cloud.C8k90Asq.webp)

## Step 1: Add Embedded Service deployment to Experience Cloud ​

Update the Experience Cloud page to include your Coral Cloud agent. This exercise assumes you already configured the messaging channel and embedded service deployment in Exercise 2.

### Add the agent to the site ​

1.  Search for **Digital Experiences** in the Setup Quick Find and select **All Sites**.
    
2.  Click **Builder** next to the `Coral Cloud` site.
    
3.  If a popup appears, click **OK**.
    
4.  Click the **Components** widget.
    
5.  Search **Embedded Messaging** and drag and drop the component onto the page (for example, in a hero section or sidebar). Note: exact placement depends on your site template and it may take a few seconds for the component to appear.
    
    ![](https://developer.salesforce.com/workshops/assets/service-agent-coral-cloud-site.D7QK-Srp.webp)
    
6.  Ensure that the Embedded Messaging Configuration you created in Exercise 2 is selected (for example, `Coral_Cloud_Agent`).
    
7.  Click **Publish** in the upper right corner.
    
8.  Click **Publish** in the confirmation window.
    
9.  Click **Got It**.
    

### View the agent as a customer ​

1.  Click the **Experience Builder menu**.
    
2.  Select **View** to open the published `Coral Cloud` site.
    
    TIP
    
    Note: It may take a few minutes for the site to publish. Go ahead and verify the challenge below while you wait for your Experience Cloud site to publish.
    
3.  Click on the Messaging icon in the lower right corner to start interacting with the new agent. Try some prompts like:
    
    txt
    
    ```
    Can you tell me about White Water Rafting Rush?
    ```
    
    txt
    
    ```
    Can you book me in for tomorrow session?
    ```
    
4.  If asked to provide your email address and membership number, use the following text.
    
    txt
    
    ```
    Can you book me in for tomorrow?
    ```
    

## Summary ​

You have just created a custom service agent that can be used to interact with your customers. Next, we will use the service deployment capabilities in Service Cloud to deploy the agent to a customer-facing Experience Cloud site.

Pager

[Previous pageExercise 2: Configure a Service Deployment](https://developer.salesforce.com/workshops/agentforce-workshop/service-agents/2-configure-a-service-deployment)

[Next pageExercise 4 (Optional): Extending a Service Agent with Heroku](https://developer.salesforce.com/workshops/agentforce-workshop/service-agents/4-extend-service-agent-with-heroku)

# Packaging Considerations for Prompt Templates

Include a prompt template in managed, unmanaged, or unlocked packages. Before you create, update, or deploy a package that contains a prompt template, understand the limitations and behaviors of packages.

## Create Packages

-   Prompt templates that include a flow with a custom object input may cause package installation to fail, as packaging for prompt flows with custom objects isn't supported.
-   Include only published versions. Draft versions can be added to the package, but they aren’t installed in customer orgs for managed packages.
-   Any future changes to a published version are skipped during upgrade without error.
-   If a published version is active and it’s different from the current version, it’s auto-activated in the customer’s organization.
-   If no versions are published, don’t package the template. If you package a template without a published version, any installation or upgrade fails because of an empty template.
-   Prompt templates with custom models can’t be packaged.
-   If you include an Apex class in a prompt template and package it, the class must be global.
-   For unmanaged, unlocked, or managed packages, avoid packaging templates that override any out-of-the-box (OOTB) template. Packaged templates can optionally be configured as overridable, which allows subscribers to create local versions of the template.
-   Retrievers like Data Search and Data Graphs aren’t included in packages. Instead, they’re part of a data kit in Data 360. Salesforce Independent Software Vendors (ISVs) are encouraged to provide retrievers to the customer, or the installation fails because of missing metadata.
-   New versions can be added to an existing template, but previously published versions can’t be modified or deleted. For overridable templates, subscribers can create additional override versions that customize the packaged template.
-   New versions can be activated, and old versions can be deactivated. If a subscriber activates an override version, that version takes precedence over the publisher’s active version.
-   Customers can’t edit packaged templates directly.However, if the publisher enables overridable templates, customers can create a new version that overrides the packaged template. Customers can also clone the template to create an independent custom template.
-   A template with no active version can be delivered, but customers can't use it until a version is activated. Customers can clone the template to create an independent custom template, or if the template is configured as overridable they can create a local override version.
-   ManagePromptTemplates permission must be assigned while creating second-generation (2GP) package versions. This snippet can be used in `sfdx-project.json` to specify the permission to assign to the build user while creating the org and building the package.
    
    ```
    {
                            "packageDirectories": [{
                            "versionName": "ver 0.2",
                            "versionNumber": "0.2.0.NEXT",        
                            "path": "force-app",
                            "default": true,
                            "package": "Prompt Template 2GP Pkg",
                            "versionDescription": "",
                            "definitionFile": "config/project-scratch-def.json",
                            "packageMetadataAccess": {
                            "permissionSets": [
                            "EinsteinGPTPromptTemplateManager"
                            ]
                            }
                            }],
                            "name": "managed",
                            "namespace": "NAMESPACE",
                            "sfdcLoginUrl": "https://login.salesforce.com",
                            "sourceApiVersion": "63.0"
                            }          
    ```
    

## Install and Upgrade Installed Prompt Templates

-   In Einstein Setup, if Add or Require Inputs After Activation isn’t enabled and you change inputs between template versions, the package installation fails with the error: 'This app can't be upgraded.'
-   Before installing or upgrading a package in production, test installation or upgrade in sandbox and test.
-   Customers can't deactivate a version after installation or upgrade.
-   You can’t overwrite a published prompt template version.
-   If the prompt template model is hidden, the existing template works as intended. However, if the template is cloned, the model won’t be available for use.
-   For active versions, auto-activate them in the customer organization. Always test changes in sandboxes before installing or upgrading a package.
-   Einstein Generative AI must be activated for installation of packages with Prompt templates otherwise installation fails.
-   Flows aren't auto-activated when a package is installed. Flows follow the standard activation process for managed packages that's established.
-   Partners can deactivate a template. However, if that template is in use for the customer, the upgrade fails. To upgrade the package, customers must remove that template from use.
-   If you package a template with a custom LLM model configuration, verify your customer org has a model with the same name, otherwise installation or upgrade fails.
-   Custom fields on Dynamic Forms-enabled Lightning pages can reference prompt templates. If you install a managed package containing a prompt template that is referenced by a custom field on a Dynamic Forms-enabled Lightning page, and that prompt template references a custom field with a namespace that is different from the Lightning page's namespace, package installation can fail.

## Delete Installed Prompt Templates

-   Versions can't be deleted from a managed template.
-   A managed template can be deleted from a 2GP package, but it isn't deleted on the customer's org. Customers see the deprecated templates and have the option to delete them.

## Overridable Prompt Templates

Publishers can configure packaged prompt templates to be overridable. When a template is overridable, subscribers can create local versions of the template and customize the prompt text or configuration. Although these custom versions are linked to the template, they remain separate. Any update to the published version doesn’t impact the custom versions.

Subscriber override versions appear in the version picker alongside publisher-managed versions. If a subscriber activates an override version, that version becomes the active version in the subscriber organization. However, activating the override does not deactivate the packaged version, the package version is automatically activated. This behavior preserves flows, especially packaged ones, which can depend on this template being active.

Publisher versions remain managed by the package and continue to receive updates through package upgrades.

## Considerations For Partners

-   To allow a template to be overridable, use `<overridable>true</overridable>`.
-   Once a template’s overridable setting is true and installed in the customer org, the setting cannot be undone. The upgrade fails with an error.
-   Deleting a packaged template from a package marks it as deletable in the customer org. If a customer deletes that template, and the template isn’t being used, their customer overrides are also deleted.
-   Subscribers can use the **Save as a new version** option to override the template.
-   If custom version is active and the template is being used, then it cannot be deleted.
-   If custom version is active, the template is being used, but there is an active managed package version then deactivating custom version will fall back to that version.
-   If custom version is active, the template is being used, but there is no active managed package version then deactivation will fail.
-   The Template Overrides option in Prompt Builder appears only in orgs with a namespace.
-   When you clone an overridable template, the cloned template isn't overridable. Explicitly set the new template as overridable.

## See Also

-   [Data Kits](https://help.salesforce.com/s/articleView?id=data.c360_a_data_package_kits.htm&language=en_US&type=5)
-   [Automate Tasks with Flows](https://help.salesforce.com/s/articleView?id=platform.flow.htm&language=en_US&type=5)

# Prompt Builder Limitations

Learn about the functional limitations of prompt templates that affect certain behaviors and outcomes.

## Audit Trail Isn’t Supported

Creating or updating a prompt template isn’t tracked in the Setup Audit Trail.

## New Custom Objects and Custom Fields Aren’t Immediately Available After Creation

When you create a custom object or custom field, it isn’t available for use in Prompt Builder immediately. To use a new custom object or field immediately, log out and log back in.

## Records Without a Name Don’t Display in the Record Selector

Prompt templates with encrypted or missing name fields can’t be previewed. Their records are unavailable in the test record selector.

## Supported Object Types

Salesforce supports many object or field suffixes to represent different types of data. Prompt Builder supports only these types of objects and fields as resources.

-   UI API-supported objects. For a full list, see [All Supported Objects](https://developer.salesforce.com/docs/atlas.en-us.248.0.uiapi.meta/uiapi/ui_api_all_supported_objects.htm).
    
    ![Important](https://sf-zdocs-cdn-prod.zoominsoftware.com/tdta-ai-generative_ai-264-0-0-production-enus/fc2f2f57-79fe-4598-a5e0-089f9b72c638/images/icon_important.png)
    
    Important The KnowledgeArticleVersion object is supported only for Flex Template types.
    
-   Standard objects (no suffix)
-   Standard fields (no suffix)
-   Custom objects (`__c`)
-   Custom fields (`__c`)
-   Histories (`__history`)
-   Related lists (`__r`)

## Object Preview Limitations

You can’t preview objects with no Name field or objects whose Name field is encrypted.

## Limitations for Field Generation Templates

You can’t use Field Generation prompt templates for rich text areas in knowledge entities (`__kav`). To populate a knowledge entity’s rich text area with a Prompt Builder template, use a Flex prompt template, Flow, or Apex.

## Limitations for Flex Templates

You can’t import or export metadata from flex templates, including metadata related to flex templates. For example:

-   Apex classes that reference flex templates
-   Flows that reference flex templates
-   Change sets to move flex-related artifacts between orgs

To delete flex templates that use flows or Apex classes, first remove any flows and Apex resources in all versions of the template. Second, delete any flows and Apex classes that reference the prompt template. Then delete the flex template.

## Limitations for Einstein Search

If a prompt uses an Einstein Search retriever, the change sets don’t include the retriever or search index metadata. You must manually create the retriever in the destination org before deploying the retriever. This rule applies to change sets and Metadata API deployments.

## Limitations for Conditional Logic

Conditional blocks evaluate a single related record. They don’t iterate over a collection, such as multiple files related to a case.

To reference more than one file, use Flow or Apex to select the file before the prompt template runs, or concatenate file names or a file count into a text field and ground the prompt template on that field.

#### See Also

-   [Ground Prompt Templates with Salesforce Resources](https://help.salesforce.com/s/articleView?id=ai.prompt_builder_ground_template.htm&language=en_US&type=5)
-   [Monitor Setup Changes with Setup Audit Trail](https://help.salesforce.com/s/articleView?id=xcloud.admin_monitorsetup.htm&language=en_US&type=5)
-   [Prompt Builder Limits](https://help.salesforce.com/s/articleView?id=ai.prompt_builder_limits.htm&language=en_US&type=5)
-   [Troubleshoot Prompt Builder](https://help.salesforce.com/s/articleView?id=ai.prompt_builder_troubleshoot.htm&language=en_US&type=5)

# Activate and Deactivate Prompt Templates

Use activation and deactivation of prompt templates to finely control which version your users can access.

During the process of crafting a prompt template, you typically create a few versions to test which template body, grounding data, and LLM combination yields the most satisfying response. Because of this iterative drafting process, prompt templates aren’t available to your users by default. You must activate them first.

When you activate a prompt template, you’re making a specific version of the prompt template available to your users. Only one version of a template can be active at a time, and if no versions are active the template becomes unavailable to your users. Activating and deactivating versions gives you the control to make available only the version of a template you want to share.

1.  Begin in the Prompt Template Workspace of Prompt Builder. See [Create a Prompt Template](https://help.salesforce.com/s/articleView?id=ai.prompt_builder_build_template.htm&language=en_US&type=5).
2.  Begin drafting your prompt in the Prompt section. When you’re ready to save your work, click **Save**. This prompt is now Version 1 of your prompt template, as denoted by the version number shown at the top of the Prompt Template Workspace.
3.  When you’re ready to activate a template and make it available to your users, click **Activate**.
    
    ![Important](https://sf-zdocs-cdn-prod.zoominsoftware.com/tdta-ai-generative_ai-264-0-0-production-enus/fc2f2f57-79fe-4598-a5e0-089f9b72c638/images/icon_important.png)
    
    Important Activating a template version makes it immutable. Even if deactivated, any version that was ever active remains immutable. To edit such a template, save it as a new version. See [Use Multiple Versions of a Prompt Template](https://help.salesforce.com/s/articleView?id=ai.prompt_builder_use_multiple_versions.htm&language=en_US&type=5).
    
4.  To deactivate an active template version, click **Deactivate**.



# Prompt Template Run-time Execution

Invoking a prompt template at run time sets off a chain of events. The run-time life cycle of a prompt template begins with loading the prompt template with input and concludes with forwarding the LLM-generated response to the calling agent or app.

## Design-time Preview

When you design a prompt template, Prompt Builder’s preview feature allows you to simulate a complete run-time experience. You preview the prompt template, provide input, preview the resolved prompt, and then get the generated response returned from the LLM.

## Prompt Execution at Run Time

When an agent or app invokes an activated prompt template at run time, it triggers the same chain of events. Let’s break it down into more detailed steps.

**Prompt Template Execution Steps**

![Illustration showing the series of steps involved with prompt template execution.](https://sf-zdocs-cdn-prod.zoominsoftware.com/tdta-ai-generative_ai-264-0-0-production-enus/fc2f2f57-79fe-4598-a5e0-089f9b72c638/generative_ai/images/prompt_builder_runtime.png)

| Step | Description |
| --- | --- |
| 1 | The prompt template gets invoked with input from an agent, a flow, Apex, or an app. |
| 2 | Prompt resolution begins with secure data retrievals. Values for merge fields (records, flows, Apex) are added to the prompt. Access to merge data is governed by the permissions of the executing user.For dynamic grounding, relevant information from structured and unstructured data in Data Cloud is retrieved using features like search retrievers, flows, and SOQL queries.|
| 3 |The resolved prompt then undergoes further protections using enabled features in the [Einstein Trust Layer](https://help.salesforce.com/s/articleView?id=ai.generative_ai_trust_layer.htm&language=en_US&type=5). Pattern-based [data masking](https://help.salesforce.com/s/articleView?id=ai.generative_ai_audit_data_mask.htm&language=en_US&type=5) is applied automatically, while field-based data masking is applied if enabled.The Einstein Trust Layer applies prompt defense measures using Salesforce system policies.|
| 4 |The secured prompt is submitted to the LLM via the LLM gateway. The LLM returns its generated response via the LLM gateway.<br>-   The generated response can include [citations](https://help.salesforce.com/s/articleView?id=ai.generative_ai_trust_citations.htm&language=en_US&type=5) to original sources that the LLM used when generating the response.<br>- The generated response can be in the user’s language (default) or in a [requested language](https://help.salesforce.com/s/articleView?id=ai.prompt_builder_multi_languages.htm&language=en_US&type=5).<br>For external model providers, our zero data retention policy ensures that data sent to the LLM from Salesforce isn’t retained but is deleted after a response is sent back to Salesforce.|
| 5 | The LLM-generated response is logged for [audit and feedback](https://help.salesforce.com/s/articleView?id=ai.generative_ai_feedback.htm&language=en_US&type=5). |
| 6 | The Einstein Trust Layer applies system policies to the LLM-generated response. If enabled, features like toxicity detection help decrease the likelihood of unintended or harmful outputs. If data masking is enabled, the Einstein Trust Layer demasks any masked data, replacing placeholders with their underlying values. |
| 7 | The generated response is returned to the requesting agent or app in a raw or structured format. |

![Note](https://sf-zdocs-cdn-prod.zoominsoftware.com/tdta-ai-generative_ai-264-0-0-production-enus/fc2f2f57-79fe-4598-a5e0-089f9b72c638/images/icon_note.png)

Note Prompt resolution is sometimes called "hydration" or "prompt grounding". We refer to it as "resolution" in the context of executing prompt templates built with Prompt Builder.

# Integrate Prompt Templates with Salesforce Features

You can call a prompt template through an invocable action anywhere on the Salesforce Platform or by using the Connect REST API or Connect in Apex.

See [the Prompt Builder section](https://developer.salesforce.com/docs/ai/agentforce/guide/get-started-prompt-builder.html) of the [Agentforce Developer Guide](https://developer.salesforce.com/docs/ai/agentforce/overview).

## See Also

-   [_Agentforce Developer Guide_: Prompt Builder](https://developer.salesforce.com/docs/ai/agentforce/guide/get-started-prompt-builder.html)
-   [How Users Work with a Prompt Template](https://help.salesforce.com/s/articleView?id=ai.prompt_builder_how_users_work_with_templates.htm&language=en_US&type=5)

# Change LLM Configurations in Prompt Templates

Select and optionally modify an LLM configuration for generating outputs in Prompt Builder.

One of the most powerful features of Prompt Builder is the ability to change the LLM configuration with only a few clicks.

## Standard and Customer LLM Configurations

LLM configurations in Prompt Builder are classified as either standard or custom. Standard configurations come included with Prompt Builder. Custom configurations are brought in via BYO-LLM. Additionally, if you modify a standard configuration, the changed configuration is saved as a custom configuration.

## Versions and LLM Configurations

Each version of a prompt template can contain a different model configuration. Only the configuration model in the activated version is used.

![Important](https://sf-zdocs-cdn-prod.zoominsoftware.com/tdta-ai-generative_ai-264-0-0-production-enus/fc2f2f57-79fe-4598-a5e0-089f9b72c638/images/icon_important.png)

Important Activating a template version makes it immutable. Even if deactivated, any version that was ever active remains immutable. To edit such a template, save it as a new version. See [Use Multiple Versions of a Prompt Template](https://help.salesforce.com/s/articleView?id=ai.prompt_builder_use_multiple_versions.htm&language=en_US&type=5).

## View a Model

The **View this model** link in the Model section of the Template Settings panel opens the AI Models (formerly Einstein Studio) model page for the selected model. On this page, make any changes to the model before continuing to draft your prompt template in Prompt Builder.

![Important](https://sf-zdocs-cdn-prod.zoominsoftware.com/tdta-ai-generative_ai-264-0-0-production-enus/fc2f2f57-79fe-4598-a5e0-089f9b72c638/images/icon_important.png)

Important Users need the Data Cloud Admin permissions to see and use the **View this model** link in the Template Settings panel. Without these permissions, users can’t access Model Configuration within AI Models.

## Replace a Hidden Model

An LLM configuration can be hidden in AI Models. A prompt template that uses a hidden model continues to run as before. However, it’s recommended that you replace the hidden model with an available one. If you open a prompt template that uses an unavailable model, Prompt Builder has you select a different model in the Models field before you can save your changes as a new version.

## See Also

-   [Large Language Model Support](https://help.salesforce.com/s/articleView?id=ai.generative_ai_large_language_model_support.htm&language=en_US&type=5)

<!--stackedit_data:
eyJoaXN0b3J5IjpbOTY1MTQ2NTY3LDE4MDg3NDUwNzMsMjE0ND
gwMTg0LDczMDk5ODExNl19
-->