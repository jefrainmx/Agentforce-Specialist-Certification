
# Get Started with Agent Script

Get to know the language for building agents in Agentforce Builder. Use Agent Script to build predictable, context-aware agent workflows that don't rely solely on interpretation by an LLM.

:::note
Beginning in April 2026, agent **topics** are now called **subagents**. There are no changes to functionality. During this transition, you may see a mix of the new and previous terms in our documentation
:::

To get hands-on with Agent Script, [Create an Agent](https://help.salesforce.com/s/articleView?id=ai.agent_setup_create.htm\&type=5), then select **Script** from the view picker. Or, author an agent with [Agentforce DX](/docs/ai/agentforce/guide/agent-dx-nga-author-agent.md).

![Agent Script UI](https://a.sfdcstatic.com/developer-website/sfdocs/genai/media/agent-script/agent-script-view3.png)

## What's Agent Script?

Agent Script is the language for building agents in Agentforce Builder. Script combines the flexibility of natural language instructions for handling conversational tasks with the reliability of programmatic expressions for handling business rules. In script, you use expressions to define if/else conditions, transitions, and other logic; set, modify, and compare variables; and select subagents and actions. You can build predictable, context-aware agent workflows that don’t rely solely on interpretation by an LLM. For example, you can use script to control when your agent transitions from one subagent to another or when actions are run in a particular sequence (sometimes called action chaining).

Agentforce Builder gives you several ways to write Agent Script.

- You can chat with Agentforce and explain what you want your agent to be able to do (for example, "If the order total is over $100, then offer free shipping."). Agentforce converts your request into subagents, actions, instructions, and other expressions.
- In Canvas view, Agent Script is summarized into easily understandable blocks, which you can expand to view the underlying script. You can edit your agent with the help of quick action shortcuts. Type `/` to add expressions for common patterns (for example, if/else conditionals) and `@` to add resources (subagents, actions, and variables).
- Advanced users can switch to Script view to write and edit script directly, with developer-friendly aids like syntax highlighting, autocompletion, and validation.

Developers can also use Agentforce DX to generate or retrieve a script file into their local Salesforce DX project and then work with it in Visual Studio Code. The Agentforce DX VS Code Extension fully supports the Agent Script language with standard code editing features. See [Agentforce DX](/docs/ai/agentforce/guide/agent-dx.md) for more details.

## What Can You Do with Agent Script?

Agent Script preserves the conversational skills and complex reasoning ability derived from natural language prompts, and it adds the determinism of programmatic instructions. For example, in Agent Script, you can define:

- Specific areas where an LLM is free to make reasoning decisions. See [Reasoning Instructions](/docs/ai/agentforce/guide/ascript-ref-instructions.md).
- Specific areas where the agent must execute deterministically. See [Reasoning Instructions](/docs/ai/agentforce/guide/ascript-ref-instructions.md).
- Variables to reliably store information about the agent's current state, rather than relying on LLM context memory. See [Variables](/docs/ai/agentforce/guide/ascript-ref-variables.md).
- Conditional expressions to determine the agent's execution path or LLM's utterances. For example, you can instruct the agent to speak differently to the customer based on the value of the `is_member` variable. Or you can deterministically specify which action to run based on the value of the `appointment_type` variable. See [Conditional Expressions](/docs/ai/agentforce/guide/ascript-ref-expressions.md).
- Conditions under which the agent transitions to a new subagent. You can deterministically transition to a new subagent. Or you can expose a subagent transition to the LLM as a tool, allowing the LLM to decide when and whether to switch subagents. See [Tools](/docs/ai/agentforce/guide/ascript-ref-tools.md) and [Utils](/docs/ai/agentforce/guide/ascript-ref-utils.md).

## Example Agent Script

Here’s a simple example of what Agent Script looks like.

```sfdocs-code {"lang":"agentscript", "title": "Agent Script Example"}
system:
    instructions: "You are a friendly and empathetic agent that helps customers with their questions."
    messages:
        error: "Sorry, something went wrong."
        welcome: "Hello! How are you feeling today?"

config:
    agent_name: "HelloWorldBot"

access:
    default_agent_user: "agent_user1@mycompanyname.com"

language:
    default_locale: "en_US"
    additional_locales: ""

variables:
    isPremiumUser: mutable boolean = False
        description: "Indicates whether the user is a premium user."

start_agent hello_world:
    description: "Respond to the user."
    reasoning:
        instructions: ->
            if @variables.isPremiumUser:
                | ask the user if they want to redeem their Premium points
            else:
                | ask the user if they want to upgrade to Premium service
```

Among other compelling features, you can see in the above reasoning instructions that you can specify conditional logic (after the `->`) alongside LLM prompts (after the `|`). This combination gives you the advantages of predictable, deterministic logic, alongside the power of LLM reasoning.

## Agent Skills

Want to build Agent Script agents using an agent skill or with Agentforce Vibes? Check out these resources!

- [Skills in Agentforce Vibes](https://developer.salesforce.com/docs/platform/einstein-for-devs/guide/skills.md) — A page describing how skills are used with Agentforce Vibes.
- [Salesforce Skills Library](https://github.com/forcedotcom/afv-library) — A curated collection of Salesforce agent skills for building applications using any AI tool that supports skills.
- [Agentforce Development Skill](https://github.com/forcedotcom/afv-library/tree/main/skills/developing-agentforce) — The specific skill (located within the Agentforce Vibes Library) designed for building, modifying, debugging, and deploying Agentforce agents using Agent Script.

## Next Steps

To learn how to build agents in Canvas view or by chatting with Agentforce, see [Build Enterprise-Ready Agents with the New Agentforce Builder](https://help.salesforce.com/s/articleView?id=ai.agent_builder_intro.htm) in Salesforce Help.

To learn more about Agent Script, review these topics.

- [Language Characteristics](/docs/ai/agentforce/guide/ascript-lang.md)
- [Agent Script Blocks](/docs/ai/agentforce/guide/ascript-blocks.md)
- [Flow of Control](/docs/ai/agentforce/guide/ascript-flow.md)
- [Agent Script Patterns](/docs/ai/agentforce/guide/ascript-patterns.md)
- [Agent Script Examples](/docs/ai/agentforce/guide/ascript-examples.md)
- [Agent Script Reference](/docs/ai/agentforce/guide/ascript-reference.md)

## See Also

- [Manage Agent Script Agents](/docs/ai/agentforce/guide/ascript-manage.md)
- *Trailhead*: [Programmatic Instructions in Agentforce](https://trailhead.salesforce.com/content/learn/modules/programmatic-instructions-in-agentforce)
- *Trailhead*: [Agent Script Basics](https://trailhead.salesforce.com/content/learn/modules/agent-script-basics)


# Agent Script Language Characteristics

Agent Script is a language designed by Salesforce specifically to build Agentforce agents. This page covers some key characteristics of the language before digging into the specifics.

## Compiled

Agent Script is a compiled language. When you save a version of the agent, the script compiles into lower-level metadata that is used by the reasoning engine.

## Determinism Plus Reasoning

Agent Script combines deterministic logic with LLM reasoning in a single workflow. This hybrid approach gives you predictable execution where you need it, while preserving the LLM's ability to handle nuanced conversations.

- **Logic instructions** (`->`) run deterministically every time. Use them for business rules, running actions, setting variables, and conditional branching.
- **Prompt instructions** (`|`) are natural language sent to the LLM. The LLM interprets these instructions and decides how to respond to the customer.

See [Flow of Control](/docs/ai/agentforce/guide/ascript-flow.md), [Agent Script Patterns](/docs/ai/agentforce/guide/ascript-patterns.md), and [Reasoning Instructions](/docs/ai/agentforce/guide/ascript-ref-instructions.md).

## Declarative With Procedural Components

Agent Script has elements of both declarative and procedural languages so that you can build an agent that is both predictable and easy to maintain.

- A declarative language is a language where you directly *declare* what you want rather than having to worry about the exact flow step by step. This type of programming language gives you the power to define and customize your agent, but without having to worry about the detailed flow. The basic [Agent Script Blocks](/docs/ai/agentforce/guide/ascript-blocks.md) resemble a declarative language.
- A procedural language is a language where you specify how to execute commands in a specific order. We use elements from procedural languages so that you can specify instructions in logical steps. The logic in [reasoning instructions](/docs/ai/agentforce/guide/ascript-ref-instructions.md) resemble a procedural language.

## Human-Readable

Agent Script is designed to be human-readable so that even non-developers can get a basic understanding of how the agent works.

## Property-Based

Agent Script is made up of a collection of properties. Each property is shown as `key: value`. Some properties are multiple lines and some properties contain sub-properties, but the `key` is always before the colon (:) and the `value` is always after the colon.

```sfdocs-code {"lang":"agentscript", "title": "Agent Script Property"}
description: "Get account info"
```

The top-level properties are called blocks. For instance, we call this section the config block.

```sfdocs-code {"lang":"agentscript", "title": "Agent Script Block"}
config:
    developer_name: "Demo_Agent_1"
    agent_label: "Demo Agent"
    description: "This is my demo agent"
```

## Indentation and Formatting

Agent Script is whitespace-sensitive, similar to languages like Python or YAML, meaning that indentation is used to indicate structure and relationships between properties. To indicate that a value belongs to the previous line’s property, indent with at least 2 spaces or 1 tab. However, you must choose one indentation method and use it consistently throughout the entire script. All lines at the same nesting level must use the same indentation, and mixing spaces and tabs will cause parsing errors.

```sfdocs-code {"lang":"agentscript", "title": "Indentation"}
inputs:
    input_1: string
    input_2: string
```

To specify logic instructions, use the arrow symbol ( `->` ) followed by indented instructions.

```sfdocs-code {"lang":"agentscript", "title": "Logic Instructions"}
instructions: ->
    if @variables.ready_to_book:
        run @actions.get_account_info
            with account_id=@variables.account_id
            set @variables.hotel_code=@outputs.hotel_code
```

To specify multiline strings in reasoning instructions, descriptions, and system messages, use the pipe symbol ( `|` ).

```sfdocs-code {"lang":"agentscript", "title": "Multiline Subagent Instructions"}
instructions:|
    Welcome to our service!
    Please provide details about your request.
    I'll help you with whatever you need.
```

The pipe symbol can also be used to switch to a prompt from logic-based instructions.

```sfdocs-code {"lang":"agentscript", "title": "Prompt Escape"}
    reasoning:
        instructions: ->
            | You are assessing the customer's timing for making a decision.
              Follow these rules to determine what to ask:

            if @variables.Lead_Record.S4STiming != "":
                | Existing timing data found.
                  Current Timing Value: {! @variables.Lead_Record.S4STiming }

                  Ask: "From what we have, you're looking to make a decision by {! @variables.Lead_Record.S4STiming }. Is that still correct?"

                  Wait for their response before proceeding.
```

See [Reasoning Instructions](/docs/ai/agentforce/guide/ascript-ref-instructions.md) in the Agent Script Reference.

## Accessing Resources

You can access resources, such as actions, subagents, and variables, using the `@` symbol.

- `@actions.<action_name>`: References an action.
- `@subagent.<subagent_name>`: References a subagent.
- `@connected_subagent.<connected_subagent_name>`: References a connected subagent.
- `@variables.<variable_name>`: References a variable.
- `@outputs.<output_name>`: References an action output.

To run an action, use the `run` command. Use the `with` command to provide inputs and use the `set` command to store outputs.

```sfdocs-code {"lang":"agentscript", "title": "Access Resources"}
run @actions.show_great_example
   with QuestionRecordId=@variables.my_great_question
   set @variables.my_great_answer = @outputs.AnswerDescription
```

See [Actions](/docs/ai/agentforce/guide/ascript-ref-actions.md) in the Agent Script Reference.

When referencing a variable from within prompt text in reasoning instructions, you must specify the variable within brackets: `{!@variables.<variable_name>}`. For example:

```sfdocs-code {"lang":"agentscript", "title": "Variable Reference"}
| Ask the user this question: {!@variables.my_question}
```

See [Variables](/docs/ai/agentforce/guide/ascript-ref-variables.md) in the Agent Script Reference.

You can specify a subagent as a tool available to the LLM. For more information, see [Tools (Reasoning Actions)](/docs/ai/agentforce/guide/ascript-ref-tools.md).

## Using Expressions

Agent Script uses familiar flow control syntax, such as `if` and `else`. It also uses basic mathematical expressions (`+`, `-`) and comparison expressions (`==`, `!=`, `>`, `<`). You can check for empty values using `is None` and `is not None`.

```sfdocs-code {"lang":"agentscript", "title": "Expressions"}
if @variables.count >= 10:
    run @actions.count_achieved_announcement
else:
    run @actions.count_missed_announcement
```

See [Conditional Expressions](/docs/ai/agentforce/guide/ascript-ref-expressions.md) and [Supported Operators](/docs/ai/agentforce/guide/ascript-ref-operators.md) in the Agent Script Reference.

## Comments to Help the Humans

You can specify comments in Agent Script with the pound (`#`) symbol followed by the comment. The script ignores any content on the line after the pound symbol. Use this mechanism to document the script within the script.

```sfdocs-code {"lang":"agentscript", "title": "Comments"}
# This is an agent sample script that demonstrates deterministic behavior
```

## See Also

- *Trailhead*: [Programmatic Instructions in Agentforce](https://trailhead.salesforce.com/content/learn/modules/programmatic-instructions-in-agentforce)
- *Trailhead*: [Agent Script Basics](https://trailhead.salesforce.com/content/learn/modules/agent-script-basics)


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE4NzU0NjAwNl19
-->