---
layout: default
title: Permitted Licenses & Use Cases
nav_order: 4
parent: Using Open Source Code
---

# Permitted Licenses & Use Cases

The licenses permitted for use in a particular software project depend heavily on the way in which the OSS will be used and what sort of project it is to be used in.

## Use cases

Typical use cases are defined as following. If you are not certain which cateogy your use case falls into, or indeed if it falls into any, contact the SDRB for advice.

### Internal use

If an application is only ever intended to be used internally to Power and will, with absolute certainty, never be used outside of the company, it would fall into this case. This requires some barrier to use by the outside world, such as maintaining the application behind the firewall and not exposed to the public internet, for example.

### SaaS (web apps)

This use case covers Power applications which are provided as a service, either to internal users, customers, or other external users. Nitro is an example of this use case, rather than "Internal use", because it powers interactions with customers and partners, in addition to Power employees.

This use-case has two parts:

#### Back-end

This covers elements of SaaS where the implementation is executed on servers operated by Power. This covers things like Ruby code in Rails applications, for example.

#### Front-end

This covers elements of SaaS where the code is shipped to browsers for execution, including Javascript and CSS.

### Mobile / Desktop App

This use case covers software which is delivered in binary format for execution on a user's device, such as our mobile applications.

## Permitted licenses

The following licenses are permitted for use for each category of use case. Any licenses not on this list are not yet permitted for use at Power, but will be considered for inclusion in this list on request to the SDRB. If you propose to use an open source project licensed under any license not present in this list, contact the SDRB. If you propose to use an open source project in a way not permitted by this combination of license and use case, contact the SDRB to discuss the available options.

| License | SPDX Identifier | Internal use | SaaS back-end | SaaS front-end | Mobile / Desktop App |
| ------- | --------------- | ------------ | ------------- | -------------- | -------------------- |
| Apache License 2.0 | Apache-2.0 | ✅ | ✅ | ✅ | ✅ |
| Berkeley Software Distribution (BSD) 3-clause | BSD-3-Clause | ✅ | ✅ | ✅ | ✅ |
| Berkeley Software Distribution (BSD) 2-clause | BSD-2-Clause | ✅ | ✅ | ✅ | ✅ |
| Common Development and Distribution License 1.0 | CDDL-1.0 | ✅ | ✅ | ✅ | ✅ |
| Creative Commons Zero v 1.0 Universal | CC0-1.0 | ✅ | ✅ | ✅ | ✅ |
| ISC License | ISC | ✅ | ✅ | ✅ | ✅ |
| MIT License | MIT | ✅ | ✅ | ✅ | ✅ |
| Mozilla Public License 1.0 | MPL-1.0 | ✅ | ✅ | ✅ | ✅ |
| Mozilla Public License 1.1 | MPL-1.1 | ✅ | ✅ | ✅ | ✅ |
| Mozilla Public License 2.0 | MPL-2.0 | ✅ | ✅ | ✅ | ✅ |
| GNU Affero General Public License version 3 | AGPL-3.0 | 🚫 | 🚫 | 🚫 | 🚫 |
| GNU General Public License version 2 | GPL-2.0 | ✅ | ✅ | 🚫 | 🚫 |
| GNU General Public License version 3 | GPL-3.0 | ✅ | ✅ | 🚫 | 🚫 |
| GNU Lesser General Public License version 2.1 | LGPL-2.1 | ✅ | ✅ | 🚫 | 🚫 |
| GNU Lesser General Public License version 3 | LGPL-3.0 | ✅ | ✅ | 🚫 | 🚫 |

## Enforcement

Power projects which use open-source software should enforce the exclusive utilisation of [permitted licenses by use-case](../using/permitted-licenses.md). Further details on how to achieve this, including standardised tooling and configuration, are coming soon.
