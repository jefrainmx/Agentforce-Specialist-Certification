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



<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE3MTE4OTAxODksLTkzNzU5MTI3NSwyMD
M1OTY5MjA4LDE4OTg5MDg3Miw3MzA5OTgxMTZdfQ==
-->