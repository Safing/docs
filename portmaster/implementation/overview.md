---
title: Implementation Overview
layout: base
---

Before diving into details it is important to understand the big picture. Just as any machine, the Portmaster has many parts and gears that have to work together seamlessly to deliver the privacy you deserve. Take a look:

![Portmaster Big Picture](/assets/images/big_picture.jpg)

### User Interface

The User Interface allows you to seamlessly interact with the Portmaster's technical might. Easily view activities on your device, configure settings or define rules.

[Read all about how this is implemented](/portmaster/implementation/user-interface/)

### Modules

Where the heavy lifting happens. The `core` module contains most of the groundwork while the other modules make use and build on top of the `core` to implement various privacy features.

[Dive deep into the Portmaster's technology](/portmaster/implementation/modules/core/)

### Logging

Every component writes logs so you understand what is going on. This also can crucially help us when debugging issues that arise.

[Find out how this is achieved](/portmaster/implementation/logs/)