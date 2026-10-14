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

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEwMjEyMDY2NDMsNzMwOTk4MTE2XX0=
-->