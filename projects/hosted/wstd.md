# Proposal to Create wstd

This document is a proposal to create wstd as a formal Hosted Project under
the auspices of the TSC of the Bytecode Alliance, as specified in the TSC’s
charter.

Proposing the adoption of wstd as a Bytecode Alliance hosted project.

Current Repository URL: https://github.com/yoshuawuyts/wstd

Proposed Repository URL: https://github.com/bytecodealliance/wstd

`wstd` is a minimal async standard library written exclusively to support Wasm
Components. It exists primarily to enable people to write async-based
applications in Rust before async-std, smol, or tokio land support for Wasm
Components and WASI 0.2. Once those runtimes land support, it is recommended
users switch to use those instead.

## Requirements

### Alignment with the Bytecode Alliance Mission

> Projects must have alignment with [the Bytecode Alliance mission:](https://github.com/bytecodealliance/governance/blob/main/mission.md)
>
> > Our mission is to provide state-of-the-art foundations to develop runtime environments and language toolchains where security, efficiency, and modularity can all coexist across a wide range of devices and architectures. We enable innovation in compilers, runtimes, and tooling, focusing on fine-grained sandboxing, capabilities-based security, modularity, and standards such as WebAssembly and WASI.
>
> The Bytecode Alliance is a group with a specific mission, and we therefore will only sponsor projects that are in alignment with and further that mission. For example, project sponsorship is untenable if the project undermines sandboxing, security, or standardization efforts.

wstd exists to further the adoption of the Component Model and WASI standards,
by enabling users to write async Rust applications targeting WASI 0.2, and by
demonstrating to the maintainers of more popular async Rust runtimes how to
use WASI 0.2 effectively.

wstd provides support for writing applications targeting the wasi:cli/command
world, or alternatively the wasi:http/proxy world.

wstd intends to support WASI 0.3 as well as WASI 0.2 in the future.

wstd is maintained by one of the current co-chairs of the WASI subgroup, and
two former co-chairs of the WASI subgroup.

### Code Review

#### Description

> All projects must gate merging pull requests on code reviews that audit not only for style but also substance, such as whether security invariants are properly maintained by the new code.
>
> It is recommended, but not required, that hosted projects maintain a `CODEOWNERS` file and automatically assign reviewers as well.
>
> Code reviews have a demonstrable impact on the quality of source code by catching bugs early, determining the best possible implementation, and fostering trust within the community. Timely responses let contributors know that their work is valued and encourages further contribution.

All proposed changes (Pull Requests) go through pull requests and CI validation
before merging. The project has comprehensive automated testing via GitHub
Actions which executes all tests using the latest version of wasmtime, as
provided by the `bytecodealliance/actions/wasmtime/setup@v1` GitHub Action.

### Code of Conduct

> All Bytecode Alliance projects must:
>
> * link to the Bytecode Alliance's Code of Conduct documents from a `CODE_OF_CONDUCT.md` file in root of the repository, and
> * enforce the codes of conduct among the community and contributors, or escalate to [the Bytecode Alliance CoC Team](mailto:report@bytecodealliance.org), if needed.
>
> Having a code of conduct is crucial for creating a positive and respectful environment in any organization, community, or group. It serves as a set of guidelines that outline expected behavior and ethical standards for all members involved.

The PR [#72] adds the Bytecode Alliance's Code of Conduct document to the
repository. This PR will be merged prior to transferring the repo to the
bytecodealliance GitHub org.

[#72]: https://github.com/yoshuawuyts/wstd/pull/72

### Continuous Integration Testing

> All projects must run continuous integration (CI) tests on all pull requests and merges. Key project features must be covered by CI.
>
> If any part of the CI gates on merging changes that is not reproducible by external contributors, then the project must make affordances to support those external contributors.
>
> Implementing CI offers several benefits to software projects, helping ensure correctness and quality, making it an essential practice for modern software development.

The project has comprehensive CI testing implemented via GitHub Actions. The
[main CI workflow] runs on all pushes and pull requests, against the latest
Wasmtime on multiple platforms. It runs all of the unit tests, integration
test [in wasmtime], and runs tests which require [external stimulus] by
executing wasmtime as either a CLI or library.

[main CI workflow]: https://github.com/yoshuawuyts/wstd/blob/main/.github/workflows/ci.yml
[in wasmtime]: https://github.com/yoshuawuyts/wstd/blob/main/.cargo/config.toml
[external stimulus]: https://github.com/yoshuawuyts/wstd/tree/main/test-programs/artifacts/tests

### Contributor Documentation

> All projects must have a `CONTRIBUTING.md` document in the root of their
> repository. This document must provide, or link to another form of
> project-specific documentation that provides, high-quality contributor
> documentation.
>
> See ["How to build a `CONTRIBUTING.md`" by the Mozilla Science
> Lab](https://mozillascience.github.io/working-open-workshop/contributing/)
> for more details on what a high-quality `CONTRIBUTING.md` file looks like.
>
> A `CONTRIBUTING.md` serves as a guide for potential contributors, outlining the expectations for individuals who wish to contribute to the project. The Bytecode Alliance is a community-driven software foundation and documents like `CONTRIBUTING.md` are necessary for fostering community contributions.

The PR [#72](https://github.com/yoshuawuyts/wstd/pull/72) adds a
`CONTRIBUTING.md` to the repository. This PR will be merged prior to
transferring the repo to the bytecodealliance GitHub org.

### Following the Bytecode Alliance Operational Principles

> All projects must follow [the Bytecode Alliance Operational Principles](https://github.com/bytecodealliance/governance/blob/main/operational-principles.md).
>
> In pursuing our mission and vision, the Bytecode Alliance follows a set of operational principles aimed at keeping us aligned on three key aspects: what we want to create, how we want to work together, and how we want to work with others.

The project demonstrates alignment with BA operational principles through its
commitment to broad testing coverage, building for consistency and
interoperability (following tree-sitter ecosystem standards), and facilitating
collaboration (open source development with clear contribution guidelines).

### Licensing Compatible with the Bytecode Alliance

> All projects must be licensed under the Apache 2.0 license with an LLVM exception. Exemptions may be granted by the board.
>
> All projects must only use dependencies and third-party code licensed under one of the following open source licenses:
>
> * Apache-2.0 WITH LLVM-exception
> * Apache-2.0
> * BSD-2-Clause
> * BSD-3-Clause
> * ISC
> * MIT
> * MPL-2.0
> * OpenSSL
> * Unicode-DFS-2016
> * Zlib
>
> All dependencies and third-party code must be properly attributed.
>
> The source for all projects must be available to all members and must be available to all non-members under the same license.
>
> All projects must automatically ensure that licensing requirements of dependencies are met in CI.
>
> We strive to build an open community and a legally-compatible software ecosystem.

The project [is licensed] with "MIT OR Apache-2.0 OR Apache-2.0 WITH LLVM-exception" in current releases. In order to conform to the BA licensing rules, we have reduced that to only "Apache-2.0 WITH LLVM-exception" in [#72].

[is licensed]: https://github.com/yoshuawuyts/wstd/blob/main/Cargo.toml#L50

### README

> All hosted projects must have a `README.md` file in the root of the repository which begins with:
>
> * The project name and logo (if one exists)
> * A one-sentence description of the project
> * `<strong>A <a href="https://bytecodealliance.org/">Bytecode Alliance</a> hosted project</strong>`
>
> The most important information about the project should be "above the fold". Projects should identify themselves as Bytecode Alliance projects so that, with time, people associate the Bytecode Alliance with quality projects that they can rely on.

The project has a [README.md] which contains the project name. There is no
logo. There is a one sentence description of the project, as well as a more
detailed description and an example.

The Hosted Project line of the README is pending in [#72]. This PR will be
merged prior to transferring the repo to the bytecodealliance GitHub org.

[README.md]: https://github.com/yoshuawuyts/wstd/blob/main/README.md

### Release Process

> Documentation of a release process that any project maintainer may execute to create a new release version of the software.
>
> Multiple people must have permissions to publish releases. A github team must have access to publish packages and package ownership on the associated package repository when possible. For example a Rust project may have multiple owners on crates.io.
>
> Projects and their releases shouldn't be tied to any single user's machine or keys to ensure continuity of the project. A project isn't an open, community project if only one person can publish releases.
>
> Automation makes fewer mistakes than humans, and getting releases right is critical, since only releases are typically used downstream, not random commits from `main`.

The project currently uses semantic versioning (latest release: v0.5.3) and is
published to crates.io. We will adopt an automated release project after
transferring the repo to the bytecodealliance GitHub org, based on the
automation used throughout wasm-tools, wit-bindgen, wasmtime, etc.

### Security Process

> All projects must have a documented security process for reporting and disclosing vulnerabilities, managing patches that fix vulnerabilities, and announcing and making available security releases. Furthermore, projects must actually follow their documented processes.
>
> It is recommended that request Common Vulnerability and Exposure (CVE) numbers for discovered vulnerabilities and report the CVE when disclosing the vulnerability.
>
> A tool like [dependabot](https://github.com/dependabot) may suffice for hosted projects. Dependabot should be used for security updates only, and not apply all updates indiscriminantly. Updating dependencies should otherwise be done with intention (never automatically). Automatic creation of pull requests is acceptable, but manual review is required to prevent supply chain attacks.
>
> Bytecode Alliance projects must be a secure foundation for others to build upon. Transparency and a managed security release process is key to being this foundation.

The project currently lacks a formal security process documentation. If and
when the proposal is approved, a security policy will be established including
vulnerability reporting procedures, security release processes, and appropriate
escalation mechanisms.

### Semantic Versioning

> All projects must follow either standard semantic versioning or their ecosystem's local-dialect of semantic versioning (for example, Rust and `cargo`'s interpretation of semantic versioning slightly differs from the standard, but is acceptable for Rust Bytecode Alliance projects).
>
> A clear versioning scheme is necessary for end-users. We desire consistency across projects and so the Bytecode Alliance has adopted semantic versioning as a required best practice.

The project follows semantic versioning as evidenced by the current version
[_0.5.3_ in crates.io](https://crates.io/crates/wstd)

### Secrets Management

> GitHub organization and repository level secrets should be used. Secrets must not be hard coded in source.
>
> For secrets like passwords for the project's associated social media account, these should be stored in the password service paid for by the Bytecode Alliance. Contact the TSC for access and ability to manage a given secret.
>
> Secure secret management is a requirement for a secure project. Additionally, projects and their associated accounts shouldn't be tied to any single user's machine or keys to ensure continuity of the project. A project isn't an open, community project if only one person can access its accounts.

The project has no hardcoded secrets in the source code. The current CI
workflows use only standard GitHub Actions and do not require any secrets.

If automated deployment to package manager registries is added, it will
be based on the existing automatic deployment used in wasm-tools, wit-bindgen,
and wasmtime, where secrets are managed properly by GitHub.

### Supply Chain Security

> All projects must follow a well-documented process for updating dependencies and auditing them for malicious supply-chain attacks.
>
> When applicable, projects should:
>
> * Integrate auditing tools in CI (such as `cargo vet`)
> * Use code review and static analysis tools on dependencies
>
> Finally, projects must document and follow their process for responding to upstream vulnerabilities in dependencies.
>
> Our mission of developing runtime environments and language toolchains where security, efficiency, and modularity can all coexist necessarily means that we have performed our due diligence to mitigate software supply chain attacks.

The project has a minimal dependency footprint. We will adopt a `cargo vet`
process like Wasmtime's after transferring to the bytecodealliance GitHub org.

### Sustainable Contributor Base

> All projects must have regular contributions from multiple contributors.
>
> It is recommended that hosted projects additionally have contributors affiliated with at least two different Bytecode Alliance organizations and that the project's leadership has representation from at least two different Bytecode Alliance organizations.
>
> There must not be any private information necessary to fully contribute to the project.
>
> A project is not considered healthy with only one contributor. An open, community project requires input from multiple stakeholders and does not rely on a single person.
>
> The TSC may waive the above contributor base requirements under certain conditions. In particular, the TSC may decide to adopt crucial upstream dependencies of existing Bytecode Alliance projects that are otherwise effectively unmaintained or only have a single maintainer.

The project currently has three maintainers: Yoshua Wuyts (Microsoft), Pat
Hickey (F5), and Dan Gohman (Fastly). Each of these maintainers has been
actively contributing to many Bytecode Alliance projects for many years. Each
maintainer is employed by Bytecode Alliance member orginizations and assigned
to work on Bytecode Alliance projects.

Yosh is currently serving as co-chair of the WASI subgroup, and Pat and Dan
have served as co-chairs of WASI in the past. Pat is currently serving as an
at-large director of the Bytecode Alliance.

### Version Control

> All projects must be hosted on [the Bytecode Alliance Organization](github.com/bytecodealliance) on GitHub.
>
> Access controls are managed via the Bytecode Alliance organization on GitHub. This allows for continuity of the project when hosted in one place. Finally, this is the only way to reasonable manage the projects within the organization.

The project is currently hosted at https://github.com/yoshuawuyts/wstd
and will be transferred to the Bytecode Alliance GitHub organization
(github.com/bytecodealliance/wstd) upon adoption. The repository
includes full history, comprehensive CI/CD configuration, and all project
assets necessary for the transfer.


## Recommendations

### Changelog

> It is recommended that hosted projects highlight key additions, breaking changes, security fixes, and otherwise noteworthy changes in a changelog.
>
> See [keepachangelog.com](https://keepachangelog.com/en/1.1.0/) for a recommended approach.
>
> We are building an ecosystem that developers can depend on, and one small part of that is communicating important changes downstream.

The project currently does not maintain a formal changelog. We will start
keeping a CHANGELOG.md file after transferring to the bytecodealliance GitHub
org.


### Continuous Fuzzing

> Not all projects will necessarily benefit from fuzzing, for example benchmark suites. The TSC may choose lift this requirement for a particular project.
>
> It is recommended that hosted projects have 24/7, round the clock, continuous fuzzing. The fuzzing should exercise significant amounts of the code base and test the project's most important properties, such as sandboxing. Bugs and vulnerabilities discovered via fuzzing should be addressed promptly.
>
> Part of our open-source and open contribution model, the corpus and setup for running fuzzing should be open-sourced as part of the project.
>
> Faults discovered via fuzzing must be reported privately to the project's core team so that the project's security vulnerability process can be followed properly, if necessary. For example, fuzzing infrastructure must not automatically open public issues for any fault that is discovered.
>
> Continuous fuzzing is a valuable practice for projects, due to its significant benefits in improving security and reliability. Within the Bytecode Alliance, we host projects that provide a sandbox. The fidelity of these sandboxes must be battle-tested via a number of methodologies including automated fuzzing.

This project does not use continuous fuzzing. Because the purpose of this
project is to create reusable abstractions for Rust programmers to use WASI
interfaces, its not in the usual sweet spot for continuous fuzzing. We can
evaluate using continuous fuzzing in the future.


### End-User Documentation

> We abide by [the OpenSSF requirements for documentation](https://bestpractices.coreinfrastructure.org/en):
>
> > The documentation of an external interface explains to an end-user or developer how to use it. This would include its application program interface (API) if the software has one. If it is a library, document the major classes/types and methods/functions that can be called. If it is a web application, define its URL interface (often its REST interface). If it is a command-line interface, document the parameters and options it supports. In many cases it's best if most of this documentation is automatically generated, so that this documentation stays synchronized with the software as it changes, but this isn't required. The project MAY use hypertext links to non-project material as documentation. Documentation MAY be automatically generated (where practical this is often the best way to do so).
>
> Furthermore, we identify a few different types of (sometimes overlapping) documentation:
>
> * **API documentation**: Documentation for each type, method, function, and module in a library.
> * **Architectural overviews**: High-level documentation about the architecture of the project and how it works from a 1000-foot view that helps endusers take advantage of the project in the best way possible and helps onboard new contributors.
> * **Examples**: Code examples that show off how to use the project as a whole or particular features it supports.
> * **Guides and tutorials**: Long-form prose, with code samples interspersed, that shows how to accomplish a task using the project.
>
> API and CLI flag documentation is required for hosted projects; all other types are recommended.
>
> Documentation is necessary for end-users to productively use the project; source code comments are not sufficient.

This project provides [rust docs] that provide comprehensive API documentation
and examples. This project does not have any sort of CLI interface.

[rust docs]: https://docs.rs/wstd/latest/wstd/

### Issue Triage Process

> Hosted projects must use an issue tracker for tracking individual issues.
>
> It is recommended that hosted projects should additionally have a documented process for expeditiously triaging incoming issues and pull requests, and follow that process. Contributors should get prompt responses to their issues and pull requests, even if a response is not an immediate fix or review.
>
> For a successful community-driven project, expedient communication within issues and PRs encourages further collaboration and contribution.

The project uses GitHub Issues for tracking but currently lacks a formal issue
triage process. Each of the maintainers is active in the issue triage process
in other Bytecode Alliance hosted projects, and has a track record of
expedient communication both in the wstd project's issue triage, and in other
projects.

### Leverage the Bytecode Alliance RFC Process

> A request for comments (RFC) is a technique for soliciting the community and contributors for feedback on proposed major changes and decisions.
>
> It is recommended that hosted projects follow [the Bytecode Alliance RFC process](https://github.com/bytecodealliance/rfcs/blob/main/accepted/rfc-process.md) for changes that significantly affect project stakeholders or contributors. The RFCs repo describes [when an RFC is needed](https://github.com/bytecodealliance/rfcs/#when-is-an-rfc-needed) in more detail:
>
> > Many changes to Bytecode Alliance projects can and should happen through every-day GitHub processes: issues and pull requests. An RFC is warranted when:
> >
> > * The work involves changes that will significantly affect stakeholders or project contributors. Each project may provide more specific guidance. Examples include:
> >     * Major architectural changes
> >     * Major new features
> >     * Simple changes that have significant downstream impact
> >     * Changes that could affect guarantees or level of support, e.g. removing support for a target platform
> >     * Changes that could affect mission alignment, e.g. by changing properties of the security model
> > * The work is substantial and you want to get early feedback on your approach.
>
> This is a best practice for aligning contributors, the community, and downstream projects' needs with proposed technical implementations.

The project will adopt the Bytecode Alliance RFC process after 
transferring the repo to the bytecodealliance GitHub org.

### Production Use

> It is recommended that hosted projects have demonstrated use in production by at least three independent organizations which are, in the TSC's judgement, of adequate quality and scope.
>
> It is recommended that projects track production usage by organizations in an `ADOPTERS.md` at the root of the project, for example see [`ADOPTERS.md`](https://github.com/bytecodealliance/wasmtime/blob/main/ADOPTERS.md) in Wasmtime.
>
> Projects should demonstrate that they are practical, useful, and reliable enough to use in production.

Created an ADOPERS.md in [#72]. This PR will be merged prior to transferring
the repo to the bytecodealliance GitHub org.

wstd is used by the [bytecodealliance/sample-wasi-http-rust] template.

[bytecodealliance/sample-wasi-http-rust]: https://github.com/bytecodealliance/sample-wasi-http-rust

### Public Project Meetings and Notes

> It is recommended that hosted projects hold regular and public project meetings. Meeting times and frequency should be advertised publicly, for example in the project's `CONTRIBUTING.md`. To avoid spam and "Zoom bombing", the video conferencing link need not be public, but should be available upon request.
>
> Agendas for upcoming meetings and notes from past meetings should be published publicly. The notes should be in the `bytecodealliance/meetings` repository.
>
> Public meetings encourage open communication, collaboration, and engagement within the project's community. Notes allow community members who were not present to remain aligned and can document any decisions made during the meeting.

The project currently does not hold regular meetings. We will start holding
regular meetings if the need emerges.


### Sanitizers and Code Analysis

> Static and dynamic code analysis tools (such as `valgrind` or `miri`) where applicable are recommended to be used by hosted projects.
>
> It is recommended that hosted projects with non-trivial amounts of unsafe code (e.g. `unsafe` in Rust or any C/C++)  run tests and fuzzers with the relevant sanitizers: Address Sanitizer, Memory Sanitizer, Thread Sanitizer, etc.
>
> Automated code analysis is key to meeting our mission of developing runtime environments and language toolchains where security, efficiency, and modularity can all coexist.

The project does not currently use sanitizers. The project contains no unsafe
code, and enforces this with `#![forbid(unsafe_code)]` at the library level.
CI includes `cargo clippy` for code analysis as part of [#72].
