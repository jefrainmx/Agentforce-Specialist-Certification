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


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTU0NTI0NTc0NSw3MzA5OTgxMTZdfQ==
-->