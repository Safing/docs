---
title: OS Integration
section: gate17
order: 10
layout: base
updated: old
---

## General

Please refer to the [corresponding Portmaster Docs](/docs/portmaster/os-integration.html) for this section.

## Windows

##### Kernel Extension

We are currently developing a kernel extension for integration with the Windows kernel. _(update coming soon)_

## macOS

_coming soon_

## Linux

On Linux we aim to provide two ways of OS integration:

##### iptables {% include code_ref.html github-portmaster="firewall/interception/nfqueue" %}

If DNS is resolved for a connection, Portmaster replies with an IP address in the `127.17/16` range. This enables the Portmaster to distinguish between domains even if they resolve to the same IP address.
These connections are then rerouted to the Gate17 entry point (`127.0.0.17:1117`) by marking them with `1717`.

If connecting to an IP address directly, the Portmaster marks the connection with `1717` and the iptables rules below will redirect the connection.

Three additonal rules are added to the iptables main chains:
```
nat OUTPUT -m mark --mark 1717 -p {tcp|udp} -j DNAT --to-destination 127.0.0.17:1117
nat OUTPUT -m mark --mark 1717 -j DNAT --to-destination 127.0.0.17
```

##### kernel module

We will provide an alternative to `iptables` by writing a kernel module to handle the needed packet interception in the future. Depending on the performance and stability of the `iptables` integration this might come sooner or later.
