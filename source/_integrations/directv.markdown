---
title: DirecTV
description: Instructions on how to integrate DirecTV receivers into Home Assistant.
ha_category:
  - Media player
  - Remote
ha_release: 0.25
ha_iot_class: Local Polling
ha_domain: directv
ha_config_flow: true
ha_ssdp: true
ha_platforms:
  - media_player
  - remote
ha_integration_type: hub
---

The **DirecTV** {% term integration %} allows you to control a [DirecTV](https://www.directv.com) receiver and its client devices.

## Requirements

For proper integration with Home Assistant, your DirecTV device settings should allow "External Access".

This is done via series of settings found via **Menu** > **Settings & Help** > **Settings** > **Whole Home** > **External Device**:

- External Access: Allow
- Current Program: Allow
- Recordings: Allow

{% include integrations/config_flow.md %}

{% include integrations/actions.md %}

## Remote

The DirecTV remote platform allows you to send remote control buttons to a DirecTV receiver. It is automatically set up when a DirecTV receiver is configured. Use the [Send remote command](/actions/directv.send_command/) action to send commands.
