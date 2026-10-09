
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


# Create an Agent

Create intelligent, trusted, and customizable agents for your customers and employees.

![Note](https://sf-zdocs-cdn-prod.zoominsoftware.com/tdta-ai-generative_ai-264-0-0-production-enus/cf864731-c3bb-4e3b-b77c-8a56c30bc21f/images/icon_note.png)

Note Starting the week of July 13, 2026, you can no longer create agents in the legacy Agentforce Builder in Setup. Instead, create an agent in Agentforce Builder in Agentforce Studio. Or [upgrade an agent](https://help.salesforce.com/s/articleView?id=ai.agent_setup_create_upgrade.htm&language=en_US&type=5) from the legacy builder to the new builder.

For the latest features and enhancements, we recommend migrating existing agents from the legacy builder to the new builder. [Learn more.](https://help.salesforce.com/s/articleView?id=ai.agent_migrate_parent.htm&language=en_US&type=5)

You can create agents in multiple ways.

To start with an agent for a common business use case, create an agent from a template. A template includes relevant subagents and actions, as well as default system messages, variables, and filters. To create an agent from a template, you must have the permissions for the associated agent type, as well as any additional permissions required for the template.

For custom use cases, create an agent with the help of generative AI. Describe the job you want your agent to be able to do. Then Salesforce creates subagents based on your description and the actions available to your agent. To create an agent with gen AI, you must have the permissions for the associated agent type.

-   **[Create a Custom Agent with AI Assistance](https://help.salesforce.com/s/articleView?id=ai.copilot_create_gen_ai_agent.htm&language=en_US&type=5)**  
    Use AI assistance to create a custom Agentforce Service agent for your business.
-   **[Create an Agent from an Agentforce Service Agent Template](https://help.salesforce.com/s/articleView?id=ai.service_agent_setup.htm&language=en_US&type=5)**  
    Agentforce Service agents intelligently support your customers by connecting to messaging and other channels and escalating to reps when necessary. Use the default Agentforce Service Agent template to create an agent designed to resolve common support cases and requests. Or select from more specialized templates to fit your use case.
-   **[Create a Help Agent in Minutes with Quick Service Agent Configuration](https://help.salesforce.com/s/articleView?id=ai.service_agent_quick_configuration.htm&language=en_US&type=5)**  
    With just a few quick steps, build AI-powered service channels grounded in your knowledge base using Quick Service Agent Configuration. This process can build your help portal, Voice channel, and web chat channel, and build a Help Agent to resolve customer issues in those channels. Help agent is based on the Agentforce Service agent template. Use these channels to provide 24/7 support and deflect cases.
-   **[Create an Agent from an Agentforce Employee Agent Template](https://help.salesforce.com/s/articleView?id=ai.agent_employee_agent_setup.htm&language=en_US&type=5)**  
    Agentforce Employee agents help employees find information, complete tasks, and access personalized support across channels. Use Agentforce Employee agent templates to build agents that serve specific departmental needs, support role-based access, and scale securely across the organization. Unlike other agent templates, Employee agents are designed for internal employees, run in the logged-in user context, and you can assign each Employee agent to specific profiles or users.
-   **[Upgrade an Agent from the Legacy Builder to the New Builder](https://help.salesforce.com/s/articleView?id=ai.agent_setup_create_upgrade.htm&language=en_US&type=5)**  
    Create a new version of an agent from the legacy Agentforce Builder in Setup in the new Agentforce Builder in Agentforce Studio, with just a few clicks. The new version contains all of the original agent's subagents, actions, system messages and settings, data, and connections, converted to Agent Script. Upgrading an agent doesn't affect the original agent in the legacy builder. You can continue to access and edit the agent in the legacy builder.
-   **[Create the Agentforce (Default) Agent in the Legacy Builder](https://help.salesforce.com/s/articleView?id=ai.agent_setup_enable_default.htm&language=en_US&type=5)**  
    Help your employees accomplish key business tasks in Salesforce and Slack with the default AI assistant for Salesforce CRM.
-   **[Migrate from Agentforce (Default) to Agentforce Employee Agent](https://help.salesforce.com/s/articleView?id=ai.migrate_agentforce_default_to_aea.htm&language=en_US&type=5)**  
    Discover the key differences between Agentforce (Default) and Agentforce Employee agent, and learn how to seamlessly migrate your default agents. The migration flow creates a new Employee agent with the same subagents and actions, variables and settings as your default agent. You can fine-tune your Agentforce (Default) agent into multiple employee agent personas, each specializing in different use cases, with improved access control and channel integrations.

#### See Also

-   [Agent Types and Considerations](https://help.salesforce.com/s/articleView?id=ai.agent_setup_explore_types.htm&language=en_US&type=5)
-   [Configure Your Agent](https://help.salesforce.com/s/articleView?id=ai.agent_parent_configure.htm&language=en_US&type=5)

# Agent Types and Considerations

Learn about agent types and default templates for specific clouds and common use cases.

| Agent Type | What it Does | Required Editions | Required Permissions |
| --- | --- | --- | --- |
| Employee Agent | Assists employees by providing access to company knowledge, performing tasks, and streamlining workflows across departments.<br>Before getting started, review [Considerations for Agentforce Employee Agent](https://help.salesforce.com/s/articleView?id=ai.agent_employee_agent_considerations.htm&language=en_US&type=5). | Available in Enterprise, Performance, Unlimited, and Developer Editions with Foundations or Agentforce 1 Editions. Access to some standard agent actions requires [additional add-on licenses](https://www.salesforce.com/agentforce/pricing/).<br>Agentforce Employee agents require [Flex Credits](https://help.salesforce.com/s/articleView?id=ai.usage_flex_credits.htm&language=en_US&type=5). | To create and manage Agentforce Employee Agent: Manage AI Agents.<br>To use Agentforce Employee Agent, see [Manage Employee Agent Access](https://help.salesforce.com/s/articleView?id=ai.agent_manage_aea_access.htm&language=en_US&type=5). |
| Lead Nurturing (formerly known as SDR) | Intelligently engages leads with personalized content, answers common questions, and schedules meetings.<br>Before getting started, review [Considerations for Using Agentforce Lead Nurturing](https://help.salesforce.com/s/articleView?id=sales.sales_agent_sdr_considerations.htm&language=en_US&type=5).| Available in Enterprise, Performance, Unlimited, and Developer Editions with Foundations or Agentforce 1 Editions | See [SDR Agent Permission Sets](https://help.salesforce.com/s/articleView?id=sales.sales_agent_sdr_permissions.htm&language=en_US&type=5). |
| Sales Coach | Intelligently gives reps personalized, actionable, and stage-specific feedback on their sales pitch or role-play session.<br>Before getting started, review [Generative AI Considerations for Agentforce Sales Coach](https://help.salesforce.com/s/articleView?id=sales.sales_coach_agent_gen_ai_considerations.htm&language=en_US&type=5). | Available in Enterprise, Performance, Unlimited, and Developer Editions with Foundations or Agentforce 1 Editions | See [Agentforce Sales Coach Permissions](https://help.salesforce.com/s/articleView?id=sales.sales_agents_coach_permissions.htm&language=en_US&type=5). |
| Service Agent | Intelligently supports your customers with common inquiries and escalates complex issues.<br>Before getting started, review [Considerations for Agentforce Service Agent](https://help.salesforce.com/s/articleView?id=ai.service_agent_considerations.htm&language=en_US&type=5).| Available in Enterprise, Performance, Unlimited, and Developer Editions with Foundations or Agentforce 1 Editions. Access to some standard agent actions requires [additional add-on licenses](https://www.salesforce.com/agentforce/pricing/). | To create and manage Agentforce Service agents: Manage Agentforce Service Agents permission set<br>![Note](https://sf-zdocs-cdn-prod.zoominsoftware.com/tdta-ai-generative_ai-264-0-0-production-enus/cf864731-c3bb-4e3b-b77c-8a56c30bc21f/images/icon_note.png)Note This permission set contains the Manage AI Agents permission, which is required to access Agentforce Builder. Manage AI Agents grants org-wide management access to all agents, not just the agent type or template named in the permission set. Users with this permission can manage, activate, and deactivate agents, customize subagents and actions, and monitor agent activity. Assign this permission set only to users who require org-wide agent management access.<br>To let the agent user securely access data and perform actions, see [Configure Service Agent Access](https://help.salesforce.com/s/articleView?id=ai.agent_user.htm&language=en_US&type=5).|
| Service Assistant | Intelligently helps your service reps resolve cases faster with case summaries and step-by-step resolution guidance.<br>Before getting started, review [Considerations for Service Assistant](https://help.salesforce.com/s/articleView?id=service.sp_considerations.htm&language=en_US&type=5).| Available in Enterprise, Performance, and Unlimited Editions with Foundations and the Agentforce for Service add-on or Agentforce 1 Service Edition | See [Permissions and Licensing for Service Assistant](https://help.salesforce.com/s/articleView?id=service.sp_permissions.htm&language=en_US&type=5). |
| Setup with Agentforce | Helps your Salesforce admins complete Setup tasks, such as managing users, troubleshooting issues, and customizing your org. <br>The Setup agent is created automatically when you enable Setup with Agentforce and isn’t visible or able to be customized in Agentforce Builder.<br>Before getting started, review [Considerations for Setup with Agentforce](https://help.salesforce.com/s/articleView?id=xcloud.setup_agentforce_considerations.htm&language=en_US&type=5).| Available in: Enterprise, Performance, Unlimited, and Developer Editions with Foundations or Agentforce 1 Editions | To enable or use Setup with Agentforce: [See Grant Permissions to Use Setup with Agentforce](https://help.salesforce.com/s/articleView?id=xcloud.setup_agentforce_permissions.htm&language=en_US&type=5) |
| Agentforce (Default) - (Retired) | Helps your employees accomplish key business tasks in Salesforce.<br>Before getting started, review [Agentforce (Default) Considerations](https://help.salesforce.com/s/articleView?id=ai.agent_default_considerations.htm&language=en_US&type=5).|![Important](https://sf-zdocs-cdn-prod.zoominsoftware.com/tdta-ai-generative_ai-264-0-0-production-enus/cf864731-c3bb-4e3b-b77c-8a56c30bc21f/images/icon_important.png)Important Starting June 17, 2025, Agentforce (Default) will not include new features or improvements and isn’t available in new Salesforce environments. We recommend migrating to Agentforce Employee agent for continued enhancements and support. If you plan to transition to Agentforce Employee agent or make related license changes, complete the migration of your existing Agentforce (Default) agents in advance to avoid potential disruption in agent availability. If you can't complete the migration in advance, you can create new agents after the transition, which can involve some downtime. See [Migrate from Agentforce (Default) to Agentforce Employee Agent](https://help.salesforce.com/s/articleView?id=ai.migrate_agentforce_default_to_aea.htm&language=en_US&type=5).| To create and manage Agentforce (Default): Manage AI Agents AND Manage Agentforce Default Agent OR Customize Application. <br>To use Agentforce (Default), see [Give Users Access to Agentforce (Default)](https://help.salesforce.com/s/articleView?id=ai.copilot_setup_user_access.htm&language=en_US&type=5). |
| Agent for Setup - (Retired) |![Note](https://sf-zdocs-cdn-prod.zoominsoftware.com/tdta-ai-generative_ai-264-0-0-production-enus/cf864731-c3bb-4e3b-b77c-8a56c30bc21f/images/icon_note.png)Note Agent for Setup is no longer being updated and can’t be enabled in new orgs beginning April 2026. We recommend that you use Setup with Agentforce instead, which can help with many more administrative tasks and is automatically updated with new functionality.<br>Helps your org admins with every day administration tasks, looks for answers in Salesforce Help, and more.<br>Before getting started, review [Agent for Setup Considerations](https://resources.docs.salesforce.com/rel1/doc/en-us/static/pdf/setup_agent_original.pdf).| Available in Enterprise, Performance, Unlimited, and Developer Editions with Foundations or Agentforce 1 Editions | To create and manage Agent for Setup: Customize Application OR Agentforce Default Admin permission set AND View Setup and Configuration. <br>To use Agent for Setup: Access Agentforce Default Agent permission set AND View Setup and Configuration|

![Note](https://sf-zdocs-cdn-prod.zoominsoftware.com/tdta-ai-generative_ai-264-0-0-production-enus/cf864731-c3bb-4e3b-b77c-8a56c30bc21f/images/icon_note.png)

Note Users with the Manage AI Agents permission can manage, activate, and deactivate agents, customize subagents and actions, and monitor agent activity. Assign this permission only to users who require org-wide management access to all agents.

-   **[Considerations for Agentforce Service Agent](https://help.salesforce.com/s/articleView?id=ai.service_agent_considerations.htm&language=en_US&type=5)**  
    To use Agentforce Service Agent, consider supported functionality, usage, limitations and allowances, limits, and other issues.
-   **[Considerations for Agentforce Employee Agent](https://help.salesforce.com/s/articleView?id=ai.agent_employee_agent_considerations.htm&language=en_US&type=5)**  
    Before setting up an Agentforce Employee agent, keep these considerations in mind.
-   **[Agentforce (Default) Considerations](https://help.salesforce.com/s/articleView?id=ai.agent_default_considerations.htm&language=en_US&type=5)**  
    To use Agentforce (Default), consider supported functionality, usage, limits and allowances, and more.

#### See Also

-   [Agentforce Considerations](https://help.salesforce.com/s/articleView?id=ai.copilot_considerations.htm&language=en_US&type=5)
-   [Agent Execution Context and Data Access by Type](https://help.salesforce.com/s/articleView?id=ai.agent_execution_data.htm&language=en_US&type=5)


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

# Agent API Troubleshooting

Review these troubleshooting tips if you run into issues when calling the API.

## HTTP 400 Response: Bad Request

If you receive an HTTP 400 response, there's a problem with your request.

- **Message field in response contains "{VALUE} is not a valid agent ID"**. Verify that your agent ID is correct in your API request. See [Call the API](/docs/ai/agentforce/guide/agent-api-get-started.md#call-the-api).

## HTTP 401 Response: Unauthorized

If you recieve an HTTP 401 response, there's typically an authorization issue. Review [Get Started with Agent API](/docs/ai/agentforce/guide/agent-api-get-started.md).

## HTTP 404 Response: Not Found

If you receive an HTTP 404 response, verify that you're using the correct token and that you're using the correct endpoint. Review [Get Started with Agent API](/docs/ai/agentforce/guide/agent-api-get-started.md).
If your org is on Government Cloud, make sure you're calling `api.gov.salesforce.com` instead of `api.salesforce.com`.

## HTTP 423 Response: Session Already Locked Exception

If you receive an HTTP 423 response, verify that you don't have any requests in progress as the API only supports one request at a time. Review [Get Started with Agent API](/docs/ai/agentforce/guide/agent-api-get-started.md).

## HTTP 500 Response: Internal Server Error

If you receive an HTTP 500 response, verify that you've followed the setup instructions correctly.

- **Message field in response contains "Unsupported Media Type"**. Use the correct `Content-Type` value in the header: `Content-Type: application/json`.
- **Error field in response contains "EngineConfigLookupException"**. When specifying your domain in the [start session endpoint](/docs/ai/agentforce/guide/agent-api-examples.md#start-session), make sure that you're using the My Domain endpoint for your org. From Setup, search for **My Domain**. Copy the value shown in the **Current My Domain URL** field.
- **Error field in response contains "HttpServerErrorException"**. Verify that you are using the correct agent ID in the endpoint. See [Get the Agent ID for an Agent](/docs/ai/agentforce/guide/agent-api-agent-id.md) for instructions on obtaining your agent ID.
- For other issues, review [Get Started with Agent API](/docs/ai/agentforce/guide/agent-api-get-started.md).

## See Also

- [Get Started with Agent API](/docs/ai/agentforce/guide/agent-api-get-started.md)
- [Agent API Examples](/docs/ai/agentforce/guide/agent-api-examples.md)
- [Agent API Considerations](/docs/ai/agentforce/guide/agent-api-considerations.md)
- [Agent API Reference](/docs/ai/agentforce/references/agent-api?meta=summary)

# Create an Agent from an Agentforce Service Agent Template

Agentforce Service agents intelligently support your customers by connecting to messaging and other channels and escalating to reps when necessary. Use the default Agentforce Service Agent template to create an agent designed to resolve common support cases and requests. Or select from more specialized templates to fit your use case.

| User Permissions Needed |   |
| --- | --- |
| To build and manage Service Agents: | Manage Agentforce Service Agents AND Manage AI Agents OR Customize Application |

-   **[Configure Service Agent Access](https://help.salesforce.com/s/articleView?id=ai.agent_user.htm&language=en_US&type=5)**  
    Learn how Agentforce Service agents control data access. Set up an agent user for your Agentforce Service agent and assign permissions, so your agent has everything it needs to do its job.
-   **[Configure Service Agent Managers](https://help.salesforce.com/s/articleView?id=ai.service_agent_managers.htm&language=en_US&type=5)**  
    When Service agents are enabled for your Salesforce org, Salesforce admins can create and edit service agents. To define other users as Service agent managers so that they can also create and edit service agents, assign those users the Manage Agentforce Service Agents permission set.

#### See Also

-   [_Trailhead_: Quick Start: Build a Service Agent with Agentforce](https://trailhead.salesforce.com/content/learn/projects/quick-start-build-your-first-agent-with-agentforce)
-   [_Agentforce Workshop_: Get Hands On with Service Agents](https://developer.salesforce.com/agentforce-workshop/service-agents/overview)

## Create an Agent from a Service Agent Template

Before you begin, [set up Einstein Generative AI](https://help.salesforce.com/s/articleView?id=ai.generative_ai_enable.htm&language=en_US&type=5) and [enable Agentforce](https://help.salesforce.com/s/articleView?id=ai.agent_setup_enable.htm&language=en_US&type=5).

1.  From the App Launcher, enter `Agent`, and then select **Agentforce Studio**.
2.  On the Agents tab, click **New Agent**.
3.  Select an Agentforce Service agent template. Under Agent Details, select or create an **Agent's User Record** for this agent. To securely access data and perform actions, Service agents operate as an agent user, or a Salesforce integration user with all the permissions that the agent needs to do its job. See [Best Practices for Agent User Permissions](https://help.salesforce.com/s/articleView?id=ai.agent_user.htm&language=en_US&type=5).
4.  Enter the agent's name and then click **Let's Go**.
5.  In the Settings section, define the settings that determine how your agent behaves in conversations, such as [system messages](https://help.salesforce.com/s/articleView?id=ai.copilot_setup_system_messages.htm&language=en_US&type=5) and [language settings](https://help.salesforce.com/s/articleView?id=ai.copilot_setup_tone.htm&language=en_US&type=5).
6.  In the Subagents section, manage and customize your agent's [subagents](https://help.salesforce.com/s/articleView?id=ai.agent_topics_manage.htm&language=en_US&type=5) and [actions](https://help.salesforce.com/s/articleView?id=ai.agent_actions_custom.htm&language=en_US&type=5).
7.  In the Data section, select a data library. The Answer Questions with Knowledge action grounds your agent's responses with it. To create or manage data libraries, see [Setting Up Data Libraries](https://help.salesforce.com/s/articleView?id=ai.data_library_setup.htm&language=en_US&type=5).
8.  Click Preview to test out your agent and confirm that it performs as expected and meets your security standards. You can simulate your agent’s behavior with mock data without risking any changes to your actual data or org. Use trace to dig into the steps the agent performed, and ask Agentforce to help you understand your agent’s behavior at any step. See [Preview and Test in Agentforce Builder](https://help.salesforce.com/s/articleView?id=ai.agent_preview_and_test.htm&language=en_US&type=5) for more details.
9.  Connect your agent to service channels to transfer agent conversations. See [Connect an Agent to Messaging](https://help.salesforce.com/s/articleView?id=ai.agent_parent_deploy_messaging.htm&language=en_US&type=5) for more information on deploying your agent to a Messaging channel.
10.  When you’re ready to use your agent outside of the builder, click Commit Version. You must commit an agent version before you can activate it. Committed versions can’t be edited. To continue making changes after committing, create a new version by clicking New Version. See [Versioning and Editing Agents](https://help.salesforce.com/s/articleView?id=ai.agent_versions_lifecycle.htm&language=en_US&type=5) for more information.
11.  When you're ready, [activate your agent](https://help.salesforce.com/s/articleView?id=ai.copilot_setup_activate_deactivate.htm&language=en_US&type=5).

## Create an Agent from a Service Agent Template in the Legacy Agentforce Builder

![Note](https://sf-zdocs-cdn-prod.zoominsoftware.com/tdta-ai-generative_ai-264-0-0-production-enus/8f79e91a-cacc-4a50-9604-d1286798b180/images/icon_note.png)
Note Starting the week of July 13, 2026, you can no longer create agents in the legacy Agentforce Builder in Setup. Instead, create an agent in Agentforce Builder in Agentforce Studio. Or [upgrade an agent](https://help.salesforce.com/s/articleView?id=ai.agent_setup_create_upgrade.htm&language=en_US&type=5) from the legacy builder to the new builder.For the latest features and enhancements, we recommend migrating existing agents from the legacy builder to the new builder. [Learn more.](https://help.salesforce.com/s/articleView?id=ai.agent_migrate_parent.htm&language=en_US&type=5)

1.  From Setup, in the Quick Find box, enter Agent, and then select **Agentforce Agents**.
2.  Click **New Agent**.
3.  Select **Create from a Template**. Select the template that you want to use to create an agent, and then click **Next**.
4.  Review the subagents that come with your template. You can customize these subagents and actions later, but if any of them don’t apply to your use cases, remove them. Then click **Next**.
5.  Give your agent a unique name, API name, description, role, and company.
    
    The description field is used by you and others in your org to identify your agent. The role and company fields are used by your agent to help it understand its responsibilities and the company that it represents.
    
6.  Under Agent User, select **New Agent User**. Then click **Next**.
    
    To securely access data and perform actions, Service agents operate as an agent user—a Salesforce integration user with all the permissions that the agent needs to do its job. Creating a new agent user in the guided setup creates an agent user record with minimal access so that your agent is secure by default. Grant the agent the additional access that it needs. See [Best Practices for Agent User Permissions](https://help.salesforce.com/s/articleView?id=ai.agent_user.htm&language=en_US&type=5).
    
7.  Select **Keep a record of conversations with enhanced event logs to review agent behavior**. See [Enable Enhanced Event Logs](https://help.salesforce.com/s/articleView?id=ai.copilot_setup_enhanced_event_logs.htm&language=en_US&type=5).
8.  Select a data source to ground your agent responses with the Answer Questions with Knowledge action. To continue without selecting any data sources, leave this field blank. You can add and remove data sources later. Then click **Create**.
    
    If you don't want to use any of the available data sources, you can create a library to limit Agentforce Service agents to specific articles or uploaded files. See [Use the Answer Questions with Knowledge Action](https://help.salesforce.com/s/articleView?id=ai.agent_setup_data_sources.htm&language=en_US&type=5).
    
9.  From the Settings page, define your agent's settings, such as [system messages](https://help.salesforce.com/s/articleView?id=ai.copilot_setup_system_messages.htm&language=en_US&type=5) and [language settings](https://help.salesforce.com/s/articleView?id=ai.copilot_setup_tone.htm&language=en_US&type=5). These settings determine how agents behave and present themselves in conversations.
10.  Back in the builder, [configure your agent with subagents, actions, and other agent assets.](https://help.salesforce.com/s/articleView?id=ai.agent_parent_configure.htm&language=en_US&type=5)
11.  Test your agent in Agentforce Builder to confirm that your agent performs as expected and [meets your security standards](https://help.salesforce.com/s/articleView?id=ai.service_agent_secure_actions.htm&language=en_US&type=5).
     
     The service agent operates in the same Agent User context here as it does when deployed in messaging channels, so design-time testing reflects how your service agent behaves when deployed.
     
12.  [Connect your service agent to channels](https://help.salesforce.com/s/articleView?id=ai.agent_parent_deploy.htm&language=en_US&type=5) and [configure the escalation subagent](https://help.salesforce.com/s/articleView?id=ai.service_agent_escalation.htm&language=en_US&type=5) to transfer agent conversations.
13.  When you're ready, [activate your agent](https://help.salesforce.com/s/articleView?id=ai.copilot_setup_activate_deactivate.htm&language=en_US&type=5).


# Create an Agent from an Agentforce Employee Agent Template

Agentforce Employee agents help employees find information, complete tasks, and access personalized support across channels. Use Agentforce Employee agent templates to build agents that serve specific departmental needs, support role-based access, and scale securely across the organization. Unlike other agent templates, Employee agents are designed for internal employees, run in the logged-in user context, and you can assign each Employee agent to specific profiles or users.


| User Permissions Needed |   |
| --- | --- |
| To build and manage Employee agents: | 
Manage AI Agents

OR

Customize Application

 |

Before you begin, [set up Einstein Generative AI](https://help.salesforce.com/s/articleView?id=ai.generative_ai_enable.htm&language=en_US&type=5) and [enable Agentforce](https://help.salesforce.com/s/articleView?id=ai.agent_setup_enable.htm&language=en_US&type=5).

-   **[Manage Employee Agent Access](https://help.salesforce.com/s/articleView?id=ai.agent_manage_aea_access.htm&language=en_US&type=5)**  
    Control user access to specific Agentforce Employee agents with permission sets or profiles. In Agentforce Builder, use the Agent Access page. In the legacy Agentforce Builder, use the Agent Access tab.

#### See Also

-   [_Trailhead_: Quick Start: Create Employee Agents in Agentforce](https://trailhead.salesforce.com/content/learn/projects/quick-start-create-employee-agents-in-agentforce)
-   [_Agentforce Workshop_: Get Hands On with Employee Agents](https://developer.salesforce.com/agentforce-workshop/employee-agents/overview)

## Create an Agent from an Employee Agent Template

1.  From the App Launcher, enter Agent, and then select the **Agentforce Studio** app.
2.  On the Agents tab, click **New Agent**.
3.  Select an Agentforce Employee agent template. Enter the agent's name and then click **Let's Go**.
4.  In the Settings section, define the settings that determine how your agent behaves in conversations, such as [system messages](https://help.salesforce.com/s/articleView?id=ai.copilot_setup_system_messages.htm&language=en_US&type=5) and [language settings](https://help.salesforce.com/s/articleView?id=ai.copilot_setup_tone.htm&language=en_US&type=5).
5.  In the Subagents section, manage and customize your agent's [subagents](https://help.salesforce.com/s/articleView?id=ai.agent_topics_manage.htm&language=en_US&type=5) and [actions](https://help.salesforce.com/s/articleView?id=ai.agent_actions_custom.htm&language=en_US&type=5).
6.  In the Data section, select a data library. The Answer Questions with Knowledge action grounds your agent's responses with it. To create or manage data libraries, see [Setting Up Data Libraries](https://help.salesforce.com/s/articleView?id=ai.data_library_setup.htm&language=en_US&type=5).
7.  Test your agent and confirm that it performs as expected and meets your security standards on the **Preview** tab. For more details about testing, see [Preview and Test in Agentforce Builder](https://help.salesforce.com/s/articleView?id=ai.agent_preview_and_test.htm&language=en_US&type=5).

To give your users access to your agent in Lightning Experience and mobile, see [Manage Employee Agent Access in Agentforce Builder](https://help.salesforce.com/s/articleView?id=ai.agent_manage_aea_access.htm&language=en_US&type=5#agent_access_setup).

You can also connect your agent to [Enhanced Web Chat v1](https://help.salesforce.com/s/articleView?id=ai.agent_deploy_enhanced_chat_v1.htm&language=en_US&type=5#connect_aea_v1), [Enhanced Chat v2](https://help.salesforce.com/s/articleView?id=ai.service_agent_deploy_enhanced_chat_v2.htm&language=en_US&type=5), or [Slack](https://slack.com/help/articles/36218109305875-Set-up-and-manage-Agentforce-in-Slack).

When you're ready, [activate your agent](https://help.salesforce.com/s/articleView?id=ai.copilot_setup_activate_deactivate.htm&language=en_US&type=5).

## Create an Agent from an Employee Agent Template in the Legacy Agentforce Builder

Note Starting the week of July 13, 2026, you can no longer create agents in the legacy Agentforce Builder in Setup. Instead, create an agent in Agentforce Builder in Agentforce Studio. Or [upgrade an agent](https://help.salesforce.com/s/articleView?id=ai.agent_setup_create_upgrade.htm&language=en_US&type=5) from the legacy builder to the new builder.

For the latest features and enhancements, we recommend migrating existing agents from the legacy builder to the new builder. [Learn more.](https://help.salesforce.com/s/articleView?id=ai.agent_migrate_parent.htm&language=en_US&type=5)

1.  From Setup, in the Quick Find box, enter Agent, and select **Agentforce Agents**.
2.  Click **New Agent**.
3.  Select **Create from a Template**, select the template that you want to use, and then click **Next**.
4.  Review the agent's subagents and actions that come with your template. You can customize these subagents and actions later, but if any of them don’t apply to your use cases, remove them, and then click **Next**.
5.  Define your agent's settings, such as [system messages](https://help.salesforce.com/s/articleView?id=ai.copilot_setup_system_messages.htm&language=en_US&type=5) and [language settings](https://help.salesforce.com/s/articleView?id=ai.copilot_setup_tone.htm&language=en_US&type=5). These settings determine how agents behave and present themselves in conversations.
6.  Select a data source to ground your agent's responses with the Answer Questions with Knowledge action, and then click **Create**. For more information about data libraries, see [Agentforce Data Library](https://help.salesforce.com/s/articleView?id=ai.data_library_parent.htm&language=en_US&type=5)
7.  [Configure your agent with subagents, actions, and other agent assets.](https://help.salesforce.com/s/articleView?id=ai.agent_parent_configure.htm&language=en_US&type=5)
8.  Test your agent in Agentforce Builder to confirm that your agent performs as expected and [meets your security standards](https://help.salesforce.com/s/articleView?id=ai.service_agent_secure_actions.htm&language=en_US&type=5).

To give your users access to your agent in Lightning Experience and mobile, see [Manage Employee Agent Access in the Legacy Agentforce Builder](https://help.salesforce.com/s/articleView?id=ai.agent_manage_aea_access.htm&language=en_US&type=5#agent_access_legacy_setup).

Optionally, connect your agent to [Enhanced Chat v1](https://help.salesforce.com/s/articleView?id=ai.agent_deploy_enhanced_chat_v1.htm&language=en_US&type=5#connect_aea_v1) or [Slack](https://slack.com/help/articles/36218109305875-Set-up-and-manage-Agentforce-in-Slack).

When you're ready, [activate your agent](https://help.salesforce.com/s/articleView?id=ai.copilot_setup_activate_deactivate.htm&language=en_US&type=5).


# Subagents

A subagent is a particular job an agent can do. Collectively, the subagents assigned to your agent define the capabilities your agent can handle. Learn about subagents in Agentforce Builder and the legacy builder.

-   **[Subagents](https://help.salesforce.com/s/articleView?id=ai.agent_topics.htm&language=en_US&type=5)**  
    A subagent is a job an agent can do. Learn about the parts of a subagent and how to use them to define an agent’s logic, reasoning, and conversational capabilities.
-   **[Subagents in the Legacy Builder](https://help.salesforce.com/s/articleView?id=ai.copilot_topics.htm&language=en_US&type=5)**  
    A subagent is a particular job an agent can do and an essential element of an agent’s reasoning. A subagent contains actions, which are the tools available for the job, and instructions, which tell the agent how to make decisions. Collectively, the subagents assigned to your agent define the capabilities your agent can handle. Salesforce provides a library of standard subagents for common use cases, and you can create custom subagents to meet your users’ specific business needs.


# Agent Actions

Actions are how agents get things done. Agents include a library of actions, which are the tools an agent can use to do its job. For example, if a user asks an agent for help with writing an email, the agent first selects a subagent, then it launches an action that drafts and revises the email and grounds it in relevant Salesforce data.

-   **[Common User Access for Standard Agent Actions](https://help.salesforce.com/s/articleView?id=ai.agent_actions_common_perms.htm&language=en_US&type=5)**  
    Learn about the permissions required for users to run many standard agent actions.
-   **[Add an Action to a Subagent from the Asset Library](https://help.salesforce.com/s/articleView?id=ai.agent_actions_add_asset_library.htm&language=en_US&type=5)**  
    Add standard actions to your agent to start handling common business use cases quickly, or create custom actions tailored to your business needs. When you add these actions to an agent, the agent gets its own, independent copy. Changes to template actions within the asset library aren't automatically synced to subagents and actions within your agent. Changes made to one agent's actions don't affect another agent's subagents or actions.
-   **[Verify Customers with Standard Subagents in Agentforce Builder](https://help.salesforce.com/s/articleView?id=ai.service_agent_customer_verification.htm&language=en_US&type=5)**  
    To verify the identity of an unverified user in an agent session, configure your agent to use the Customer Verification subagent or the Service Customer Verification subagent and limit access to subagents and actions that you specify. You can require different levels of verification for different subagents and actions, based on your business’s security requirements.
-   **[Edit the Loading Text for an Agent Action](https://help.salesforce.com/s/articleView?id=ai.agent_actions_loading_text.htm&language=en_US&type=5)**  
    Loading text tells the user what an agent is doing while an action runs in the background. For editable actions, both standard and custom, you can specify the loading text and tailor it for each action individually.
-   **[Agent Actions in the Legacy Builder](https://help.salesforce.com/s/articleView?id=ai.copilot_actions_legacy.htm&language=en_US&type=5)**  
    Create and manage actions in the legacy Agentforce Builder.
-   **[Editing Standard Agent Action Reference Actions](https://help.salesforce.com/s/articleView?id=ai.copilot_actions_edit_reference.htm&language=en_US&type=5)**  
    Customize the behavior of some standard agent actions by editing the underlying flow or prompt template.
-   **[Explore Standard Agent Actions](https://help.salesforce.com/s/articleView?id=ai.agent_actions_ref_pointer.htm&language=en_US&type=5)**  
    Learn all about the agent actions Salesforce provides out of the box in our comprehensive reference library.

### See Also

-   [The Building Blocks of Agents](https://help.salesforce.com/s/articleView?id=ai.copilot_building_blocks.htm&language=en_US&type=5)
-   [Trust and Agentforce](https://help.salesforce.com/s/articleView?id=ai.copilot_trust.htm&language=en_US&type=5)
-   [Standard Agent Action Reference](https://help.salesforce.com/s/articleView?id=ai.copilot_actions_ref.htm&language=en_US&type=5)


# Deploy Your Agent to Channels

Connect your agent to multiple channels. Meet your customers and employees where they spend the most time.

Review key concepts for deploying agents to channels.

Connections and Adaptive Response Formats

A connection includes adaptive response formats that help your agent structure responses and deliver multimedia content, such as images, buttons, links, and videos. It also includes settings and Omni-Channel flows that help route conversations to and from an agent.

Connections help you scale agent development and reduce repetitive setup by letting you build an agent once and easily add it to multiple channels in Agentforce Builder. They also help the agent make customer and employee experiences more dynamic, channel-specific, and consistent. One way to think of connections is to consider how people act in different settings. People adapt their communication methods to align with each setting’s unique rules, etiquettes, and constraints. For example, you use text and a casual tone in Slack, but use audio and a formal tone on phone calls. Each agent template supports specific connections, and you can connect the agent to the channels associated with those connections.

When a user interacts with your agent on a connected channel, your agent identifies the connection associated with the experience. The agent adapts its reasoning based on the behind-the-scenes instructions associated with the connection, classifies the user’s utterance into the most relevant subagent, and launches one or more actions. Before sending a response, the agent determines which adaptive response format to structure it with, if any. To select an adaptive response format, the agent considers the formats available, the action's output, and the accompanying agent message. It takes the adaptive response formats available with the connection and the action output with its accompanying message into account.

For example, let's say that a customer sends a message to an Agenforce Service agent (ASA) on an enhanced Facebook Messenger channel. The ASA has the Messaging connection, which is associated with all enhanced Messaging channels and includes adaptive response formats that map to messaging components. The Messaging connection sends instructions to the reasoning engine that help the ASA reason and respond on an enhanced Facebook Messenger channel. The agent classifies the user’s utterance to a subagent and launches an action. Then it structures the response with the Rich Link Response adaptive response format and sends the response on Facebook Messenger.

To learn more, see [Set Up Connections in the Legacy Builder](https://help.salesforce.com/s/articleView?id=ai.agent_response_enable.htm&language=en_US&type=5).

Channels

Channels are the messaging platforms, apps, and interfaces that you can deploy an agent to. Channels include the Agentforce panel in Lightning Experience, the Salesforce mobile app, Slack, messaging platforms, and email. Channel support varies by agent type. Some agent types and templates are available for your workforce, and you can add others to your customer-facing channels.

Omni-Channel Flows

Omni-Channel flows make it easy to route agent conversations. These flows use the Route Work action to route conversations and their associated records, such as messaging session and email records. Agents that connect to messaging or email have at least one inbound and outbound Omni-Channel flow.

When a customer interacts with an agent on a channel, a record associated with the conversation is created. Then, an inbound Omni-Channel flow routes the record from the customer channel to an agent. For example, when a customer sends a message on WhatsApp, an inbound Omni-Channel flow routes the conversation from WhatsApp to an Agentforce Service agent. You can connect your agent to multiple inbound flows, but each inbound flow can be connected to one agent only.

Agents use an outbound Omni-Channel flow to route conversations to another destination, such as a service rep, queue, or different agent. You can customize an outbound Omni-Channel flow to meet your business needs. For example, if you have multiple destinations that each excel at a different use case, you can add a Decision element to the flow that routes the conversation to the most relevant destination. You can connect your agent to multiple outbound flows, and each outbound flow can be connected to multiple destinations.

To learn more about Omni-Channel flows, see [Route Work with Omni-Channel](https://help.salesforce.com/s/articleView?id=service.omnichannel_route_work.htm&language=en_US&type=5).

Escalation

When a customer or employee wants to chat with a person or the conversation becomes complex or sensitive, the agent launches the Escalation subagent. For some channels, the subagent transfers the conversation to another destination using the agent’s outbound Omni-Channel flow. The conversation history, including messages and information gathered, is also transferred to the next destination. You can customize the Escalation subagent by adding specific instructions and agent actions. For example, you can customize the Esclation subagent to create a case when transferring the conversation is unsuccessful or isn't supported for your channel. You can also customize the message the agent sends before it transfers a conversation.

To learn more about the Escalation subagent, see [Transfer Conversations from an Agent with an Omni-Channel Flow](https://help.salesforce.com/s/articleView?id=ai.service_agent_escalation.htm&language=en_US&type=5).

-   **[Explore Standard Connections and Adaptive Responses Formats](https://help.salesforce.com/s/articleView?id=ai.agent_surfaces_ref_pointer.htm&language=en_US&type=5)**  
    Learn about the agent connections and adaptive response formats that Salesforce provides out of the box in our comprehensive reference library.
-   **[Set Up Connections in Agentforce Builder](https://help.salesforce.com/s/articleView?id=ai.agent_connections_set_up.htm&language=en_US&type=5)**  
    To get started with deploying your agent to channels, add connections to it. Each connection includes behind-the-scenes instructions that help an agent reason and respond for one or more channels. Each connection contains adaptive response formats that help your agent structure responses and deliver multimedia content, such as images, buttons, links, and videos. You can find adaptive response formats and other settings, including the Omni-Channel flows that route conversations to and from an agent, in your connection settings.
-   **[Set Up Connections in the Legacy Builder](https://help.salesforce.com/s/articleView?id=ai.agent_response_enable.htm&language=en_US&type=5)**  
    To get started with deploying your agent to channels, set up connections. Each connection includes behind-the-scenes instructions that help an agent reason and respond for one or more channels. Each connection contains adaptive response formats that help your agent structure responses and deliver multimedia content, such as images, buttons, links, and videos. You can find adaptive response formats and other settings, including the Omni-Channel flows that route conversations to and from an agent, in your connection settings.
-   **[Connect an Agent to Lightning Experience and Mobile](https://help.salesforce.com/s/articleView?id=ai.agent_deploy_emp_lex.htm&language=en_US&type=5)**  
    Deploying Agentforce Employee agents to Lightning Experience and the Salesforce mobile app is as easy as activating your agent.
-   **[Connect an Agent to Slack](https://help.salesforce.com/s/articleView?id=ai.agent_deploy_emp_slack.htm&language=en_US&type=5)**  
    Collaborate with Agentforce Employee agents in the same place where your team collaborates. Add the Slack connection to your agent and then finish setting up the agent in Slack.
-   **[Connect an Agent to Messaging](https://help.salesforce.com/s/articleView?id=ai.agent_parent_deploy_messaging.htm&language=en_US&type=5)**  
    Route conversations to your Agentforce Service agents and Agentforce Employee agents with messaging channels, including Enhanced Chat and other enhanced messaging channels. Learn how to use context variables, multiple languages, and progess indicators in messaging channels.
-   **[Connect an Agent to Service Email](https://help.salesforce.com/s/articleView?id=ai.agent_email_parent.htm&language=en_US&type=5)**  
    Agentforce Service agents can autonomously respond to customer email inquiries. For example, if a customer emails you asking when their package will arrive, your agent can respond to them with the estimated delivery date and tracking number. Email responses are grounded in your Agentforce Data Libraries.
-   **[Choose Your Telephony Provider for Voice-Enabled Agents](https://help.salesforce.com/s/articleView?id=ai.agentforce_voice_telephony_overview.htm&language=en_US&type=5)**  
    Route voice conversations to your voice-enabled Agentforce Service agents. Voice-enabled agents use Agentforce Voice features to provide the autonomous AI layer for your contact center. Agentforce Voice replaces static, hierarchical IVR logic with dynamic, intent-driven conversations.
-   **[Connect a Service Agent to Partner Telephony](https://help.salesforce.com/s/articleView?id=ai.agent_connect_telephony_parent.htm&language=en_US&type=5)**  
    Route voice conversations to your Agentforce Service agents. Learn how to create a telephony connection to your partner telephony system, configure voice mode settings, and route calls to your agent.
-   **[Transfer Conversations from an Agent with an Omni-Channel Flow](https://help.salesforce.com/s/articleView?id=ai.service_agent_escalation.htm&language=en_US&type=5)**  
    When an agent encounters conversations that it can’t resolve, it uses the Escalation subagent to escalate the conversation. In the new Agentforce Builder, you can also run the Escalation subagent using the escalate utility function in Agent Script. Escalation and transferring works differently depending on the agent type and channel. You can customize the experience that customers receive when transferring isn’t possible.
-   **[Activate or Deactivate Your Agent](https://help.salesforce.com/s/articleView?id=ai.copilot_setup_activate_deactivate.htm&language=en_US&type=5)**  
    Activate your agent to make it available to your customers or employees. When an agent is deployed to one or more channels, including the Agentforce panel, activating the agent makes it immediately available to your users.

# Connect a Service Agent to Partner Telephony

Route voice conversations to your Agentforce Service agents. Learn how to create a telephony connection to your partner telephony system, configure voice mode settings, and route calls to your agent.

[Watch this video for a demonstration of how to route voice conversations to an Agentforce Service agent.](https://play.vidyard.com/7UjuTize5zUoSPooDJyN2V)

This flow chart summarizes the setup steps.![Flow chart that shows the Agentforce Voice setup steps](https://sf-zdocs-cdn-prod.zoominsoftware.com/tdta-ai-generative_ai-264-0-0-production-enus/cf864731-c3bb-4e3b-b77c-8a56c30bc21f/generative_ai/images/agentforce_voice_setup_flowchart.png)


## Roles of Agentforce Voice and Salesforce Voice with Telephony Providers

Agentforce Voice is the conversational AI capability built into Agentforce. Agentforce Voice processes voice interactions, understanding the customer intent and generating spoken responses.

[Salesforce Voice with Telephony Providers](https://help.salesforce.com/s/articleView?id=service.voice_about.htm&language=en_US&type=5) integrates third-party telephony systems, such as Amazon Connect, Genesys, and CCaaS systems, with Salesforce. To use Agentforce Voice, at minimum, Voice with Telephony Providers must be turned on–a complete setup isn’t required. For example, if you are using CCaaS, you just need to turn on Voice with Telephony Providers. Although, with a complete Voice with Telephony Providers setup, Agentforce Voice integrates seamlessly into your contact center, making it easy to handle scenarios such as agent escalation and context passing.

Agentforce Voice and Voice with Telephony Providers work together to transform your contact center from traditional, static telephony into an intelligent, conversational experience. With Agentforce Voice and Voice with Telephony Providers, provide 24/7 support with built-in agent transfer and escalation capabilities when your customers need them.

-   **[Complete the Prerequisites](https://help.salesforce.com/s/articleView?id=ai.agentforce_voice_setup_prereqs.htm&language=en_US&type=5)**  
    Before you connect an agent to your partner telephony system, complete these prerequisites.
-   **[Launch Agentforce Voice Setup](https://help.salesforce.com/s/articleView?id=ai.agent_agentforce_voice_setup.htm&language=en_US&type=5)**  
    Agentforce Voice Setup walks you through the entire setup process.
-   **[Choose Your Communication Protocol](https://help.salesforce.com/s/articleView?id=ai.agent_agentforce_voice_choose_your_protocol.htm&language=en_US&type=5)**  
    You can set up Agentforce Voice with the PSTN, SIP, or Dynamic Routing communication protocol. The steps vary based on the protocol.
-   **[Configure Call Routing and Call Escalation for the Agent](https://help.salesforce.com/s/articleView?id=ai.agent_call_routing_escalation.htm&language=en_US&type=5)**  
    Configure an Omni-Channel flow to transfer inbound calls to the voice-enabled agent. Create an escalation Omni-Channel flow to disconnect the agent and, if supported by your telephony or CCaaS system, transfer the call to a rep. Add the activated escalation flow to the agent.
-   **[Configure the Channel and Telephony Settings for PSTN](https://help.salesforce.com/s/articleView?id=ai.agentforce_voice_pstn_channel_and_telephony_settings.htm&language=en_US&type=5)**  
    Create a channel that's used to manage inbound calls routed to the Agentforce agent. If supported, configure your telephony system to create a VoiceCall record in Salesforce for every incoming call, and then transfer each call to the Agentforce agent using the procured phone number. When needed, transfer the call to a human service rep.
-   **[Configure the Channel and Telephony Settings for SIP or Dynamic Routing](https://help.salesforce.com/s/articleView?id=ai.agentforce_voice_sip_channel_and_telephony_settings.htm&language=en_US&type=5)**  
    Create a channel that’s used to manage inbound calls routed to the Agentforce agent. If supported, configure your telephony system to create a VoiceCall record in Salesforce for every incoming call, and then transfer each call to the Agentforce agent using the SIP address or dynamic routing phone number. When needed, transfer the call to a human service rep.
-   **[Connecting Related Voice Calls](https://help.salesforce.com/s/articleView?id=ai.agent_connect_related_voice_calls.htm&language=en_US&type=5)**  
    When a customer conversation involves call transfers, a separate voice call record can be created in Salesforce for each call segment. This action results in multiple voice call records for the same conversation. To provide a single, comprehensive view and preserve the full call context, connect these related voice call records. Connecting records enables more informed decisions. For instance, you can escalate the call to the appropriate rep based on all gathered information.


# Configure Service Agent Access

Learn how Agentforce Service agents control data access. Set up an agent user for your Agentforce Service agent and assign permissions, so your agent has everything it needs to do its job.

Agentforce Service agents connect to channels that aren’t restricted to logged-in users. When a Service agent can’t use an end user’s user record to control access, it uses a dedicated user record that determines what types of data it can read and edit. This is called the agent user or the agent’s user record.

If an Agentforce Service agent doesn’t have permission to view a product inventory or reservation calendar, it can’t answer questions about them. Conversely, if the agent has access to data it doesn’t need, the agent can expose proprietary information to customers. Configuring your agent user to have access to the data it needs to do its job while limiting its access to everything else is an essential part of building a safe, reliable, and helpful agent.

## Service Agent Access By End User

Your Service agent governs access differently depending on the authentication level of the end user. Learn when the agent user’s access applies.


 **End User Type** 
|   |**Unidentified End User** | **Identified (verified) End User** | **Authenticated User** |
| --- | --- | --- | --- |
| **Description** | The customer interacts with an agent without verifying their identity. For example, agents that handle FAQs. | The customer interacting with an agent has a contact record, but not a user record. They might be verified (for example, they’ve provided an OTP to confirm their identity), but they aren’t logged in. | The customer is interacting with an agent on an Experience Cloud site, is logged in through the site, and has a user record. Available for Enhanced Chat and Experience Cloud sites only with [credential-based user verification enabled](https://help.salesforce.com/s/articleView?id=service.miaw_credential_user_verification_setup.htm&language=en_US&type=5). |
| **Runs As** | Agent User (EinsteinServiceAgent User) | Agent User (EinsteinServiceAgent User) | Logged-in site user |
| **Data Access Governed By** | Agent user profile, permissions, field-level security, and sharing rules. OWD for internal users apply. | Agent user profile, permissions, field-level security, and sharing rules. OWD for internal users apply. | Logged-in site user’s profile, permissions, field-level security, and sharing rules. OWD depend on whether the user is internal or external. |
| **User Identified By** | N/A | Context variables (for example, `MessagingSession.ContactId`). Context variables tell the agent who the user is but don’t control data access. | Logged-in site user |

## Create an Agent User

You create or select an existing agent user whenever you [make a new Agentforce Service Agent](https://help.salesforce.com/s/articleView?id=ai.service_agent_setup.htm&language=en_US&type=5). After the agent user is created, you can view it by opening **Setup** and typing `Users` in the Quick Find box, then selecting **Users**.

After the agent user is created, it has these properties:

-   **Name**: EinsteinServiceAgent User
    
-   **User License**: Einstein Agent
    
-   **Profile**: Einstein Agent User
    
-   **Org-wide sharing defaults (OWD)**: Internal
    
-   **Permission Sets**: Agentforce Service Agent Secure Base, \[Agent\_Name\]\_Permissions
    
-   **Permission Set Group**: AgentforceServiceAgentUserPsg, which contains the Agentforce Service Agent User, Data Cloud User, and Prompt Template User permission sets
    
-   **Permission Set Licenses**: Agentforce Service Agent User, Data Cloud, Einstein Prompt Templates
    

The agent user is created with minimal access so that your agent is secure by default. To support your use cases, expand your agent user’s access, based on the principle of least privilege. Only Salesforce users with admin permissions can view or edit agent users.

![Tip](https://sf-zdocs-cdn-prod.zoominsoftware.com/tdta-ai-generative_ai-264-0-0-production-enus/cf864731-c3bb-4e3b-b77c-8a56c30bc21f/images/icon_tip.png)

Tip

When you have multiple agent users in your org, here are some ways to make it easier to manage agent users on the Users Setup page. To differentiate between multiple agent users, update the first name of each user to the name of the agent that it’s associated with. To easily find all agent users, create a list view that filters by the Einstein Agent User profile on the Users Setup page.

## Grant the Agent User Object Access

The agent user requires the minimum level of object permissions for each object that the agent interacts with via flows, Apex, or prompt templates. When you add a new action to your agent, make sure that the agent user has access to the objects referenced in the action. If you connect your agent to an Enhanced Messaging channel, your agent also requires access to the Messaging Session object.

Object permissions for agent users are handled the same way as they are for regular users. [To manage object permissions](https://help.salesforce.com/s/articleView?id=platform.perm_object_access_summary.htm&language=en_US&type=5), edit the \[Agent\_Name\]\_Permissions permission set associated with your agent user. If you want to create a different permission set for your agent user, make sure that it’s associated with the Einstein Agent license and Einstein Agent User profile. For more information, see [Object Permissions](https://help.salesforce.com/s/articleView?id=platform.users_profiles_object_perms.htm&language=en_US&type=5).

## Grant the Agent User Record Access

**Assign a Role**

Roles grant users record access via sharing rules and role hierarchies. [Assign the agent user to a role](https://help.salesforce.com/s/articleView?id=platform.assigning_users_to_roles.htm&language=en_US&type=5) that lets the agent view or edit the records that it interacts with.

When assigning a role, consider the role hierarchy for your org and give your agent a role that lets it view or edit the records it’s necessary for your agent to interact with. Follow the principle of least privilege. For more information, see [Controlling Access Using the Role Hierarchy](https://help.salesforce.com/s/articleView?id=platform.security_controlling_access_using_hierarchies.htm&language=en_US&type=5).

**Review and Modify Sharing Rules**

When a Service agent runs in the agent user’s context, org-wide sharing defaults (OWD) for internal users apply. [Restrict your OWD for internal users](https://help.salesforce.com/s/articleView?id=platform.admin_sharing.htm&language=en_US&type=5) to limit record access for all internal users. [Create sharing rules](https://help.salesforce.com/s/articleView?id=platform.security_sharing_rules_create.htm&language=en_US&type=5) to selectively grant access, excluding the Einstein Agent User where appropriate.

**Scope Data Access to Verified Users**

When a Service agent runs in the context of the agent user, context variables (for example, `MessagingSession.ContactId`) can be used to pass the customer’s identity to the agent, but they don’t control data access. Plan ahead to scope record access to verified users, especially for any agent actions that access private customer information (for example, looking up order information).

First, pass verified customer IDs into the custom `VerifiedCustomerId` variableIf you use the standard [Customer Verification or Service Customer Verification](https://help.salesforce.com/s/articleView?id=ai.service_agentforce_customer_verification.htm&language=en_US&type=5#service_agentforce_customer_verification) subagents for user verification in your agent, the actions are configured to store the user’s ID in the `VerifiedCustomerId` variable after their identity is successfully verified. If you don’t, you can create a custom agent action and an Apex class or flow to pass the verified ID to your agent and store it in the `VerifiedCustomerId` variable.

After you’ve verified and stored the customer ID, use it to restrict record access.

-   Build a check of the `VerifiedCustomerID` variable into the Apex classes and flows called by standard and custom agent actions to customer records (`WHERE ContactId = VerifiedCustomerId`).Some standard actions support customer verification by default. For example, the [Get Cases for Verified Contact](https://help.salesforce.com/s/articleView?id=ai.copilot_action_get_cases_verified_contact.htm&language=en_US&type=5) action calls a flow that looks up the customer’s contact ID, checks it against the `VerifiedCustomerId` variable, and uses the verified customer ID to scope its queries. Carefully test and customize each action to meet your security needs.
    
-   Create filters on subagents and actions to restrict access to only verified customers.
    
    -   To add a filter to a subagent in Canvas view, in the Agent Router, place your cursor after the transition you want to add a filter to. From the Add to block shortcut, click **Add filter**. Specify a variable, an operator, and a value to create the condition `VerifiedCustomerId is not None`. To add an additional condition, place your cursor after the value. From the Add to block shortcut, select And or Or, and then specify another variable, operator, and value.
    -   To add a filter to an action in Canvas view, in a subagent, place your cursor after the action you want to add a filter to. From the Add to block shortcut, click **Add filter**. Specify a variable, an operator, and a value to create the condition VerifiedCustomerId is not None. To add an additional condition, place your cursor after the value. From the Add to block shortcut, select And or Or, and then specify another variable, operator, and value.

To learn more, see [Agent Script Pattern: Enforce Business Rules with Filters](https://developer.salesforce.com/docs/ai/agentforce/guide/ascript-patterns-filtering.html).

## Assign Additional Permissions

In addition to object and record access, agent users require [permissions required to run agent actions](https://help.salesforce.com/s/articleView?id=ai.agent_actions_common_perms.htm&language=en_US&type=5)

Review your agent user’s current access and make sure that they have the necessary permissions for your use case.

On the Agent Access page in Agentforce Builder, you can review the user record that represents the agent in the Agent's User Record section. Review and edit the agent's assigned permission sets and permission set groups in the Permissions and Profiles section.

To manage agent user permissions, edit the \[Agent\_Name\]\_Permissions permission set associated with your agent user. If you want to create a different permission set for your agent user, make sure that it’s associated with the Einstein Agent license and Einstein Agent User profile.
[Video: Setup Agent Permissions](https://play.vidyard.com/71611389-ded2-4cda-a6dc-502e1e72700a)

# Maintain Trust with Agentforce Actions in the Legacy Builder

Agents connected to employee channels, such as Lightning Experience, the Salesforce mobile app, and Slack, limit access to subagents and actions by default, based on the end user's context. Agentforce Service agents connected to customer channels, such as enhanced Messaging channels and Enhanced Chat, require additional configuration to ensure secure access. As you configure your agent, it's important to think through the security and identification requirements for your use case and only grant your agents the actions and access required to complete the tasks you want them to be able to complete autonomously on behalf of your customers. For sensitive actions, we recommend building customer verification directly into the action’s flow.

You have full control over the actions that your agents can take, so you can tailor your customer experience to your needs. To enhance security and ensure that agents operate within defined boundaries, we recommend:

-   Assigning agents that connect to customer channels the minimum user permissions required to do their job.
-   Building identity confirmation and access control directly into the flow of sensitive actions.

Every company’s risk tolerance and security standards are unique, and there’s no one way to incorporate identity verification into your agent implementation. For instance, depending on your company policy, you might allow an Agentforce Service agent to accept order IDs conversationally and provide order statuses without requiring any formal identity verification beyond that. However, if your business requires shipping sensitive or regulated materials, you might require customers to authenticate themselves before looking up order information on their behalf. Consider your company’s risk tolerance and security standards before configuring your agent. To prevent agents from sharing data outside the intended scope, configure them with authentication and authorization in mind.

## Agentforce Actions and Security

When your agent is connected to customer channels, think of agent actions as either public or private. While Salesforce doesn’t have a specific setting to designate actions as public or private, this framework helps you conceptualize and implement your company’s security standards.

### Public Actions

Public actions are actions that your company is comfortable taking on behalf of anyone, regardless of identity, without authentication. For example, the [Answer Questions with Knowledge](https://help.salesforce.com/s/articleView?id=ai.copilot_actions_ref_answer_questions_with_knowledge&language=en_US&type=5) action is usually considered a public action, especially if it’s grounded in public information such as return policies. Looking up an order can also be a public action if you’re comfortable doing so without securely confirming the requester's identity. In such cases, the information required to identify a specific order, such as the order ID or email address, can be passed conversationally.

### Private Actions

Private actions require the requester’s identity to be confirmed according to your company’s comfort level; for example, through authentication or through the sharing of identifying information in a messaging session. Updating personal appointment information, making purchases, or requesting services on a support contract are typically examples of private actions, and we don't recommend making them public. For an Agentforce Service agent to complete a private action, the user triggering the action must be authorized to access the action, and their identity should be securely confirmed.

## Guidelines for Securely Implementing Private Actions

To enhance the security of agents connected to customer channels, it's best practice to require agents to confirm the identity of the person they’re interacting with before they take a private action on their behalf.

For particularly sensitive actions, we recommend confirming identity using techniques such as two-factor authentication, which handle the authentication process outside the scope of the conversation. Sharing identifying information within the chat isn't a secure verification method, but the approach you choose depends on your risk tolerance and security standards.

After a customer's identity has been confirmed, the identifying information can be saved in the associated [MessagingSession](https://developer.salesforce.com/docs/atlas.en-us.object_reference.meta/object_reference/sforce_api_objects_messagingsession.htm) record. Before completing any private action, the agent can reference the MessagingSession record to confirm the identity and permissions of the person it's interacting with. This process can be built directly into the flow of private actions.

When building an agent that connects to customer channels and can take private actions, it’s crucial to consider how to mitigate risk. While all use cases are different, keep these guidelines in mind.

| Guideline | Details |
| --- | --- |
| Follow the principle of least privilege. |-   **Restrict access:** Grant only the minimum necessary permissions to your agent.<br>-**Review permissions regularly:** To ensure that permissions are still appropriate, conduct periodic reviews. |
| Implement robust access controls. |-   **Enforce strong authentication:** Implement strong authentication mechanisms, such as two-factor authentication, to verify the identity of users interacting with your agent.<br>-   **Monitor access logs:** To identify any suspicious activity, regularly review the access logs.|
| Design secure actions. |-   **Limit scope:** Design actions to operate within specific boundaries and prevent unauthorized access to sensitive data. Build confirmation of user identity and permissions directly into each private action.<br>-   **Validate input:** To prevent malicious input and potential security vulnerabilities, implement input validation.<br>-   **Error handling:** To prevent information disclosure and system instability, implement robust error handling. |

![Important](https://sf-zdocs-cdn-prod.zoominsoftware.com/tdta-ai-generative_ai-264-0-0-production-enus/cf864731-c3bb-4e3b-b77c-8a56c30bc21f/images/icon_important.png)

Important

Organization-wide sharing defaults (OWD) determine what access users have to records they don’t own. In an agent session with an authenticated user, the session runs in the end user’s context and OWD depend on whether the user is external or internal. In an agent session with an unauthenticated user, the session runs in [the agent user’s](https://help.salesforce.com/s/articleView?id=ai.agent_user.htm&language=en_US&type=5) context and OWD for internal users apply.

Carefully review your OWD, your agent user’s permissions, and your agent configuration to ensure the right record access for your end users and your business.

-   For all agents that use the agent’s user record, we recommend using [filters](https://help.salesforce.com/s/articleView?id=ai.agent_asset_filters.htm&language=en_US&type=5) and [variables](https://help.salesforce.com/s/articleView?id=ai.agent_variables.htm&language=en_US&type=5) to limit record access at the subagent and action levels. This strategy protects sensitive data regardless of your OWD.
-   You can [restrict your OWD for internal users](https://help.salesforce.com/s/articleView?id=platform.admin_sharing.htm&language=en_US&type=5) to limit record access for all internal users. Then you can [create sharing rules](https://help.salesforce.com/s/articleView?id=platform.admin_sharing.htm&language=en_US&type=5) to selectively grant access, excluding the Einstein Agent User where appropriate.

## Next Steps

Learn how to build user authentication into your private agent actions, including with the Customer Verification standard subagent.

-   **[Add User Identification to Agentforce Actions](https://help.salesforce.com/s/articleView?id=ai.service_agent_secure_actions_implement.htm&language=en_US&type=5)**  
    When configuring your agent that connects to customer channels so that it can take private actions securely, have it confirm the identity of the person it’s interacting with according to your company’s standards.
-   **[Verify Customers with Standard Subagents in the Legacy Builder](https://help.salesforce.com/s/articleView?id=ai.service_agentforce_customer_verification.htm&language=en_US&type=5#service_agentforce_customer_verification)**  
    Before an Agentforce Service agent takes a private action on a user’s behalf, Salesforce recommends verifying the identity of the person the agent is interacting with. To verify the identity of an unverified user in an agent session, configure your agent to use the Customer Verification subagent or the Service Customer Verification subagent and limit access to subagents and actions that you specify. You can require different levels of verification for different subagents and actions, based on your business’s security requirements.
-   **[Example Implementation of a Secure Agentforce Service Agent](https://help.salesforce.com/s/articleView?id=ai.service_agent_secure_actions_example.htm&language=en_US&type=5)**  
    The details of implementing secure Agentforce Service agents vary depending on where the agent is deployed and the surrounding user authentication policies. To get a feel for the underlying patterns, let’s look at an example.

#### See Also

-   [_Trailhead_: Deploy Agent Authentication](https://trailhead.salesforce.com/content/learn/modules/agent-customization-with-apex)

# Agentforce Glossary of Terms

Learn more about the terms used in Agentforce and generative AI at Salesforce.

[A](https://help.salesforce.com/s/articleView?id=ai.copilot_glossary.htm&language=en_US&type=5#copilot_glossary__a) | [B](https://help.salesforce.com/s/articleView?id=ai.copilot_glossary.htm&language=en_US&type=5#copilot_glossary__b) | [C](https://help.salesforce.com/s/articleView?id=ai.copilot_glossary.htm&language=en_US&type=5#copilot_glossary__c) | [D](https://help.salesforce.com/s/articleView?id=ai.copilot_glossary.htm&language=en_US&type=5#copilot_glossary__d) | [E](https://help.salesforce.com/s/articleView?id=ai.copilot_glossary.htm&language=en_US&type=5#copilot_glossary__e) | [F](https://help.salesforce.com/s/articleView?id=ai.copilot_glossary.htm&language=en_US&type=5#copilot_glossary__f) | [G](https://help.salesforce.com/s/articleView?id=ai.copilot_glossary.htm&language=en_US&type=5#copilot_glossary__g) | [H](https://help.salesforce.com/s/articleView?id=ai.copilot_glossary.htm&language=en_US&type=5#copilot_glossary__h) | [I](https://help.salesforce.com/s/articleView?id=ai.copilot_glossary.htm&language=en_US&type=5#copilot_glossary__i) | [L](https://help.salesforce.com/s/articleView?id=ai.copilot_glossary.htm&language=en_US&type=5#copilot_glossary__l) | [M](https://help.salesforce.com/s/articleView?id=ai.copilot_glossary.htm&language=en_US&type=5#copilot_glossary__m) | [N](https://help.salesforce.com/s/articleView?id=ai.copilot_glossary.htm&language=en_US&type=5#copilot_glossary__n) | [O](https://help.salesforce.com/s/articleView?id=ai.copilot_glossary.htm&language=en_US&type=5#copilot_glossary__o) | [P](https://help.salesforce.com/s/articleView?id=ai.copilot_glossary.htm&language=en_US&type=5#copilot_glossary__p) | [R](https://help.salesforce.com/s/articleView?id=ai.copilot_glossary.htm&language=en_US&type=5#copilot_glossary__r) | [S](https://help.salesforce.com/s/articleView?id=ai.copilot_glossary.htm&language=en_US&type=5#copilot_glossary__s) | [T](https://help.salesforce.com/s/articleView?id=ai.copilot_glossary.htm&language=en_US&type=5#copilot_glossary__t) | [U](https://help.salesforce.com/s/articleView?id=ai.copilot_glossary.htm&language=en_US&type=5#copilot_glossary__u) | [V](https://help.salesforce.com/s/articleView?id=ai.copilot_glossary.htm&language=en_US&type=5#copilot_glossary__v)

![Note](https://sf-zdocs-cdn-prod.zoominsoftware.com/tdta-ai-generative_ai-264-0-0-production-enus/8f79e91a-cacc-4a50-9604-d1286798b180/images/icon_note.png)

Note Beginning in April 2026, agent topics are now called subagents. There are no changes to functionality. During this transition, you may see a mix of the new and previous terms in our documentation.

## A

Action, agent action

A function your agent executes on the platform to get information and perform tasks. In other words, an action is how an agent gets things done in Salesforce. An agent action includes:

-   A natural language name and instructions that tells the agent how and when to use the action, how to retrieve required inputs, and how to format and use outputs.
-   The Salesforce functionality that the agent action calls to get information or perform a task, called a reference action. For example, an agent action can call an API to retrieve data, a flow to update a record, a prompt template to generate a response, an Apex class to run custom business logic, or a predictive model to make a recommendation.

Agent

Goal-oriented, autonomous AI that performs tasks and business interactions and provides relevant answers drawn from business data. An agent is more autonomous than other conversational AI solutions, so it can independently identify opportunities for action, anticipate next steps, and initiate tasks within the use cases and guardrails you specify. Some agents initiate and complete tasks on behalf of a user. Others assist users with tasks and questions in the user’s flow of work.

Agents can be deployed to customer or employee channels, depending on the associated agent type.

An agent can be created from a template or from scratch. An agent contains subagents and actions.

See [What Are Agents?](https://help.salesforce.com/s/articleView?id=ai.copilot_overview.htm&language=en_US&type=5)

Agent Router (formerly known as Topic Selector)

A special system subagent that helps you control subagent classification and routing in agents created in Agentforce Builder in Agentforce Studio.

When you create an agent, the Agent Router is added to your agent and is defined as the starting subagent for every agent conversation. By default, the agent uses this subagent for subagent classification, which is the process of selecting the most relevant subagent based on what the user wants to do and the jobs that the agent can do.

You can edit the Agent Router just like any other subagent, so you can customize its reasoning instructions and actions to set initial variables, add logic, and add or remove transitions to subagents to control your agent's routing behavior.

See [Subagent Classification and Routing](https://help.salesforce.com/s/articleView?id=ai.agent_topics_routing.htm&language=en_US&type=5).

Agent user, Agent’s user record

A Salesforce integration user with all the permissions that the agent needs to do its job. You can create an agent user in the Agent Creator guided setup when you create an agent that connects to customer channels.

An AI agent can interact with employees or customers. Most agents that interact with employees run in the context of the logged-in user. However, agents connected to customer channels chat with a broad set of users, including unverified users. To securely access data and perform actions that an end user doesn’t have access to, the agent operates as an agent user. The permissions that you give to an agent user determines the actions that the associated agent can take.

See [Best Practices for Agent User Permissions](https://help.salesforce.com/s/articleView?id=ai.agent_user.htm&language=en_US&type=5) and [Agent Execution Context and Data Access by Type](https://help.salesforce.com/s/articleView?id=ai.agent_execution_data.htm&language=en_US&type=5).

Agentforce Data Library

Agentforce Data Library provides grounding information for agents. Create a data library to index knowledge articles and fields, file uploads, or web sources. Indexes enable AI agents to retrieve and use relevant, accurate information for LLM prompts.

See [Agentforce Data Library](https://help.salesforce.com/s/articleView?id=ai.data_library_parent.htm&language=en_US&type=5).

Agentic feature, Agentforce feature

A generative AI solution that uses the LLM gateway and the reasoning engine (usually branded as “Agentforce.” An agentic feature is often a conversational experience with a chat UI, but others operate in the background.

Artificial intelligence (AI)

A branch of computer science in which computer systems use data to draw inferences, perform tasks, and solve problems with human-like reasoning.

Assets, agent assets

Refers to the subagents, actions, variables, surfaces, and default settings (such as system messages) assigned to an agent.

You can view assets available for your agents in the asset library. You can view and manage the assets assigned to your agent in Agentforce Builder.

## B

Bias

Systematic and repeatable errors in a computer system that create unfair outcomes, in ways different from the intended function of the system, due to inaccurate assumptions in the machine learning process.

## C

Channel

A messaging platform, app, or interface that you can deploy an agent to. Employees and other internal stakeholders can interact with agents in Salesforce, Slack, and other employee channels. Customer channels, such as messaging platforms and email, are where your customers can interact with an agent.

See [Deploy Your Agent to Channels](https://help.salesforce.com/s/articleView?id=ai.agent_parent_deploy.htm&language=en_US&type=5).

Chunking

The process of breaking unstructured data into manageable, semantically meaningful chunks that can then be turned into [vector embeddings](https://help.salesforce.com/s/articleView?id=ai.copilot_glossary.htm&language=en_US&type=5#copilot_glossary__vector_embedding). Chunking strategies vary depending on the context of the content being chunked.

See [Chunk Data](https://help.salesforce.com/s/articleView?id=data.c360_a_search_index_grounding.htm&language=en_US&type=5).

Citation

Citations link AI-generated responses to the grounding sources that are relevant to the response. Citations allow users to see what information the large language model (LLM) used to generate the response, and to verify the validity of the source data.

See [Build Trust in AI Responses with Citations](https://help.salesforce.com/s/articleView?id=ai.generative_ai_trust_citations.htm&language=en_US&type=5).

Connection

A connection includes all of the components and settings that help your agent connect to a specific channel, including adaptive response formats, and connection settings. You can also find the Omni-Channel flows that route conversations to and from an agent in your connection settings.

See [Deploy Your Agent to Channels](https://help.salesforce.com/s/articleView?id=ai.agent_parent_deploy.htm&language=en_US&type=5).

Conversation recommendations (Lightning Experience and mobile only)

Clickable suggested requests or questions that appear directly in the Agentforce conversation panel and persist even when the user moves to a new page. Formerly known as Recommended Actions. Supported for Agentforce Employee agents only.

## D

Digital Wallet

An account management tool that offers near real-time consumption data for enabled products across your active contracts. Use Digital Wallet to track your org’s Agentforce usage and credit consumption against generative AI usage types.

See [About Digital Wallet](https://help.salesforce.com/s/articleView?id=xcloud.wallet_about.htm&language=en_US&type=5) and [Generative AI Usage and Billing](https://help.salesforce.com/s/articleView?id=ai.generative_ai_usage.htm&language=en_US&type=5).

## E

Embedded feature, Einstein feature

A non-Agentforce feature (usually branded as “Einstein”) that uses AI. It can be a predictive AI solution, or it can be a generative AI solution that uses the LLM gateway and doesn’t use the reasoning engine.

## F

Filter

Limits access to subagents and actions based on conditions and variables you specify. When you apply a filter to a subagent or action, the agent can only use the asset when the filter conditions are met.

Fine-tuning, Tuning

The process of adapting a pre-trained language model for a specific task by training it on a smaller, task-specific dataset.

Fine-tuning can also more generally refer to the process of testing and refining instructions to improve prompt performance.

Follow-up actions (Lightning Experience only)

Context-sensitive actions that appear in the Agentforce conversation panel after a user completes a specific standard action. These actions guide users through a natural workflow by suggesting the next logical step based on the previous action's output. By definition, follow-up actions can’t be executed on their own. They can only follow a standard action (for example, you can’t ‘refine an email’ without first ‘drafting an email’).

## G

Generative AI gateway, Einstein gateway, the gateway

Exposes normalized APIs to interact with foundation models and services provided by different vendors, internally and from the partner ecosystem.

Generative pre-trained transformer (GPT)

A family of language models trained on a large body of text data so that they can generate human-like text.

Grounding

The process through which domain-specific knowledge and customer information is added to a prompt to give the model the context it needs to respond more accurately.

See [Ground Agentforce in Your Data](https://help.salesforce.com/s/articleView?id=ai.agent_parent_data.htm&language=en_US&type=5).

## H

Hallucination

A type of output where a model generates semantically correct text that is factually incorrect or makes little to no sense, given the context.

Human in the loop (HITL)

A model that requires human interaction.

Hyperparameter

A parameter used to control the training process. Hyperparameters sit outside the generated model.

## I

Instructions

Instructions describe a task to a LLM using natural language. Instructions are the basis of prompt templates. In Agentforce, instructions include instructions include agent-level instructions, subagent instructions (sometimes called reasoning instructions), and sometimes user input to the agent.

Intent

An end user’s goal for interacting with an AI agent.

## L

Large language model

A language model consisting of a neural network with many parameters trained on large quantities of text.

Agents harness the power of a large language model (LLM) to communicate with users and take action in your org. Agents make reasoning engine calls to the LLM at different times during a task or interaction with a user. The number and size of the LLM calls depends on the task and which subagents and actions are launched.

See [How Agentforce Works](https://help.salesforce.com/s/articleView?id=ai.agent_reasoning_engine.htm&language=en_US&type=5).

## M

Machine learning

A subfield of AI specializing in computer systems that are designed to learn, adapt, and improve based on feedback and inferences from data, rather than explicit instruction.

Model card

Documents details about the model’s performance as well as inputs, outputs, training method, conditions under which the model works best, and ethical considerations in use.

## N

Natural language processing (NLP)

A branch of AI that uses machine learning to understand language as written by people. Large language models are one of many approaches to NLP.

## O

Omni-Channel flow

A flow used to route conversations to or from an agent. Omni-Channel flows use the Route Work action to route conversations and their associated records, such as messaging session and email records. Agents that connect to customer channels have at least one inbound and outbound Omni-Channel flow.

See [Deploy Your Agent to Channels](https://help.salesforce.com/s/articleView?id=ai.agent_parent_deploy.htm&language=en_US&type=5).

## P

Parameter size

The number of parameters a model uses to process and generate data.

Prompt

A natural language description of the task to be accomplished. An input to the LLM.

Prompt design

Prompt design is the process of creating prompts that improve the quality and accuracy of a model’s responses.

Prompt engineering

An emerging discipline within AI focused on maximizing the performance and reliability of models by crafting prompts in a systematic and rigorous way.

Prompt injection

A method used to control or manipulate the model's output by giving it certain prompts. With this method, users and third parties attempt to get around restrictions and perform tasks that the model wasn't designed for.

Prompt resolution

The process of populating an LLM prompt at run time with additional information, such as values from structured data sources and knowledge retrieved from unstructured data sources. This process is sometimes referred to as dynamic grounding or hydrating a prompt. See [Prompt Template Run-time Execution](https://help.salesforce.com/s/articleView?id=ai.prompt_builder_runtime.htm&language=en_US&type=5).

Prompt template

A string with placeholders that are replaced with business data values to generate a final text instruction that is sent to the LLM.

## R

Reasoning engine, Atlas reasoning engine

Guides how an agent launches subagents and actions and generates responses during a conversation to accomplish a task for the user–in other words, how an agent reasons and takes action.

The Atlas reasoning engine is a graph-based reasoning engine. You can think of it like a flowchart with nodes, variables, and transitions, so agents follow specific, predictable paths. Unlike strictly prompt-based reasoning engines, Atlas separates an agent’s big-picture workflow from its conversational skills.

See [How Agents Work](https://help.salesforce.com/s/articleView?id=ai.agent_builder_reasoning_engine.htm&language=en_US&type=5).

Reference action

The Salesforce functionality that an agent action calls to get information or perform a task. For example, an agent action can call an API to retrieve data, a flow to update a record, a prompt template to generate a response, an Apex class to run custom business logic, or a predictive model to make a recommendation.

See [Create a Custom Action](https://help.salesforce.com/s/articleView?id=ai.agent_actions_custom.htm&language=en_US&type=5) to learn what reference action types are supported.

Retrieval-augmented generation (RAG)

A form of grounding that uses an information retrieval system like a knowledge base to enrich a prompt with relevant context, for inference or training.

See [Ground Agentforce in Your Data](https://help.salesforce.com/s/articleView?id=ai.agent_parent_data.htm&language=en_US&type=5).

Retriever

A logical layer between a search service and knowledge retrieval-powered solutions, such as [retrieval-augmented generation](https://help.salesforce.com/s/articleView?id=ai.copilot_glossary.htm&language=en_US&type=5#copilot_glossary__rag) (RAG) implementations. It defines the runtime search and retrieval configuration for an application, agent, prompt template, and other solution components. A retriever serves as a reusable, versioned, and packageable artifact that simplifies the setup of knowledge retrieval with search-based grounding for agents, data libraries, prompt templates, with Apex, or in Flow.

See [Retrieve Data](https://help.salesforce.com/s/articleView?id=data.c360_a_ai_retriever.htm&language=en_US&type=5).

## S

Search index

A Data 360 search index holds a collection of [content chunks](https://help.salesforce.com/s/articleView?id=ai.copilot_glossary.htm&language=en_US&type=5#copilot_glossary__chunking) and their respective [vector embeddings](https://help.salesforce.com/s/articleView?id=ai.copilot_glossary.htm&language=en_US&type=5#copilot_glossary__vector_embedding). The search index facilitates search for relevant vectors given a query vector. Depending on your data and query needs, you can create either a vector search index or a hybrid search index.

See [Use Search for AI, Automation, and Analytics](https://help.salesforce.com/s/articleView?id=data.c360_a_search_index_ground_ai.htm&language=en_US&type=5).

Semantic retrieval

A scenario that allows an LLM to use similar and relevant historical business data that exists in a customer's CRM data.

Subagent (fomerly known as topic)

A particular job an agent can do. A subagent contains actions, which are the tools available for the job, and instructions, which tell the agent how to make decisions. Collectively, the subagents assigned to your agent define the capabilities your agent can handle.

Subagents can be standard (Salesforce-provided) or custom. Standard subagents are available out of the box in the asset library or assigned to a new agent by default.

See [Subagents](https://help.salesforce.com/s/articleView?id=ai.agent_topics.htm&language=en_US&type=5).

Suggested actions (Lightning Experience only)

A set of three contextually relevant actions in the Agentforce conversation panel, based on the current page the user is viewing. These actions help users identify the most immediate step they can take to complete a task or learn more about a specific feature. Suggested actions consider page context only and are rules-based. The result of a suggested action is predefined, so it can differ from the result of entering a similar free text input in an agent conversation.

## T

Temperature

A parameter that controls how predictable and varied a model's outputs are. A model with a high temperature generates random and diverse responses. A model with a low temperature generates focused and more consistent responses.

Template, agent template

A blueprint for an individual agent designed for a particular use case. It contains subagents, actions, filters, variables, and system messages. When you create an agent from a template, you can choose which assets from the template to include.

An agent template is a child of an agent type. A type can be associated with many templates, but a template can only be associated with one type. For example, Agentforce Service Agent (ASA) is an agent type that connects to customer channels. To create an agent from a template of the ASA type, you need the required permissions for ASA and any permissions associated with the template.

See [Create an Agent](https://help.salesforce.com/s/articleView?id=ai.agent_setup_create.htm&language=en_US&type=5).

Token

To understand or generate text, a large language model (LLM) breaks the text into smaller units called tokens. A token can be as big as a single word or as small as a single character, depending on how the text is processed or generated.

Token size can affect agent billing and performance. In general, the greater the number of tokens in a prompt or response, the more complex the task and the slower the response of the LLM.

The maximum number of tokens that can be processed at a time is called a context window and varies by model. To learn more about context windows for supported models, see [_Agentforce Developer Guide_: Supported Models](https://developer.salesforce.com/docs/ai/agentforce/guide/supported-models.html#context-window).

Topic, agent topic

Topics are now called subagents. See [Subagent (fomerly known as topic)](https://help.salesforce.com/s/articleView?id=ai.copilot_glossary.htm&language=en_US&type=5#copilot_glossary__subagent).

Toxicity

Describes many types of discourse, including but not limited to offensive, unreasonable, disrespectful, unpleasant, harmful, abusive, or hateful language.

Trusted AI

Guidelines created by Salesforce that are focused on the responsible development and implementation of AI.

Type, agent type

A broad category of agents that share similar capabilities and constraints. A type controls permissions required to build or access an agent and the channels that an agent can be deployed to. For example, agents of the Agentforce Service Agent type can be deployed to customer channels, such as Enhanced Chat. Agents of the Agentforce Employee Agent type can be deployed to employee channels, such as Slack.

An agent type is a parent of an agent template. Each agent type is associated with a default template for that type (usually of the same name as the agent type), as well as other templates.

A type can be associated with many templates, but a template can only be associated with one type. For example, Agentforce Service Agent (ASA) is an agent type that connects to customer channels. To create an agent from a template of the ASA type, you need the required permissions for ASA and any permissions associated with the template.

See [Agent Types and Considerations](https://help.salesforce.com/s/articleView?id=ai.agent_setup_explore_types.htm&language=en_US&type=5).

## U

Unstructured data

Data that doesn’t have a specific, consistent format and can’t be easily stored in a typical relational database. Common forms of unstructured data include chat transcripts, audio files, websites, legal documents, and other large texts, such as books.

See [Unstructured Data in Data 360](https://help.salesforce.com/s/articleView?id=data.c360_a_unstructured_data_about.htm&language=en_US&type=5).

Usage type

Usage types are the different categories that classify how credits are consumed when using Agentforce and other generative AI features. Each usage type has its own multiplier rate as listed in the rate card that determines how many credits are charged per unit of use. You can track your org's usage of Agentforce features and the credit consumption in Digital Wallet.

See [Generative AI Usage and Billing](https://help.salesforce.com/s/articleView?id=ai.generative_ai_usage.htm&language=en_US&type=5) and [About Digital Wallet](https://help.salesforce.com/s/articleView?id=xcloud.wallet_about.htm&language=en_US&type=5).

User message, user utterance

Input from an end user to an agent, often a question or request. This can be free-text input entered into a chat UI or sent in an email, a selection from a predefined menu, or even voice input.

For agents that don’t directly interact with an end user, sometimes the admin or builder provides a string that’s treated as a user message in order to define the agent’s task.

## V

Variable

Stores contextual information about agent conversations. Variables can be used to personalize agent conversations, implement user verification, and ensure consistent agent behavior. Variables can be used in filters, instructions, and as input for actions.

Salesforce provides different types of variables. See [Agent Variables](https://help.salesforce.com/s/articleView?id=ai.agent_variables.htm&language=en_US&type=5).

Vector embedding

A numerical representation of [unstructured data](https://help.salesforce.com/s/articleView?id=ai.copilot_glossary.htm&language=en_US&type=5#copilot_glossary__unstructured_data) that machines can read. Vector embeddings measure the semantic similarity of different pieces of text, enabling accurate and relevant search results for generative AI prompts.

See [Vector Search](https://help.salesforce.com/s/articleView?id=data.c360_a_search_index_vector_index.htm&language=en_US&type=5).

Did this article solve your issue?

Let us know so we can improve!

YesNo

---
---
---
---

# Agent API v1.0.0 YAML
- **openapi:** 3.0.0
# info

- **title:** Agent API
- **version:** v1.0.0
- **description:** 
Use Agent API to communicate with AI agents in your org. Get access to your topics and actions in Agentforce by sending messages to AI agents. Create a Salesforce app in your org, generate a token, and then start using the API. To onboard to this API, see [Get Started with the Agent API](/docs/ai/agentforce/guide/agent-api-get-started.html) and [Agent API Examples](/docs/ai/agentforce/guide/agent-api-examples.html).

## Postman Collection

The quickest way to get started with the Agent API is with our [Postman collection](https://www.postman.com/salesforce-developers/salesforce-developers/collection/gwv9bjy/agent-api).

## Endpoints

- [Start a Session](?meta=startSession): Start a session with an agent.
- [Send a Message (sync)](?meta=sendMessage): Send a sync message to the agent on an active session.
- [Send a Message (streaming)](?meta=sendMessageStream): Send a streaming message to the agent on an active session.
- [End a Session](?meta=endSession): End a session.
- [Submit Feedback](?meta=submitFeedback): Submit feedback for a message.


# servers

| url | description |
| --- | --- |
| https://api.salesforce.com/einstein/ai-agent/v1 | Agent API - Production Environment |

# paths

## /agents/{id}/sessions

### post

- **summary:** Start a session
- **description:** Begin an agent session. The endpoint contains the ID of the Salesforce agent. You can find this ID in the URL of the agent details page. When you select the agent from Setup, use the ID at the end of the URL.
- **operationId:** startSession
#### parameters

| in | name | description | required | schema |
| --- | --- | --- | --- | --- |
| path | id | The ID of the Salesforce agent. You can find this ID in the URL of the agent details page. When you select the agent from Setup, use the ID at the end of the URL. | true | [object Object] |
| header | Authorization | Authorization information that contains the JWT. | true | [object Object] |

#### requestBody

- **description:** Request payload to initiate a session.
- **required:** true
##### content

###### application/json

###### schema

- **$ref:** #/components/schemas/StartSessionRequest




#### responses

##### 200

- **$ref:** #/components/responses/StartSessionResponse

##### 400

- **$ref:** #/components/responses/BadRequestError

##### 401

- **$ref:** #/components/responses/UnauthorizedError

##### 403

- **$ref:** #/components/responses/ForbiddenError

##### 404

- **$ref:** #/components/responses/NotFoundError

##### 422

- **$ref:** #/components/responses/RequestProcessingException

##### 423

- **$ref:** #/components/responses/ServerBusyError

##### 429

- **$ref:** #/components/responses/TooManyRequestsError

##### 503

- **$ref:** #/components/responses/ServiceUnavailable

##### default

- **$ref:** #/components/responses/ErrorResponse




## /sessions/{session-id}/messages

### post

- **summary:** Send a message (synchronous)
- **description:** Send a synchronous message to the agent on an active session. The endpoint contains the ID of the active session, which was returned in the response of the Start Session call.
- **operationId:** sendMessage
#### parameters

| in | name | description | required | schema |
| --- | --- | --- | --- | --- |
| path | session-id | The ID of the active session, which is the `sessionId` value returned from the Start Session call. | true | [object Object] |
| header | Authorization | Authorization information that contains the JWT. | true | [object Object] |

#### requestBody

- **description:** Request payload to continue the chat.
- **required:** true
##### content

###### application/json

###### schema

- **$ref:** #/components/schemas/SendMessageRequest




#### responses

##### 200

- **$ref:** #/components/responses/SendMessageSyncResponse

##### 400

- **$ref:** #/components/responses/BadRequestError

##### 401

- **$ref:** #/components/responses/UnauthorizedError

##### 403

- **$ref:** #/components/responses/ForbiddenError

##### 404

- **$ref:** #/components/responses/NotFoundError

##### 422

- **$ref:** #/components/responses/RequestProcessingException

##### 423

- **$ref:** #/components/responses/ServerBusyError

##### 429

- **$ref:** #/components/responses/TooManyRequestsError

##### 503

- **$ref:** #/components/responses/ServiceUnavailable

##### default

- **$ref:** #/components/responses/ErrorResponse




## /sessions/{session-id}/messages/stream

### post

- **summary:** Send a message (streaming)
- **description:** Send a streaming message to the agent on an active session. Returns an SSE stream in the response. The endpoint contains the ID of the active session, which was returned in the response of the Start Session call.
- **operationId:** sendMessageStream
- **x-sse:** true
#### parameters

| in | name | description | required | schema |
| --- | --- | --- | --- | --- |
| path | session-id | The ID of the active session, which is the `sessionId` value returned from the Start Session call. | true | [object Object] |
| header | Authorization | Authorization information that contains the JWT. | true | [object Object] |
| header | Accept | Indicates which content type the sender is able to understand. For this endpoint, specify `text/event-stream`. | true | [object Object] |

#### requestBody

- **description:** Request payload to continue the chat.
- **required:** true
##### content

###### application/json

###### schema

- **$ref:** #/components/schemas/SendMessageRequest




#### responses

##### 200

- **$ref:** #/components/responses/StreamMessageResponse

##### 400

- **$ref:** #/components/responses/BadRequestError

##### 401

- **$ref:** #/components/responses/UnauthorizedError

##### 403

- **$ref:** #/components/responses/ForbiddenError

##### 404

- **$ref:** #/components/responses/NotFoundError

##### 422

- **$ref:** #/components/responses/RequestProcessingException

##### 423

- **$ref:** #/components/responses/ServerBusyError

##### 429

- **$ref:** #/components/responses/TooManyRequestsError

##### 503

- **$ref:** #/components/responses/ServiceUnavailable

##### default

- **$ref:** #/components/responses/ErrorResponse




## /sessions/{session-id}

### delete

- **summary:** End an active session
- **description:** Send a message to the agent to end a session. The endpoint contains the ID of the active session, which was returned in the response of the Start Session call.
- **operationId:** endSession
#### parameters

| in | name | description | required | schema | example | allowEmptyValue |
| --- | --- | --- | --- | --- | --- | --- |
| path | session-id | The ID of the active session, which is the `sessionId` value returned from the Start Session call. | true | [object Object] |  |  |
| header | Authorization | Authorization information that contains the JWT. | true | [object Object] |  |  |
| header | x-session-end-reason | The reason the session ended. | true | [object Object] | UserRequest | false |

#### responses

##### 200

- **$ref:** #/components/responses/SendMessageSyncResponse

##### 400

- **$ref:** #/components/responses/BadRequestError

##### 401

- **$ref:** #/components/responses/UnauthorizedError

##### 403

- **$ref:** #/components/responses/ForbiddenError

##### 404

- **$ref:** #/components/responses/NotFoundError

##### 422

- **$ref:** #/components/responses/RequestProcessingException

##### 423

- **$ref:** #/components/responses/ServerBusyError

##### 429

- **$ref:** #/components/responses/TooManyRequestsError

##### 503

- **$ref:** #/components/responses/ServiceUnavailable

##### default

- **$ref:** #/components/responses/ErrorResponse




## /sessions/{session-id}/feedback

### post

- **summary:** Submit feedback
- **description:** Submit feedback for a message. Feedback data is stored in Data 360.
- **operationId:** submitFeedback
#### parameters

| in | name | description | required | schema |
| --- | --- | --- | --- | --- |
| path | session-id | The ID of the session, which is the `sessionId` value returned from the Start Session call. | true | [object Object] |
| header | Authorization | Authorization information that contains the JWT. | true | [object Object] |

#### requestBody

- **description:** The feedback payload.
- **required:** true
##### content

###### application/json

###### schema

- **$ref:** #/components/schemas/FeedbackMessage




#### responses

##### 202

- **description:** Feedback successfully accepted.

##### 400

- **$ref:** #/components/responses/BadRequestError

##### 401

- **$ref:** #/components/responses/UnauthorizedError

##### 403

- **$ref:** #/components/responses/ForbiddenError

##### 404

- **$ref:** #/components/responses/NotFoundError

##### 422

- **$ref:** #/components/responses/RequestProcessingException

##### 423

- **$ref:** #/components/responses/ServerBusyError

##### 429

- **$ref:** #/components/responses/TooManyRequestsError

##### 503

- **$ref:** #/components/responses/ServiceUnavailable

##### default

- **$ref:** #/components/responses/ErrorResponse





# components

## securitySchemes

### jwtBearer

- **type:** http
- **scheme:** bearer
- **description:** Salesforce OAuth access token obtained using the JWT Bearer flow. To learn more, see [Get Started with the Agent API](/docs/ai/agentforce/guide/agent-api-get-started.html).


## schemas

### ResponseSessionId

- **description:** Agent session ID. Use this value for the session ID when sending messages or ending a session.
- **type:** string
- **example:** 57904eb6-5352-4c5e-adf6-5f100572cf5d
- **nullable:** false

### ExternalSessionKey

- **description:** UUID that you provide for the conversation. You can use this parameter to trace the conversation in your agent's event logs.
- **type:** string
- **example:** 57904eb6-5352-4c5e-adf6-5f100572cf5d
- **nullable:** false

### StartSessionRequest

- **type:** object
#### properties

##### externalSessionKey

- **$ref:** #/components/schemas/ExternalSessionKey

##### instanceConfig

- **$ref:** #/components/schemas/InstanceConfig

##### tz

- **description:** Client timezone where the customer starts the chat. Uses the tz database timezone format. Can be null.
- **type:** string
- **example:** America/Los_Angeles

##### variables

- **$ref:** #/components/schemas/Variables

##### featureSupport

- **deprecated:** true
- **$ref:** #/components/schemas/SessionFeature

##### streamingCapabilities

- **$ref:** #/components/schemas/StreamingCapability

##### bypassUser

- **description:** Indicates whether to use the agent-assigned user instead of the logged in user. If set to `true`, the API uses the user associated with the agent. If set to `false`, the API uses the user associated with the token. Set this value to `true` when using the client credentials flow. Defaults to `false`.
- **type:** boolean
- **example:** true


#### required

- externalSessionKey
- instanceConfig


### SendMessageRequest

- **description:** Represents a send message request.
- **type:** object
#### properties

##### message

- **$ref:** #/components/schemas/AbstractRequestMessage

##### variables

- **$ref:** #/components/schemas/Variables


#### required

- message


### CancelMessage

- **description:** Represents a cancel message request.
#### allOf

| $ref | type | properties |
| --- | --- | --- |
| #/components/schemas/AbstractRequestMessage |  |  |
|  | object | [object Object] |


### ReplyMessage

- **description:** Used when answering a question with a choice of multiple records.
#### allOf

| $ref | type | properties | required |
| --- | --- | --- | --- |
| #/components/schemas/AbstractRequestMessage |  |  |  |
|  | object | [object Object] | reply |


### StartSessionSyncResponseMessage

- **type:** object
#### properties

##### sessionId

- **$ref:** #/components/schemas/ResponseSessionId

##### _links

- **$ref:** #/components/schemas/SyncLinks

##### messages

- **description:** Array of initial messages. Each message can be one of the following response message types: [Inform](?meta=type%3AInformMessage), [TextChunk](?meta=type%3ATextChunkMessage), [ValidationFailureChunk](?meta=type%3AValidationFailureChunkMessage), [ProgressIndicator](?meta=type%3AProgressIndicatorMessage), [Inquire](?meta=type%3AInquireMessage), [Confirm](?meta=type%3AConfirmMessage), [Failure](?meta=type%3AFailureMessage), [Escalate](?meta=type%3AEscalateMessage), [SessionEnded](?meta=type%3ASessionEndedMessage), [EndOfTurn](?meta=type%3AEndOfTurnMessage), [Error](?meta=type%3AErrorMessage).

- **type:** array
- **minimum:** 0
###### items

- **$ref:** #/components/schemas/AbstractResponseMessage



#### required

- sessionId
- _links
- messages


### SendMessagesSyncResponseMessage

- **type:** object
#### properties

##### messages

- **type:** array
- **description:** Array of response messages. Each message can be one of the following response message types: [Inform](?meta=type%3AInformMessage), [TextChunk](?meta=type%3ATextChunkMessage), [ValidationFailureChunk](?meta=type%3AValidationFailureChunkMessage), [ProgressIndicator](?meta=type%3AProgressIndicatorMessage), [Inquire](?meta=type%3AInquireMessage), [Confirm](?meta=type%3AConfirmMessage), [Failure](?meta=type%3AFailureMessage), [Escalate](?meta=type%3AEscalateMessage), [SessionEnded](?meta=type%3ASessionEndedMessage), [EndOfTurn](?meta=type%3AEndOfTurnMessage), [Error](?meta=type%3AErrorMessage).

- **minimum:** 0
###### items

- **$ref:** #/components/schemas/AbstractResponseMessage


##### _links

- **$ref:** #/components/schemas/SyncLinks


#### required

- messages
- _links


### FeedbackMessage

- **type:** object
#### properties

##### feedbackId

- **$ref:** #/components/schemas/FeedbackId

##### feedback

- **$ref:** #/components/schemas/FeedbackRating

##### text

- **type:** string
- **description:** Textual representation of user feedback.
- **example:** Email looks great.

##### details

- **type:** object
- **description:** Additional details to provide as key value pairs.
- **additionalProperties:** true
- **maxProperties:** 10
###### example

- **userId:** uid



#### required

- feedbackId
- feedback


### FeedbackRating

- **type:** string
- **description:** Feedback rating, suggesting a thumbs up or thumbs down.
#### enum

- GOOD
- BAD


### ServerSentEvent

- **description:** Server sent event (SSE) contents.
- **type:** object
#### properties

##### id

- **description:** Event ID.
- **type:** string
- **example:** 1692632086370-0

##### event

- **$ref:** #/components/schemas/EventType

##### retry

- **description:** Reserved for future use.
- **type:** number

##### data

- **description:** Data associated with this event.
###### oneOf

| $ref |
| --- |
| #/components/schemas/CopilotEvent |
| #/components/schemas/ErrorEvent |



#### required

- event
- data


### ErrorEvent

- **$ref:** #/components/schemas/Error

### EventType

- **description:** Type of streaming event. See [Inform](?meta=type%3AInformMessage), [TextChunk](?meta=type%3ATextChunkMessage), [ValidationFailureChunk](?meta=type%3AValidationFailureChunkMessage), [ProgressIndicator](?meta=type%3AProgressIndicatorMessage), [Inquire](?meta=type%3AInquireMessage), [Confirm](?meta=type%3AConfirmMessage), [Failure](?meta=type%3AFailureMessage), [Escalate](?meta=type%3AEscalateMessage), [SessionEnded](?meta=type%3ASessionEndedMessage), [EndOfTurn](?meta=type%3AEndOfTurnMessage), [Error](?meta=type%3AErrorMessage).
- **type:** string
#### enum

- UNKNOWN
- END_OF_TURN
- PROGRESS_INDICATOR
- INFORM
- INQUIRE
- CONFIRM
- FAILURE
- SESSION_ENDED
- ERROR
- ESCALATE
- TEXT_CHUNK


### CopilotEvent

- **description:** Event wrapper.
- **type:** object
#### properties

##### timestamp

- **description:** Event timestamp.
- **type:** number
- **example:** 1716299066

##### originEventId

- **$ref:** #/components/schemas/EventId

##### traceId

- **description:** Event trace ID.
- **type:** string
- **example:** 69feac6d79e075633486f4f722fd97c3

##### offset

- **description:** Event offset.
- **type:** number

##### message

- **$ref:** #/components/schemas/AbstractResponseMessage
- **description:** Response message. Message can be one of the following response message types: [Inform](?meta=type%3AInformMessage), [TextChunk](?meta=type%3ATextChunkMessage), [ValidationFailureChunk](?meta=type%3AValidationFailureChunkMessage), [ProgressIndicator](?meta=type%3AProgressIndicatorMessage), [Inquire](?meta=type%3AInquireMessage), [Confirm](?meta=type%3AConfirmMessage), [Failure](?meta=type%3AFailureMessage), [Escalate](?meta=type%3AEscalateMessage), [SessionEnded](?meta=type%3ASessionEndedMessage), [EndOfTurn](?meta=type%3AEndOfTurnMessage), [Error](?meta=type%3AErrorMessage).




### EndOfTurnMessage

- **description:** Represents the end of the turn.
#### allOf

| $ref |
| --- |
| #/components/schemas/AbstractResponseMessage |


### ProgressIndicatorMessage

- **description:** Represents a progress indicator.
#### allOf

| $ref | type | properties | required |
| --- | --- | --- | --- |
| #/components/schemas/AbstractResponseMessage |  |  |  |
|  | object | [object Object] | indicatorType,message |


### ProgressIndicatorType

- **type:** string
- **description:** Indicates the type of progress indicator.
- **example:** ACTION
#### enum

- ACTION


### PlanTemplateMessage

- **description:** Represents a plan template message.
#### allOf

| $ref | type | description | properties | required |
| --- | --- | --- | --- | --- |
| #/components/schemas/AbstractRequestMessage |  |  |  |  |
|  | object | Represents the type of message to be sent by client when it wants to execute an existing plan. | [object Object] | details |


### AbstractRequestMessage

- **description:** Represents the message to be sent. Can be one of the following request message types: [Text](?meta=type%3ATextMessage), [Reply](?meta=type%3AReplyMessage), [Cancel](?meta=type%3ACancelMessage), [TransferFailed](?meta=type%3ATransferFailedMessage), [TransferSucceeded](?meta=type%3ATransferSucceededMessage), [PlanTemplate](?meta=type%3APlanTemplateMessage).
- **type:** object
#### properties

##### type

- **type:** string
###### enum

- Text
- Reply
- Cancel
- TransferFailed
- TransferSucceeded
- PlanTemplate

- **description:** Request message type. Can be one of the following types: [Text](?meta=type%3ATextMessage), [Reply](?meta=type%3AReplyMessage), [Cancel](?meta=type%3ACancelMessage), [TransferFailed](?meta=type%3ATransferFailedMessage), [TransferSucceeded](?meta=type%3ATransferSucceededMessage), [PlanTemplate](?meta=type%3APlanTemplateMessage).


##### sequenceId

- **$ref:** #/components/schemas/SequenceId


#### required

- type
- sequenceId

#### example

- **type:** Text
- **sequenceId:** 1
- **text:** Can you provide a summary of my orders?


### AbstractResponseMessage

- **type:** object
- **description:** Response message. Message can be one of the following response message types: [Inform](?meta=type%3AInformMessage), [TextChunk](?meta=type%3ATextChunkMessage), [ValidationFailureChunk](?meta=type%3AValidationFailureChunkMessage), [ProgressIndicator](?meta=type%3AProgressIndicatorMessage), [Inquire](?meta=type%3AInquireMessage), [Confirm](?meta=type%3AConfirmMessage), [Failure](?meta=type%3AFailureMessage), [Escalate](?meta=type%3AEscalateMessage), [SessionEnded](?meta=type%3ASessionEndedMessage), [EndOfTurn](?meta=type%3AEndOfTurnMessage), [Error](?meta=type%3AErrorMessage).

#### properties

##### id

- **$ref:** #/components/schemas/MessageId

##### type

- **type:** string
- **description:** Indicates the type of message. Can be one of the following strings: [Inform](?meta=type%3AInformMessage), [TextChunk](?meta=type%3ATextChunkMessage), [ValidationFailureChunk](?meta=type%3AValidationFailureChunkMessage), [ProgressIndicator](?meta=type%3AProgressIndicatorMessage), [Inquire](?meta=type%3AInquireMessage), [Confirm](?meta=type%3AConfirmMessage), [Failure](?meta=type%3AFailureMessage), [Escalate](?meta=type%3AEscalateMessage), [SessionEnded](?meta=type%3ASessionEndedMessage), [EndOfTurn](?meta=type%3AEndOfTurnMessage), [Error](?meta=type%3AErrorMessage).
- **example:** Inform


#### required

- id
- type


### TextChunkMessage

- **description:** Represents a chunk of the text response.
#### allOf

| $ref | type | properties | required |
| --- | --- | --- | --- |
| #/components/schemas/AbstractResponseMessage |  |  |  |
|  | object |  |  |
|  |  | [object Object] | offset,message,formatType |


### TextFormatType

- **type:** string
- **description:** The text format type.
#### enum

- Unknown
- Text


### ValidationFailureChunkMessage

- **description:** Indicates that there was a failure validating the agent's response. If you receive a validation failure chunk, remove all previously rendered chunks and display only the new streamed content.
#### allOf

| $ref | type | properties | required |
| --- | --- | --- | --- |
| #/components/schemas/AbstractResponseMessage |  |  |  |
|  | object |  |  |
|  |  | [object Object] | offset |


### InformMessage

- **description:** Informs caller of response.
#### allOf

| $ref | type | properties | required |
| --- | --- | --- | --- |
| #/components/schemas/AbstractResponseMessage |  |  |  |
|  | object | [object Object] | message,isContentSafe,feedbackId |


### InquireMessage

- **description:** Indicates that more information is required.
#### allOf

| $ref | type | properties | required |
| --- | --- | --- | --- |
| #/components/schemas/AbstractResponseMessage |  |  |  |
|  | object | [object Object] | feedbackId,collect |


### InquireCollectMessage

- **type:** object
- **description:** Inquire type
#### properties

##### targetType

- **$ref:** #/components/schemas/TargetTypeId

##### targetProperty

- **$ref:** #/components/schemas/TargetPropertyId

##### data

- **$ref:** #/components/schemas/SourceTypeMessage


#### required

- targetType


### ConfirmMessage

- **description:** Indicates that the agent is asking the user to verify that an action should be taken.
#### allOf

| $ref | type | properties | required |
| --- | --- | --- | --- |
| #/components/schemas/AbstractResponseMessage |  |  |  |
|  | object | [object Object] | feedbackId,confirm |


### ErrorMessage

- **description:** Indicates there was an error in the response.
#### allOf

| $ref | type | properties | required |
| --- | --- | --- | --- |
| #/components/schemas/AbstractResponseMessage |  |  |  |
|  | object | [object Object] | feedbackId,httpStatus,error,message,expected |


### SessionFeature

- **type:** string
- **description:** Defines how the session supports message processing.
- **example:** Sync
#### enum

- Sync
- Streaming


### ChunkType

- **description:** Defines the types of stream chunks you'd like to receive when streaming.
- **type:** string
#### enum

- Text


### StreamingCapability

- **type:** object
- **description:** Describes the streaming capabilities.
#### properties

##### chunkTypes

- **type:** array
- **description:** Array of chunk types.
- **minimum:** 0
###### items

- **$ref:** #/components/schemas/ChunkType




### RichContentCapability

- **type:** object
#### properties

##### messageTypes

- **type:** array
- **minimum:** 1
###### items

- **$ref:** #/components/schemas/MessageTypeCapability



#### required

- messageTypes


### MessageTypeCapability

- **type:** object
#### properties

##### messageType

- **$ref:** #/components/schemas/MessageType

##### formatTypes

- **type:** array
- **minimum:** 1
###### items

- **$ref:** #/components/schemas/FormatTypeCapability



#### required

- messageType
- formatTypes


### FormatTypeCapability

- **type:** object
#### properties

##### formatType

- **$ref:** #/components/schemas/FormatType


#### required

- formatType


### MessageType

- **description:** Message type that supports rich content output formats.
* `ChoicesMessage`: Represents multiple choice content.

- **type:** string
#### enum

- ChoicesMessage

- **example:** ChoicesMessage

### FormatType

- **type:** string
- **description:** The rendering format of a message. Describes how the message looks.
- **example:** MessageDefinition
#### enum

- MessageDefinition
- Text


### PlanId

- **type:** string
- **description:** Unique ID to identify the plan.
- **example:** 9247bbd8-5ed9-11ee-8c99-0242ac120002

### ContentSafety

- **type:** boolean
- **description:** Indicates whether the content is deemed as safe. A false value doesn't necessarily mean that the content isn't toxic.
- **example:** true

### CitedReference

- **type:** object
#### properties

##### type

- **type:** string
- **description:** Type of citation. This value can be either a CRM record (`record`) or an external link (`link`).
###### enum

- record
- link


##### value

- **type:** string
- **description:** External link address.

##### recordId

- **type:** string
- **description:** Salesforce org record ID.

##### label

- **type:** string
- **description:** UI label for citation.

##### inlineMetadata

- **description:** Inline metadata information used for inline citations.
- **type:** array
###### items

- **$ref:** #/components/schemas/InlineReferenceMetadata



#### required

- type
- value


### InlineReferenceMetadata

- **type:** object
#### properties

##### claim

- **type:** string
- **description:** Text from the agent response relevant to this reference.

##### location

- **type:** integer
- **description:** Index location for where this citation should be placed.


#### required

- claim
- location


### SourceTypeMessage

- **type:** object
- **description:** Bundle for a source type.
#### properties

##### type

- **$ref:** #/components/schemas/SourceTypeId

##### property

- **$ref:** #/components/schemas/SourcePropertyId

##### value

- **$ref:** #/components/schemas/TypeValue


#### required

- type
- value


### SourceTypeId

- **type:** string
- **description:** The action type ID. See [Agent Actions](https://help.salesforce.com/s/articleView?id=ai.copilot_actions.htm).
- **example:** copilotActionOutput/EmployeeCopilot__UpdateRecordFields

### SourcePropertyId

- **type:** string
- **description:** The action property ID. See [Agent Actions](https://help.salesforce.com/s/articleView?id=ai.copilot_actions.htm).
- **example:** result

### TargetTypeId

- **type:** string
- **description:** The action type ID. See [Agent Actions](https://help.salesforce.com/s/articleView?id=ai.copilot_actions.htm).
- **example:** @aiFunctionInput/BookFlight

### TargetTypeMessage

- **type:** object
- **description:** Bundle for a target type.
#### properties

##### type

- **$ref:** #/components/schemas/TargetTypeId

##### property

- **$ref:** #/components/schemas/TargetPropertyId

##### value

- **$ref:** #/components/schemas/TypeValue


#### required

- type
- value


### TargetPropertyId

- **type:** string
- **description:** The action property ID. See [Agent Actions](https://help.salesforce.com/s/articleView?id=ai.copilot_actions.htm).
- **example:** flightInfo

### TypeValue

- **description:** A type value.
- **example:** a free form string or an object or an array

### MessageId

- **description:** UUID that references this message.
- **type:** string
- **example:** a133c185-73a7-4adf-b6d9-b7fd62babb4e

### SequenceId

- **description:** Client-generated sequence number of the message in a session. Increase this number for each subsequent message.
- **type:** number
- **example:** 1

### SyncLinks

- **description:** List of Agentforce endpoints for HATEOS compliance.
- **type:** object
#### properties

##### self

- **$ref:** #/components/schemas/HyperLink

##### messages

- **$ref:** #/components/schemas/HyperLink

##### session

- **$ref:** #/components/schemas/HyperLink

##### end

- **$ref:** #/components/schemas/HyperLink


#### required

- self


### HyperLink

- **description:** Hyperlink object included in the links schema.
- **type:** object
#### properties

##### href

- **description:** Link to the endpoint.
- **type:** string
- **example:** https://api.salesforce.com/sessions



### InReplyToMessageId

- **description:** Message ID of the previous response you are replying to.
- **type:** string
- **example:** a133c185-73a7-4adf-b6d9-b7fd62babb4e

### Variables

- **type:** array
- **description:** Array of custom and context agent variables passed to the agent during a session. See [Agent Variables](https://help.salesforce.com/s/articleView?id=ai.agent_variables.htm). Many variables are read-only and can only be set during the start session call. By default, context variables (which have the `$Context` prefix) aren't editable after the session has started, except for the `$Context.EndUserLanguage` variable. You can only modify editable variables during a send message call. When specifying variables that are derived from custom fields, omit the `__c` suffix. For instance, `Conversation_Key__c` becomes `$Context.Conversation_Key`. This array can be null.
#### items

- **$ref:** #/components/schemas/Variable


### Variable

- **description:** Custom or context variable passed to the agent during a session. See [Agent Variables](https://help.salesforce.com/s/articleView?id=ai.agent_variables.htm). Many variables are read-only and can only be set during the start session call. By default, context variables (which have the `$Context` prefix) aren't editable after the session has started, except for the `$Context.EndUserLanguage` variable. You can only modify editable variables during a send message call. When specifying variables that are derived from custom fields, omit the `__c` suffix. For instance, `Conversation_Key__c` becomes `$Context.Conversation_Key`.
- **type:** object
#### properties

##### name

- **description:** API name for the agent variable.
- **type:** string
- **example:** $Context.EndUserLanguage

##### type

- **description:** Variable type.
- **type:** string
- **example:** Text
###### enum

- Object
- Json
- Boolean
- Date
- DateTime
- Money
- Number
- Text
- Ref
- List


##### value

- **description:** Variable value.
- **type:** string
- **example:** en_US


#### required

- name
- type
- value


### BooleanVariable

#### allOf

| $ref | type | properties | required |
| --- | --- | --- | --- |
| #/components/schemas/Variable |  |  |  |
|  | object | [object Object] | value |


### DateVariable

#### allOf

| $ref | type | properties | required |
| --- | --- | --- | --- |
| #/components/schemas/Variable |  |  |  |
|  | object | [object Object] | value |


### DateTimeVariable

#### allOf

| $ref | type | properties | required |
| --- | --- | --- | --- |
| #/components/schemas/Variable |  |  |  |
|  | object | [object Object] | value |


### MoneyVariable

#### allOf

| $ref | type | properties | required |
| --- | --- | --- | --- |
| #/components/schemas/Variable |  |  |  |
|  | object | [object Object] | value |


### NumberVariable

#### allOf

| $ref | type | properties | required |
| --- | --- | --- | --- |
| #/components/schemas/Variable |  |  |  |
|  | object | [object Object] | value |


### TextVariable

#### allOf

| $ref | type | properties | required |
| --- | --- | --- | --- |
| #/components/schemas/Variable |  |  |  |
|  | object | [object Object] | value |


### ObjectVariable

#### allOf

| $ref | type | properties | required |
| --- | --- | --- | --- |
| #/components/schemas/Variable |  |  |  |
|  | object | [object Object] | value |


### RefVariable

#### allOf

| $ref | type | properties | required |
| --- | --- | --- | --- |
| #/components/schemas/Variable |  |  |  |
|  | object | [object Object] | value |


### ListVariable

#### allOf

| $ref | type | properties | required |
| --- | --- | --- | --- |
| #/components/schemas/Variable |  |  |  |
|  | object | [object Object] | value |


### JsonVariable

#### allOf

| $ref | type | properties | required |
| --- | --- | --- | --- |
| #/components/schemas/Variable |  |  |  |
|  | object | [object Object] | value |


### Referrer

- **type:** object
#### properties

##### type

- **description:** Referrer type.
- **type:** string
###### enum

- Salesforce:Core:Bot:Id
- Salesforce:BotRuntime:Session:Id

- **example:** Salesforce:Core:Bot:Id

##### value

- **type:** string
- **description:** ID of referrer.
- **example:** string


#### required

- type
- value


### TransferFailedMessage

- **description:** Represents a transfer failed message.
#### allOf

| $ref | type | properties | required |
| --- | --- | --- | --- |
| #/components/schemas/AbstractRequestMessage |  |  |  |
|  | object | [object Object] | reason |


### TransferSucceededMessage

- **description:** Represents a transfer succeeded message.
#### allOf

| $ref | type | properties |
| --- | --- | --- |
| #/components/schemas/AbstractRequestMessage |  |  |
|  | object | [object Object] |


### EndSessionReason

- **type:** string
#### enum

- UserRequest
- Transfer
- Expiration
- Error
- Other

- **example:** Transfer
- **nullable:** false

### TextMessage

- **description:** Represents a text request.
#### allOf

| $ref | type | properties | required |
| --- | --- | --- | --- |
| #/components/schemas/AbstractRequestMessage |  |  |  |
|  | object | [object Object] | text |


### SessionEndedMessage

- **description:** Indicates the session has ended.
#### allOf

| $ref | type | properties | required |
| --- | --- | --- | --- |
| #/components/schemas/AbstractResponseMessage |  |  |  |
|  | object | [object Object] | reason |


### FailureMessage

- **description:** Indicates that something didn't execute properly.
#### allOf

| $ref | type | properties | required |
| --- | --- | --- | --- |
| #/components/schemas/AbstractResponseMessage |  |  |  |
|  | object | [object Object] | feedbackId,code |


### EscalateMessage

- **description:** Indicates that a human rep should handle this request. The escalation message is automatically translated based on the end user's language setting. If the language isn't supported, the original message is returned without translation.
#### allOf

| $ref | type | properties | required |
| --- | --- | --- | --- |
| #/components/schemas/AbstractResponseMessage |  |  |  |
|  | object | [object Object] | feedbackId,targets |


### InstanceConfig

- **type:** object
- **description:** API configuration parameters.
#### properties

##### endpoint

- **description:** My Domain URL for your Salesforce org. From Setup, search for My Domain. Copy the value shown in the Current My Domain URL field. See [Get Started with Agent API](/docs/ai/agentforce/guide/agent-api-get-started.html).
- **type:** string
- **example:** https://d5e000009s7bceah-dev-ed.my.salesforce.com/


#### required

- endpoint


### FeedbackId

- **type:** string
- **description:** Unique ID to identify the generation. Used to submit feedback.
- **example:** 9247bbd8-5ed9-11ee-8c99-0242ac120002

### EventId

- **type:** string
- **description:** Unique ID to identify the event.
- **example:** auMZc8ZRv37sIW2iJKq3M9MFx1YvV11A2x

### Status

- **type:** object
#### properties

##### status

- **type:** string
- **description:** Health status of Agent API.
###### enum

- UP
- DOWN

- **example:** UP


#### required

- status


### Error

- **type:** object
#### properties

##### status

- **description:** HTTP status.
- **type:** integer
- **format:** int32

##### path

- **description:** Request path.
- **type:** string

##### requestId

- **description:** Request ID. A UUID in string format to help with request tracking.
- **type:** string

##### error

- **description:** Error class name.
- **type:** string

##### message

- **description:** Exception message.
- **type:** string

##### timestamp

- **description:** Unix timestamp.
- **type:** number


#### required

- status
- path
- requestId
- error
- message
- timestamp

#### example

- **status:** 500
- **path:** /agents/00DRM00000067To/messages
- **requestId:** 19c056ab-d909-49df-b976-65e56b6ab214
- **error:** InactiveConfigException
- **message:** Config is not active
- **timestamp:** 1531245973799



## responses

### StatusResponse

- **description:** OK
#### content

##### application/json

###### schema

- **$ref:** #/components/schemas/Status




### ErrorResponse

- **description:** Something went wrong
#### content

##### application/json

###### schema

- **$ref:** #/components/schemas/Error



#### headers

##### X-Request-ID

- **description:** Request ID. A UUID in string format to help with request tracking.
- **example:** 36a73651-a46d-4d16-9a8a-fd436ed62e1a
###### schema

- **type:** string




### StartSessionResponse

- **description:** Response to a new session.
#### content

##### application/json

###### schema

- **$ref:** #/components/schemas/StartSessionSyncResponseMessage



#### headers

##### x-session-mode

- **description:** Agent session mode.
- **example:** default
###### schema

- **type:** string




### SendMessageSyncResponse

- **description:** Batched Response (Headless)
#### content

##### application/json

###### schema

- **$ref:** #/components/schemas/SendMessagesSyncResponseMessage




### StreamMessageResponse

- **description:** OK
#### content

##### text/event-stream

###### schema

- **$ref:** #/components/schemas/ServerSentEvent




### BadRequestError

- **description:** Bad Request
#### content

##### application/json

###### schema

- **$ref:** #/components/schemas/Error

###### example

- **status:** 400
- **path:** /v6/00DRM00000067To/sessions/HelloWorldBot/messages
- **requestId:** 19c056ab-d909-49df-b976-65e56b6ab214
- **error:** BadRequestError
- **message:** Bad Request
- **timestamp:** 1531245973799



#### headers

##### X-Request-ID

- **description:** Request ID. A UUID in string format to help with request tracking.
- **example:** 36a73651-a46d-4d16-9a8a-fd436ed62e1a
###### schema

- **type:** string




### UnauthorizedError

- **description:** Access bearer token is missing or invalid
#### content

##### application/json

###### schema

- **$ref:** #/components/schemas/Error

###### example

- **status:** 401
- **path:** /v1/00DRM00000067To/chatbots/HelloWorldBot/messages
- **requestId:** 19c056ab-d909-49df-b976-65e56b6ab214
- **error:** UnauthorizedError
- **message:** Access bearer token is missing or invalid
- **timestamp:** 1531245973799



#### headers

##### X-Request-ID

- **description:** Request ID. A UUID in string format to help with request tracking.
- **example:** 36a73651-a46d-4d16-9a8a-fd436ed62e1a
###### schema

- **type:** string




### ForbiddenError

- **description:** User forbidden from accessing the resource
#### content

##### application/json

###### schema

- **$ref:** #/components/schemas/Error

###### example

- **status:** 403
- **path:** /v1/00DRM00000067To/chatbots/HelloWorldBot/messages
- **requestId:** 19c056ab-d909-49df-b976-65e56b6ab214
- **error:** ForbiddenError
- **message:** User forbidden from accessing the resource
- **timestamp:** 1531245973799



#### headers

##### X-Request-ID

- **description:** Request ID. A UUID in string format to help with request tracking.
- **example:** 36a73651-a46d-4d16-9a8a-fd436ed62e1a
###### schema

- **type:** string




### NotFoundError

- **description:** Resource not found
#### content

##### application/json

###### schema

- **$ref:** #/components/schemas/Error

###### example

- **status:** 404
- **path:** /v1/00DRM00000067To/chatbots/HelloWorldBot/messages
- **requestId:** 19c056ab-d909-49df-b976-65e56b6ab214
- **error:** NotFoundError
- **message:** Resource not found
- **timestamp:** 1531245973799



#### headers

##### X-Request-ID

- **description:** Request ID. A UUID in string format to help with request tracking.
- **example:** 36a73651-a46d-4d16-9a8a-fd436ed62e1a
###### schema

- **type:** string




### NotAvailableError

- **description:** Resource not available at the time of the request
#### content

##### application/json

###### schema

- **$ref:** #/components/schemas/Error

###### example

- **status:** 410
- **path:** /v1/00DRM00000067To/chatbots/HelloWorldBot/messages
- **requestId:** 19c056ab-d909-49df-b976-65e56b6ab214
- **error:** NotAvailableError
- **message:** Resource not available at the time of the request
- **timestamp:** 1531245973799



#### headers

##### X-Request-ID

- **description:** Request ID. A UUID in string format to help with request tracking.
- **example:** 36a73651-a46d-4d16-9a8a-fd436ed62e1a
###### schema

- **type:** string




### RequestProcessingException

- **description:** Any exception that occurred during the request execution
#### content

##### application/json

###### schema

- **$ref:** #/components/schemas/Error

###### example

- **status:** 422
- **path:** v4.0.0/messages
- **requestId:** 19c056ab-d909-49df-b976-65e56b6ab214
- **error:** RequestProcessingException
- **message:** Cannot determine the active version for the agent
- **timestamp:** 1531245973799



#### headers

##### X-Request-ID

- **description:** Request ID. A UUID in string format to help with request tracking.
- **example:** 36a73651-a46d-4d16-9a8a-fd436ed62e1a
###### schema

- **type:** string




### ServerBusyError

- **description:** Server is busy and cannot process the request at this time
#### content

##### application/json

###### schema

- **$ref:** #/components/schemas/Error

###### example

- **status:** 423
- **path:** /v1/00DRM00000067To/chatbots/HelloWorldBot/messages
- **requestId:** 19c056ab-d909-49df-b976-65e56b6ab214
- **error:** ServerBusyError
- **message:** Server is busy and cannot process the request at this time
- **timestamp:** 1531245973799



#### headers

##### X-Request-ID

- **description:** Request ID. A UUID in string format to help with request tracking.
- **example:** 36a73651-a46d-4d16-9a8a-fd436ed62e1a
###### schema

- **type:** string




### TooManyRequestsError

- **description:** Too many requests for the server to handle
#### content

##### application/json

###### schema

- **$ref:** #/components/schemas/Error

###### example

- **status:** 429
- **path:** /v1/00DRM00000067To/chatbots/HelloWorldBot/messages
- **requestId:** 19c056ab-d909-49df-b976-65e56b6ab214
- **error:** TooManyRequestsError
- **message:** Too many requests for the server to handle
- **timestamp:** 1531245973799



#### headers

##### X-Request-ID

- **description:** Request ID. A UUID in string format to help with request tracking.
- **example:** 36a73651-a46d-4d16-9a8a-fd436ed62e1a
###### schema

- **type:** string




### ServiceUnavailable

- **description:** Service is unavailable possibly because Apex or Flow calls timed out
#### content

##### application/json

###### schema

- **$ref:** #/components/schemas/Error

###### example

- **status:** 503
- **path:** /v1/00DRM00000067To/chatbots/HelloWorldBot/messages
- **requestId:** 19c056ab-d909-49df-b976-65e56b6ab214
- **error:** ServiceUnavailable
- **message:** Service is unavailable possibly because Apex/Flow calls timed out
- **timestamp:** 1531245973799



#### headers

##### X-Request-ID

- **description:** Request ID. A UUID in string format to help with request tracking.
- **example:** 36a73651-a46d-4d16-9a8a-fd436ed62e1a
###### schema

- **type:** string










<!--stackedit_data:
eyJoaXN0b3J5IjpbMTI2NTc1ODY5LDMwNjc1NDc1OCwtMTQ0Mj
I4MTU0LDE4NDYzODU3NjIsMTkzNDg2MTUyMiw5MDA0NDU2MjIs
MzUzNDcwNTMyLC0xODU1MzY2MDAzLC0xNTEyMjg0MjMyLDE4NT
kyNjg1MzUsNDQ4MTQ5MTMzLC0xNTU1MDkyNTEwXX0=
-->