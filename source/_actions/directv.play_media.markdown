---
title: "Play specified media"
action: media_player.play_media
domain: directv
description: "Changes the channel on a DirecTV receiver."
---

Use this action to change the channel on a DirecTV receiver from an automation or script.

{% include actions/ui_header.md %}

To change a DirecTV channel from an automation or a script:

1. Go to {% my automations title="**Settings** > **Automations & scenes**" %}.
2. Open an existing automation or script, or select **Create automation** > **Create new automation**.
3. If you're setting up a new automation, add a trigger in the **When** section. Scripts don't need a trigger. They run when something else calls them.
4. In the **Then do** section, select **Add action**.
5. Select what you want to control. Under **By target** (see [Targets](#targets)), select the DirecTV media player.
6. From the actions shown for that target, select **Play specified media**.
7. Enter the channel number as the **Media content ID** and use `channel` as the **Media content type**.
8. Select **Save**.

### Options in the UI

{% options_ui %}
Media content ID:
  description: The channel number to change to.
Media content type:
  description: The media type. Use `channel`.
{% endoptions_ui %}

{% include actions/yaml_header.md %}

In YAML, refer to this action as `media_player.play_media`. A basic example looks like this:

{% example %}
action: |
  action: media_player.play_media
  target:
    entity_id: media_player.directv_receiver
  data:
    media_content_id: "202"
    media_content_type: channel
{% endexample %}

This changes `media_player.directv_receiver` to channel 202.

### Options in YAML

{% options_yaml %}
media_content_id:
  description: The channel number to change to.
  required: true
  type: string
media_content_type:
  description: The media type. Use `channel`.
  required: true
  type: string
{% endoptions_yaml %}

{% include actions/targets.md domain="media_player" %}

## Good to know

- The channel must be available on the DirecTV receiver.
- DirecTV also supports standard media player actions, such as play, pause, stop, next track, previous track, turn on, and turn off, depending on the receiver.

{% include actions/stuck.md %}

{% include actions/related.md %}
