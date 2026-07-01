---
title: "Send remote command"
action: remote.send_command
domain: directv
description: "Sends remote control commands to a DirecTV receiver."
---

Use this action to send one or more remote control button commands to a DirecTV receiver.

{% include actions/ui_header.md %}

To send a DirecTV remote command from an automation or a script:

1. Go to {% my automations title="**Settings** > **Automations & scenes**" %}.
2. Open an existing automation or script, or select **Create automation** > **Create new automation**.
3. If you're setting up a new automation, add a trigger in the **When** section. Scripts don't need a trigger. They run when something else calls them.
4. In the **Then do** section, select **Add action**.
5. Select what you want to control. Under **By target** (see [Targets](#targets)), select the DirecTV remote.
6. From the actions shown for that target, select **Send remote command**.
7. Enter a command, or enter a list of commands.
8. Select **Save**.

### Options in the UI

{% options_ui %}
Command:
  description: The command to send. You can also enter a list of commands.
Repeats:
  description: How many times to repeat the command.
  required: false
  default: 1
Delay seconds:
  description: The delay between repeated commands.
  required: false
  default: 0.4
Hold seconds:
  description: How long to hold the command.
  required: false
  default: 0
{% endoptions_ui %}

{% include actions/yaml_header.md %}

In YAML, refer to this action as `remote.send_command`. A basic example looks like this:

{% example %}
action: |
  action: remote.send_command
  target:
    entity_id: remote.directv_receiver
  data:
    command:
      - left
      - left
      - menu
      - select
{% endexample %}

This sends four button commands to `remote.directv_receiver`.

### Options in YAML

{% options_yaml %}
command:
  description: The command to send. You can also provide a list of commands.
  required: true
  type: string
num_repeats:
  description: How many times to repeat the command.
  required: false
  type: integer
  default: 1
delay_secs:
  description: The delay between repeated commands.
  required: false
  type: float
  default: 0.4
hold_secs:
  description: How long to hold the command.
  required: false
  type: float
  default: 0
{% endoptions_yaml %}

{% include actions/targets.md domain="remote" %}

## Good to know

The commands available to you depend on the DirecTV receiver.

## Supported commands

- `power`
- `poweron`
- `poweroff`
- `format`
- `pause`
- `rew`
- `replay`
- `stop`
- `advance`
- `ffwd`
- `record`
- `play`
- `guide`
- `active`
- `list`
- `exit`
- `back`
- `menu`
- `info`
- `up`
- `down`
- `left`
- `right`
- `select`
- `red`
- `green`
- `yellow`
- `blue`
- `chanup`
- `chandown`
- `prev`
- `0`
- `1`
- `2`
- `3`
- `4`
- `5`
- `6`
- `7`
- `8`
- `9`
- `dash`
- `enter`

{% include actions/stuck.md %}

{% include actions/related.md %}
