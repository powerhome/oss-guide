---
layout: default
title: Permitted Licenses & Use Cases
nav_order: 4
parent: Using Open Source Code
---

# Permitted Licenses & Use Cases

The licenses permitted for use in a particular software project depend heavily on the way in which the OSS will be used and what sort of project it is to be used in.

## Use cases

Typical use cases are defined as following. If you are not certain which cateogy your use case falls into, or indeed if it falls into any, contact the SDRT for advice.

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

The following licenses are permitted for use for each category of use case. Any licenses not on this list are not yet permitted for use at Power, but will be considered for inclusion in this list on request to the SDRT. If you propose to use an open source project licensed under any license not present in this list, contact the SDRT. If you propose to use an open source project in a way not permitted by this combination of license and use case, contact the SDRT to discuss the available options.

| License | SPDX Identifier | Internal use | SaaS back-end | SaaS front-end | Mobile / Desktop App |
| ------- | --------------- | ------------ | ------------- | -------------- | -------------------- |
| Apache License 2.0 | Apache-2.0 | ✅ | ✅ | ✅ | ✅ |
| Artistic License 2.0 | Artistic-2.0 | ✅ | ✅ | 🚫 | 🚫 |
| Berkeley Software Distribution (BSD) 3-clause | BSD-3-Clause | ✅ | ✅ | ✅ | ✅ |
| Berkeley Software Distribution (BSD) 2-clause | BSD-2-Clause | ✅ | ✅ | ✅ | ✅ |
| Common Development and Distribution License 1.0 | CDDL-1.0 | ✅ | ✅ | ✅ | ✅ |
| Creative Commons Attribution 3.0 International | CC-BY-3.0 | ✅ | ✅ | ✅ | ✅ |
| Creative Commons Attribution 4.0 International | CC-BY-4.0 | ✅ | ✅ | ✅ | ✅ |
| Creative Commons Zero v 1.0 Universal | CC0-1.0 | ✅ | ✅ | ✅ | ✅ |
| GNU Affero General Public License version 3 | AGPL-3.0 | 🚫 | 🚫 | 🚫 | 🚫 |
| GNU General Public License version 2 | GPL-2.0 | ✅ | ✅ | 🚫 | 🚫 |
| GNU General Public License version 3 | GPL-3.0 | ✅ | ✅ | 🚫 | 🚫 |
| GNU Lesser General Public License version 2.1 | LGPL-2.1 | ✅ | ✅ | 🚫 | 🚫 |
| GNU Lesser General Public License version 3 | LGPL-3.0 | ✅ | ✅ | 🚫 | 🚫 |
| ISC License | ISC | ✅ | ✅ | ✅ | ✅ |
| MIT License | MIT | ✅ | ✅ | ✅ | ✅ |
| Mozilla Public License 1.0 | MPL-1.0 | ✅ | ✅ | ✅ | ✅ |
| Mozilla Public License 1.1 | MPL-1.1 | ✅ | ✅ | ✅ | ✅ |
| Mozilla Public License 2.0 | MPL-2.0 | ✅ | ✅ | ✅ | ✅ |
| Python License 2.0 | Python-2.0 | ✅ | ✅ | ✅ | ✅ |
| Ruby License | Ruby | ✅ | ✅ | ✅ | ✅ |
| Open Data Commons Attribution License v1.0 | ODC-By-1.0 | ✅ | ✅ | ✅ | ✅ |
| The Unlicense | Unlicense | ✅ | ✅ | ✅ | ✅ |
| The zlib/libpng License | Zlib | ✅ | ✅ | ✅ | ✅ |
| Zero-Clause BSD License | 0BSD | ✅ | ✅ | ✅ | ✅ |

## Enforcement

Power projects which use open-source software should enforce the exclusive utilisation of permitted licenses by use-case using [license_finder](https://github.com/pivotal/LicenseFinder). Check out the project README to understand how to begin using it. In order to get started with the list of permitted licenses, inherit from the standard Power configuration:

```shell
license_finder inherited_decisions add https://tech.powerhrg.com/oss-guide/license_rules.yml
```

Check which dependencies are not permitted by the standard configuration:

```shell
license_finder action_items
```

You should run this check as part of your development workflow when modifying dependencies, as well as in your CI builds. See [an example of how to achieve this](https://github.com/powerhome/milano/pull/506).

### Conditionally permitted licenses

If a license on the above list is permitted only for certain use-cases, you will have to manually mark a dependency as allowed based on the use-case within your application. If in doubt, check with the SDRT, and then mark the dependency allowed, eg:

```shell
license_finder approvals add redis-objects --version "1.4.3" --who "Ben Langfeld <blangfeld@powerhrg.com>" --why "SaaS backend use-case permitted w/ Artistic-2.0 license by https://tech.powerhrg.com/oss-guide/docs/using/permitted-licenses.html#permitted-licenses"
```

### Incorrectly identified licenses

If a dependency's license is not identified, or is identified incorrectly, you can specify it manually, eg:

```shell
license_finder licenses add unf BSD-2-Clause --who "Ben Langfeld <blangfeld@powerhrg.com>" --why "https://github.com/knu/ruby-unf/pull/12"
```
