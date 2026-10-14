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
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTMxODcxNTM5OCwyMTQ0ODAxODQsNzMwOT
k4MTE2XX0=
-->