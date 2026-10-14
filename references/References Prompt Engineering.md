# Enable Prompt Builder

Enable Einstein in your organization and assign users the appropriate permission set to use Prompt Builder.

Note If you’re working from a scratch org, add Prompt Builder to your definition file before enabling Einstein. See [Scratch Org Features](https://developer.salesforce.com/docs/atlas.en-us.sfdx_dev.meta/sfdx_dev/sfdx_dev_scratch_orgs_def_file_config_values.htm#so_einsteingenerativeai).

- Follow [Set Up Einstein Generative AI](https://help.salesforce.com/s/articleView?id=ai.generative_ai_enable.htm&language=en_US&type=5).
- (Optional) To use prompt templates with sales emails, activate Sales Emails.
  * From Setup, in the Quick Find box, enter Einstein Sales, and then select Einstein for Sales.
  * Enable Sales Emails. It can take a few minutes before the feature is ready to use.
- Assign the Prompt Template Manager permission set to users that need to create and manage prompt templates in Prompt Builder
	* From Setup, in the Quick Find box, enter Permission Sets, and then select Permission Sets.
	* From the Permission Sets list view, click Prompt Template Manager.
	* From the Prompt Template Manager detail page, click Manage Assignments and Add Assignments.
	* Select the checkboxes next to the names of the users, including yourself, that you want assigned to the permission set, and click Next. To add a user to the Prompt Template Manager permission set, the user must have access to Setup.
	* Click Assign.
- Refresh the page so that Prompt Builder is now visible in Setup.
- To open Prompt Builder from Setup, in the Quick Find box, enter Prompt Builder, and then select **Prompt Builder**.   ![Prompt Builder Setup page](https://sf-zdocs-cdn-prod.zoominsoftware.com/tdta-ai-generative_ai-264-0-0-production-enus/fc2f2f57-79fe-4598-a5e0-089f9b72c638/generative_ai/images/prompt_builder_setup.png)
## See Also

-   [Create a Prompt Template](https://help.salesforce.com/s/articleView?id=ai.prompt_builder_build_template.htm&language=en_US&type=5)
-   [Troubleshoot Prompt Builder](https://help.salesforce.com/s/articleView?id=ai.prompt_builder_troubleshoot.htm&language=en_US&type=5)

# Prompt Builder Key Concepts

Learn the key concepts and vocabulary used throughout Prompt Builder.

## Prompts

Generative language models are versatile and can create different types of responses. To produce a response, tell the LLM what you want in the form of a prompt. Prompts determine the quality and relevance of the LLM’s response, so it’s important to craft prompts that the model can understand and use.

## Prompt Design

Prompt design is the process of creating prompts that improve the quality and accuracy of the model’s responses. Many models expect a certain prompt structure, so it’s important to test and iterate them on the model you’re using. After you understand what structure works best for a model, you can optimize your prompts for the given use case. To scale the prompt design process, create reusable prompts called prompt templates.

## Prompt Templates

Behind the scenes, Einstein generative AI uses prompt templates. Prompt templates are reusable, detailed prompts that you can create and manage in Prompt Builder. These templates are use case-driven and include the information that helps the LLM generate a high-quality response, such as a goal, constraints, and brand guidelines. And to make sure that the prompts you send to the LLM are grounded in the most up-to-date data, prompt templates include placeholders for information that changes, such as customer names, contact information, and product prices.

## Grounding

Grounding improves responses by connecting your prompt to data that’s relevant to your request. Without grounding, a model’s response can contain generic or irrelevant details. The LLM uses your Salesforce data or uploaded files to add context and personalization to your prompts. In Prompt Builder, you can ground prompts using merge fields that reference record fields, flows, Apex, and uploaded files. The LLM uses the grounding data along with the original, generic data that it was trained on.

The Einstein Trust layer masks sensitive data from the LLM by sending placeholder text instead. To see the placeholder text, look at the Resolved Prompt. In the response, you can see the demasked data added back in by Salesforce. You can see a summary of all masked data for the response in the Data Masking Details dialog.

To learn more about how Einstein keeps your data secure, see [Einstein Trust Layer](https://help.salesforce.com/s/articleView?id=ai.generative_ai_trust_layer.htm&language=en_US&type=5).

## Prompt Template Type

Prompt template types help you to create a prompt template for your particular use case. For example, a Sales Email prompt template helps your sales team to draft personalized emails for a contact or a lead.

## Prompt Instructions

Prompt instructions are natural language instructions in a prompt template. Instructions describe a task for the LLM, such as “Write a description no longer than 500 characters.” Add instructions to a prompt template, and then relevant CRM data replaces the template’s placeholders. The prompt template is now a grounded prompt and sent to the LLM.

## Prompts and Prompt Templates

Behind the scenes, large language models (LLMs) power Einstein generative AI. An LLM can help your users with many language-based tasks. For example, it can generate a personalized email to a customer or analyze customer feedback and extract key insights. But an LLM can’t create great content by itself—it needs guidance from you in the form of a prompt.

A prompt is the set of instructions that you give an LLM. It provides specific contextual information, data, instructions, and constraints that help the model generate accurate and personalized output. The output that the LLM generates is called a response.

![Example](https://sf-zdocs-cdn-prod.zoominsoftware.com/tdta-ai-generative_ai-264-0-0-production-enus/fc2f2f57-79fe-4598-a5e0-089f9b72c638/images/icon_example.png)

Example

This prompt instructs the LLM to create a summary of open cases for the Astro’s Bakery account.

```
You’re a support representative and you need to create a short summary of all open cases for the Astro’s Bakery account.

When I ask you to summarize the open cases, you must strictly follow my instructions below.

Instructions:
"""
Summarize the open cases in one paragraph no more than 500 characters. Mention how many open cases there are and what the case issues are.
Use clear, concise, and straightforward language using active voice and strictly avoiding the use of filler words and phrases and redundant language. 

Use the following information to write the summary: 

Case #1 details: The widgets we received are the wrong size. We needed a widget in size A, but we received a widget in size B.

Case #2 details: Our widgets haven’t been delivered. We can't track our order. According to the last tracking update, the widgets should have arrived on June 5. Now it's June 10, and they still haven't arrived.

Do not attribute any positive or negative traits in the summary.
"""

Now create the summary.
```

The LLM generated this summary.

```
There are two open cases for the Astro’s Bakery account. In Case #1, the issue is that the received widget is the wrong size. The requested size was A, but size B was received instead. In Case #2, the issue is that the widgets haven’t been delivered and the order cannot be tracked. The expected delivery date was June 5, but as of June 10, the widgets have not arrived.
```

The quality of an LLM’s response depends on the prompt’s specificity. Vague or inaccurate instructions can lead an LLM to produce an irrelevant or a biased response. Sometimes an LLM can even hallucinate and generate false information. And because you make a new call to the LLM every time you run a prompt, its responses can differ, even if you’re passing in the exact same prompt. To prevent hallucinations and to minimize variability between responses, create a prompt with as much specific data as possible. It’s important to review and edit your prompt until you consistently achieve high-quality, accurate responses.

The process of creating and iterating on a new prompt to generate just one high-quality response can be time-consuming. It’s even harder to design dozens of original prompts, each with different data and specifications. Also, prompts created by different people can produce inconsistent output due to variations in writing style. To scale prompt design efficiently, it’s best to use a prompt template, which is a reusable prompt. A prompt template includes placeholders for specific details about customers, products, and more.

![Example](https://sf-zdocs-cdn-prod.zoominsoftware.com/tdta-ai-generative_ai-264-0-0-production-enus/fc2f2f57-79fe-4598-a5e0-089f9b72c638/images/icon_example.png)

Example

This prompt template instructs an LLM to generate a summary of an account’s open cases. Unlike the previous example prompt, this prompt template doesn’t specify an account name or describe current open cases. Instead, the prompt template contains merge fields, such as `{!$Input:Account.Id}`, as placeholders.

```
You are a support representative and you need to create a short summary of all open cases for account {!$Input:Account.Id}.

When I ask you to summarize the open cases, you must strictly follow my instructions.

Instructions:
"""
Summarize the open cases in one paragraph no more than 500 characters. Mention how many open cases there are and what the case issues are.
Use clear, concise, and straightforward language using active voice and strictly avoiding the use of filler words and phrases and redundant language. 

Use the following information to write the summary: 

{!$Flow:Get_Open_Cases_for_Account}

Do not attribute any positive or negative traits in the summary.
"""

Now create the summary.
```

![Note](https://sf-zdocs-cdn-prod.zoominsoftware.com/tdta-ai-generative_ai-264-0-0-production-enus/fc2f2f57-79fe-4598-a5e0-089f9b72c638/images/icon_note.png)

Note The `{!$Resource}` wrapper syntax displays as `Resource` in the Prompt Builder UI. The wrapper syntax enables you to copy and paste the text into the Prompt Template Workspace with correctly configured resources.

Prompt Builder replaces the placeholders in your template with your real data. The result is a prompt that’s tailored to the data that you selected. This process of populating a prompt template with specific data is called prompt resolution. An example of a resolved prompt is the prompt about the two open cases for the Astro’s Bakery account. With Einstein, prompt resolution is as easy as selecting Salesforce records to associate with the prompt.

Using prompt templates is ideal for B2C communications because they can generate consistent and data-driven output at scale. Templates that contain the same brand guidelines generate content with a unified voice and style. Each template is developed for a specific use case, and you can reuse it by tailoring the prompt with different data.

## See Also

-   [Get to Know Prompt Builder](https://help.salesforce.com/s/articleView?id=ai.prompt_builder_get_to_know.htm&language=en_US&type=5)

# Prompt Builder Limits

Learn the numerical limits of prompt templates.

## Numerical Limits

Prompt templates have these numerical limits.

Numerical Limits
| Limit Description | Limit |
| --- | --- |
| Maximum template size | 128,000 characters |
| Maximum number of template versions | 50 |
| Maximum number of merge fields | 50 |
| Maximum number of flow merge fields | 5 |
| Maximum number of Apex merge fields | 5 |
| Maximum number of related list merge fields | 5 |
| Maximum number of inputs in a Flex template | 5 |

## File Upload Limits

Most AI models support at least one file type for prompt templates.

These file limits apply across all AI models.

-   Maximum quantity: 10 files per request
-   Total file size: 15 MB per request

The 15 MB total applies to the files sent to the AI model. Files that convert to PDF count toward this total after conversion.

![Important](https://sf-zdocs-cdn-prod.zoominsoftware.com/tdta-ai-generative_ai-264-0-0-production-enus/fc2f2f57-79fe-4598-a5e0-089f9b72c638/images/icon_important.png)

Important Some AI models have smaller limits than the ones listed here. Open **Details** for the selected AI model for per-type limits.

Unsupported files, files that fail conversion, and files that exceed a limit are excluded from the request. The Resolution panel lists excluded files after processing.

## See Also

-   [Grounding with File Inputs](https://help.salesforce.com/s/articleView?id=ai.prompt_builder_ground_file.htm&language=en_US&type=5)
-   [Prompt Builder Limitations](https://help.salesforce.com/s/articleView?id=ai.prompt_builder_limitations.htm&language=en_US&type=5)

# Grounding with Related List Merge Fields

Ground your prompt templates with your object’s related lists to add depth and context to your grounding.

![Note](https://sf-zdocs-cdn-prod.zoominsoftware.com/tdta-ai-generative_ai-264-0-0-production-enus/fc2f2f57-79fe-4598-a5e0-089f9b72c638/images/icon_note.png)

Note Where possible, we changed noninclusive terms to align with our company value of Equality. We maintained certain terms to avoid any effect on customer implementations.

With related list support in Prompt Builder you can add related list merge fields in your prompt templates for rich grounding. When you ground a prompt template with a related list, the fields for the related list are based on the page layout of the parent object for the current user. Record-level filters aren’t applied. The retrieved data is rendered in JSON format and shown in the resolution.

## Considerations, Guidelines, and Limitations

Consider these points when grounding your prompt templates with related lists in Prompt Builder.

-   Activities related lists on objects such as Account and Case aren’t supported.
-   If you configure a related list in a prompt template and a user doesn’t have the related list on their parent object’s page layout or Read permission on the associated object, no related list data is sent to the LLM.
-   Only related lists available on the object’s page layout are available for grounding in Prompt Builder. If an object has custom record types, only related lists on the master record type’s layout are available. If no default record type exists for the context user, the Salesforce default record type is used instead.
-   When entering an expression rather than selecting a resource in the Resource field, an object is shown as `{!$RelatedList:Account.Contacts.Records}`. After you enter this expression, Prompt Builder simplifies the UI presentation, leaving only `Related List: Account.Contacts`.
-   In situations where a related list yields zero results, the prompt response still responds successfully but without adding any related list content to the response.
-   The User and Organization related lists aren’t supported due to a limitation involving global variables.
-   Prompt Builder grounds related-list files that are Salesforce Files. Classic Attachment records aren’t supported.
-   In Salesforce Classic, uploading a file from the **Notes & Attachments** or **Attachments** related list can create a classic Attachment record instead of a Salesforce File. Prompt Builder can’t resolve that file for grounding. Files uploaded from the **Files** related list, including uploads in Lightning Experience, are Salesforce Files.
-   Related lists such as **Notes & Attachments** and **Combined Attachments** can include Salesforce Files and classic Attachment records. Prompt Builder uses only the Salesforce Files in that list.
-   Convert existing classic Attachment records to Salesforce Files before you use them for grounding. If a related-list file is missing from the resolved prompt, then convert it to a Salesforce File and preview again. File size and system limits aren’t the cause.


# Grounding Prompts with Record Snapshots

Ground your prompt templates with Record Snapshots for a more convenient and powerful prompt authoring experience.

For the most part, grounding your prompts with different types of Salesforce data has the same basic process. Start by crafting a prompt that incorporates Salesforce data. Then populate your prompt with grounding resources from the resources field in the Preview section. And then Prompt Builder resolves the grounding resources with real data when generating the response.

Record Snapshots brings a new way to ground your prompts, by automatically including data available on the user's page layout for an object with one resource. Instead of individually selecting multiple fields and related lists for an object, you can include relevant data for grounding with one click.

The data that Record Snapshots uses to ground your prompt depends on the page layout of the user. Page layouts are configurable, and the configuration impacts which data is used by Record Snapshots. In other words, when a prompt runs with Record Snapshots, the data used in the snapshot resolution reflects the data visible to that user. You can still select individual fields and resources in addition to Record Snapshot for an object.

![Note](https://sf-zdocs-cdn-prod.zoominsoftware.com/tdta-ai-generative_ai-264-0-0-production-enus/fc2f2f57-79fe-4598-a5e0-089f9b72c638/images/icon_note.png)

Note The account record snapshot output includes additional grounding data, such as key account fields, products, top opportunities, statistics on open cases, and past activities. The additional grounding data is always included independent of the page layout when it’s available.

## Considerations and Limitations

Consider these points when grounding your prompts with Record Snapshots.
- Dynamic Forms aren’t used in Record Snapshots. However, if Dynamic Forms are activated for an object used by Record Snapshots, the underlying page layout is still used.
- Prompt Builder restricts the quantity of data received from each source to avoid overflowing the prompt token limits.
- “Empty” data (fields without values, sections without limits, and so on) are filtered out.
- Prompt Builder imposes these limitations on each data source used with Record Snapshots.
    
    | Data Source | Limit | Criteria |
    | --- | --- | --- |
    | Page layout | None for the number of fields returned. |   |
    | Compact page layout | None for the number of fields returned. |   |
    | Related Lists | The first 6 related lists from the page layout are used, and up to 5 records are used per related list. |   |
    | Tasks | The next 5 upcoming tasks are used. | Tasks are selected based on ActivityDate (ascending order), Priority (descending order), and ModifiedDate (descending order). |
    | Events | The next 5 upcoming events are used. | Events are selected based on start date (ascending order). |
    | Emails | The 5 most recent emails are used. |   |
    

#### See Also

-   [Review, Revise, and Repeat: Ensure That a Prompt Template Is Effective](https://help.salesforce.com/s/articleView?id=ai.prompt_builder_review_revise.htm&language=en_US&type=5)
-   [Assign Page Layouts to Profiles or Record Types](https://help.salesforce.com/s/articleView?id=platform.layouts_assigning.htm&language=en_US&type=5)
-   [Page Layout Considerations](https://help.salesforce.com/s/articleView?id=platform.layouts_considerations.htm&language=en_US&type=5)

# Ground Prompt Templates with Salesforce Resources

With Prompt Builder, you can dynamically ground prompt templates with CRM data using merge fields.

The zero-retention agreement in the Einstein Trust Layer ensures that anything shared with the LLM isn’t stored or used for training. For more information, see [The Einstein Trust Layer](https://trailhead.salesforce.com/content/learn/modules/the-einstein-trust-layer) Trailhead module.

When you create a prompt template in Prompt Builder, you first choose an object, such as an account or contact, to associate with your template. For a field generation template, you also select the field that you want Einstein to help users complete.

As you write your prompt template in the Prompt Template Workspace, you can use the **Insert Resource** button to add merge fields that reference record fields, flows, Apex, Data 360 DMOs, and related lists. When you create a prompt template, it works with Apex or flows whose required inputs are a subset of the prompt template inputs. For flows, all inputs are considered required and must be present in the prompt template. For Apex, inputs are optional unless annotated as required. Optional Apex inputs don’t have to be present in the prompt template. Apex and flows with no parameters work with all prompt templates.

#### See Also

-   [Prompt Builder Limits](https://help.salesforce.com/s/articleView?id=ai.prompt_builder_limits.htm&language=en_US&type=5)
-   [Prompt Builder Limitations](https://help.salesforce.com/s/articleView?id=ai.prompt_builder_limitations.htm&language=en_US&type=5)
-   [Troubleshoot Prompt Builder](https://help.salesforce.com/s/articleView?id=ai.prompt_builder_troubleshoot.htm&language=en_US&type=5)

# Get Started with Prompt Builder

## Learning Objectives

In this project, you’ll:

- Create and test a prompt template that includes merge fields.  
    
- Associate a prompt template with a text field for field generation.  
    

## Streamline Content Generation

Prompt Builder gives your organization an easy way to tap into the power of generative AI. It helps you combine existing data with some well-crafted instructions to create prompt templates. In a nutshell, prompt templates are used to create prompts, the messages sent to large language models (LLMs) in order to generate content.

Prompt templates are special because they include placeholders for specific details about customers, products, cases, and more. Each time a prompt template is used, it merges the data to create a unique, personalized prompt, which results in a personalized response. And since prompt templates are reusable, they’re a key part of a scalable AI implementation. For a more in-depth explanation of prompts and prompt templates, check out [Prompt Fundamentals](https://trailhead.salesforce.com/content/learn/modules/prompt-fundamentals).

In this project you get hands-on by creating a prompt template, and then use it to get actual generated responses from an LLM. Specifically, you’ll focus on a scenario everyone is familiar with: customer support cases. In an effort to boost productivity and customer satisfaction, you want to use generative AI to summarize the details of a case in about 100 words. This enables agents to get up to speed quickly and makes it easier to identify cases that deserve special attention.

## Sign Up for a Trial Org with Agentforce

To complete this project, you need a special, limited-time custom playground that contains Einstein AI and our sample data.

1.  Click **Create Playground**.  
    
2.  Your new org is automatically attached to your Trailhead account!  
    
3.  Make note of your org's expiration date and complete this badge before then.  
    

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

This custom playground is designed to work with the challenges in this badge and may not work for other badges. Always check that you’re using the Trailhead Playground or special org that we recommend.

If you’re working on related Einstein AI content in Trailhead, you may also use this org for these projects:

-   [Quick Start: Agentforce](https://trailhead.salesforce.com/content/learn/projects/quick-start-einstein-copilot)  
    
-   [Quick Start: Create a Prompt Builder Flex Template](https://trailhead.salesforce.com/content/learn/projects/quick-start-create-prompt-builder-flex-template)  
    
-   [Quick Start: Create a Sales Email Prompt Template](https://trailhead.salesforce.com/content/learn/modules/quick-start-create-a-sales-email-prompt-template)  
    

## Enable Agentforce Studio

Now, let’s make sure Agentforce Studio is turned on in your org.

1.  If you don’t already have your Agentforce-enabled trial org open, scroll down to the Challenge section and click **Launch** to open it.  
    
2.  Click ![setup](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/projects/quick-start-prompt-builder/get-started-with-prompt-builder/images/42c79cc86ee9a09de750283761cd9083_kix.l7nor34dxyii.png) and click **Setup**. The Setup page opens in a new tab.  
    
3.  In the Quick Find box, search for and select **Salesforce Go**.  
    
4.  In the Search features... textbox, enter and select **Agentforce Studio**.  
    

![](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/projects/quick-start-prompt-builder/get-started-with-prompt-builder/images/af144ad159b5d8d56e6590317516df4a_kix.btx6p2qpvkq9.png)\[alt text: The Salesforce Go page showing Agentforce Studio selected from the search features menu.\]

5.  Click **Get Started**.  
    
6.  Click **Turn On**.  
    
7.  Click **Confirm**.  
    
8.  Wait just a moment until you see the Turn On button change to **On**, then refresh your browser.  
    

## Create a Field Generation Prompt Template

In this project, you want a case summary to appear in a text field on the record. To save a little time, Team Trailhead has already created a field named Quick Summary and added it to the page layout. At this point there’s nothing special about it, but let’s change that!

1.  Click ![App Launcher](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/projects/quick-start-prompt-builder/get-started-with-prompt-builder/images/915af7df5f41491f716e685cdb1aa123_kix.p6cm6f81ol7x.png) , then search for and select **Agentforce Studio**.  
    
2.  Click **Prompt Templates** to open Prompt Builder in Setup.  
    
3.  Click **New Prompt Template**.  
    
4.  For Prompt Template Type, select **Field Generation**.  
    
5.  For Prompt Template Name, enter `Quick SummaryCopy`.  
    
6.  Press the Tab key to populate the API Name field: `Quick_SummaryCopy`.  
    
7.  For Template Description, enter `A short summary of case detailsCopy`.  
    
8.  For Object, find and select **Case**.  
    
9.  For Object Field, find and select **Quick Summary**.  
    
10.  Click **Next**.  
     

Great, you now have the start of a prompt template. It’s time to build it by writing some clear instructions that describe what you want from the LLM. As you learn in the [Prompt Fundamentals](https://trailhead.salesforce.com/content/learn/modules/prompt-fundamentals) badge, there are several things you can add to get better results. In this example you include the overall goal, size limits, and some guardrails.

Writing a good prompt is somewhat of an art form, so for this project we give you a prompt that we know works well.

1.  Paste the following text into the **Prompt** | **Insert Resource** field. `Summarize the concatenation of the contents of the comment bodies of COMMENTS along with the text from SUBJECT, the case priority which is PRIORITY, and the case type which is TYPE. Keep the response to a single short paragraph.Copy`
2.  Click **Save**.  
    
3.  In the Models list, make sure **OpenAI** **GPT 4 Omni Mini** is selected. There are several models to choose from in your Agentforce-enabled org, and OpenAI GPT 4 Mini produces some great results.  
    

![The Template Properties pane displays a list of model types and a list of available models. OpenAI GPT 4 Omni Mini is selected.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/projects/quick-start-prompt-builder/get-started-with-prompt-builder/images/a6653900954e560fc1228c8f08c97b51_kix.hqe546v2plae.png)

This sample text includes a few placeholders in all caps for things like case priority. Let’s replace those with actual merge fields so the LLM can create a tailored response for a variety of situations.

1.  In the prompt sample text, place the mouse cursor in front of the word PRIORITY.  
    

![Prompt template workspace with pre-populated prompt text.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/projects/quick-start-prompt-builder/get-started-with-prompt-builder/images/5f7afc793bc86466d47e92cf1a0d766c_kix.r1u6fekj4mf9.png)

2.  Click **+** **Insert Resource** to open the list of resources.  
    

![The Resources menu displays Current Organization, Current User, and Case resources.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/projects/quick-start-prompt-builder/get-started-with-prompt-builder/images/d9158d958c35ca6ffc290b311bf1fba8_kix.hyg1inelslrl.png)

3.  Click **Case**, then click **Priority**.  
    A merge field is inserted as blue text.  
    
4.  Delete PRIORITY to leave behind just the merge field. It should now look like this:  
    …the case priority which is **Input:Case.Priority**, and the case type…  
    

Next, you repeat the process to replace the COMMENTS, SUBJECT, and TYPE text placeholders.

1.  Place the mouse cursor in front of COMMENTS.  
    
2.  Click in the **Resource** box. Select **Case**, then click **CaseComments**.  
    Note: Notice the colorful text, it indicates that this is a related list. (The text color may vary depending on your browser settings.)  
    
3.  Delete COMMENTS to leave behind just the merge field. It should now look like this:  
    Summarize the concatenation of the contents of the comment bodies of **RelatedList: Case.CaseComments** along with the text…  
    

4.  Place the mouse cursor in front of SUBJECT.  
    
5.  Click in the **Resource** box. Select **Case**, then click **Subject**.  
    
6.  Delete SUBJECT to leave behind just the merge field.  
    
7.  And finally, place the mouse cursor in front of TYPE.  
    
8.  Click in the **Resource** box. Select **Case**, then click **Case Type**.  
    
9.  Delete TYPE to leave behind just the merge field.  
    
10.  Click **Save**.  
     

With merge fields in place, your prompt template should look like this:

Summarize the concatenation of the contents of the comment bodies of **RelatedList: Case.CaseComments** along with the text from **Input:Case.Subject**, the case priority which is **Input:Case.Priority**, and the case type which is **Input:Case.Type**.

Keep the response to a single short paragraph.

It’s just that easy to ground your prompt in real data. Now that your prompt template includes merge fields and good instructions, it’s time to test it out. Prompt Builder makes it easy to preview your prompt template using actual data. All you need is a sample record to draw from.

1.  Click **Preview**, then click **Inputs** to expand the Inputs box.  
    
2.  In the Related Record box, find and select case **00001002**.  
    

![Related record input box corresponding to the preceding step.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/projects/quick-start-prompt-builder/get-started-with-prompt-builder/images/5f3b50ada5d875a5016b410698d95a24_kix.gboo58kfg7et.png)

3.  Click **Preview**.  
    
4.  Click **Activate**.  
    

This is the moment you’ve been waiting for! Your instructions have been sent to the LLM, and in response you get a generated summary of the case in just a few sentences in the Generated Response field. Yours may appear a little different than the examples in this project. That’s OK, it’s normal for LLMs to respond to the same prompt in more than one way.![The Prompt Builder template showing the generated response.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/projects/quick-start-prompt-builder/get-started-with-prompt-builder/images/22c05129ac6755569cc9f2d2bc8b90e8_kix.w9z7sb6cf2ph.png)

## Enable Dynamic Forms for Cases

Your prompt template is ready to go. The last step is to update the page layout so that your customer support team can use the new prompt template.

1.  While still on the Prompt Builder page, verify that you’ve clicked **Activate**.  
    
2.  Close the Setup tab to return to the Sales app.  
    
3.  Click ![App Launcher](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/projects/quick-start-prompt-builder/get-started-with-prompt-builder/images/915af7df5f41491f716e685cdb1aa123_kix.ihgz6u47q9hk.png), then search for and select **Cases**.  
    
4.  Click the arrow next to Recently Viewed, and select **All Open Cases**.  
    
5.  Click case number **00001002**.  
    
6.  Click ![Setup](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/projects/quick-start-prompt-builder/get-started-with-prompt-builder/images/7044ccc1a277b34ac3da9638b8942c35_kix.xfyi1rs4rv3t.jpg) and click **Edit Page**.  
    
7.  In the Details section, click inside the record **Details** component \[1\].  
    

![Record Detail in the Details section](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/projects/quick-start-prompt-builder/get-started-with-prompt-builder/images/fd29036f3f1b7b0e9a761b626c5e926f_kix.uw7syr1z60gg.png)

8.  In the properties pane to the right, click **Upgrade Now** to upgrade to Dynamic Forms. (If you don’t see the Upgrade Now button in the properties pane, click in the center of the Details panel.)  
    
9.  Click **Next**.  
    
10.  Select the **Case Layout** page layout.  
     
11.  Click **Finish**.  
     
12.  In the Case Information section, click the **Quick Summary** field.  
     
13.  For Prompt Template, find and select **Quick Summary**.  
     

![Prompt Template selection box corresponding to the preceding steps.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/projects/quick-start-prompt-builder/get-started-with-prompt-builder/images/9951ff72e1dc9925386fa1c31a874817_kix.1y10cm3bkyq.png)

14.  Click **Save** and then **Activate**.  
     
15.  Click the **Assign as Org Default** button (you may need to scroll down a bit), then click **Next**.  
     
16.  On the Assign form factor screen, select **Desktop and phone**.  
     
17.  Click **Next** and then **Save**.  
     
18.  Click ![back](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/projects/quick-start-prompt-builder/get-started-with-prompt-builder/images/ba7568e9626b0b320824369985f2ea96_kix.xlohzgsso2ah.png) to leave Lightning App Builder.  
     

Excellent, the Quick Summary field is ready to use Einstein Generative AI. You can tell because the edit button has a little star next to the pencil now.

Let’s try it out.

1.  On the Case 00001002 record, in the Details pane, click ![Edit](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/projects/quick-start-prompt-builder/get-started-with-prompt-builder/images/1a2ac6759f6cbf54f3750c59b8a4d8bf_kix.na3e4j6uj0ei.png) on the Quick Summary field.  
    

![Screenshot of the Quick Summary field with Einstein-enabled icon.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/projects/quick-start-prompt-builder/get-started-with-prompt-builder/images/18b13b02e4d27708b97936e140db16c1_kix.9zl97sgldz4x.png)

2.  Click ![Get Einstein’s help in creating this field value.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/projects/quick-start-prompt-builder/get-started-with-prompt-builder/images/c2acfb8d7a4feeb4d59ad5a69134b848_kix.5wmo2aiatic1.png) on the right of the field.  
    This automatically opens up the Einstein overlay and uses your prompt template to start a new conversation. In a moment Einstein will suggest a case summary. Again, yours may be a little different than ours:  
        
    Here is what I came up with  
    The comments regarding the case include the following actions: contacting engineering for a PDF of the wiring diagram, emailing the diagram to the customer while awaiting a reply, and noting that the generator was manufactured in 2019. This case, which has a low priority and pertains to electrical issues, seeks guidance on the electrical wiring installation for GC5060.  
       
    In the Einstein overlay panel, it looks like this:  
    

![Einstein overlay with a suggested case summary.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/projects/quick-start-prompt-builder/get-started-with-prompt-builder/images/7ac71b50eb01f4b87443c8fe9d297aa7_kix.xv3qljnumfin.png)

This gives your users a chance to review the summary, and even continue the conversation with Einstein to work together on a revised version. For this example, you just accept the first suggestion.

3.  Click **Use**. (There should be a Use button in the Einstein overlay. If there isn’t, just refresh the page and do steps 1 & 2 again.)  
    
4.  Click the **X** to close the Einstein overlay.  
    Notice that the Quick Summary field is filled in.  
    
5.  Click **Save**.  
    

With just a few clicks, your users can access the power of Agentforce to quickly create useful content so that they can focus on more important things. The conversational nature of Agentforce lets your users refine the generated content in real time, and they can always tweak it after it’s placed into the field.

Great job creating such a helpful prompt template. Have fun experimenting in the Prompt Builder to discover other ways to automate text generation for your organization.

## Resources

-   [_Trailhead_: Prompt Fundamentals](https://trailhead.salesforce.com/content/learn/modules/prompt-fundamentals)
-   [_Trailhead_: Prompt Builder Basics](https://trailhead.salesforce.com/content/learn/modules/prompt-builder-basics)
-   [_Trailhead_: Generative AI Basics](https://trailhead.salesforce.com/content/learn/modules/generative-ai-basics)

# Create and Ground Prompt Templates

## Learning Objectives

After completing this unit, you’ll be able to:

-   Describe what grounding is.  
    
-   Use Prompt Builder to create a sales email prompt template.  
    
-   Add resources to a prompt template.  
    
-   Use an Apex class to provide data to a prompt template.  
    

## The Why and the How

In the [Prompt Builder: Quick Look](https://trailhead.salesforce.com/content/learn/modules/prompt-studio-quick-look) module, Linda Rosenberg, a Salesforce admin, aimed to reduce her sales team's manual workload by automating tasks with prompt templates. In this module, we take a deeper dive and show you _why_ and _how_ she did it.

## Build a Sales Email Prompt Template

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

To create a sales email prompt template, your org needs the Einstein for Sales, Einstein for Platform, or Einstein for Service add-on. You also need to enable Einstein for Sales in Setup.

Linda needs to create a template that her sales team can use to generate emails. She wants to reduce the time that the team spends on creating invitations to customers for product events.

To do this, Linda navigates to Prompt Builder in Salesforce Setup. When she navigates to Prompt Builder, the first page that’s shown is the Prompt Builder Explore page. Here you find:

-   Guidance to help you learn more about the features of Prompt Builder.  
    
-   Access to prompt template walkthroughs and examples.  
    
-   A listing of all existing prompt templates with their type, category and status.  
    
-   Functionality to edit and delete existing prompt templates.  
    

![Prompt Builder Explore page.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/prompt-builder-basics/create-and-ground-prompt-templates/images/95a113dca83b776e558477bf481472e0_kix.xv4567lcneta.png)

From the Explore page, Linda can also create a prompt template. She clicks the **New Prompt Template** button.

![Template type setup.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/prompt-builder-basics/create-and-ground-prompt-templates/images/ac4c3c34c622de8aa010af1236a6e8b4_kix.dugeapct6kw.png)

Linda starts to complete the fields in the template type setup screen.

When you set up a prompt template, it’s important to have a clear goal. In this case, Linda must think about who her company’s customers are and what the sales team wants them to see in the email.

Linda understands that her email may be sent to any Cloud Kicks contact. Therefore, Contact is the recipient object. She completes the template type setup by selecting:

1.  Prompt Template Type: **Sales Email**  
    
2.  Prompt Template Name: `Invite Customer to Local Product EventCopy`
3.  API Name: `Invite_Customer_to_Local_Product_EventCopy`
4.  Template Description: `Email customer to invite to local product event.Copy`
5.  Recipient: **Contact**  
    
6.  Related Object: **Account**  
    

## Ground Your Template

Making templates _specific_ makes them effective. Another way of saying “specific” is to say your template is _grounded_.

Once Linda has defined her template type, she begins drafting and grounding her prompt in the Prompt Template Workspace.

![Prompt template workspace with prompt.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/prompt-builder-basics/create-and-ground-prompt-templates/images/e0ca687be16abb145c282e185a510b90_kix.mc50owi3ebch.png)

Linda includes the customer name, who the email is from, their titles, and details about the event.

| 
You are a Salesforce admin and your name is Linda Rosenberg from the organization Cloud Kicks. Your prospect is Rob Hutchinson, a director from Acme Inc., and they are based in Toronto, Ontario.

In the email, invite the prospect to attend the event “Floating on Clouds: Toronto Kickoff” on September 18, an event for customers of Cloud Kicks new and old to network and preview upcoming products, in no more than 70 words. Explain to the prospect the possible benefits of attending the event and mention that you would be happy to chat with them further at the event or online if they need more information.

 |
| --- |

The prompt looks great. However, her first draft is hard-coded for only one specific sender and recipient. That would be okay if the prompt is going to be used once. But the concept of a prompt template is that it can be used for any sender and recipient. What she needs is a way to get her company’s CRM data into the template and ground it automatically.

Happily, Linda knows that she can use merge fields, Apex, and Flow as resources to enable Prompt Builder to securely access Salesforce data.

## Add Merge Fields to a Prompt Template

Linda reviews her prompt and looks for areas where she can use merge fields to take her prompt from hardcoded for one-time use to reusable for any sender and recipient.

| 
You are a **Salesforce admin** and your name is **Linda Rosenberg** from the organization **Cloud Kicks**. Your prospect is **Rob Hutchinson**, a **director**. They are based in **Toronto,** **Ontario**.

In the email, invite the prospect to attend the event **“Floating on Clouds: Toronto Kickoff” on September 18, an event for customers of Cloud Kicks new and old to network and preview upcoming products**, in no more than 70 words. Explain to the prospect the possible benefits of attending the event and mention that you would be happy to chat with them further at the event or online if they need more information.

 |
| --- |

Within the Prompt Template Workspace, Linda uses the **Resources** picklist to choose the type of resource to use. She sees there are multiple options for sales email prompt templates. Current Organization, Sender, and Recipient are all available to use in her prompt template.

![List of resources including Flows (None Available), Apex, Current Organization, Sender, Recipient, and Account.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/prompt-builder-basics/create-and-ground-prompt-templates/images/b242bbdf003e5428f24ad4827f37cee4_kix.ius19giuqzl4.png)

In the Resources picklist, Linda selects **Sender** and **Recipient**, where she then selects specific information, like title, name, company, and so on to ground her prompt template. She saves her work.

| 
![Resource picker displays the sender merge fields available.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/prompt-builder-basics/create-and-ground-prompt-templates/images/c478e67264bddc8dad9d0f0b62cc6944_kix.y1ngy4xvdrnz.png)

 | 

![Resource picker displays the recipient merge fields available.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/prompt-builder-basics/create-and-ground-prompt-templates/images/5efc5aaac51723854424a46bbb499b21_kix.ulq42lzdaghv.png)

 |
| --- | --- |

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

In this module you see the syntax `{!$Resource}Copy` in the prompt templates. This special syntax helps you to easily copy and paste the text from this module into the Prompt Template Workspace. It ensures all of your resources stay where and how you expected them in your template.

| 
You are a `**{!$Input:Sender.Title}**Copy` and your name is `**{!$Input:Sender.Name}**Copy` from `**{!$Input:Sender.CompanyName}**Copy`. Your prospect is `**{!$Input:Recipient.Name}**Copy`, a `**{!$Input:Recipient.Title}**Copy`. They are based in `**{!$Input:Recipient.MailingCity}**Copy`.

In the email, invite the prospect to attend the event "Floating on Clouds: Toronto Kickoff" on September 18, an event for customers of Cloud Kicks new and old to network and preview upcoming products, in no more than 70 words. Explain to the prospect the possible benefits of attending the event and mention that you would be happy to chat with them further at the event or online if they need more information.

 |
| --- |

After she’s done, she notices there’s one piece of her prompt that needs an adjustment before it can display the correct response: "Floating on Clouds: Toronto Kickoff" on September 18.

At Cloud Kicks, “Floating on Clouds” is a nationwide event that hosts local customers based on their city. Linda wants to make sure the sales email prompt template is as personalized as possible and generates emails that invite customers to local events.

Linda understands that using only merge fields for this portion isn't enough. She needs logic incorporated into her prompt template. There are several approaches to accomplish this within Prompt Builder, including using Apex or Template-Triggered Prompt Flows. First, let’s explore how to use Apex in prompt templates.

## Add Apex to a Prompt Template

If you want to use data from a SOQL query or an external API in your prompt, consider Apex. Apex is also effective if you want to generate well-formatted JSON or do programmatic data filtering.

In this case, Linda wants to create an Apex class that finds events that are close to a given contact and returns the name of the event, subject, location, and start time. Using the Developer Console she creates a class named `ContactEventsCopy` with a method annotated as `InvocableMethodCopy`. The `InvocableMethodCopy` must accept `List<Request>Copy` where the inputs defined in the `RequestCopy` class match the inputs within the prompt. Also, the `InvocableMethodCopy` must be labeled with the `CapabilityTypeCopy` that matches the template type.

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

If you are interested in learning more about adding Apex classes to prompt templates or to see code samples, check out the [Salesforce Documentation](https://help.salesforce.com/s/articleView?id=ai.prompt_builder_ground_apex.htm&type=5).

Once her class is created, Linda returns to the Prompt Template Workspace in Prompt Builder and notices that Apex is now a resource. She adds the Apex class by clicking **Resources** and selecting **Apex**.

| 
![List of resources including Flows (None Available), Apex, Current Organization, Sender, Recipient, and Account.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/prompt-builder-basics/create-and-ground-prompt-templates/images/acbc6dae34997c03588b488c9e2f14d2_kix.pa6h43kprsb9.png)

 | 

![Resource picker displays the Apex classes available.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/prompt-builder-basics/create-and-ground-prompt-templates/images/1858a82ae5ea6d4342f30518560bd72b_kix.totuorra1rsp.png)

 |
| --- | --- |

| 
You’re a `{!$Input:Sender.Title}Copy` and your name is `{!$Input:Sender.Name}Copy` from `{!$Input:Sender.CompanyName}Copy`. Your prospect is `{!$Input:Recipient.Name},Copy` a `{!$Input:Recipient.Title}Copy`. They are based in `{!$Input:Recipient.MailingCity}Copy`.

In the email, invite the prospect to attend an event for customers of Cloud Kicks new and old to network and preview upcoming products, in no more than 70 words.Explain to the prospect the possible benefits of attending the event and mention that you would be happy to chat with them further at the event or online if they need more information.

Add the following event information to the email: `{!$Apex:ContactEvents.Prompt}Copy`.

 |
| --- |

Great! Now instead of referencing one single event. Linda can rely on her Apex class to return an event close to the specified contact.

## Resources

-   [_Salesforce Help_: Ground with Apex Merge Fields](https://help.salesforce.com/s/articleView?id=ai.prompt_builder_ground_apex.htm&type=5)
-   [_Salesforce Help_: Set Up Sales Emails](https://help.salesforce.com/s/articleView?id=ai.einstein_sales_emails_setup.htm&type=5)
-   [_Trailhead_: Prompt Fundamentals](https://trailhead.salesforce.com/content/learn/modules/prompt-fundamentals)


# Prompt Builder

Simplify your users’ daily tasks by integrating generative-AI moments powered by prompt templates into their workflow. Create, test, revise, customize, and manage prompt templates that incorporate your CRM data from merge fields that reference record fields, flows, related lists, and Apex. Prompt Builder helps you to make effective prompts that safely connect you and your data with LLMs.

Create different types of prompt templates in Prompt Builder.

-   A Sales Email prompt template helps your sales team to draft personalized emails for a contact or a lead.
-   A Field Generation prompt template brings generative AI-assisted workflows to fields within Lightning record pages. Enable your users to populate a field with a summary or description created by an LLM to facilitate more productive conversations with your customers.
-   A Flex prompt template takes a variable number of inputs of different object types. This flexibility opens up a wide array of possibilities, such as generating a newsletter based on product and campaign objects.

Call a prompt template through an invocable action anywhere on the Salesforce Platform or by using the Connect REST API or Connect in Apex.

Assign the Prompt Template Manager permission set to Salesforce admins who create and manage prompt templates in Prompt Builder.

#### See Also

-   [Integrate Prompt Templates with Salesforce Features](https://help.salesforce.com/s/articleView?id=ai.prompt_builder_integrate.htm&language=en_US&type=5)
-   [_Trailhead_: Prompt Fundamentals](https://trailhead.salesforce.com/content/learn/modules/prompt-fundamentals)
-   [_Trailhead_: Prompt Builder: Quick Look](https://trailhead.salesforce.com/content/learn/modules/prompt-studio-quick-look)
-   [_Trailhead_: Prompt Builder: Basics](https://trailhead.salesforce.com/content/learn/modules/prompt-builder-basics)
-   [_Video_: Get to Know Prompt Builder](https://salesforce.vidyard.com/watch/kJPBHFRvvTpjJZ51Y4hj3A)
-   [_Video_: How to Build a Prompt Template](https://salesforce.vidyard.com/watch/V1G9tgorNbyeaD811SRamA)

# Get Started with the Drive Productivity with Salesforce AI Trail

## Learning Objectives

After completing this module, you’ll be able to:

-   Navigate through the Drive Productivity with Salesforce AI trail.  
    
-   Describe Salesforce AI products, their capabilities, use cases, and implementation considerations.  
    
-   List the three current waves of the AI revolution.  
    

## Begin Your Salesforce AI Journey

Hello! Welcome to the [Drive Productivity with Salesforce AI](https://trailhead.salesforce.com/einstein-ai-trail) trail. This trail is aimed at Salesforce administrators, sales and service professionals, data professionals, and anyone interested in learning how Salesforce AI features can transform their business and customer experiences.

The content in this trail is designed to help you skill up on Salesforce AI products and features while setting you up for success, whether your goal is to apply what you learn to your job, obtain the Salesforce [Agentforce Specialist certification](https://trailhead.salesforce.com/en/credentials/aispecialist), or both.

The trail consists of six sections.

1.  Protect Generative AI data with the Einstein Trust Layer  
    
2.  Use Generative AI in CRM  
    
3.  Create Generative AI Experiences Using Prompt Builder  
    
4.  Set Up and Use Agentforce as a Conversational AI Assistant  
    
5.  Configure Custom AI Models with Model Builder  
    
6.  Get Certification Ready  
    

Each section includes a mix of Trailhead badges–many with hands-on learning experiences–along with videos and demos presented by a Salesforce instructor, and Salesforce Help articles that provide additional details.

## Practice with Salesforce AI Tools

As you move through this trail, you get to try out Salesforce AI tools and features. To complete the exercises and hands-on challenges, you use custom Trailhead Playgrounds with Salesforce AI enabled. You set up your first Playground when you get to the Create Generative AI Experiences Using Prompt Builder section of this trail. Each Playground is available for a limited time, so be sure to complete each project within the time specified on each Playground.

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

A regular Trailhead Playground won’t work for the hands-on challenges in this trail because Salesforce AI features are not enabled in regular Playgrounds.

## What Is Salesforce AI?

You just learned about the trail and the orgs you use, now let’s dig into Salesforce AI. This 7-minute video explains how Salesforce AI enhances your business productivity with predictive and generative AI tools that help your organization work smarter and connect more deeply with customers. Be sure to watch the video so you can pass the quiz at the end of this module.

## What’s Next?

Now that you know the basics of Salesforce AI, take the quiz below and continue on with the [Drive Productivity with Salesforce AI](https://trailhead.salesforce.com/einstein-ai-trail) trail. We recommend that you consume the content in the order presented to get the most out of your learning and to be able to complete each hands-on challenge.

We included documentation in the Resources section of each Trailhead badge to supplement your learning. These resources are meant to enhance your understanding of Salesforce AI and act as helpful study material for the Salesforce [Agentforce Specialist](https://trailhead.salesforce.com/en/credentials/aispecialist) exam.

## Resources

-   [_Salesforce Help_: Einstein Generative AI Glossary of Terms](https://help.salesforce.com/s/articleView?id=ai.generative_ai_glossary.htm&type=5)
-   [_Salesforce Help_: Data 360 Glossary of Terms](https://help.salesforce.com/s/articleView?id=data.c360_a_glossary_guide.htm&type=5)

# Best Practices for Building Prompt Templates

Learn the best practices for building effective prompt templates.

-   Make sure that your prompt templates are concise and easy to understand. Avoid using industry jargon or technical terms. Instead, use natural language and [conversation design best practices](https://help.salesforce.com/s/articleView?id=service.bots_service_best_practice.htm&language=en_US&type=5).
-   To give the LLM more contextual information, ask it to role play as a character, such as a sales or support representative. Then define the character’s goal. For example, include language such as, “You are a marketing executive who wants to invite major customers to a live event.”
-   Iterate on your prompt templates. Try achieving the same goal using different templates to see how the parts impact the model’s response. Get end-user feedback to see how well your prompt templates generate the desired response.
-   Choose a style, and stick to it. When you use a consistent writing style in your prompt templates, the LLM generates consistent responses. Your writing style is shaped by your word choice, intensifiers, emojis, and punctuation.
-   To help the LLM differentiate between context and instructions, create an instructions section in your prompt template. On a separate line, enter Instructions:, then surround your instructions with triple quotes (""").
-   Include direct instructions for the LLM to only generate the expected type of content. For example, if you want the LLM to draft an email, add instructions such as, “Follow these instructions strictly to generate only the message to be sent to the customer.” These instructions prevent the LLM from generating a response about the process of creating content, instead of just generating the content that you want.
-   Start with one of the templates in the [Example Prompt Template Library](https://help.salesforce.com/s/articleView?id=ai.prompt_builder_example_library.htm&language=en_US&type=5), and customize it to fit your specific needs. Study the language that the templates use, especially the text related to writing style. You can use similar phrasing in your own templates.

#### See Also

-   [Ingredients of a Prompt Template](https://help.salesforce.com/s/articleView?id=ai.prompt_builder_template_ingredients.htm&language=en_US&type=5)


# Trust Layer

It’s important that your data stays safe while you innovate with new technology, such as large language models (LLMs). The Einstein Trust Layer includes protections for your data and your users when interfacing with LLMs.

- Grounding in CRM data to ensure accuracy
- Masking of sensitive data, such as social security numbers
- Toxicity detection on LLM generations
- Audit trail and feedback
- Zero data retention agreements with third-party LLM partners

![Einstein trust layer](https://a.sfdcstatic.com/developer-website/sfdocs/genai/media/trust-layer.webp)

## Zero Data Retention

At Salesforce, trust is our #1 value. To keep your data secure, Salesforce has agreements in place with LLM providers, such as OpenAI. These agreements include commitments for zero data retention, allowing you to use generative AI capabilities without worrying about your private data being retained by third-party LLM providers.

## Trusted Generative AI

Salesforce’s Einstein generative AI solutions are designed, developed, and delivered based on our five principles for trusted generative AI.

- **Accuracy**: We back up model responses with explanations and sources whenever possible. We recommend that a human check each model response before sharing them with end users for the majority of use cases.
- **Safety**: We work to detect and mitigate bias, toxicity, and harmful responses from models used in our products through industry-leading detection and mitigation techniques.
- **Transparency**: We ensure that our models and features respect data provenance and are grounded in your data whenever possible.
- **Empowerment**: We believe our products should augment people’s capabilities and make them more efficient and purposeful in their work.
- **Sustainability**: We strive towards building right-sized models that prioritize accuracy and reducing our carbon footprint.

## Reviewing Generative AI Outputs

Generative AI is a tool that helps you be more creative, productive, and make smarter business decisions. This technology isn’t a replacement for human judgment. You’re ultimately responsible for any LLM-generated response you share with your customers. Whether text is human- or LLM-generated, your customers associate it with your organization’s brand and use it to make decisions. So it’s important to make sure that LLM-generated responses intended for external audiences are accurate and helpful, and that they align with your company’s values, voice, and tone.

When your end users review generated responses for external audiences, focus on the accuracy and safety of the content.

- **Accuracy**: Generative AI can sometimes “hallucinate”—fabricate responses that aren’t grounded in fact or existing sources. Before you publish a response, check to make sure that key details are correct. For example, is the customer service suggestion based on an existing and up-to-date knowledge article?
- **Bias and Toxicity**: Because AI is created by humans and trained on data created by humans, it can also contain bias against historically marginalized groups. Rarely, some responses can contain harmful language. Check your responses to make sure they’re appropriate for your customers.

If the response doesn’t meet your standards or your company’s business needs, you don’t have to use it. Some solutions allow end users to edit the response directly, and if not, it’s best to start over and generate another response.

## Next Steps

- Review our [Einstein Trust Layer](https://help.salesforce.com/s/articleView?id=ai.generative_ai_trust_layer.htm) documentation in Salesforce Help.
- Understand [Toxicity Confidence Scoring](/docs/ai/agentforce/guide/models-api-toxicity-scoring.md) with the Models API.
- Understand [Data Masking](/docs/ai/agentforce/guide/models-api-data-masking.md) with the Models API.

## See Also

- *Salesforce Research*: [Trusted AI](https://www.salesforceairesearch.com/trusted-ai)

# Meet the Agentforce Trust Layer

## Learning Objectives

After completing this unit, you’ll be able to:

-   Discuss the #1 Salesforce value, Trust.  
    
-   Describe concerns related to trust and generative AI.  
    
-   Explain why Salesforce created the Einstein Trust Layer.  
    

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

This module includes some beta features of the Einstein Trust Layer. Customers should make their purchase decisions based upon features that are currently generally available.

## Before You Begin

We know you’re eager to learn how Salesforce protects your company and customer data as we roll out new generative artificial intelligence (AI) tools. But, before you begin, you should be familiar with the concepts and terminology covered in these badges.

-   [Generative AI Basics](https://trailhead.salesforce.com/content/learn/modules/generative-ai-basics)  
    
-   [Natural Language Processing Basics](https://trailhead.salesforce.com/content/learn/modules/natural-language-processing-basics)  
    
-   [Large Language Models](https://trailhead.salesforce.com/content/learn/modules/large-language-models)  
    
-   [Prompt Fundamentals](https://trailhead.salesforce.com/content/learn/modules/prompt-fundamentals)  
    

The [Agentforce Glossary of Terms](https://help.salesforce.com/s/articleView?id=ai.copilot_glossary.htm&type=5) also covers many of the terms used in this badge, such as LLMs, prompts, grounding, hallucinations, toxic language, and more.

## Generative AI, Salesforce, and Trust

Everyone is excited about generative AI because it unleashes their creativity in whole new ways. Working with generative AI can be really fun—for instance, using Midjourney to create images of your pets as superheroes or using ChatGPT to create a poem written by a pirate. Companies are excited about generative AI because of the productivity gains. [According to Salesforce research](https://www.salesforce.com/news/stories/generative-ai-for-marketing-research/), employees estimate that generative AI will save them an average of 5 hours per week. For full-time employees, that adds up to a whole month per year!

But for all this excitement, you probably have questions, like:

-   How do I take advantage of generative AI tools and keep my data and my customers’ data safe?  
    
-   How do I know what data different generative AI providers are collecting and how it will be used?  
    
-   How can I be sure that I’m not accidentally handing over personal or company data to train AI models?  
    
-   How do I verify that AI-generated responses are accurate, unbiased, and trustworthy?  
    

### Salesforce and Trust

At Salesforce, we’ve been asking the same questions about artificial intelligence and security. In fact, we’ve been all-in on AI for almost a decade. In 2016, we launched the Einstein platform, bringing predictive AI to our clouds. Shortly thereafter, in 2018, we started investing in large language models (LLMs).

We’ve been hard at work building generative AI solutions to help customers use their data more efficiently and help make companies, employees, and customers more productive and efficient. And because Trust is our #1 value, we believe it’s not enough to deliver only the technological capabilities of generative AI. We believe we have a duty to be responsible, accountable, transparent, empowering, and inclusive. That’s why, as Salesforce builds generative AI tools, we carry our value of Trust right along with us.

That’s where the Trust Layer comes in. We built the Trust Layer to help you and your colleagues use generative AI at your organization safely and securely. Let’s take a look at what Salesforce is doing to make its generative AI the most secure in the industry.

## What Is the Einstein Trust Layer?

The Einstein Trust Layer elevates the security of generative AI through data and privacy controls that are seamlessly integrated into the end-user experience. These controls enable Einstein to deliver AI that’s securely grounded in your customer and company data, without introducing potential security risks. In its simplest form, the Trust Layer is a sequence of gateways and retrieval mechanisms that together enable trusted and open generative AI.

![The Einstein Trust Layer process.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/the-einstein-trust-layer/meet-the-einstein-trust-layer/images/b7e7e25de679f0a6b881906d59a9cf00_kix.u0bgnhwtkwm3.png)

The Einstein Trust Layer lets customers get the benefit of generative AI without compromising their data security and privacy controls. It includes a toolbox of features that protect your data—like secure data retrieval, dynamic grounding, data masking, and zero data retention—so you don’t have to worry about where your data might end up. Toxic language detection scans prompts and responses for accuracy and to assure they are appropriate. And for additional accountability, an audit trail tracks a prompt through each step of its journey. You learn more about each of these features in the next units.

Data masking for LLMs is currently disabled for agents. For embedded generative AI features, such as Einstein Service Replies, Einstein Work Summaries data masking is available, and you can configure it in Einstein Trust Layer setup.

We designed our open model ecosystem so you have secure access to many large language models (LLMs), both inside and outside of Salesforce. The Trust Layer sits between an LLM and your employees and customers to keep your data safe while you use generative AI for all your business use cases, including sales emails, work summaries, and service replies in your contact center.

In the next units, dive into the prompt and response journeys to learn how the Einstein Trust Layer protects your data.

## Resources

-   [_Documentation_: Einstein Generative AI Glossary of Terms](https://help.salesforce.com/s/articleView?id=ai.generative_ai_glossary.htm&type=5)
-   [_Blog_: Meet Salesforce’s Trusted AI Principles](https://blog.salesforceairesearch.com/meet-salesforces-trusted-ai-principles/)
-   [_Blog_: Generative AI: 5 Guidelines for Responsible Development](https://blog.salesforceairesearch.com/generative-ai-5-guidelines-for-responsible-development/)
-   [_Trailhead_: Responsible Creation of Artificial Intelligence](https://trailhead.salesforce.com/content/learn/modules/responsible-creation-of-artificial-intelligence)
-   [_Trailhead_: Generative AI Basics](https://trailhead.salesforce.com/content/learn/modules/generative-ai-basics)
-   [_Trailhead_: Natural Language Processing](https://trailhead.salesforce.com/content/learn/modules/natural-language-processing-basics)
-   [_Trailhead_: Large Language Models](https://trailhead.salesforce.com/content/learn/modules/large-language-models)
-   [_Trailhead_: Prompt Fundamentals](https://trailhead.salesforce.com/content/learn/modules/prompt-fundamentals)

# Follow the Prompt Journey

## Learning Objectives

After completing this unit, you’ll be able to:

-   Explain how the trust layer securely handles your data.  
    
-   Describe how dynamic grounding improves a prompt's context.  
    
-   Describe how the Trust Layer's guardrails defend your data.  
    

## The Prompt Journey

You just learned a little bit about what the Trust Layer is, so let's look at how it fits into the bigger picture of generative AI at Salesforce. In this unit, you learn how a prompt moves through the Einstein Trust Layer on its way to the LLM.

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

This module includes some beta features of the Einstein Trust Layer. Customers should make their purchase decisions based upon features that are currently generally available.

![The Einstein Trust Layer highlighting the prompt journey.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/the-einstein-trust-layer/follow-the-prompt-journey/images/0222476248a89e2a2c7756cf2f144a04_kix.qnyougmxuv2n.png)

Prompt defense is available in Prompt Builder, Prompt Template Connect API, and the Prompt Template Invocable Action.

### The Power of Prompts

In the [Prompt Fundamentals](https://trailhead.salesforce.com/content/learn/modules/prompt-fundamentals) Trailhead module, you learn that prompts are what power generative AI applications. You also learn that clear instructions, contextual information, and constraints help create a great prompt, which leads to a great response from the LLM. To make this easy and consistent for our customers, we pre-built prompt templates for all sorts of business use cases, like sales emails or customer service replies. When a request to the Trust Layer is made from any of our Salesforce apps, a relevant prompt template is called by the Trust Layer.

Let’s walk through a customer service case to illustrate the prompt journey. You’ll see the prompt template, how the template becomes populated with customer data and relevant resources, and ways the Einstein Trust Layer protects data before it moves to an external LLM to generate a response that’s relevant to the prompt.

### Meet Jessica

Jessica is a customer service agent at a consumer credit card company. Her company has just implemented Service Replies, an Einstein-powered feature that generates suggested replies to customer agents during their chats with their customers. Jessica agreed to be one of the first agents to try it out. She’s known for her personal touch when working with customers, so she’s a little nervous that AI-generated replies might not match her style. But she’s eager to add some generative AI experience to her resume and curious to see if Service Replies could help her help more customers.

Jessica starts chatting with her first customer of the day, who wants help to upgrade his credit card. Service Replies begins suggesting replies right in the Service Console. The replies are refreshed each time the customer sends a new message, so they make sense in the context of the conversation. They’re also personalized to the customer, based on customer data stored in Salesforce. Each suggested reply is built from a prompt template. A prompt template contains instructions and placeholders that will be filled with business data—in this case, the data related to Jessica’s customer and their support case, and relevant data and flows from Jessica’s org. The prompt template is behind the Salesforce Trust Layer and Jessica, as an end user in the Service Console, can’t see prompt templates.

Let’s take a closer look at how this data moves through the trust layer to deliver relevant, high-quality replies while keeping customer data safe and secure.

![A customer service prompt template includes instructions and placeholder fields.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/the-einstein-trust-layer/follow-the-prompt-journey/images/77b1159adc57c133c0c836710b3e6357_kix.xu63vynncdel.png)

You are an agent at **{!organization.name}**. Your client is **{!contact.name}** at **{!account.name}** and is located at {!contact.address} who has been a customer for {!customer.history}.

Generate the customer service agent’s response in the conversation with a customer below. Ask for details about the customer’s issue, but you must not offer any specific suggestions or solutions. If you are unsure, say you will look into it.

Conversation: **{!conv\_context}**

Here are the knowledge articles that will be relevant to your response to the customer.

Relevant Articles: **{!Retriever.knowledge\_recommendations}**

### Dynamic Grounding

Relevant, high-quality responses require relevant, high-quality input data. When Jessica’s customer enters the conversation, Service Replies links the conversation to a prompt template and begins replacing the placeholder fields with page context, merge fields, and relevant knowledge articles from the customer record. This process is called _dynamic grounding_. In general, the more grounded a prompt is, the more accurate and relevant the response will be. Dynamic grounding is what makes prompt templates reusable so they can be scaled across an entire organization.

The process of dynamic grounding starts with _secure data retrieval_, which identifies relevant data about Jessica’s customer from her org. Most importantly, secure data retrieval respects all of the Salesforce permissions currently in place in her org that limit access to certain data on objects, fields, and more. This ensures that Jessica is only pulling information that she’s authorized to access. The data that is retrieved doesn’t contain any private information, or anything that requires escalated permissions.

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

Dynamic grounding pulls data from your org, so it’s important to make sure your data is kept current, accurate, and complete. Visit the [Data Quality](https://trailhead.salesforce.com/content/learn/modules/data_quality) Trailhead module to learn how to keep your data healthy.

![Our customer service prompt template filled in with data from Jessica’s org.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/the-einstein-trust-layer/follow-the-prompt-journey/images/c73c93ee4277f1e29cf505685dff347b_kix.mknkie3a5mhm.png)

You are an agent at **Cumulus Financial**. Your client is **Dennis Maxfield** at **Northern Trail Outfitters** and is located at **415 Mission St., San Francisco, CA, 94105** who has been a customer for **5 years**.

Generate the customer service agent’s response in the conversation with a customer below. Ask for details about the customer’s issue, but you must not offer any specific suggestions or solutions. If you are unsure, say you will look into it.

Conversation: **“Hello, I’m not able to upgrade my Cumulus credit card. Can you help? Is there a minimum credit score required for some of these cards?”**

Here are the knowledge articles that will be relevant to your response to the customer.

Relevant Articles: **{!Retriever.knowledge\_recommendations}**

### Semantic Search

In Jessica’s case, customer data is enough to personalize the conversation. But it’s not enough to help Jessica quickly and effectively solve the customer’s problem. Jessica needs information from other data sources like knowledge articles and customer history to answer questions and identify solutions. [_Semantic search_](https://help.salesforce.com/s/articleView?id=release-notes.rn_comm_einstein_semantic_search.htm&release=250&type=5) uses machine learning and search methods to find relevant information in other data sources that can be automatically included in the prompt. This means that Jessica doesn’t have to search for these sources manually, saving her time and effort.

Here, semantic search found a relevant knowledge article to help solve the credit card issue and included the relevant chunk of the article in the prompt template. Now this prompt is really taking shape!

![Our customer service prompt template is populated with a text block from a knowledge article.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/the-einstein-trust-layer/follow-the-prompt-journey/images/be706784dded73301fb415b10f9f865e_kix.1y9dkp1wlcn5.png)

You are an agent at **Cumulus Financial**. Your client is **Dennis Maxfield** at **Northern Trail Outfitters** and is located at **415 Mission St., San Francisco, CA 94105** who has been a customer for **5 years**.

Generate the customer service agent’s response in the conversation with a customer below. Ask for details about the customer’s issue, but you must not offer any specific suggestions or solutions. If you are unsure, say you will look into it.

Conversation: **“Hello, I’m not able to upgrade my Cumulus credit card. Can you help? Is there a minimum credit score required for some of these cards?”**

Here are the knowledge articles that will be relevant to your response to the customer.

Relevant Articles: **“Remember to review the requirements for a credit card - ensuring that the client has provided all the necessary information and has a credit score in excess of the minimum amount required for a new credit card”**

### Data Masking

Although the prompt contains accurate data about Jessica’s customer and their issue, it’s not yet ready to go to the LLM because it contains information like client and customer names and addresses. The Trust Layer adds another level of protection to Jessica’s customer data through _data masking_. Data masking involves tokenizing each value, so that each value is replaced with a placeholder based on what it represents. This means that the LLM can maintain the context of Jessica’s conversation with her customer and still generate a relevant response.

Salesforce uses a blend of pattern matching and advanced machine learning techniques to intelligently identify customer details like names and credit card information, then masks them. Data masking happens behind the scenes, so Jessica doesn’t have to do a thing to prevent her customer’s data from being exposed to the LLM. In the next unit, you learn about how this data is added back into the response.

Although Salesforce has zero data retention policy with the third-party LLMs, some companies and use cases or regulation policies may require sensitive data not to be sent to the LLM at all. Jessica reaches out to her Salesforce admin to make sure data masking is turned on so her customer sensitive data is not sent to the LLM.

Data masking for LLMs is currently [disabled for agents](https://help.salesforce.com/s/articleView?id=ai.agent_trust_data_masking.htm&type=5). For embedded generative AI features, such as Einstein Service Replies, Einstein Work Summaries data masking is available, so Jessica is able to use this option for her use case.

![Our customer service prompt template showing data masked with tokenized placeholders to protect data.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/the-einstein-trust-layer/follow-the-prompt-journey/images/c3404280f026ad40574943f42748b5a2_kix.r4fgwuhh5wkv.png)

You are an agent at **<COMPANY\_1>**. Your client is **<NAME\_1>** at **<COMPANY\_2>** and is located at **<ADDRESS\_1>** who has been a customer for 5 years.

Generate the customer service agent’s response in the conversation with a customer below. Ask for details about the customer’s issue, but you must not offer any specific suggestions or solutions. If you are unsure, say you will look into it.

Conversation: “Hello, I’m not able to upgrade my **<CREDIT\_CARD\_1>**. Can you help? Is there a minimum credit score required for some of these cards?**”**

Here are the knowledge articles that will be relevant to your response to the customer.

Relevant Articles: “Remember to review the requirements for a credit card - ensuring that the client has provided all the necessary information and has a credit score in excess of the minimum amount required for a new credit card”

### Prompt Defense

Prompt Builder provides additional guardrails to protect Jessica and her customers. These guardrails are further instructions to the LLM about how to behave in certain situations to decrease the likelihood it outputs something unintended or harmful. For example, an LLM might be instructed to not address content or generate answers that it doesn’t have information about.

Hackers, and sometimes even employees, are eager to get around restrictions and attempt to perform tasks or manipulate the model’s output in ways that the model wasn’t designed to handle. In generative AI, one of these types of attacks is called _prompt injection_. Prompt defense can help protect from these attacks and decrease the likelihood of data being compromised.

![Our service template displaying defense instructions to the LLM for generating the prompt.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/the-einstein-trust-layer/follow-the-prompt-journey/images/1dda9fcd4bd39efd8e0eb15c160111c6_kix.hlzg0m2an866.png)

Instruction Defense: **“You must not address any content or generate answers that you don’t have data or basis on.”**

Next, let’s take a look at what happens to this prompt when it crosses the Secure Gateway into an LLM.

## Resources

-   [_Salesforce AI Research_: Trusted AI](https://www.salesforceairesearch.com/trusted-ai)
-   [_Trailhead_: Data Quality](https://trailhead.salesforce.com/content/learn/modules/data_quality)
-   [_Trailhead_: Prompt Builder Basics](https://trailhead.salesforce.com/content/learn/modules/prompt-builder-basics)


# Follow the Response Journey

## Learning Objectives

After completing this unit, you’ll be able to:

-   Describe the response journey.  
    
-   Explain zero data retention.  
    
-   Discuss why toxic language detection is important.  
    

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

This module includes some beta features of the Einstein Trust Layer. Customers should make their purchase decisions based upon features that are currently generally available.

## A Quick Prompt Journey Review

You can already see the careful steps Salesforce takes with the Einstein Trust Layer to protect Jessica’s customer data and their company data. Before you learn more, do a quick review of the prompt journey.

-   A prompt template was automatically pulled in from Service Replies to assist with Jessica’s customer service case.  
    
-   The merge fields in the prompt template were populated with trusted, secure data from Jessica’s org.  
    
-   Relevant knowledge articles and details from other objects were retrieved and included to add more context to the prompt.  
    
-   Personally identifiable information (PII) was masked.  
    
-   Extra security guardrails were applied to the prompt to further protect it.  
    
-   Now the prompt is ready to pass through the secure gateway to the external LLM.  
    

### The Secure LLM Gateway

Populated with relevant data, with protective measures in place, the prompt is ready to leave the Salesforce Trust Boundary by passing through the Secure LLM Gateway to connected LLMs. In this case, the LLM Jessica’s org is connected to is OpenAI. OpenAI uses this prompt to generate a relevant, high-quality response for Jessica to use in her conversation with her customer.

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

The prompt may interact with the Trust Layer differently when interacting with LLMs that live inside the Salesforce Trust Boundary, such as Salesforce LLMs developed in-house.

## Zero Data Retention

If Jessica was using a consumer-facing LLM tool, like a generative AI chatbot, without a robust trust layer, her prompt, including all of her customer’s data, and even the LLM’s response, could be stored by the LLM for model training. But when Salesforce partners with an external API-based LLM, we require an agreement to keep the entire interaction safe—it’s called _zero data retention_. Our zero data retention policy means that no customer data including the prompt text and generated responses are stored outside of Salesforce.

![A closeup of the process a prompt takes through the secure gateway to the LLM shows that no data is retained by the LLM.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/the-einstein-trust-layer/follow-the-response-journey/images/8650fd5c91ab40f271f5d5eaba2029d9_kix.t0en6fqjogkd.png)

Here’s how it works. Jessica’s prompt is sent out to an LLM—remember, that prompt is an instruction. The LLM takes that prompt, and following its instructions while adhering to the guardrails, generates one or more responses.

Typically, OpenAI wants to retain prompts and prompt responses for a period of time to monitor for abuse. OpenAI’s incredibly powerful LLMs check to see if anything unusual is happening to their models—like the prompt injection attacks that you learned about in the last unit. But our zero data retention policy prevents the LLM partners from retaining any data from the interaction. We arrived at an agreement where _we_ handle that moderation.

We don’t allow OpenAI to store anything. So when a prompt is sent to OpenAI, the model forgets the prompt and the responses as soon as the response is sent back to Salesforce. This is important because it allows Salesforce to handle its own content and abuse moderation. Additionally, users like Jessica don’t have to worry about LLM providers retaining and using their customers’ data.

## The Response Journey

When we first introduced Jessica, we mentioned that she was a little nervous that AI-generated replies might not match her level of conscientiousness. She’s really not sure what to expect, but she doesn’t need to worry, because the Einstein Trust Layer has that covered. It contains several features that help keep the conversation personalized and professional.

![The Einstein Trust Layer highlighting the response journey.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/the-einstein-trust-layer/follow-the-response-journey/images/483d6445faf7b199bac9dae7aa8212dd_kix.ly8y81u4qdpt.png)

So far, we’ve seen the prompt template from Jessica’s conversation with her customer become populated with relevant customer information and helpful context related to the case. Now, the LLM has digested those details and delivered a response back into the Salesforce Trust Boundary. But it’s not quite ready for Jessica to see, yet. While the tone is friendly and the content accurate, it still needs to be checked by the Trust Layer for unintended output. The response also still contains blocks of masked data, and Jessica would think that’s much too impersonal to share with her customer. The Trust Layer still has a few more important actions to perform before it shares the response with her.

![A customer service reply shows masked personal information and a link to a relevant knowledge article.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/the-einstein-trust-layer/follow-the-response-journey/images/2f3738e640ad56d375ede630fbe0533a_kix.hmie3aj2kcps.png)

Hello **<NAME\_1>**! It’s great to speak with you. I’m sorry you’re having trouble upgrading your credit card today - we appreciate your 5+ years of partnership with **<COMPANY\_1>** and we’ll work to resolve this issue swiftly.

Yes, there is a minimum credit score that is required\*for some of our credit card offerings. Could you tell me more about what trouble you’re having with the application process?

Source: Minimum Requirements for Cumulus Card Upgrades

### Toxic Language Detection and Data Demasking

Two important things happen as the response to Jessica’s conversation passes back into the Salesforce Trust Boundary from the LLM. First, _toxic language detection_ protects Jessica and her customers from toxicity. What’s that, you ask? The Trust Layer uses machine learning models to identify and flag toxic content in prompts and responses, in five categories: violence, sexual, profanity, hate, and physical. The overall toxicity score combines the scores from all detected categories and produces an overall score that ranges from 0 to 1, with 1 being the most toxic. The score for the initial response is returned along with the response to the application that called it—in this case, Service Replies.

Next, before the generated response is shared with Jessica, the Trust Layer needs to reveal the masked data we talked about earlier so that the response is personal and relevant to Jessica’s customer. The Trust Layer uses the same tokenized data we saved when we originally masked the data to demask it. Once the data is demasked, the response is shared with Jessica.

Also, notice that there is a Source link at the bottom of the response. Knowledge Article Creation adds credibility to responses by including links to contributing, helpful source articles.

![A demasked service reply recommendation including a link to a knowledge article.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/the-einstein-trust-layer/follow-the-response-journey/images/6a3658d1224ac8674ef0b0d9f10e136f_kix.n403eppnai7p.png)

Hello **Dennis Maxfield**! It’s great to speak with you. I’m sorry you’re having trouble upgrading your credit card today - we appreciate your 5+ years of partnership with **Cumulus Financial** and we’ll work to resolve this issue swiftly.

Yes, there is a minimum credit score that is required\* for some of our credit card offerings. Could you tell me more about what trouble you’re having with the application process?

Source: Minimum Requirements for Cumulus Card Upgrades

### Feedback Framework

Now, seeing the response for the first time, Jessica smiles. She’s impressed with the quality and level of detail in the response she received from the LLM. She’s also pleased with how well it aligns with her personal case-handling style. As Jessica reviews the response before sending it to her customer, she sees that she can choose to accept it as is, edit it before sending it, or ignore it.

She can also give qualitative feedback in the form of a thumbs up or thumbs down, and if the response wasn’t helpful, specify a reason why. This feedback is collected, and in the future, it can be [securely used to improve](https://help.salesforce.com/s/articleView?id=ai.generative_ai_feedback.htm&type=5) the quality of the prompts.

![The feedback framework.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/the-einstein-trust-layer/follow-the-response-journey/images/5da9dfee4d49fcab2c1e5b8feba852c2_kix.sp14vru2j2ku.png)

### Audit Trail

There is one final piece of the Trust Layer to show you. Remember the zero data retention policy we talked about in the beginning of this unit? Since the Trust Layer is handling toxic language scoring and moderation internally, we keep track of every step that happens during the entire prompt-to-response journey.

Everything that has transpired during this entire interaction between Jessica and her customer is timestamped metadata that we collect into an audit trail. This includes the prompt, the original unfiltered response, any toxic language scores, and feedback collected along the way. The Einstein Trust Layer audit trail adds a level of accountability so Jessica can be sure her customer’s data is protected.

![The customer service reply shows the audit trail and timestamped metadata.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/the-einstein-trust-layer/follow-the-response-journey/images/dd775808896a5c5b1e6b9c53f9208a1b_kix.8kxn70ha9pin.jpg)

A lot has happened since Jessica started helping her customer, but it all happened within a blink of an eye. Within seconds, her conversation went from a prompt called by a chat, through the security of the entire Trust Layer process, to a relevant, professional response she can share with a customer.

She closes the case, knowing her customer is happy with the response and the customer service experience he received. And best of all, she’s excited to continue to use the generative AI power of Service Replies, because she feels confident that it will help her close her cases faster and delight her customers.

Every single one of the Salesforce generative AI solutions goes through the same Trust Layer journey. All of our solutions are safe, so you can be confident that your data and your customers data is secure.

Congratulations, you just learned how the Einstein Trust Layer works! To learn more about what Salesforce is doing around trust and generative AI, earn the [Responsible Creation of Artificial Intelligence](https://trailhead.salesforce.com/content/learn/modules/responsible-creation-of-artificial-intelligence) Trailhead badge.

## Resources

-   [_Trailhead_: Responsible Creation of Artificial Intelligence](https://trailhead.salesforce.com/content/learn/modules/responsible-creation-of-artificial-intelligence)
-   [_Salesforce Help_: Einstein Generative AI & Trust](https://help.salesforce.com/s/articleView?id=ai.generative_ai_trust_overview.htm&type=5)

# Explore Large Language Model Data Masking

## Learning Objectives

After completing this unit, you’ll be able to:

-   Explain the importance of masking sensitive information from large language models (LLMs).  
    
-   Describe Einstein Trust Layer functionality.  
    

## Before You Start

We recommend completing the following content, which covers the Einstein Trust Layer and reviews creating prompt templates using Prompt Builder.

-   [The Trust Layer](https://trailhead.salesforce.com/content/learn/modules/the-einstein-trust-layer)  
    
-   [Prompt Builder Basics](https://trailhead.salesforce.com/content/learn/modules/prompt-builder-basics)  
    

## Introduction to Large Language Model Data Masking

Safeguarding your data with generative AI technology can be challenging. Einstein Trust Layer uses data masking to help prevent sensitive information from exposure to third-party large language models (LLMs). Hence the name LLM Data Masking. Let’s learn more about the process.

## How LLM Data Masking Works

### Detection and Masking Process

Einstein Trust Layer uses advanced pattern matching and machine learning techniques to detect sensitive data in prompts. After it’s identified, this data is masked, meaning it’s replaced with placeholder text. For example, let’s say the name Jim is the first instance of a person’s name in the prompt text. Jim is replaced by <Person\_0>. By replacing real data with placeholder text in the prompt, the Einstein Trust Layer ensures that sensitive details aren’t exposed to the LLM.

Data masking for LLMs is [disabled](https://help.salesforce.com/s/articleView?id=ai.agent_trust_data_masking.htm&type=5) for agents. See Data Masking and Agents. For embedded generative AI features, such as Einstein Service Replies, Einstein Work Summaries data masking is available, and you can configure it in Einstein Trust Layer setup.

### Demasking

After receiving the generated response from the LLM, the Einstein Trust Layer reverts the masked data back to its original form. Demasking helps make the response you see accurate and relevant to the task at hand.

## How to Prepare for Data Masking

Before you configure data masking, evaluate the data security and privacy risks to your business and your use cases posed by generative AI. One of the key risks that LLM data masking helps mitigate is data leakage. Data leakage can come from exposing private or personal information to third-party LLMs, such as customer names, credit card numbers, or Social Security numbers.

Salesforce has a zero data retention policy with third-party LLM providers like Open AI and Azure Open AI. This means that the data you send through the prompt isn’t retained by the LLM. Even with the zero data retention policy in place, you may still want to make sure sensitive data is not exposed to the LLM.

Take a look at some questions that can help you make a risk assessment and create a risk profile in order to determine your risk tolerance.

-   What are your current governance and security policies?  
    
-   Is your company bound by data-handling regulations like General Data Protection Regulation (GDPR) or Payment Card Industry Data Security Standard (PCI DSS)? Some of these regulations require that you don’t expose certain types of sensitive data to LLMs.  
    
-   What are your data residency requirements?  
    
-   If your company is global, what country or region’s data do you need to protect?  
    
-   Is the sensitive data necessary for grounding the prompt in order to generate the response that’s relevant and useful?  
    
-   What are your AI application use cases? Will these use cases include sensitive data in the prompts?  
    

For a more detailed discussion on risk and mitigation strategies and creating a risk profile, see [AI + Data: Project Planning](https://trailhead.salesforce.com/content/learn/modules/ai-data-project-planning).

Also consider the impact of masking certain types of data and the impact on the quality of the response generated. Your specific use cases and testing is the key to striking the right balance between data security and the quality of the response.

Let’s walk through some examples to understand the impact better.

1.  In the prompt text, you’re asking the LLM to help with downloading an Amazon app to your device. However, because Amazon is a company name, it’s masked from the LLM. The LLM is unable to provide a useful response because it doesn’t understand which app you need help downloading.  
    
2.  In the prompt text, you’re asking the LLM to summarize a sales order. The sales order is a 10-digit number that has a similar pattern to a US phone number. As a result, the sales order is masked because the LLM is preserving the privacy of the phone number before sending the prompt to the LLM. This can cause the LLM to generate a response that may not be accurate or useful.  
    

## How to Use the Einstein Trust Layer

You walk through the setup in detail in the next unit. For now, let’s gain insight into what’s enabled by default and what you can do to customize it further.

### Einstein Trust Layer

After you set up Einstein AI with Data 360, LLM data masking is turned on by default for certain sensitive data types. This makes it easy to keep sensitive data safe. You can review the default settings and update them according to your organization’s governance policies and regulatory requirements.

To track data masking activities, the Einstein Trust Layer logs these actions in Data 360 as part of an audit trail. You can use the prebuilt dashboards to verify data masking and demasking or create custom reports and dashboards.

### Supported Data Entries and Languages

The Einstein Trust Layer supports a variety of data types for masking, including company names, credit card numbers, and email addresses. These entries are supported in multiple languages, making sure that your global operations can comply with data masking requirements. Read the [Einstein Trust Layer Region and Language Support help article](https://help.salesforce.com/s/articleView?id=ai.generative_ai_trust_lang_region.htm&type=5) to see which data types and languages are supported.

In this unit, you learned about the importance of data masking and how it relates to the Einstein Trust Layer. In the next unit, you learn how to configure data masking in the Einstein Trust Layer and view data masking at run time in Prompt Builder.

## Resources

-   [_Salesforce Help_: Data Masking](https://help.salesforce.com/s/articleView?id=ai.generative_ai_mask_data.htm&type=5)
-   [_Salesforce Video_: Einstein Trust Layer: How It Works and Why It Matters](https://salesforce.vidyard.com/watch/Kw7DfNqG7AGPAZcqrrn2T5)

# Configure LLM Data Masking Policies

## Learning Objectives

After completing this unit, you’ll be able to:

-   Sign up for a Custom Playground with Data 360 and Einstein AI.  
    
-   Configure LLM Data Masking in Trust Layer.  
    
-   Verify masked data in the Prompt Builder.  
    

## Sign Up for a Custom Playground with Data 360 and Einstein AI

To complete this project, you need a custom playground that contains Data 360, Einstein AI, and our sample data.

1.  Click **Create Playground**.  
    
2.  Your new org is automatically attached to your Trailhead account!  
    
3.  Make note of your org's expiration date and complete this badge before then.  
    

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

This custom playground is designed to work with the challenges in this badge and may not work for other badges. Always check that you’re using the Trailhead playground or the special org that we recommend.

## Set Up Einstein Trust Layer

### Enable Einstein Generative AI

Before you can configure Einstein Trust Layer data masking policies, you must turn on Einstein Generative AI. Data 360 is required for Einstein Trust Layer to function correctly and to see and verify Einstein Trust Layer settings. For this module, we set up Data 360 for you in advance as part of the custom Data 360 and Salesforce playground. You just turn on Einstein Generative AI and configure the Einstein Trust Layer. Follow all the steps in this unit and click verify to earn 500 points to complete the challenge at the end of this unit.

1.  If you haven’t already, launch your Data 360 and Salesforce playground.  
    
2.  Click the gear icon (![](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/llm-data-masking-in-the-einstein-trust-layer/configure-llm-data-masking-policies/images/b5628af0e4d39768578d1ee9a1d53da4_kix.4jxvvaxmk51q.jpg)) and click **Setup**. The Setup page opens in a new tab.  
    
3.  In the Setup **Quick Find** search box, search for and select **Einstein Setup**.  
    
4.  Ensure the Turn on Einstein toggle is set to **On**.  
    

![A Salesforce Einstein Setup page with the ability to activate Einstein and adjust trust layer settings.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/llm-data-masking-in-the-einstein-trust-layer/configure-llm-data-masking-policies/images/5c919f28d9b3d5279d3efe6fa214327b_kix.2f132ks7vo2r.png)

5.  Click **Go to Einstein Trust Layer**. Refresh the screen if you don’t see the Einstein Trust Layer settings.  
    
6.  If the **Large Language Model Data Masking** isn’t already turned on, use the toggle to turn it on.  
    

Let’s take a moment to see what data types are listed. You'll see a list of sensitive data types such as name, email address, and credit card number. In the previous unit, you learned about pattern-based masking. Now you can see the type of data that Einstein Trust Layer is able to detect using ‌patterns and context. Notice that **Name**, **Email Address**, **Phone Number**, **Credit Card**, and **United States’ Social Security Numbers (US SSN)** are masked by default.

![A table with a list of sensitive data attributes, such as names, emails, and credit card numbers, with toggles to enable or disable data masking.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/llm-data-masking-in-the-einstein-trust-layer/configure-llm-data-masking-policies/images/0fec178972af2a72a79554cd230ee417_kix.rmomj7so3o4d.png)

## Turn on Sales Emails

### Enable Sales Emails

Before we create an Email Prompt Template, we need to turn on Sales Email.

1.  In the **Quick Find** search box, type `Einstein for Sales.Copy`
2.  Click **Einstein for Sales**. This opens the Einstein for Sales page.  
    
3.  Toggle the **Turn on Sales Emails** switch to **Enabled**. Note: The deployment can take up to 10 minutes but no need to wait, proceed to the next step.  
    

Next, let’s see data masking in action in the Prompt Builder. As you learned in the [Prompt Builder Basics](https://trailhead.salesforce.com/content/learn/modules/prompt-builder-basics) badge, the key to scalable generative AI is to use prompt templates to tell a large language model (LLM) how it should generate content.

## Create an Email Prompt Template

1.  With **Einstein Generative AI** menu expanded, click **Prompt Builder**. Refresh the screen if you don’t see the **Prompt Builder** menu.  
    
2.  Click **New Prompt Template**.  
    
3.  Select **Sales Email** for the **Prompt Template Type**. If you don’t see Sales Email in the list, refresh the screen.  
    
4.  Enter a **Prompt Template Name**. Let’s call it `Verification EmailCopy`(API Name '`Verification_EmailCopy`')_._  
    
5.  Enter a Template Description. This description is displayed in the list of prompt templates and can be useful to distinguish prompt templates as you add more. Let’s call it `Verify contact informationCopy`_._  
    
6.  The Recipient field defaults to Contact and the Related Object field is blank. Accept the defaults, and click **Next**. You’re redirected to the Prompt Template Workspace.  
    

## Verify Data Masking

Excellent! For this scenario, we’ve provided a prompt for you to use and see how data is masked in prompts. Notice that the prompt text includes several pieces of personally identifiable information (PII) and payment card industry (PCI) information. Usually, when you create a prompt template, you ‌use merge fields from the contact records, but for now, include this information directly in the prompt.

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

The prompt text provided here includes examples of sensitive information such as credit card and social security numbers in plain text. This is only to demonstrate how data masking works to protect your data in such cases and should not be considered as acceptable practice.

1.  Copy and paste the text below into the Prompt Template Workspace:  
    

Your name is Becca and you’re a Sales associate at Coral Cloud Resorts writing an email to a new contact to verify their information on record. Instructions: """ Introduce yourself welcome the new contact Andy Young. Let them know that you’re sending this email to verify their information. List the following information as a bullet list. Full Name: Andy Young Company Name: Dickenson PLC Business Phone Number: (785) 241-6200 Mobile Phone Number: (785) 265-5350 Email: a\_young@dickenson.com SSN: 243930486 Credit Card on file: 378282246310005 Use clear and straightforward language, using active voice, and avoiding the use of filler words. End with asking them to call Coral Cloud Resorts to verify their information on the file """ Now create the email.

2.  In Preview Settings (![](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/llm-data-masking-in-the-einstein-trust-layer/configure-llm-data-masking-policies/images/d68e485e555881e6bb83700381bd739e_kix.1d3b41km8969.png), under Inputs, type `AndyCopy` and select Andy Young.  
    
3.  Click **Save & Preview**. Your Resolved Prompt and Generated Response tabs should look something like this (note that LLM responses can differ slightly so it may not look exactly the same):  
    

![A screenshot of a prompt template workspace, displaying an email template, a preview of the template, and a response to the template.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/llm-data-masking-in-the-einstein-trust-layer/configure-llm-data-masking-policies/images/a6935e66f89c3aa8a64372af8f8ff68b_kix.wknjzu6lhpz8.png)

Notice that the Resolved Prompt tab shows the prompt text with the placeholder information. This is the prompt text that is sent to the LLM. This gives you a preview of the data that’s masked before sending it to the LLM. The Generated Response tab shows the generated email with the actual information after the data has been demasked. You’ll also see a shield icon (![Shield icon](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/llm-data-masking-in-the-einstein-trust-layer/configure-llm-data-masking-policies/images/673ecece889336f97167fd58c9942bd8_kix.mo3rbww8wemp.png)) in the Generated Response tab, which includes a link to see the data masking details.

4.  In the **Generated Response** tab, click the shield icon to view your data masking details. This opens a new window where you can see the placeholder text used to mask and the corresponding actual value. You should see that the credit card number, email address, names of people, both phone numbers, and SSN are masked. However, also notice that the company’s name isn’t currently masked.  
    
5.  Click **OK** to close the data masking details window.  
    

![A table is displayed with masked data and the corresponding true values of a credit card number, email address, names, phone numbers, and SSN.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/llm-data-masking-in-the-einstein-trust-layer/configure-llm-data-masking-policies/images/87e77dca2e34edadd2910ef269761987_kix.es3ahqozigdc.png)

### Update LLM Data Masking Settings

In this case, you also want the company name to be masked, so let’s get back to the configuration and update the settings.

1.  Click the gear icon (![](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/llm-data-masking-in-the-einstein-trust-layer/configure-llm-data-masking-policies/images/b5628af0e4d39768578d1ee9a1d53da4_kix.5sycjjm2jllf.jpg)) and click **Setup**. The Setup page opens in a new tab.  
    
2.  In the **Quick Find** search box, type `EinsteinCopy`.  
    
3.  Expand the **Einstein Generative AI** menu in the left pane.  
    
4.  Click **Einstein Setup**. This opens the **Einstein Setup** page.  
    
5.  Click **Go to Einstein Trust Layer**.  
    
6.  Turn on masking for **Company Name** under **Sensitive Data**.  
    

### Verify Data Masking for Company Name

1.  Navigate to the Prompt Builder tab that shows the Verification Email tab. If you closed the Verification Email prompt template, you can open it by navigating to the Prompt Builder menu in the left pane. Click the **Verification Email** prompt template you created in the previous section to open the prompt template.  
    
2.  In Preview Settings, under Inputs, type `AndyCopy` and select **Andy Young**.  
    
3.  Click **Preview**.  
    

**Note:** It can take a couple of minutes for the LLM Data Masking updates to take effect.

4.  Click the data masking shield (![Shield icon](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/llm-data-masking-in-the-einstein-trust-layer/configure-llm-data-masking-policies/images/673ecece889336f97167fd58c9942bd8_kix.toh5lvuju8s5.png)) in the Generated Response tab. Notice that ‌company names are now masked.  
    
5.  Click **OK** to close the window.  
    

![A table is displayed with masked data and the corresponding true values of a credit card, email address, names of people and organizations, phone numbers, and SSN.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/llm-data-masking-in-the-einstein-trust-layer/configure-llm-data-masking-policies/images/44ab1630c3293adaa1adb5a4388ad30c_kix.1nzignouzqgt.png)

After you implement LLM Data Masking in your Salesforce org, be sure to test it on a regular basis. You also want to assess if masking certain types of data for specific use cases affect the quality of the response from the LLM. Large language models change and improve over time, so doing periodic assessments of the results you’re getting is one of best practices in the world of generative AI.

### Verify Invalid Credit Card Number Is Not Masked

Some types of sensitive data have specific formats and validation rules, such as credit card numbers, SSNs, and even phone numbers. LLM data masking knows about those rules, and checks to see if items are valid. If an item isn’t a valid value, it won’t be masked. Try updating the credit card number in your prompt text and see what happens:

1.  Using the same **Verification Email** prompt template you created before, In the prompt text, change the credit card number as follows:  
    **Credit Card on file: 378282246310005**  
    to  
    **Credit Card on file:** `333312312312312Copy`
2.  Click **Save & Preview**.  
    
3.  Click the data masking shield (![Shield icon](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/llm-data-masking-in-the-einstein-trust-layer/configure-llm-data-masking-policies/images/673ecece889336f97167fd58c9942bd8_kix.je5v19be0x0l.png)) in the Generated Response tab. Notice that the modified credit card number is no longer masked.  
    
4.  Click **OK** to close the window.  
    

In this unit, you learned how to configure data masking in the Einstein Trust Layer setup and see how data masking works using Prompt Builder. You also learned about the format and rules Einstein Trust Layer uses to identify sensitive data. If you haven’t already done so, follow the steps at the beginning of this unit to sign up for a custom playground with Data 360 and Einstein AI to complete the hands-on challenge.


# Einstein Trust Layer

Trusting generative AI with your company secrets and your customer data while balancing the benefits of generative AI is still a challenge today. The Einstein Trust Layer is a secure AI architecture, built into the Salesforce platform. It’s a set of agreements, security technology, and data and privacy controls used to keep your company safe while you explore generative AI solutions.

Watch the video for a quick overview of how the Einstein Trust Layer works. You can also click [this link](https://salesforce.vidyard.com/watch/Kw7DfNqG7AGPAZcqrrn2T5) to launch the video in full screen mode on a different tab.

For a detailed walkthrough of the Einstein Trust Layer and its capabilities, see [Einstein Trust Layer: Designed for Trust](https://help.salesforce.com/s/articleView?id=ai.generative_ai_trust_arch.htm&language=en_US&type=5).




#### See Also

-   [Einstein Trust Layer Region and Language Support](https://help.salesforce.com/s/articleView?id=ai.generative_ai_trust_lang_region.htm&language=en_US&type=5)
-   [Set up Einstein Trust Layer](https://help.salesforce.com/s/articleView?id=ai.generative_ai_trust_setup.htm&language=en_US&type=5)
-   [Large Language Model Data Masking](https://help.salesforce.com/s/articleView?id=ai.generative_ai_mask_data.htm&language=en_US&type=5)
-   [Audit Trail](https://help.salesforce.com/s/articleView?id=ai.generative_ai_audit_trail.htm&language=en_US&type=5)
-   [_Trailhead_: The Einstein Trust Layer](https://trailhead.salesforce.com/content/learn/modules/the-einstein-trust-layer)

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEzMjI5MTI5MDAsMTg0OTIxOTgyMywxOD
YzNDQ3ODA2LC05Mzc1OTEyNzUsMjAzNTk2OTIwOCwxODk4OTA4
NzIsNzMwOTk4MTE2XX0=
-->