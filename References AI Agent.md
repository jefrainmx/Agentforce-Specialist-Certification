
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

# Agent Script Blocks

A script consists of blocks where each block contains a set of properties. These properties can describe data or procedures. Agent Script contains several different block types.

![Agent Script Blocks](https://a.sfdcstatic.com/developer-website/sfdocs/genai/media/agent-script/agent-script-blocks4.svg)

This section gives you a high-level understanding of each block type.

## System Block

The system block contains general instructions for the agent. This information includes a list of message prompts that the agent uses during specific scenarios. `welcome` and `error` are required messages:

- For multiline messages, use the pipe symbol ("|")
- To personalize messages or include other context information, use [linked variables](/docs/ai/agentforce/guide/ascript-ref-variables.md#linked-variables).

For example, to dynamically inject the user's preferred name into the welcome message, use `{!@variables.userPreferredName}`.

In this example, if the `userPreferredName` is `Sam`, customers see the welcome message "Hi Sam! I'm your personal shopping assistant".

```sfdocs-code {"lang":"agentscript", "title": "System Block"}
system:
    instructions:|
        You are an AI agent. Have a friendly conversation with the user.

    messages:
        welcome:|
            Welcome  {!@variables.userPreferredName}! I'm your personal shopping assistant.

            I can help you:
            - Find products and check availability
            - Track your orders
            - Process returns and refunds
            - Answer questions about our policies

            How can I assist you today?
        error: "Whoops!"
```

## Config Block

The config block contains configuration parameters that define the agent.

| Parameter                    | Description                                                                                                                                                                                                                                                                     |
| :--------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `developer_name`             | The Salesforce API name of the agent (max 80 chars). Must start with a letter, contain only alphanumeric and underscores, and can't end with underscore or have consecutive underscores. Must be unique in your org - you can't have two agents with the same `developer_name`. |
| ~~`default_agent_user`~~     | Deprecated in this block. Specify `default_agent_user` in the [Access Block](#access-block).                                                                                                                                                                                    |
| `agent_label`                | Optional. The agent's label, displayed in the UI. Auto-generated from `developer_name` if not provided.                                                                                                                                                                         |
| `description`                | Description of the agent's goals and purpose.                                                                                                                                                                                                                                   |
| `company`                    | Optional. Information about your company.                                                                                                                                                                                                                                       |
| `role`                       | Optional. The agent's role. For example, "Help the customer select the perfect gift."                                                                                                                                                                                           |
| `agent_version`              | The agent's version. Set automatically when you create a new version of your agent.                                                                                                                                                                                             |
| `agent_type`                 | Optional. The type of agent. Currently, allowed values are `AgentforceServiceAgent` (default) or `AgentforceEmployeeAgent`. Set automatically when you create an agent from a template.                                                                                         |
| `enable_enhanced_event_logs` | Optional. Indicates whether to enable conversation logging for debugging and monitoring. Allowed values are `True` or `False`. Default: `False`.                                                                                                                                |
| `user_locale`                | Optional. User locale setting.                                                                                                                                                                                                                                                  |
| `runtime`                    | Optional. Sub-block that controls the agent's runtime behavior, such as streaming, citations, and groundedness checks. See [Runtime Sub-Block](#runtime-sub-block).                                                                                                             |
| `file_upload`                | Optional. Sub-block that controls how the agent handles files uploaded by the customer during a conversation. See [File Upload Sub-Block](#file-upload-sub-block).                                                                                                              |

### Example Config Block

```sfdocs-code {"lang":"agentscript", "title": "Config Block"}
config:
    developer_name: "Demo_Agent_1"
    agent_label: "Demo Agent"
    description: "This is my demo agent"
```

## Runtime Sub-Block

The `runtime` block is a sub-block of [Config](#config-block) that controls the agent's runtime behavior.

| Parameter               | Description                                                                                                                                                                                                                                                                                                                                                                                                                           |
| :---------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `streaming`             | Controls whether the agent's response is streamed to the client incrementally as it's produced. When `False`, the response is delivered as a single chunk.**When to use:** Leave on (or omit) for interactive chat and voice channels where customers expect the reply to appear progressively. Set to `False` for clients or integrations that only consume a single completed message.                                              |
| `thought_chunks`        | Controls whether the agent's step-by-step thinking is streamed alongside its responses. When `True`, clients that render "thinking" output can display it during the turn.**When to use:** Enable when your client renders reasoning to the customer or to developers (for example, an "agent is thinking" panel or a debug view). Disable for customer-facing surfaces where exposing internal reasoning is undesirable.             |
| `citation`              | Controls the citation-enrichment post-processing step, which annotates knowledge-based answers with references to their source. Set to `False` to skip citation enrichment.**When to use:** Leave on for knowledge-grounded agents where customers benefit from seeing or clicking through to the source. Disable for channels that can't render citations, or when the extra post-processing latency isn't worth it.                 |
| `groundedness`          | By default, Agentforce checks the LLM's responses against source content. This extra step takes some time but reduces the chance of hallucinations. Set to `False` to turn this check off.**When to use:** Leave on for knowledge-heavy agents where reducing hallucinations matters. Disable when you need faster responses and have accepted the tradeoff, or when you've confirmed the check isn't adding value for your use case. |
| `reset_to_initial_node` | When `True`, each new customer turn restarts at the start_agent block, instead of resuming where the previous turn left off.**When to use:** Enable for stateless, one-shot Q&A or planner-style agents that should re-plan from scratch every turn. Leave off (the default) for multi-turn flows that need to resume mid-conversation.                                                                                               |

```sfdocs-code {"lang":"agentscript", "title": "Runtime Block"}
config:
    developer_name: "Demo_Agent_1"
    runtime:
        streaming: True
        thought_chunks: False
        citation: True
        groundedness: True
        reset_to_initial_node: False
```

## File Upload Sub-Block

The `file_upload` block, nested inside `config`, controls how the agent handles files that the customer uploaded during a conversation.

| Parameter | Description                                                                                                                           |
| :-------- | :------------------------------------------------------------------------------------------------------------------------------------ |
| `mode`    | Required. [How the agent handles uploaded](#allowed-mode-values) files. Allowed values are `auto`, `managed`, `disabled`, or `error`. |
| `message` | Optional. A message shown to the customer if uploads aren't successful.                                                               |

### Allowed `mode` values

- **`auto`** — Default file handling. Uploaded files are made available to the agent using standard behavior.
- **`managed`** — Use this mode when you want fine-grained control over which uploaded files reach which subagent. This is the mode that pairs with slice syntax on `@system_variables.uploaded_files`, so you can pass a specific batch (for example, `@system_variables.uploaded_files[0:5]`) into an individual subagent.
- **`disabled`** — Uploads are rejected without displaying a message to the customer.
- **`error`** — Uploads are rejected and treated as an error. If provided, the message in `message` is shown to the customer. If `message` isn't provided, Agentforce generates a message.

```sfdocs-code {"lang":"agentscript", "title": "Config Block with File Upload"}
config:
    developer_name: "Support_Agent"
    agent_label: "Customer Support Agent"
    file_upload:
        mode: "managed"
        message: "Something went wrong. Try again."
```

## Access Block

The access block defines the agent's default user.

| Parameter            | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| :------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `default_agent_user` | The agent user's username, which is in the form of an email address. `username` is a field on the [User](https://developer.salesforce.com/docs/atlas.en-us.object_reference.meta/object_reference/sforce_api_objects_user.htm) object. You can also see a user's username in Setup. Required for [Agentforce Service agents](https://help.salesforce.com/s/articleView?id=ai.service_agent_setup.htm&type=5). An agent runs in the context of a user, and the user's permissions grant or deny access to Salesforce resources and data. |

```sfdocs-code {"lang":"agentscript", "title": "Example Access Block"}
access:
    default_agent_user: "service@example.com"
```

## Variables Block

The variables block contains the list of global variables that the agent and script can use. See [Variables](/docs/ai/agentforce/guide/ascript-ref-variables.md).

```sfdocs-code {"lang":"agentscript", "title": "Variables Block"}
variables:
    string_var: mutable string = "hello world"
    hotel_info: mutable string = "Dreamforce Hotel"
```

You reference variables throughout the script by using the syntax `@variables.<variable_name>`.

## Language Block

The language block defines which languages the agent supports.

```sfdocs-code {"lang":"agentscript", "title": "Language Block"}
language:
    default_locale: "en_US"
    additional_locales: ""
    all_additional_locales: False
```

For a list of supported languages, see [Agentforce Language Support](https://help.salesforce.com/s/articleView?id=ai.agent_language_support.htm).

## Modality Block

The modality block configures agent behavior for a specific modality. The current allowed modality is `voice`. Use `modality voice:` to control how the agent sounds — its voice, speaking speed, pronunciation of specialized terms, and how it handles turn-taking on a live call.

```sfdocs-code {"lang":"agentscript", "title": "Modality Block"}
modality voice:
    outbound:
        persona_id: "<voice identifier>"
        model:
            parameters:
                speed: 0.9
```

By default, a voice agent uses the ElevenLabs v3 Conversational model.

- To select a different voice model, see [Configure Voice Models in Agent Script](/docs/ai/agentforce/guide/ascript-voice.md).
- To see the complete voice catalog, see [Voice Catalog for Agentforce Voice](/docs/ai/agentforce/guide/ascript-voice-catalog.md).

### Voice Variables

The `voice` variant supports these variables. All variables are optional except `voice_id` when configuring a live voice channel.

| Variable                         | Type     | Range     | Description                                                                                                                                                            |
| :------------------------------- | :------- | :-------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `voice_id`                       | string   | —         | Unique identifier for the outbound voice (for example, `"UgBBYS2sOqTuMpoF3BR0"`).                                                                                      |
| `outbound_speed`                 | number   | 0.5 – 2.0 | Speech rate. `1.0` is normal; lower is slower, higher is faster.                                                                                                       |
| `outbound_style_exaggeration`    | number   | 0.0 – 1.0 | How strongly the voice expresses its style. Higher values are more expressive; lower values are flatter and more consistent.                                           |
| `inbound_filler_words_detection` | boolean  | —         | When `True`, filler words (like "um", "uh") in the customer's speech are detected and ignored.                                                                         |
| `inbound_keywords`               | block    | —         | Keyword boost list. Contains a `keywords` sequence of strings that improves recognition for domain-specific terms.                                                     |
| `pronunciation_dict`             | sequence | —         | Custom pronunciations for specialized words or names. Each entry has `grapheme` (written form), `phoneme` (phonetic spelling), and `type` (either `"IPA"` or `"CMU"`). |
| `outbound_filler_sentences`      | sequence | —         | Short "thinking" phrases the agent says while an action is running, so the customer doesn't hear dead air. Each entry has a `waiting` list of strings.                 |
| `additional_configs`             | block    | —         | Container for `speak_up_config`, `endpointing_config`, and `beepboop_config`. See [Additional Configs](#additional-configs).                                           |

### Additional Configs

The `additional_configs` block groups three sub-configurations that fine-tune turn-taking behavior on a live call.

| Sub-config           | Variable                          | Type   | Range          | Description                                                                                                               |
| :------------------- | :-------------------------------- | :----- | :------------- | :------------------------------------------------------------------------------------------------------------------------ |
| `speak_up_config`    | `speak_up_first_wait_time_ms`     | number | 10000 – 300000 | How long to wait, in milliseconds, before speaking up for the first time after the customer goes silent.                  |
| `speak_up_config`    | `speak_up_follow_up_wait_time_ms` | number | 10000 – 300000 | How long to wait, in milliseconds, before speaking up again if the customer is still silent.                              |
| `speak_up_config`    | `speak_up_message`                | string | —              | The message the agent says when it speaks up.                                                                             |
| `endpointing_config` | `max_wait_time_ms`                | number | 500 – 60000    | Maximum time, in milliseconds, to wait for the customer to continue speaking before treating the turn as complete.        |
| `beepboop_config`    | `max_wait_time_ms`                | number | 500 – 60000    | Maximum time, in milliseconds, to wait when analyzing an inbound automated tone (like a fax machine or answering system). |

### Full Example

```sfdocs-code {"lang":"agentscript", "title": "Full Voice Modality"}
modality voice:
    inbound_filler_words_detection: True
    inbound_keywords:
        keywords:
            - "urgent"
            - "emergency"
    voice_id: "UgBBYS2sOqTuMpoF3BR0"
    outbound_speed: 1.0
    outbound_style_exaggeration: 0.5
    pronunciation_dict:
        - grapheme: "Eliquis"
          phoneme: "ɛlɪkwɪs"
          type: "IPA"
    outbound_filler_sentences:
        - waiting: ["Let me look into that...", "Give me a moment..."]
    additional_configs:
        speak_up_config:
            speak_up_first_wait_time_ms: 10000
            speak_up_follow_up_wait_time_ms: 10000
            speak_up_message: "Are you still there?"
        endpointing_config:
            max_wait_time_ms: 1000
        beepboop_config:
            max_wait_time_ms: 1000
```

:::note
The voice modality requires a deterministic locale. If your agent uses a `language` block with `adaptive: True`, adaptive language mode is ignored on voice channels and a warning is emitted. Configure a specific `default_locale` in the language block when pairing it with `modality voice`.
:::

To branch agent logic based on the customer's current channel at runtime (as opposed to configuring voice-specific behavior here), use the [`@system_variables.current_modality`](/docs/ai/agentforce/guide/ascript-ref-variables-system.md#current_modality) system variable.

## Connection Block

Use the connection block to describe how this agent interacts with outside connections. For instance, this code snippet shows how the agent interacts with [Enhanced Chat](https://help.salesforce.com/s/articleView?id=service.miaw_intro_landing.htm).

```sfdocs-code {"lang":"agentscript", "title": "Connection Block"}
connection messaging:
    escalation_message: "One moment while I connect you to the next available service representative."
    outbound_route_type: "OmniChannelFlow"
    outbound_route_name: "agent_support_flow"
    adaptive_response_allowed: True
```

You can use the connection block alongside the [@utils.escalate](/docs/ai/agentforce/guide/ascript-ref-utils.md#utilsescalate) command.

## Subagent Blocks

Use the subagent block to specify the instructions, logic, and actions for a subagent. A subagent block contains a description, a list of actions, and the reasoning instructions. To define a connection to another Agentforce agent in your Salesforce org, see [Connected Subagent Blocks](#connected-subagent-block).

```sfdocs-code {"lang":"agentscript", "title": "Subagent Block"}
subagent Order_Management:
    description: "Handles order lookup, order updates, and summaries including status, date, location, items, and driver."

    reasoning:
        instructions: ->
            if @variables.order_summary == "":
                run @actions.lookup_current_order
                with member_email=@variables.member_email
                set @variables.order_summary=@outputs.order_summary

            | Refer to the user by name {!@variables.member_name}.
              Show their current order summary: {!@variables.order_summary} when conversation starts or if requested.
              If they want past order info, ask for Order ID and use {!@actions.lookup_order}.

        actions:
            lookup_order: @actions.lookup_order
                with query = ...
                set @variables.order_summary=@outputs.order_summary
                set @variables.order_id=@outputs.order_id

            lookup_current_order: @actions.lookup_current_order
                with member_email=@variables.member_email
                set @variables.order_summary=@outputs.order_summary
                set @variables.order_id=@outputs.order_id

    actions:
        lookup_order:
            description: "Retrieve order details."
            inputs:
                query: string
            outputs:
                order_summary: string
                order_id: string
            target: "flow://SvcCopilotTmpl__GetOrdersByContact"


        lookup_current_order:
            description: "Retrieve current order details."
            inputs:
                member_email: string
            outputs:
                order_summary: string
                order_id: string
            target: "flow://SvcCopilotTmpl__GetOrderByOrderNumber"
```

These properties make up a subagent block:

- **subagent name**: This value is the name of the subagent that should accurately describe the scope and purpose of this subagent in a few words. Because this value can’t have spaces, use `snake_case` to name the subagent.
- **description**: This property contains the description for this subagent. This value should help the agent determine when to use this subagent based on the user’s intent.
- **system.instructions** (optional): Override system-level system instructions for this subagent only. By overriding system-level instructions, you can avoid giving conflicting intructions to the LLM, which can cause unexpected agent behavior. You can also change the agent's voice & tone for a specific subagent. See [Avoid Conflicting Instructions with Instruction Overrides](/docs/ai/agentforce/guide/ascript-patterns-system-overrides.md).
- **reasoning**: This section contains information sent to the reasoning engine. Its primary properties are instructions and actions.
  - **reasoning.instructions**: This property contains guidance for the reasoning engine after it has decided that this subagent is relevant to the user's request. The reasoning instructions can be a combination of logic instructions and prompt-based instructions. See [Reasoning Instructions](/docs/ai/agentforce/guide/ascript-ref-instructions.md).
  - **reasoning.actions**: The list of tools that are applicable for the reasoning engine to use. This list can point to agent actions listed in the higher-level actions section, as well as other functionality available to the reasoning engine (such as transitioning to another subagent, or setting a variable's value). See [Tools (Reasoning Actions)](/docs/ai/agentforce/guide/ascript-ref-tools.md).
- **actions**: This section defines the agent actions available from this subagent. It contains a description of the action, the list of inputs and outputs, and the target location where this action resides. If you want to allow the reasoning engine to use one of these agent actions, you must also point to this action from the `reasoning.actions` section. See [Actions](/docs/ai/agentforce/guide/ascript-ref-actions.md).

## Connected Subagent Block

Use the `connected_subagent` block to define a connection to another Agentforce agent in your Salesforce org. Connected subagents differ from [subagents](#subagent-blocks) that are part of your current agent. A connected subagent represents a complete, independent agent with its own distinct expertise and identity. A connected subagent can contain one or more subagents of its own. You can use a connected subagent in a [reasoning action](/docs/ai/agentforce/guide/ascript-ref-actions.md#using-actions) to delegate tasks to another Agentforce agent.

For more information about using multiple agents in a Salesforce org, see [Multi-Agent Orchestration](https://help.salesforce.com/s/articleView?id=ai.agent_multi_orch.htm\&type=5) and [Agent Script in Multi-Agent Solutions](https://help.salesforce.com/s/articleView?id=ai.agent_multi_orch_script.htm\&type=5) in Salesforce Help.

```sfdocs-code {"lang":"agentscript", "title": "Example - Define the CRM_Agent Connected Subagent"}
connected_subagent CRM_Agent:
    label: "CRM_Agent"
    target: "agentforce://X00Dfi200000dpFZ_CRM_Agent"
    loading_text: |
        Fetching CRM information....
    description: "Use this tool for any request about CRM information"
    # define input variables that you'll use to pass information to the connected agent
    inputs:
        EndUserLanguage: string = @variables.EndUserLanguage
        currentRecordId: string = @variables.currentRecordId
```

```sfdocs-code {"lang":"agentscript", "title": "Example - Delegate Control to a Connected Subagent (Handoff Mode)"}
start_agent agent_router:
    model_config:
        model: "model://sfdc_ai__DefaultEinsteinHyperClassifier"
    reasoning:
        actions:
            go_to_crm: @utils.transition to @connected_subagent.CRM_Agent
```

```sfdocs-code {"lang":"agentscript", "title": "Example - Route to the Connected Subagent and Supervise its Output (Supervisor Mode)"}
start_agent agent_router:
    label: "Agent Router"
    description: "Welcome the user and determine the appropriate subagent based on user input"
    reasoning:
        instructions: ->
            | Select the best tool to call based on conversation history and user's intent.
        actions:
            # transition to a subagent
            go_to_off_topic: @utils.transition to @subagent.off_topic

            # Route to the CRM_Agent connected subagent
            crm_agent: @connected_subagent.CRM_Agent
```

These properties make up a `connected_subagent` block:

- **connected_subagent name**: The name used to reference this connected subagent elsewhere in your Agent Script.
- **target**: The URI identifying the Agentforce agent (also called the reference agent). This value is filled in when you [connect an agent as a subagent in Agentforce Builder](https://help.salesforce.com/s/articleView?id=ai.agent_multi_orch_connect.htm\&type=5).
- **label** (optional): A human-readable label for the connected subagent.
- **description** (required): Describes the connected subagent's capabilities or when it should be called. This description helps the reasoning engine decide when to delegate to the connected subagent.
- **loading_text** (optional): A message shown to the customer while the connected subagent runs.
- **inputs** (optional): Values passed to the connected subagent. Each input binding has two sides:

  - The **left side** (for example, `customer_id`) is a custom, or mutable, variable defined in the connected subagent (that is, in the other Agentforce agent).
  - The **right side** (for example, `@variables.Customer_Id`) binds the connected subagent's input to a variable in the calling agent. These variables can be either context, or linked variables, or custom, or mutable variables.

  For example, suppose your input is `customer_id: string = @variables.Customer_Id`. The connected subagent's `customer_id` variable receives the value of the calling agent's `Customer_Id` variable.

:::note
In this release, variables are passed in one direction only: from the orchestrator agent to the connected subagent. Variables aren’t passed from a connected subagent back to the orchestrator agent.
:::

- **after_response** (optional): Runs after the connected subagent has responded to the user.
  - **if/then (conditional)** - branch on outcome.
  - **set** - set the value of a custom, or mutable, variable for the pipeline.
  - **transition** - delegate control to the next connected subagent. Any script commands placed after the
    transition are skipped.
- **delegate_escalation** (optional): If `True`, allows the connected subagent to escalate to a human representative. Applies only if the connected subagent is in handoff mode. Otherwise, if unspecified, or if the orchestrator agent is in supervision mode, escalation to a human occurs in the orchestrator agent only.

## Start Agent Block

The start agent block (called the "Agent Router" in Canvas view) is a subagent that uses the `start_agent` prefix instead of the `subagent` prefix. With every customer utterance, the agent begins execution at this block. The `start_agent` subagent is used to initiate the conversation, and typically determines when to switch to the agent's other subagents. This block handles subagent classification, filtering, and routing.

```sfdocs-code {"lang":"agentscript", "title": "Start Agent Block"}
start_agent agent_router:
    description: "Welcome the user and determine the appropriate subagent based on user input"
    reasoning:
        instructions: |
            You are an agent router for this assistant. Welcome the guest
            and analyze their input to determine the most appropriate subagent
            to handle their request.
        actions:
            go_to_identity: @utils.transition to @subagent.Identity_Verification
                description: "Verifies user identity"
                available when @variables.verified == False
            go_to_order: @utils.transition to @subagent.Order_Management
                description: "Handles order lookup, refunds, and order updates."
                available when @variables.verified == True
            go_to_faq: @utils.transition to @subagent.General_FAQ
                description: "Handles various frequently asked questions."
                available when @variables.verified == True
            go_to_escalation: @utils.transition to @subagent.Escalation
                description: "Handles escalation to a human rep."
                available when @variables.verified == True and @variables.is_business_hours == True
```

For more guidance on how to use the start agent block for subagent routing and filtering, see [Subagent Classification and Routing](https://help.salesforce.com/s/articleView?id=ai.agent_topics_routing.htm) in Salesforce Help.

## Related Topics

- [Agent Script Patterns](/docs/ai/agentforce/guide/ascript-patterns.md)
- [Agent Script Reference](/docs/ai/agentforce/guide/ascript-reference.md)
- [Configure Models in Agent Script](/docs/ai/agentforce/guide/ascript-model.md)
- [Configure Voice Models in Agent Script](/docs/ai/agentforce/guide/ascript-voice.md)

# Agent Script Flow of Control

Understanding the order of execution and flow of control helps you to design better agents. Agentforce has these main execution paths:

1. First request to an agent
2. Processing a subagent
3. Transitioning between subagents

## First Request to an Agent

All requests, including the first request, begin at the agent router, the `start_agent` block. You typically use the `start_agent` subagent to set the initial value of variables, and to perform subagent classification. Subagent classification tells the LLM which subagent to choose based on the current context.

See [Start Agent Block](/docs/ai/agentforce/guide/ascript-blocks.md#start-agent-block).

## Processing a Subagent

Agentforce uses a subagent's text instructions, variables, `if`/`else` conditions, and other programmatic instructions to create an LLM prompt. The reasoning instructions are processed sequentially, in top-to-bottom order. While the reasoning instructions can contain programmatic logic and text instructions, the LLM only starts reasoning after it has received the resolved prompt, not while Agentforce is still parsing.

If reasoning instructions contain a transition command, Agentforce immediately transitions to the specified subagent, discarding any existing resolved prompt. The final prompt only contains instructions that were resolved from the second subagent.

See [Reasoning Instructions](/docs/ai/agentforce/guide/ascript-ref-instructions.md).

### Example: How Agentforce Creates a Prompt from a Subagent

Agentforce processes a subagent to create a prompt, which it then sends to the LLM. Consider this subagent.

```sfdocs-code {"lang":"agentscript", "title": "Order Management Subagent"}

subagent Order_Management:
    description: "Handles order inquiries."
    reasoning:
        instructions:->
            set @variables.num_turns = @variables.num_turns + 1
            run @actions.get_delivery_date
                with order_ID=@variables.order_ID
                set @variables.updated_delivery_date=@outputs.delivery_date

            | Tell the user that the expected delivery date for order number {!@variables.order_ID} is {!@variables.updated_delivery_date}

            run @actions.check_if_late
                with order_ID=@variables.order_ID
                with delivery_date=@variables.updated_delivery_date
                set @variables.is_late = @outputs.is_late

            if @variables.is_late == True:
                | Apologize to the customer for the delay in receiving their order.
    after_reasoning:
       if @variables.num_turns > 5:
           transition to @subagent.escalate_order

```

Suppose that:

- the order ID is `1234`
- the current delivery date is `February 10, 2026`
- the package is late
- the agent has entered this subagent twice in the current session, so `num_turns` is 2

Here's the prompt that Agentforce creates after processing the reasoning instructions:

```sfdocs-code {"lang":"agentscript", "title": "Agentforce Prompt After Processing"}
Tell the user that the expected delivery date for order number 1234 is February 10, 2026.
Apologize to the customer for the delay in receiving their order.
```

#### How Agentforce Constructs the Prompt

To construct the prompt, Agentforce parses the reasoning instructions line by line, following these steps:

1. Initialize the prompt to empty.
2. Increments the global variable `num_turns` from 2 to 3.
3. Run the action `get_delivery_date`.
4. Set the variable `updated_delivery_date` to the value of `outputs.delivery_date`, which was returned by the action.
5. Concatenate this string to the prompt: `Tell the user that the expected delivery date for order number 1234 is February 10, 2026.`
6. Run action `check_if_late`.
7. Set the variable `is_late` to the value of `outputs.is_late`, which was returned by the action.
8. Check whether the value of `@variables.is_late` == `True`.
9. Concatenate this string to the prompt: `Apologize to the customer for the delay in receiving their order.`
10. Process the `after_reasoning` instructions, which don't transition because `num_turns` is 3.
11. Send the prompt to the LLM and return the LLM's response to the customer.

## Transitioning Between Subagents

You can transition between subagents from a reasoning action, reasoning instructions, or before and after reasoning blocks. A transition (using [@utils.transition to](/docs/ai/agentforce/guide/ascript-ref-utils.md#utilstransition-to)) is one-way and control doesn't return to the previous subagent. Agentforce discards any prompt instructions from the previous subagent. Then, Agentforce reads the second subagent from top to bottom. The final prompt contains only instructions from the second subagent.

After the second subagent completes, Agentforce waits for the next customer utterance, at which point it returns to the `start_agent` subagent.

In this example, we've defined a reasoning action called `go_to_account_help` that transitions to the subagent `account_help`.

```sfdocs-code {"lang":"agentscript", "title": "Transition Reasoning Action"}
reasoning:
    actions:
        go_to_account_help: @utils.transition to @subagent.account_help
            description: "When a user needs help with account access"
```

For more about transitions and subagents, see [Referencing a Subagent as a Tool](/docs/ai/agentforce/guide/ascript-ref-tools.md#referencing-a-subagent-as-a-tool) and the reference documentation for [@utils.transition to](/docs/ai/agentforce/guide/ascript-ref-utils.md#utilstransition-to).

## Related Topics

- [Agent Script Patterns](/docs/ai/agentforce/guide/ascript-patterns.md)
- [Agent Script Reference](/docs/ai/agentforce/guide/ascript-reference.md)



# Agent Script Reference: Variables (Custom and Linked)

Variables let agents deterministically remember information across conversation turns, track progress, and maintain context throughout the session. You define all variables in the `variables` block, and all subagents in the agent can access the variables.

This page covers custom and linked variables. For predefined runtime variables, see [Agent Script Reference: System Variables](/docs/ai/agentforce/guide/ascript-ref-variables-system.md).

- **[custom variable](#custom-variables):** You can initialize a variable with a default value, and the agent can change the variable's value.
- **[linked variable](#linked-variables):** The value of a linked variable is tied to an output such as an action's output. Linked variables can't have a default value.

## Defining a Variable

Define variables in the [`Variables`](/docs/ai/agentforce/guide/ascript-blocks.md#variables-block) block.

```sfdocs-code {"lang":"agentscript", "title": "Reference a Variable From Script"}
    CurrentState: mutable string = "gatheringInfo"
        description: "The current state, or step, of the interview."
        label: "State"
        visibility: "External"
```

## Variable Names

Variable names must follow Salesforce developer name standards:

- Begin with a letter, not an underscore.
- Contain only alphanumeric characters and underscores.
- Can't end with underscore.
- Can't contain consecutive underscores (\__).
- Maximum length of 80 characters.

## Referencing Variables

To reference a variable from the script, use `@variables.<variable_name>`.

```sfdocs-code {"lang":"agentscript", "title": "Reference a Variable From Script"}

            if @variables.Customer_Contact is None:
                set @variables.No_Matching_Contact = True
```

To reference a variable from within reasoning instructions, use `{!@variables.<variable_name>}`.

```sfdocs-code {"lang":"agentscript", "title": "Reference a Variable From Reasoning Instructions"}
reasoning:
    instructions: ->
        | Always use {!@variables.Customer_Email} for the customer's email address.
```

## Concatenating (Appending) String Variables

To concatenate, or append, string variables, use the `+` operator. For example, this expression combines the salutation, first name, and last name into a single variable, with a space between each value.

```sfdocs-code {"lang":"agentscript", "title": "Concatenate String Variables"}
set @variables.full_name = @variables.salutation + " " + @variables.first_name + " " + @variables.last_name
```

## Custom Variables

Custom variables have these properties:

- `mutable` - Optional. Allows the agent to change the variable's value. To ensure a variable's value is never changed, define the variable without `mutable`.
- `description` - describes the variable. Optional. If you want the LLM to use reasoning to set the variable's value, include a description to help the LLM set the value correctly. See [Let the LLM set variables with user-entered information (slot filling)](/docs/ai/agentforce/guide/ascript-patterns-variables.md#let-the-llm-set-variables-with-user-entered-information-slot-filling).
- `label` - Optional. The variable's name as displayed in the UI. By default, the description is generated from the name. For example, if your variable's name is `my_var`, the UI displays the label `My Var`.
- `visibility` - Optional. Default value is `Internal`. Set visibility to `External` to allow an API to set the variable's value, or to change the variable's value when [testing the agent in simulate mode](https://help.salesforce.com/s/articleView?id=ai.agent_test_in_builder.htm\&language=en_US\&type=5).

```sfdocs-code {"lang":"agentscript", "title": "Example: Define Custom Variables"}
variables:
    isPremiumUser: mutable boolean = False
        description: "Indicates whether the user is a premium user."
        label: "Has Gold Status"

    customer_loyalty_tier: mutable string = "standard"
        description:|
            Stores the customer's membership tier level.
```

Custom variables can have these types:

| Type         | Notes                                                                                                              | Example                                                                                                                                |
| :----------- | :----------------------------------------------------------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------- |
| `string`     | Any alphanumeric string without special characters.                                                                | `name: mutable string = ""`                                                                                                            |
| `number`     | Use for both integers and decimals. For example, 42 or 3.14. Compiles to IEEE 754 double-precision floating point. | `age: mutable number`, `price: mutable number = 99.99`                                                                                 |
| `boolean`    | Allowed values are `True` or `False`. The value is case-sensitive, so capitalize the first letter.                 | `is_active: mutable boolean = True`                                                                                                    |
| `object`     | Value is a complex JSON object in the form `{"key": "value"}.`                                                     | `order_line: mutable object = {"SKU": "abc12344409","count": 42}`                                                                      |
| `date`       | Any valid date format.                                                                                             | `start_date: mutable date`                                                                                                             |
| `id`         | Deprecated. Use `string` to store a Salesforce record ID.                                                          | See string type.                                                                                                                       |
| `list[type]` | A list of values of the specified type. All primitive types and `object` type are supported.                       | `flags: mutable list[boolean] = [True, False, True]`, `scores: list[number] = [95, 87.5, 92]`, `obj_list: mutable list[object] = None` |

## No Value (None) and Empty String ("")

Use `None` to check whether a variable has a value. You can use `None` with any variable type. For a string variable, you can also use `""` to check if the variable is set to an empty string. When checking string variables in conditional statements, you might want to use both `None` and `""`.

For more information, see [Agent Script Reference: Conditional Expressions](/docs/ai/agentforce/guide/ascript-ref-expressions.md).

## Linked Variables

A linked variable's value is tied to a source, such as an action's output. Linked variables have these restrictions:

- can't have a default value
- can't be set by the agent
- can't be an object or a list

The `source` field references where the variable gets its value. Supported source namespaces are:

| Namespace           | Available Properties                          | Description                          |
| :------------------ | :-------------------------------------------- | :----------------------------------- |
| `@MessagingSession` | `Id`, `MessagingEndUserId`, `EndUserLanguage` | Properties of the messaging session  |
| `@MessagingEndUser` | `ContactId`                                   | Properties of the messaging end user |
| `@VoiceCall`        | `Id`                                          | Properties of the voice call         |

```sfdocs-code {"lang":"agentscript", "title": "Example: Define Linked Variables"}
variables:
    session_id: linked string
        source: @MessagingSession.Id
        description: "The messaging session ID"
    contact_id: linked string
        source: @MessagingEndUser.ContactId
        description: "The contact ID of the end user"
    voice_call_id: linked string
        source: @VoiceCall.Id
        description: "The voice call ID"
```

Linked variables can have these types:

- `string`
- `number`
- `boolean`
- `date`
- `id` (deprecated; use `string` for Salesforce record IDs)

## Examples and Patterns

For examples and patterns using variables, see [Agent Script Pattern: Using Variables Effectively](/docs/ai/agentforce/guide/ascript-patterns-variables.md) and [Agent Script Pattern: Using List Variables](/docs/ai/agentforce/guide/ascript-patterns-var-list.md)

## Related Topics

- Pattern: [Using Variables Effectively](/docs/ai/agentforce/guide/ascript-patterns-variables.md)
- Pattern: [Using List Variables](/docs/ai/agentforce/guide/ascript-patterns-var-list.md)
- Reference: [System Variables](/docs/ai/agentforce/guide/ascript-ref-variables-system.md)
- Reference: [List Variables](/docs/ai/agentforce/guide/ascript-ref-variables-list.md)
- [Flow of Control](/docs/ai/agentforce/guide/ascript-flow.md)
- Reference: [Utils](/docs/ai/agentforce/guide/ascript-ref-utils.md)

# Agent API Session Lifecycle

To communicate with an agent through the Agent API, you must [create a session](/docs/ai/agentforce/guide/agent-api-examples.md#start-session). Then you [send messages](/docs/ai/agentforce/guide/agent-api-examples.md#send-synchronous-messages) to the agent by using the ID associated with that session. The agent keep tracks of the context throughout the session. When you’re finished working with the agent, [end the session](/docs/ai/agentforce/guide/agent-api-examples.md#end-session).

![API Flow](https://a.sfdcstatic.com/developer-website/sfdocs/genai/media/agent-api-lifecycle.svg)

The Agent API provides endpoints for each stage in this lifecycle, along with an endpoint to submit feedback on a response.

## Synchronous and Streaming Messages

Sending and receiving messages can be performed synchronously or with the streaming endpoint. The [synchronous endpoint](/docs/ai/agentforce/guide/agent-api-examples.md#send-synchronous-messages) is best for simple use cases where you want the entire response in one shot. The [streaming endpoint](/docs/ai/agentforce/guide/agent-api-examples.md#send-streaming-messages) is best if you intend to show the response to the user as the chunks of content arrive, like in a real-time chat conversation.

## See Also

- [Get Started with Agent API](/docs/ai/agentforce/guide/agent-api-get-started.md)
- [Agent API Examples](/docs/ai/agentforce/guide/agent-api-examples.md)
- [Agent API Postman Collection](https://www.postman.com/salesforce-developers/salesforce-developers/collection/gwv9bjy/agent-api)
- [Agent API Reference](/docs/ai/agentforce/references/agent-api?meta=summary)

# Agent API Examples

This section provides examples using the Agent API endpoints. To onboard, see [Get Started with Agent API](/docs/ai/agentforce/guide/agent-api-get-started.md).

:::note
The examples on this page use `api.salesforce.com` as the base endpoint. If your org is on Government Cloud, replace `api.salesforce.com` with `api.gov.salesforce.com` in every Agent API request.
:::

## Postman Collection

The quickest way to get started with the Agent API is with our [Postman collection](https://www.postman.com/salesforce-developers/salesforce-developers/collection/gwv9bjy/agent-api).

## Start Session

This curl command creates a new agent session with the Agent API.

```sfdocs-code {"lang":"bash", "title": "Sample Request: Start Session"}
curl --location -X POST https://api.salesforce.com/einstein/ai-agent/v1/agents/{AGENT_ID}/sessions \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer {ACCESS_TOKEN}' \
--data '{
  "externalSessionKey": "{RANDOM_UUID}",
  "instanceConfig": {
    "endpoint": "https://{MY_DOMAIN_URL}"
  },
  "streamingCapabilities": {
    "chunkTypes": ["Text"]
  },
  "bypassUser": true
}'
```

:::note
The `bypassUser` parameter indicates whether to use the agent-assigned user instead of the logged in user. If set to `true`, the API uses the user associated with the agent. If set to `false`, the API uses the user associated with the token.
:::

To make this request, these values are required.

- `AGENT_ID`: The ID of the agent that you want to interact with. The method for obtaining this ID depends on which builder you used to create your agent. See [Get the Agent ID for an Agent](/docs/ai/agentforce/guide/agent-api-agent-id.md) for detailed instructions.
- `RANDOM_UUID`: A random UUID value that you provide to represent the session key. You can use this parameter to trace the conversation in your agent's event logs.
- `ACCESS_TOKEN`: The token that you created in [Create a Token](/docs/ai/agentforce/guide/agent-api-get-started.md#create-a-token).
- `MY_DOMAIN_URL`: From Setup, search for **My Domain**. Copy the value shown in the **Current My Domain URL** field.
- Specify `application/json` in the `Content-Type` header to indicate JSON content in the request.

This example shows a start session response. The response returns the session ID (`sessionId`) value, which is required when sending messages to an agent.

```sfdocs-code {"lang":"json", "title": "Sample Response: Start Session"}
{
  "sessionId": "8e715939-a121-40ec-80e3-a8d1ac89da33",
  "_links": {
    "self": null,
    "messages": {
      "href": "https://api.salesforce.com/einstein/ai-agent/v1/sessions/8e715939-a121-40ec-80e3-a8d1ac89da33/messages/stream"
    },
    "session": {
      "href": "https://api.salesforce.com/einstein/ai-agent/v1/agents/0XxQZ0000000Ty50AE/sessions"
    },
    "end": {
      "href": "https://api.salesforce.com/einstein/ai-agent/v1/sessions/8e715939-a121-40ec-80e3-a8d1ac89da33"
    }
  },
  "messages": [
    {
      "type": "Inform",
      "id": "8e7cafae-0eb5-44b1-9195-21f1cd6e1f4b",
      "feedbackId": "",
      "planId": "",
      "isContentSafe": true,
      "message": "Hi, I'm an AI service assistant. How can I help you?",
      "result": [],
      "citedReferences": []
    }
  ]
}
```

For API reference info, see [Start Session](/docs/ai/agentforce/references/agent-api?meta=startSession).

## Send Synchronous Messages

When you send a message by using the synchronous endpoint, the server sends back the response synchronously in one response. To use the streaming endpoint, see [Send Streaming Messages](#send-streaming-messages).

Before sending messages, you must start a session. See [Start Session](#start-session).

This curl command sends a message to the synchronous endpoint.

```sfdocs-code {"lang":"bash", "title": "Sample Request: Send Sync Message"}
curl --location 'https://api.salesforce.com/einstein/ai-agent/v1/sessions/{SESSION_ID}/messages' \
--header 'Accept: application/json' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer {ACCESS_TOKEN}' \
--data '{
  "message": {
    "sequenceId": {SEQUENCE_ID},
    "type": "Text",
    "text": "Show me the cases associated with Lauren Bailey."
  }
}'
```

To make this request, these values are required.

- `SESSION_ID`: The session ID found in the response payload when you created a session.
- `ACCESS_TOKEN`: The token that you created in [Create a Token](/docs/ai/agentforce/guide/agent-api-get-started.md#create-a-token).
- `SEQUENCE_ID`: A number that you provide to represent the sequence ID. Increase this number for each subsequent message in this session.
- Specify `application/json` in the `Content-Type` header to indicate JSON content in the request.

This example shows a potential response to a synchronous send message request.

```sfdocs-code {"lang":"json", "title": "Sample ASA Response: Send Sync Message"}
{
    "messages": [
        {
            "type": "Inform",
            "id": "ceb6b5de-6063-4e39-bc02-91e9bf7da867",
            "metrics": {},
            "feedbackId": "0bc8720e-e010-4129-87bb-70caaa885ee4",
            "planId": "0bc8720e-e010-4129-87bb-70caaa885ee4",
            "isContentSafe": true,
            "message": "Here are two cases related to Lauren Bailey:\n\n1. Case Number: 00001116\n   - Subject: I have a question about my bill\n   - Description: When I received my most recent bill, I noticed there was a charge I didn't recognize. Can you look over my orders and help me understand what this might have been? Thank you!\n   - Status: New\n   - Created Date: 2025-04-05\n2. Case Number: 00001106\n   - Subject: I have a product suggestion.\n   - Description: I've been using your products for a long time, and I have a suggestion that I think would make them even better. What's the best way to share this with you?\n   - Status: Closed\n   - Created Date: 2025-04-05\n   - Closed Date: 2022-10-13.",
            "result": [],
            "citedReferences": []
        }
    ],
    "_links": {
        …(shortened)
    }
}
```

For API reference info, see [Send Synchronous Messages](/docs/ai/agentforce/references/agent-api?meta=sendMessage).

## Send Streaming Messages

When you send a message using the streaming endpoint, the server sends back information using the server-sent event (SSE) protocol. To use the synchronous endpoint, see [Send Synchronous Messages](#send-synchronous-messages).

Before sending messages, you must start a session. See [Start Session](#start-session).

This curl command sends a message to the streaming endpoint.

```sfdocs-code {"lang":"bash", "title": "Sample Request: Send Streaming Message"}
curl --location 'https://api.salesforce.com/einstein/ai-agent/v1/sessions/{SESSION_ID}/messages/stream' \
--header 'Accept: text/event-stream' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer {ACCESS_TOKEN}' \
--data '{
  "message": {
    "sequenceId": {SEQUENCE_ID},
    "type": "Text",
    "text": "Show me the cases associated with Lauren Bailey."
  }
}'
```

To make this request, these values are required.

- `SESSION_ID`: The session ID found in the response payload when you created a session.
- `ACCESS_TOKEN`: The token that you created in [Create a Token](/docs/ai/agentforce/guide/agent-api-get-started.md#create-a-token).
- `SEQUENCE_ID`: A number that you provide to represent the sequence ID. Increase this number for each subsequent message in this session.
- Specify `application/json` in the `Content-Type` header to indicate JSON content in the request.
- Specify `text/event-stream` in the `Accept` header so that the response contains the message stream.

When you make a streaming request, messages return in the event stream.

This example shows a [`ProgressIndicator`](/docs/ai/agentforce/references/agent-api?meta=type%3AProgressIndicatorMessage) event, which indicates that a response is in progress.

```sfdocs-code {"lang":"json", "title": "Sample Event: Streaming Message (ProgressIndicator)"}
{
  "timestamp": 1736902938827,
  "originEventId": "1736902935340-REQ",
  "traceId": "2fdb1d5e7eb48d35b9d1ba402eeb4b69",
  "offset": 0,
  "message": {
    "type": "ProgressIndicator",
    "id": "c4410599-8c0a-412d-910f-a60e4159d807",
    "indicatorType": "ACTION",
    "message": "Working on it"
}
```

The message streams in text chunk increments. This example shows a [`TextChunk`](/docs/ai/agentforce/references/agent-api?meta=type%3ATextChunkMessage) event.

```sfdocs-code {"lang":"json", "title": "Sample Event: Streaming Message (TextChunk)"}
{
  "timestamp": 1736902952425,
  "originEventId": "1736902935340-REQ",
  "traceId": "2fdb1d5e7eb48d35b9d1ba402eeb4b69",
  "offset": 1,
  "message": {
    "type": "TextChunk",
    "id": "6fc64974-9c20-484e-8b8c-105e460d4a00",
    "offset": 1,
    "message": "Here",
    "formatType": "Text"
  }
}
```

The API returns the complete message in an [`Inform`](/docs/ai/agentforce/references/agent-api?meta=type%3AInformMessage) event.

```sfdocs-code {"lang":"json", "title": "Sample Event: Streaming Message (Inform)"}
{
    "messages": [
        {
            "type": "Inform",
            "id": "f0313bcb-65a2-4abb-9d84-b872247b1420",
            "metrics": {},
            "feedbackId": "ab403163-b87f-4e4b-9fa6-18670a2be655",
            "planId": "ab403163-b87f-4e4b-9fa6-18670a2be655",
            "isContentSafe": true,
            "message": "Here are two cases related to Lauren Bailey:\n\n1. Case Number: 00001116\n   - Subject: I have a question about my bill\n   - Description: When I received my most recent bill, I noticed there was a charge I didn't recognize. Can you look over my orders and help me understand what this might have been? Thank you!\n   - Status: New\n   - Created Date: 2025-04-05\n2. Case Number: 00001106\n   - Subject: I have a product suggestion.\n   - Description: I've been using your products for a long time, and I have a suggestion that I think would make them even better. What's the best way to share this with you?\n   - Status: Closed\n   - Created Date: 2025-04-05\n   - Closed Date: 2022-10-13",
            "result": [],
            "citedReferences": []
        }
    ],
    "_links": {
        "self": null,
        "messages": {
            "href": "https://api.salesforce.com/einstein/ai-agent/v1/sessions/499713a4-b441-4234-bafd-392ee08dbd01/messages"
        },
        "messagesStream": {
            "href": "https://api.salesforce.com/einstein/ai-agent/v1/sessions/499713a4-b441-4234-bafd-392ee08dbd01/messages/stream"
        },
        "session": {
            "href": "https://api.salesforce.com/einstein/ai-agent/v1/agents/0XxQZ0000000Ty50AE/sessions"
        },
        "end": {
            "href": "https://api.salesforce.com/einstein/ai-agent/v1/sessions/499713a4-b441-4234-bafd-392ee08dbd01"
        }
    }
}
```

The API returns an [`EndOfTurn`](/docs/ai/agentforce/references/agent-api?meta=type%3AEndOfTurnMessage) event when the response is complete.

```sfdocs-code {"lang":"json", "title": "Sample Event: Streaming Message (EndOfTurn)"}
{
  "timestamp": 1736902953027,
  "originEventId": "1736902935340-REQ",
  "traceId": "2fdb1d5e7eb48d35b9d1ba402eeb4b69",
  "offset": 0,
  "message": {
    "type": "EndOfTurn",
    "id": "2a2be92b-f479-481a-9f22-1e5bf39e038e"
  }
}
```

:::tip
If you receive a [ValidationFailureChunk](/docs/ai/agentforce/references/agent-api?meta=type%3AValidationFailureChunkMessage) streaming event, there was a failure validating the agent's response. Remove all previously rendered chunks and display only the new streamed content.
:::

For API reference info, see [Send Streaming Messages](/docs/ai/agentforce/references/agent-api?meta=sendMessageStream).

## Send Agent Variables

For an example using agent variables, see [Send Agent Variables with the Agent API](/docs/ai/agentforce/guide/agent-api-variables.md).

## Handle Citations

Some message responses include cited sources. Cited sources surface in the `citedReferences` array of an `Inform` response message. Citations can either appear as sources at the bottom of the response, or inline citations (using the `inlineMetadata` object) that are associated with a specific location in the response.

```sfdocs-code {"lang":"json", "title": "Sample Response Body with Inline Citations"}
{
    "timestamp": 1745599724677,
    "originEventId": "1745599714159-REQ",
    "traceId": "310046aaded69001de5dbddaec4f8a75",
    "offset": 0,
    "message": {
        "type": "Inform",
        "id": "484c59e5-9c24-4735-ba55-0707a071a9e7",
        "feedbackId": "a9695531-091b-42de-8b4d-61f3aaadd42e",
        "planId": "a9695531-091b-42de-8b4d-61f3aaadd42e",
        "isContentSafe": true,
        "message": "The 2024 Acura ZDX is Acura's first-ever all-electric vehicle, featuring:\n\n- Maximum Range: 313 miles\n- Starting Price: $65,850\n- Interior: Premium and spacious\n- Charging: Compatible with Tesla's Supercharger network\n- Trim Levels: Two available trims\n- Platform: Shares a platform with the Cadillac Lyriq and is built in the same Tennessee factory\n- Sales: Conducted exclusively online\n- Pricing:\n   - ZDX A-Spec: $65,850\n   - ZDX A-Spec with all-wheel drive: $69,850\n   - ZDX Type S: $74,850\n- Tax Credit: Eligible for a federal tax credit of up to $7,500\n\nIf you have any more questions or need further details, feel free to ask!",
        "result": [],
        "citedReferences": [
            {
                "type": "link",
                "value": "https://myorgdomain.salesforce.com/ka0RZ000002DzSmYAK",
                "recordId": "ka0RZ000002DzSmYAK",
                "label": null,
                "inlineMetadata": [
                    {
                        "claim": "The 2024 Acura ZDX is Acura's first-ever all-electric vehicle, featuring:\n\n- Maximum Range: 313 miles\n- Starting Price: $65,850\n- Interior: Premium and spacious\n- Charging: Compatible with Tesla's Supercharger network\n- Trim Levels:",
                        "location": 236
                    }
                ]
            },
            {
                "type": "link",
                "value": "https://myorgdoamin.salesforce.com/ka0RZ000002E0INYA0",
                "recordId": "ka0RZ000002E0INYA0",
                "label": null,
                "inlineMetadata": [
                    {
                        "claim": "Two available trims\n- Platform: Shares a platform with the Cadillac Lyriq and is built in the same Tennessee factory\n- Sales: Conducted exclusively online\n- Pricing:\n   - ZDX A-Spec: $65,850\n   - ZDX A-Spec with all-wheel drive: $69,850\n   - ZDX Type S: $74,850\n- Tax Credit: Eligible for a federal tax credit of up to $7,500",
                        "location": 562
                    }
                ]
            }
        ]
    }
}
```

For API reference info, see [InformMessage](/docs/ai/agentforce/references/agent-api?meta=type%3AInformMessage) and [CitedReference](/docs/ai/agentforce/references/agent-api?meta=type%3ACitedReference).

## End Session

This curl command sends an end session request.

```sfdocs-code {"lang":"bash", "title": "Sample Request: End Session"}
curl --location --request DELETE 'https://api.salesforce.com/einstein/ai-agent/v1/sessions/{SESSION_ID}' \
--header 'x-session-end-reason: UserRequest' \
--header 'Authorization: Bearer {ACCESS_TOKEN}'
```

To make this request, these values are required.

- `SESSION_ID`: The session ID found in the response payload when you created a session.
- `ACCESS_TOKEN`: The token that you created in [Create a Token](/docs/ai/agentforce/guide/agent-api-get-started.md#create-a-token).

This example shows a response to an end message request.

```sfdocs-code {"lang":"json", "title": "Sample Response: End Session"}
{
  "messages": [
    {
      "type": "SessionEnded",
      "id": "c5692ca0-ee1b-414a-9d96-4e7862456500",
      "reason": "ClientRequest",
      "feedbackId": ""
    }
  ],
  "_links": {
    "self": null,
    "messages": {
      "href": "https://api.salesforce.com/einstein/ai-agent/v1/sessions/8d705938-a121-40ec-80e3-a8d1ac89da33/messages/stream"
    },
    "session": {
      "href": "https://api.salesforce.com/einstein/ai-agent/v1/agents/0XxQZ0000000Ty50AE/sessions"
    },
    "end": {
      "href": "https://api.salesforce.com/einstein/ai-agent/v1/sessions/8d705938-a121-40ec-80e3-a8d1ac89da33"
    }
  }
}
```

For API reference info, see [End Session](/docs/ai/agentforce/references/agent-api?meta=endSession).

## Submit Feedback

You can also submit feedback to the org based on the agent’s responses. This feedback is stored in Data 360. To learn more, see [About Generative AI Audit and Feedback Data](https://help.salesforce.com/s/articleView?id=ai.generative_ai_feedback_about.htm).

```sfdocs-code {"lang":"bash", "title": "Sample Request: Submit Feedback"}
curl -v --location 'https://api.salesforce.com/einstein/ai-agent/v1/sessions/{SESSION_ID}/feedback' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer {ACCESS_TOKEN}' \
--data '{
  "feedbackId": "9247bbd8-5ed9-11ee-8c99-0242ac120002",
  "feedback": "GOOD",
  "text": "Email looks great"
}'
```

To make this request, these values are required.

- `SESSION_ID`: The session ID found in the response payload when you created a session.
- `ACCESS_TOKEN`: The token that you created in [Create a Token](/docs/ai/agentforce/guide/agent-api-get-started.md#create-a-token).
- Specify `application/json` in the `Content-Type` header to indicate JSON content in the request.

If the feedback was received, you get an HTTP 201 response.

For API reference info, see [Submit Feedback](/docs/ai/agentforce/references/agent-api?meta=submitFeedback).

## See Also

- [Get Started with Agent API](/docs/ai/agentforce/guide/agent-api-get-started.md)
- [Send Agent Variables with the Agent API](/docs/ai/agentforce/guide/agent-api-variables.md)
- [Agent API Postman Collection](https://www.postman.com/salesforce-developers/salesforce-developers/collection/gwv9bjy/agent-api)
- [Send Agent Variables with the Agent API](/docs/ai/agentforce/guide/agent-api-variables.md)
- [Agent API Session Lifecycle](/docs/ai/agentforce/guide/agent-api-lifecycle.md)
- [Agent API Considerations](/docs/ai/agentforce/guide/agent-api-considerations.md)
- [Agent API Troubleshooting](/docs/ai/agentforce/guide/agent-api-troubleshooting.md)
- [Agent API Reference](/docs/ai/agentforce/references/agent-api?meta=summary)
- *Developer Relations YouTube Video*: [Integrate Agentforce with Microsoft Teams](https://www.youtube.com/watch?v=cbIOq_rQang)

# Agent API Considerations

Review these considerations before you use the Agent API.

## Supported Agent Types

The Agent API isn’t supported for agents of type “Agentforce (Default)”.

## Usage and Billing

Agent API usage impacts credit consumption as described in the following Salesforce help topic: [Generative AI Usage and Billing](https://help.salesforce.com/s/articleView?id=ai.generative_ai_usage.htm).

## API Timeout

The Agent API has a 120-second timeout. When a call times out, you receive an HTTP 500 response.

## Government Cloud

If your org is on Government Cloud, use `api.gov.salesforce.com` as the base endpoint for all Agent API requests instead of `api.salesforce.com`. The path and request format are otherwise identical to the standard endpoint. For example, to start a session, use `https://api.gov.salesforce.com/einstein/ai-agent/v1/agents/{AGENT_ID}/sessions`.

## See Also

- [Get Started with Agent API](/docs/ai/agentforce/guide/agent-api-get-started.md)
- [Agent API Examples](/docs/ai/agentforce/guide/agent-api-examples.md)
- [Agent API Troubleshooting](/docs/ai/agentforce/guide/agent-api-troubleshooting.md)
- [Agent API Reference](/docs/ai/agentforce/references/agent-api?meta=summary)
<!--stackedit_data:
eyJoaXN0b3J5IjpbOTczMzI2ODUyLDQ0ODE0OTEzMywtMTU1NT
A5MjUxMF19
-->