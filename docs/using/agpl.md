---
layout: default
title: The AGPL License
nav_order: 3
parent: Using Open Source Code
---

# The AGPL license

This page highlights our policy with respect to the [GNU Affero General Public License (AGPL)](https://www.gnu.org/licenses/agpl-3.0.en.html). It's a special license worth special treatment.

- Assume by default, code licensed under the GNU Affero General Public License (AGPL) **should not** be used at Power. To get an exception, first contact the SDRT and we will work with you and the relevant teams to determine if your use case warrants an exception.
- Many AGPL licensed products offer commercially licensed alternatives. In fact many commercial products use the AGPL licensing to draw users to their commercial options. We suggest you view AGPL licensed code as the bait to a commercial option and then consider the merits of the commercial option. Getting commercially licensed code requires you work with the SDRT.
- Some software products that used AGPL to drive commercial licensing are re-licensing their products to use "source-available" licenses that are not actually open source licenses (meaning: they do not comply with the [Open Source Definition](https://opensource.org/osd)). To use any of these, open a ticket with the SDRT and we'll initiate a review for you. We have approved some of these, but each case differs.

We ask that you not check in AGPL-licensed code to our repositories and not include a dependency on AGPL licensed code in your products. For those cases where we have granted you an exception to use an AGPL code base, we'll instruct you on how we want the code handled.

If you have any questions about this policy or about open source licenses, please contact the SDRT. We're here to help and will gladly explain the rationale behind this and other policies.

## Why is the AGPL problematic?

The preamble of the AGPL states the following:

```
A secondary benefit of defending all users' freedom is that
improvements made in alternate versions of the program, if they
receive widespread use, become available for other developers to
incorporate.  Many developers of free software are heartened and
encouraged by the resulting cooperation.  However, in the case of
software used on network servers, this result may fail to come about.
The GNU General Public License permits making a modified version and
letting the public access it on a server without ever releasing its
source code to the public.

The GNU Affero General Public License is designed specifically to
ensure that, in such cases, the modified source code becomes available
to the community.  It requires the operator of a network server to
provide the source code of the modified version running there to the
users of that server.  Therefore, public use of a modified version, on
a publicly accessible server, gives the public access to the source
code of the modified version.
```

The substantial difference between AGPL-3.0 and GPL-3.0 is the following additional clause:

```
13. Remote Network Interaction; Use with the GNU General Public License.

Notwithstanding any other provision of this License, if you modify the
Program, your modified version must prominently offer all users
interacting with it remotely through a computer network (if your version
supports such interaction) an opportunity to receive the Corresponding
Source of your version by providing access to the Corresponding Source
from a network server at no charge, through some standard or customary
means of facilitating copying of software.  This Corresponding Source
shall include the Corresponding Source for any work covered by version 3
of the GNU General Public License that is incorporated pursuant to the
following paragraph.
```

Use of dependencies licensed under the GPL (or similar copyleft licenses) is prohibited at Power for software we distribute because the terms of the GPL oblige us to also distribute our derived works under the GPL, which we generally do not wish to do. Use of dependencies under these licenses is permitted, however, for non-distributed projects, such as the "SaaS back-end" use case, where the software runs on our hardware and is not distributed. See [the GPL FAQ](https://www.gnu.org/licenses/gpl-faq.html#GPLRequireSourcePostedPublic) for reference.

Use of dependencies licensed under the AGPL, however, is prohibited at Power even for the use-cases where the standard GPL because of its clause 13, which extends the copyleft trigger to use over the network, and not just distribution.

The wording of clause 13 is not ideal; that it uses the verb "to modify" leads some to [interpret a derived work which links to the program licensed under the AGPL as being unaffected by copyleft](https://opensource.stackexchange.com/a/4692). Clause 0, however, defines modifications:

```
To "modify" a work means to copy from or adapt all or part of the work
in a fashion requiring copyright permission, other than the making of an
exact copy.  The resulting work is called a "modified version" of the
earlier work or a work "based on" the earlier work.
```

This can be interpreted to suggest that creation of a work based on the program licensed as AGPL triggers the clause 13 obligation to distribute the derived work. The GPL FAQ provides clarification on the authors' position on what this means, suggesting this interpretation:

* https://www.gnu.org/licenses/gpl-faq.html#LinkingWithGPL
* https://www.gnu.org/licenses/gpl-faq.html#GPLStaticVsDynamic

This basically reduces to the age old debate within the open-source software community about whether linking (or specifically dynamic linking) constitutes creation of a derived work. This is an open question. Given all the risk involved in being wrong, we opt to consider for our usage purposes that dynamic linking does constitute a derived work. In the interpreted (Ruby/Javascript) world, we consider invoking code in dependencies (packaged as Ruby gems or npm modules) to be analagous to dynamic linking, and indeed for the packaging of this combination in Docker images (for deployment) to be analagous to static linking; thus, we consider inclusion of these dependencies in our projects to constitute forming a derived work. This is the reason why we do not allow use of GPL or other copy-left licenses in code that we distribute.

Additionally, our understanding is that the intent of the copyright holder when they license their code as AGPL is to provide an avenue for them to sue in cases of violations of the above interpretation. Whether or not our interpretation is correct, and therefore they would be successful, is something that we do not wish to test in a court room with our IP, money and business at risk; we prefer to be cautious enough not to provide cause for someone to sue us over this, and therefore prohibit these use-cases even assuming that our interpretation were wrong.
