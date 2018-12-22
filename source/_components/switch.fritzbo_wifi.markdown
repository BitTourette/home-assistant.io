---
layout: page
title: "Fritzbox (Guest) Wifi Switch"
description: "Instructions on how to integrate the Fritzbox (Guest) wifi as switch."
date: 2018-12-22 04:10
sidebar: true
comments: false
sharing: true
footer: true
logo: avm.png
ha_category: Switch
ha_iot_class: "Local Polling"
---

Fritzbox Wifi switch. 

{% linkable_title Configuration %}

`configuration.yaml` file:

```yaml
# Example configuration.yaml entry
switch:
  - platform: fritzbox_wifi
    host: ip-of-your-fritzbox
    password: "password"
    name: "name-of-the-switch"
    interface: 3
```
If you have more than 1 Fritzbox you can set up multiple switches and/or setup one switch for 2.4GHz/5GHz and Guest Wifi

{% configuration %}
host:
  description: IP of yout Fritzbox
  required: false
  default: 169.254.1.1
  type: string
password:
  description: Login password of your Fritzbox
  required: true
  type: string
name:
  description: The name of the virtual WiFi switch
  required: false
  default: Guest Wifi
  type: string
interface:
  description: Interface number you want do switch on/off. Mostly modern Fritzboxes will have 3 Wifi Cards (2.4GHz ->1, 5Ghz -> 2, Guest Wifi -> 3). For older ones you have to cange it to '2'
  required: false
  default: 3
  type: integer
port:
  description: API Port
  required: false
  default: 49000
  type: integer
{% endconfiguration %}
