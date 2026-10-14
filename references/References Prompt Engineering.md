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


<!--stackedit_data:
eyJoaXN0b3J5IjpbMTI3NDEyNjY1NiwtOTM3NTkxMjc1LDIwMz
U5NjkyMDgsMTg5ODkwODcyLDczMDk5ODExNl19
-->