# Bytecode Alliance Core and Hosted Project Requirements

This document enumerates the standards to which all Bytecode Alliance core and hosted projects are held. Additionally, it defines the process for applying for adoption as a hosted project or promotion from hosted project to core project.

## What are Hosted and Core Projects?

The Bytecode Alliance holds itself and its projects, whether hosted or core, to exceptional standards. This is part of our principle of [curation](https://github.com/bytecodealliance/governance/blob/main/operational-principles.md?plain=1#L17-L23) and we do not believe we can accomplish our [mission](https://github.com/bytecodealliance/governance/blob/main/mission.md) otherwise.

Core projects are the Bytecode Alliance's flagships and are held to an even higher standard than hosted projects. In return, core projects are prominently advertised on the Bytecode Alliance webpage and can elect a delegate to the Bytecode Alliance's Technical Steering Committee, as per [the TSC charter](https://github.com/bytecodealliance/governance/blob/main/TSC/charter.md#composition).

## Applying for Adoption as a Hosted Project

If you would like to propose that the Bytecode Alliance adopt your project as a new hosted project, file an issue against [the Bytecode Alliance governance repository](https://github.com/bytecodealliance/governance). The issue should enumerate each item marked as "Hosted Projects: Required" with a checkbox. Provide supplemental information, examples, and evidence that your project meets the associated requirement as bullet points below this checkbox. Here is an example issue:

```md
Proposing the adoption of `my-example-project` as a Bytecode Alliance
hosted project.

My Example project is a cool project. Here is some high level information
about what it does. There should be a link to the repo here.

### Hosted Project Requirements

* [ ] Alignment with the Bytecode Alliance Mission
  * My Example Project has alignment with the Bytecode Alliance mission
    because it is all about security, efficiency, and modularity blah
    blah blah
* [ ] Code Review
  * We follow the code review requirements, for example here are some
    examples showing our review culture in practice:
    * link 1
    * link 2
    * link 3
* Etc...
```

The Bytecode Alliance Technical Steering Committee (TSC) will provide timely acknowledgement of the application. The TSC will then perform an in-depth review of the project, evaluate whether it meets the hosted project requirements, and will decide based on consensus whether to accept the project. Next, the TSC will reply in the issue with the results of the review and whether the project has been accepted. If it has been accepted, then the TSC will work with maintainers on the logistics of moving the repository to the `bytecodealliance` github organization.

## Applying for Promotion from Hosted Project to Core Project

Once the project maintainers have come to a consenus agreement regarding the promotion to a core project, they will initiate the process by creating an issue within the [the Bytecode Alliance governance repository](https://github.com/bytecodealliance/governance). The issue should enumerate each item marked as "Hosted Projects: Required" with a checkbox. Provide supplemental information, examples, and evidence that your project meets the associated requirement as bullet points below the checkbox. Here is an example issue:


```md
Proposing the promotion of `my-example-project` to a core project.

My Example project is a cool project. Here is some high level information
about what it does. There should be a link to the repo here.

### Core Project Requirements

* [ ] Alignment with the Bytecode Alliance Mission
  * My Example Project has alignment with the Bytecode Alliance mission
    because it is all about security, efficiency, and modularity, blah
    blah blah
* [ ] Changelog
  * link to changelog
* Etc...
```

The Bytecode Alliance Technical Steering Committee (TSC) will provide timely acknowledgement of the application. The TSC will then perform an in-depth review of the project, evaluate whether it meets the core project requirements, and decide based on consensus whether to promote the project. Next, the TSC will reply in the issue with the results of the review and whether the project has been promoted. If it has been promoted, then the project maintainers will [choose a delegate to represent the project on the TSC](https://github.com/bytecodealliance/governance/blob/d0310b2f4fab7d5bd076627b196dfc0ffe040ec1/TSC/charter.md#composition).

----------------------

## Requirements

### Alignment with the Bytecode Alliance Mission

**Core Projects: Required**

**Hosted Projects: Required**

#### Description

Projects must have alignment with [the Bytecode Alliance mission:](https://github.com/bytecodealliance/governance/blob/main/mission.md)

> Our mission is to provide state-of-the-art foundations to develop runtime environments and language toolchains where security, efficiency, and modularity can all coexist across a wide range of devices and architectures. We enable innovation in compilers, runtimes, and tooling, focusing on fine-grained sandboxing, capabilities-based security, modularity, and standards such as WebAssembly and WASI.

#### Motivation

The Bytecode Alliance is a group with a specific mission, and we therefore will only sponsor projects that are in alignment with and further that mission. For example, project sponsorship is untenable if the project undermines sandboxing, security, or standardization efforts.

----------------------

### Changelog

**Core Projects: Required**

**Hosted Projects: Recommended**

#### Description

Core projects must, and hosted projects should, highlight key additions, breaking changes, security fixes, and otherwise noteworthy changes in a changelog.

See [keepachangelog.com](https://keepachangelog.com/en/1.1.0/) for a recommended approach.

#### Motivation

We are building an ecosystem that developers can depend on, and one small part of that is communicating important changes downstream.

----------------------

### Code Review

**Core Projects: Required**

**Hosted Projects: Required**

#### Description

All projects must gate merging pull requests on code reviews that audit not only for style but also substance, such as whether security invariants are properly maintained by the new code.

Core projects must maintain [a `CODEOWNERS` file](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-code-owners) and use it to automatically assign reviewers to pull requests. Auto-assigned reviewers must respond to pull requests in a timely fashion. However, that response doesn't have to be a full code review; it could also be

- "I intend to review this but I can't immediately. Please leave me a message if I haven't responded by `$SPECIFIC_DATE_IN_NEAR_FUTURE`."
- "I think `$SPECIFIC_OTHER_MAINTAINER` should review this." (Note that the best reviewer for a PR may not necessarily be listed in the `CODEOWNERS` file.)

It is recommended, but not required, that hosted projects maintain a `CODEOWNERS` file and automatically assign reviewers as well.

#### Motivation

Code reviews have a demonstrable impact on the quality of source code by catching bugs early, determining the best possible implementation, and fostering trust within the community. Timely responses let contributors know that their work is valued and encourages further contribution.

----------------------

### Code of Conduct

**Core Projects: Required**

**Hosted Projects: Required**

#### Description

All Bytecode Alliance projects must:

* link to the Bytecode Alliance's Code of Conduct documents from a `CODE_OF_CONDUCT.md` file in root of the repository, and
* enforce the codes of conduct among the community and contributors, or escalate to [the Bytecode Alliance CoC Team](mailto:report@bytecodealliance.org), if needed.

#### Motivation

Having a code of conduct is crucial for creating a positive and respectful environment in any organization, community, or group. It serves as a set of guidelines that outline expected behavior and ethical standards for all members involved.

----------------------

### Continuous Fuzzing

**Core Projects: Required**

**Hosted Projects: Recommended**

#### Description

Not all projects will necessarily benefit from fuzzing, for example benchmark suites. The TSC may choose lift this requirement for a particular project.

It is required that core projects have 24/7, round the clock, continuous fuzzing. The fuzzing must exercise significant amounts of the code base and test the project's most important properties, such as sandboxing. Bugs and vulnerabilities discovered via fuzzing must be addressed promptly.

Part of our open-source and open contribution model, the corpus and setup for running fuzzing must be open-sourced as part of the project.

Faults discovered via fuzzing must be reported privately to the project's core team so that the project's security vulnerability process can be followed properly, if necessary. For example, fuzzing infrastructure must not automatically open public issues for any fault that is discovered.

#### Motivation

Continuous fuzzing is a valuable practice for projects, due to its significant benefits in improving security and reliability. Within the Bytecode Alliance, we host projects that provide a sandbox. The fidelity of these sandboxes must be battle-tested via a number of methodologies including automated fuzzing.

----------------------

### Continuous Integration Testing

**Core Projects: Required**

**Hosted Projects: Required**

#### Description

All projects must run continuous integration (CI) tests on all pull requests and merges. Key project features must be covered by CI.

If any part of the CI gates on merging changes that is not reproducible by external contributors, then the project must make affordances to support those external contributors.

#### Motivation

Implementing CI offers several benefits to software projects, helping ensure correctness and quality, making it an essential practice for modern software development.

----------------------

### Contributor Documentation

**Core Projects: Required**

**Hosted Projects: Required**

#### Description

All projects must have a `CONTRIBUTING.md` document in the root of their repository. This document must provide, or link to another form of project-specific documentation that provides, high-quality contributor documentation.

See ["How to build a `CONTRIBUTING.md`" by the Mozilla Science Lab](https://mozillascience.github.io/working-open-workshop/contributing/) for more details on what a high-quality `CONTRIBUTING.md` file looks like.

#### Motivation

A `CONTRIBUTING.md` serves as a guide for potential contributors, outlining the expectations for individuals who wish to contribute to the project. The Bytecode Alliance is a community-driven software foundation and documents like `CONTRIBUTING.md` are necessary for fostering community contributions.

----------------------

### End-User Documentation

**Core Projects: Required**

**Hosted Projects: Recommended**

#### Description

We abide by [the OpenSSF requirements for documentation](https://bestpractices.coreinfrastructure.org/en):

> The documentation of an external interface explains to an end-user or developer how to use it. This would include its application program interface (API) if the software has one. If it is a library, document the major classes/types and methods/functions that can be called. If it is a web application, define its URL interface (often its REST interface). If it is a command-line interface, document the parameters and options it supports. In many cases it's best if most of this documentation is automatically generated, so that this documentation stays synchronized with the software as it changes, but this isn't required. The project MAY use hypertext links to non-project material as documentation. Documentation MAY be automatically generated (where practical this is often the best way to do so).

Furthermore, we identify a few different types of (sometimes overlapping) documentation:

* **API documentation**: Documentation for each type, method, function, and module in a library.
* **Architectural overviews**: High-level documentation about the architecture of the project and how it works from a 1000-foot view that helps endusers take advantage of the project in the best way possible and helps onboard new contributors.
* **Examples**: Code examples that show off how to use the project as a whole or particular features it supports.
* **Guides and tutorials**: Long-form prose, with code samples interspersed, that shows how to accomplish a task using the project.

All of the above types of documentation are required for core projects.

API and CLI flag documentation is required for hosted projects; all other types are recommended.

#### Motivation

Documentation is necessary for end-users to productively use the project; source code comments are not sufficient.

----------------------

### Following the Bytecode Alliance Operational Principles

**Core Projects: Required**

**Hosted Projects: Required**

#### Description

All projects must follow [the Bytecode Alliance Operational Principles](https://github.com/bytecodealliance/governance/blob/main/operational-principles.md).

#### Motivation

In pursuing our mission and vision, the Bytecode Alliance follows a set of operational principles aimed at keeping us aligned on three key aspects: what we want to create, how we want to work together, and how we want to work with others.

----------------------

### Issue Triage Process

**Core Projects: Required**

**Hosted Projects: Recommended**

#### Description

Core and hosted projects must use an issue tracker for tracking individual issues.

Core projects must, and hosted projects should, have a documented process for expeditiously triaging incoming issues and pull requests, and follow that process. Contributors should get prompt responses to their issues and pull requests, even if a response is not an immediate fix or review.

#### Motivation

For a successful community-driven project, expedient communication within issues and PRs encourages further collaboration and contribution.

----------------------

### Leverage the Bytecode Alliance RFC Process

**Core Projects: Required**

**Hosted Projects: Recommended**

#### Description

A request for comments (RFC) is a technique for soliciting the community and contributors for feedback on proposed major changes and decisions.

Core projects must, and hosted projects should, follow [the Bytecode Alliance RFC process](https://github.com/bytecodealliance/rfcs/blob/main/accepted/rfc-process.md) for changes that significantly affect project stakeholders or contributors. The RFCs repo describes [when an RFC is needed](https://github.com/bytecodealliance/rfcs/#when-is-an-rfc-needed) in more detail:

> Many changes to Bytecode Alliance projects can and should happen through every-day GitHub processes: issues and pull requests. An RFC is warranted when:
>
> * The work involves changes that will significantly affect stakeholders or project contributors. Each project may provide more specific guidance. Examples include:
>     * Major architectural changes
>     * Major new features
>     * Simple changes that have significant downstream impact
>     * Changes that could affect guarantees or level of support, e.g. removing support for a target platform
>     * Changes that could affect mission alignment, e.g. by changing properties of the security model
> * The work is substantial and you want to get early feedback on your approach.

#### Motivation

This is a best practice for aligning contributors, the community, and downstream project's needs with proposed technical implementations.

----------------------

### Licensing Compatible with the Bytecode Alliance

**Core Projects: Required**

**Hosted Projects: Required**

#### Description

All projects must be licensed under the Apache 2.0 license with an LLVM exception. Exemptions may be granted by the board.

All projects must only use dependencies and third-party code licensed under one of the following open source licenses:

* Apache-2.0 WITH LLVM-exception
* Apache-2.0
* BSD-2-Clause
* BSD-3-Clause
* ISC
* MIT
* MPL-2.0
* OpenSSL
* Unicode-DFS-2016
* Zlib

All dependencies and third-party code must be properly attributed.

The source for all projects must be available to all members and must be available to all non-members under the same license.

All projects must automatically ensure that licensing requirements of dependencies are met in CI.

#### Motivation

We strive to build an open community and a legally-compatible software ecosystem.

----------------------

### Production Use

**Core Projects: Required**

**Hosted Projects: Recommended**

#### Description

Core projects must have demonstrated use in production by at least three independent organizations which are, in the TSC's judgement, of adequate quality and scope.

It is recommended that projects track production usage by organizations in an `ADOPTERS.md` at the root of the project, for example see [`ADOPTERS.md`](https://github.com/bytecodealliance/wasmtime/blob/main/ADOPTERS.md) in Wasmtime.

#### Motivation

In order to become a core project, that project must demonstrate that it is practical, useful, and reliable enough to use in production.

----------------------

### Public Project Meetings and Notes

**Core Projects: Required**

**Hosted Projects: Recommended**

#### Description

Core projects must hold regular and public project meetings. Meeting times and frequency must be advertised publicly, for example in the project's `CONTRIBUTING.md`. To avoid spam and "Zoom bombing", the video conferencing link need not be public, but must be available upon request.

Agendas for upcoming meetings and notes from past meetings must be published publicly. The notes should be in the `bytecodealliance/meetings` repository.

It is recommended, but not required, that hosted projects also abide by these rules.

#### Motivation

Public meetings encourage open communication, collaboration, and engagement within the project's community. Notes allow community members who were not present to remain aligned and can document any decisions made during the meeting.

----------------------

### README

**Core Projects: Required**

**Hosted Projects: Required**

#### Description

All projects must have a `README.md` file in the root of the repository which begins with:

* The project name and logo (if one exists)
* A one-sentence description of the project
* `<strong>A <a href="https://bytecodealliance.org/">Bytecode Alliance</a> project</strong>`

#### Motivation

The most important information about the project should be "above the fold". Projects should identify themselves as Bytecode Alliance projects so that with time they associate the Bytecode Alliance with quality projects that they can rely on.

----------------------

### Release Process

**Core Projects: Required**

**Hosted Projects: Required**

#### Description

Documentation of a release process that any project maintainer may execute to create a new release version of the software.

Multiple people must have permissions to publish releases. A github team must have access to publish packages and package ownership on the associated package repository when possible. For example a Rust project may have multiple owners on crates.io.

Core projects must additionally leverage a fully-automated release process, where the only manual step performed by project maintainers is to trigger the process (for example by starting a github workflow or merging an automated pull request).

#### Motivation

Projects and their releases shouldn't be tied to any single user's machine or keys to ensure continuity of the project. A project isn't an open, community project if only one person can publish releases.

Automation makes fewer mistakes than humans, and getting releases right is critical, since only releases are typically used downstream, not random commits from `main`.

----------------------

### Sanitizers and Code Analysis

**Core Projects: Required**

**Hosted Projects: Recommended**

#### Description

Static and dynamic code analysis tools (such as `valgrind` or `miri`) where applicable must be used by core projects and are recommended to be used by hosted projects.

Core projects with non-trivial amounts of unsafe code (e.g. `unsafe` in Rust or any C/C++) must run tests and fuzzers with the relevant sanitizers: Address Sanitizer, Memory Sanitizer, Thread Sanitizer, etc. It is recommended, but not required, that hosted projects do the same.

#### Motivation

Automated code analysis is key to meeting our mission of developing runtime environments and language toolchains where security, efficiency, and modularity can all coexist.

----------------------

### Security Process

**Core Projects: Required**

**Hosted Projects: Required**

#### Description

All projects must have a documented security process for reporting and disclosing vulnerabilities, managing patches that fix vulnerabilities, and announcing and making available security releases. Furthermore, projects must actually follow their documented processes.

Core projects must request Common Vulnerability and Exposure (CVE) numbers for discovered vulnerabilities and report the CVE when disclosing the vulnerability.

A tool like [dependabot](https://github.com/dependabot) may suffice for hosted projects. Dependabot should be used for security updates only, and not apply all updates indiscriminantly. Updating dependencies should otherwise be done with intention (never automatically). Automatic creation of pull requests is acceptable, but manual review is required to prevent supply chain attacks.

#### Motivation

Bytecode Alliance projects must be a secure foundation for others to build upon. Transparency and a managed security release process is key to being this foundation.

----------------------

### Semantic Versioning

**Core Projects: Required**

**Hosted Projects: Required**

#### Description

All projects must follow either standard semantic versioning or their ecosystem's local-dialect of semantic versioning (for example, Rust and `cargo`'s interpretation of semantic versioning slightly differs from the standard, but is acceptable for Rust Bytecode Alliance projects).

#### Motivation

A clear versioning scheme is necessary for end-users. We desire consistency across projects and so the Bytecode Alliance has adopted semantic versioning as a required best practice.

----------------------

### Secrets Management

**Core Projects: Required**

**Hosted Projects: Required**

#### Description

GitHub organization and repository level secrets should be used. Secrets must not be hard coded in source.

For secrets like passwords for the project's associated social media account, these should be stored in the password service paid for by the Bytecode Alliance. Contact the TSC for access and ability to manage a given secret.

#### Motivation

Secure secret management is a requirement for a secure project. Additionally, projects and their associated accounts shouldn't be tied to any single user's machine or keys to ensure continuity of the project. A project isn't an open, community project if only one person can access its accounts.

----------------------

### Supply Chain Security

**Core Projects: Required**

**Hosted Projects: Required**

#### Description

All projects must follow a well-documented process for updating dependencies and auditing them for malicious supply-chain attacks.

When applicable, projects should:

* Integrate auditing tools in CI (such as `cargo vet`)
* Use code review and static analysis tools on dependencies

Finally, projects must document and follow their process for responding to upstream vulnerabilities in dependencies.

#### Motivation

Our mission of developing runtime environments and language toolchains where security, efficiency, and modularity can all coexist necessarily means that we have performed our due dilligence to mitigate software supply chain attacks.

----------------------

### Sustainable Contributor Base

**Core Projects: Required**

**Hosted Projects: Required**

#### Description

All projects must have regular contributions from multiple contributors.

Core projects mush have contributors affiliated with at least two different Bytecode Alliance organizations and the project leadership must have representation from at least two different Bytecode Alliance organizations.

Hosted projects may have contributors and leadership from the same Bytecode Alliance organization.

There must not be any private information necessary to fully contribute to the project.

#### Motivation

A project is not considered healthy with only one contributor. An open, community project requires input from multiple stakeholders and does not rely on a single person.

----------------------

### Version Control

**Core Projects: Required**

**Hosted Projects: Required**

#### Description

All projects must be hosted on [the Bytecode Alliance Organization](github.com/bytecodealliance) on GitHub.

#### Motivation

Access controls are managed via the Bytecode Alliance organization on GitHub. This allows for continuity of the project when hosted in one place. Finally, this is the only way to reasonable manage the projects within the organization.
