# Proposal to Create Wasmtime

This document is a proposal to promote Wasmtime to a Core Project, as specified in the TSC’s charter.

Repository URL: https://github.com/bytecodealliance/wasmtime

Wasmtime is a lightweight WebAssembly runtime that is fast, secure, and standards-compliant.

> **Note:** The Wasmtime repository also contains the [Cranelift](https://github.com/bytecodealliance/wasmtime/tree/main/cranelift) code generator. Cranelift is a separate project with other uses besides Wasmtime, and isn't seeking Core Project status at this time.

## Requirements

### Alignment with the Bytecode Alliance Mission

> Projects must have alignment with [the Bytecode Alliance mission:](https://github.com/bytecodealliance/governance/blob/main/mission.md)
>
> > Our mission is to provide state-of-the-art foundations to develop runtime environments and language toolchains where security, efficiency, and modularity can all coexist across a wide range of devices and architectures. We enable innovation in compilers, runtimes, and tooling, focusing on fine-grained sandboxing, capabilities-based security, modularity, and standards such as WebAssembly and WASI.
>
> The Bytecode Alliance is a group with a specific mission, and we therefore will only sponsor projects that are in alignment with and further that mission. For example, project sponsorship is untenable if the project undermines sandboxing, security, or standardization efforts.

From its inception as a project, Wasmtime has been focused on the same goals the Bytecode Alliance is pursuing as a whole. As such, it has always served as a core part of how the Bytecode Alliance is pursuing its mission, and has always strived to hold itself to the highest standards.

The [original announcement](https://bytecodealliance.org/articles/announcing-the-bytecode-alliance) of the Bytecode Alliance introduced the term "nanoprocess": a fine-grained unit of composable functionality which gets access to those, and only those, capabilities it needs to serve its purpose. This concept ultimate became the foundation of the [WebAssembly Component Model](https://component-model.bytecodealliance.org/), with [WASI](https://wasi.dev/) as a set of standardized APIs to facilitate communication with outside systems.

From the beginning, Wasmtime has been a key part of driving the vision of the Component Model and WASI forward: the project has consistently spearheaded the implementation of the standards underlying this vision.

To ensure that Wasmtime can serve the purpose of supporting the exploration and realization of new proposals, the maintainers are taking care to keep the code base approachable. Among the more than [1000 papers on Google Scholar](https://scholar.google.com/scholar?q=wasmtime) to mention Wasmtime as of this writing, [a recent meta-study](https://arxiv.org/pdf/2404.12621) on the use of different runtimes in academic research shows this paying off: as documented in section 6.2 of that paper (and visualized in figure 16 on page 23), 30% of all analyzed papers used Wasmtime as the test bed for research into feature addition, with the next most popular runtime at 17.5%.

Aside from feature work, Wasmtime's well-maintained and approachable code base also helps its maintainers in treating security as a hard requirement that can't be traded off against any other priorities, as described in a [post on the Bytecode Alliance blog](https://bytecodealliance.org/articles/security-and-correctness-in-wasmtime) in 2022.

To further the Bytecode Alliance goal of bringing security, efficiency, and modularity to a wide range of use cases and platforms, Wasmtime is designed to be usable in a diverse set of environments. To satisfy different tradeoffs between peak performance, fast startup, and portability, it integrates three different execution engines:
1. the optimizing [Cranelift](https://github.com/bytecodealliance/wasmtime/tree/main/cranelift) compiler
2. the baseline [Winch](https://github.com/bytecodealliance/wasmtime/tree/main/winch) compiler,
3. the [Pulley](https://github.com/bytecodealliance/wasmtime/tree/main/pulley) interpreter (currently in-progress).

Combined with the ease of portability that Wasmtime's [support for `#![no_std]` environments](https://docs.wasmtime.dev/stability-platform-support.html#support-for-no_std) brings, Wasmtime is portable and usable in environments ranging from small embedded devices to large-scale compute clusters.

More details on the various aspects of this can be found in the comments on the other requirements below.

### Changelog

> Core projects must highlight key additions, breaking changes, security fixes, and otherwise noteworthy changes in a changelog.
>
> See [keepachangelog.com](https://keepachangelog.com/en/1.1.0/) for a recommended approach.
>
> We are building an ecosystem that developers can depend on, and one small part of that is communicating important changes downstream.

The Wasmtime project publishes detailed release notes for all releases, and keeps an up-to-date [index of the notes](https://github.com/bytecodealliance/wasmtime/blob/main/RELEASES.md) for each release. These notes include lists of notable bug fixes, changes to existing functionality, and newly introduced features or functionality.

Additionally, blog posts covering the releases and highlighting key changes are regularly published to the Bytecode Alliance blog.

Recent examples of changelogs and announcement posts include
- https://bytecodealliance.org/articles/wasmtime-27.0
- https://github.com/bytecodealliance/wasmtime/blob/release-27.0.0/RELEASES.md
- https://bytecodealliance.org/articles/wasmtime-26.0
- https://github.com/bytecodealliance/wasmtime/blob/release-26.0.0/RELEASES.md

### Code Review

> All projects must gate merging pull requests on code reviews that audit not only for style but also substance, such as whether security invariants are properly maintained by the new code.
>
> Core projects must maintain [a `CODEOWNERS` file](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-code-owners) and use it to automatically assign reviewers to pull requests. Auto-assigned reviewers must respond to pull requests in a timely fashion. However, that response doesn't have to be a full code review; it could also be
>
> - "I intend to review this but I can't immediately. Please leave me a message if I haven't responded by `$SPECIFIC_DATE_IN_NEAR_FUTURE`."
> - "I think `$SPECIFIC_OTHER_MAINTAINER` should review this." (Note that the best reviewer for a PR may not necessarily be listed in the `CODEOWNERS` file.)
>
> Code reviews have a demonstrable impact on the quality of source code by catching bugs early, determining the best possible implementation, and fostering trust within the community. Timely responses let contributors know that their work is valued and encourages further contribution.

Wasmtime has a [CODEOWNERS file](https://github.com/bytecodealliance/wasmtime/blob/main/CODEOWNERS) gating all merges, and auto-assigns the [@bytecodealliance/wasmtime-core-reviewers](https://github.com/orgs/bytecodealliance/teams/wasmtime-core-reviewers) team to review PRs.

The review process is highly efficient, with [a medium response time of 6 hours](https://next.ossinsight.io/analyze/bytecodealliance?repoIds=101767772&period=past_12_months#pull-request-efficiency) over the last year.

Good recent examples of the typical review experience for Wasmtime include
* https://github.com/bytecodealliance/wasmtime/pull/9668
* https://github.com/bytecodealliance/wasmtime/pull/9659
* https://github.com/bytecodealliance/wasmtime/pull/9520

### Code of Conduct

> All Bytecode Alliance projects must:
>
> * link to the Bytecode Alliance's Code of Conduct documents from a `CODE_OF_CONDUCT.md` file in root of the repository, and
> * enforce the codes of conduct among the community and contributors, or escalate to [the Bytecode Alliance CoC Team](mailto:report@bytecodealliance.org), if needed.
>
> Having a code of conduct is crucial for creating a positive and respectful environment in any organization, community, or group. It serves as a set of guidelines that outline expected behavior and ethical standards for all members involved.

Wasmtime has a [CoC file](https://github.com/bytecodealliance/wasmtime/blob/main/CODE_OF_CONDUCT.md) in its repository, and the project takes CoC enforcement very seriously.

Over the years, there have been situations where individuals violated the CoC or skated very close to doing so, and the project has always acted on those instances without delay as soon as maintainers gained awareness of them.

Since it doesn't seem appropriate to call out specific instances of this in a public document, this application doesn't include links to them as evidence. Those can be provided to the TSC in private communication as needed, though.

### Continuous Fuzzing

> Not all projects will necessarily benefit from fuzzing, for example benchmark suites. The TSC may choose lift this requirement for a particular project.
>
> It is required that core projects have continuous fuzzing, for example in [OSS-Fuzz](https://github.com/google/oss-fuzz). The fuzzing must exercise significant amounts of the code base and test the project's most important properties, such as sandboxing. Bugs and vulnerabilities discovered via fuzzing must be addressed promptly.
>
> Part of our open-source and open contribution model, the corpus and setup for running fuzzing must be open-sourced as part of the project.
>
> Faults discovered via fuzzing must be reported privately to the project's core team so that the project's security vulnerability process can be followed properly, if necessary. For example, fuzzing infrastructure must not automatically open public issues for any fault that is discovered.
>
> Continuous fuzzing is a valuable practice for projects, due to its significant benefits in improving security and reliability. Within the Bytecode Alliance, we host projects that provide a sandbox. The fidelity of these sandboxes must be battle-tested via a number of methodologies including automated fuzzing.

Wasmtime was the first Rust project admitted to OSS-Fuzz, spearheading Rust fuzzing infrastructure. As [described in a 2022 blog post](https://bytecodealliance.org/articles/security-and-correctness-in-wasmtime#ubiquitous-fuzzing), Wasmtime has since gained a rich set of different fuzzers, which are run against all code landing on `main` that's active in the default compile configuration.

This catches that vast majority of issues before they become exploitable vulnerabilities, since our release process guarantees at least a 2-week window between code landing on `main` and any release including that code.

The fuzzing doesn't just include Wasmtime itself, but also its dependency tree, notably including Cranelift, [regalloc2](https://github.com/bytecodealliance/regalloc2/), and [wasm-tools](https://github.com/bytecodealliance/wasm-tools). Wasmtime's fuzzing additionally strives to be as comprehensive as possible to go above-and-beyond "just compile the fuzz input as wasm". The Wasmtime project has invested heavily in design patterns for fuzzing in Rust such as the [`arbitrary` crate](https://crates.io/crates/arbitrary), the [`wasm-smith`](https://crates.io/crates/wasm-smith) crate, [integration with the spec interpreter](https://github.com/bytecodealliance/wasmtime/tree/main/crates/fuzzing/wasm-spec-interpreter), etc. Wasmtime's fuzzing includes a large suite of fuzz targets such as:

* [Arbitrary bytes can be thrown at the validator](https://github.com/bytecodealliance/wasm-tools/blob/main/fuzz/src/validate.rs)
* [Low-level tooling can roundtrip any module without crashes](https://github.com/bytecodealliance/wasm-tools/blob/main/fuzz/src/roundtrip.rs)
* [Arbitrarily generated modules are valid](https://github.com/bytecodealliance/wasm-tools/blob/main/fuzz/src/validate_valid_module.rs)
* [Arbitrary bytes can be compiled as wasm](https://github.com/bytecodealliance/wasmtime/blob/main/fuzz/fuzz_targets/compile.rs)
* [Any valid module can be instantiated](https://github.com/bytecodealliance/wasmtime/blob/main/fuzz/fuzz_targets/instantiate.rs)
* [Instantiating sets of modules works](https://github.com/bytecodealliance/wasmtime/blob/main/fuzz/fuzz_targets/instantiate-many.rs)
* [Differential execution against V8, the spec interpreter, wasmi, and Wasmtime itself](https://github.com/bytecodealliance/wasmtime/blob/main/fuzz/fuzz_targets/differential.rs)
* [Arbitrary component values can be used from Wasmtime and round-trip](https://github.com/bytecodealliance/wasmtime/blob/main/fuzz/fuzz_targets/component_api.rs)
* [Memory accesses from wasm behave as expected](https://github.com/bytecodealliance/wasmtime/blob/main/fuzz/fuzz_targets/memory_accesses.rs)
* [Stack traces always work regardless of how "interesting" the wasm stack is](https://github.com/bytecodealliance/wasmtime/blob/main/fuzz/fuzz_targets/stacks.rs)
* [GC operations are stressed specifically in tables](https://github.com/bytecodealliance/wasmtime/blob/main/fuzz/fuzz_targets/table_ops.rs)
* [All spec tests from upstream are run with arbitrary configuration parameters](https://github.com/bytecodealliance/wasmtime/blob/main/fuzz/fuzz_targets/wast_tests.rs)

Wasmtime has a large number of configuration knobs and fuzzing does not only cover the default settings of these knobs. Wasmtime's fuzzing will generate [arbitrary configurations for an `Engine`](https://github.com/bytecodealliance/wasmtime/blob/main/crates/fuzzing/src/generators/config.rs) to test interesting combinations of settings to ensure that non-default settings work the same as default settings.

All of Wasmtime's fuzzing is targetted at testing as much as possible about the WebAssembly sandbox. There are many components to Wasmtime and its runtime and many of them are security critical and all are required to be fuzzed to be considered ["tier 1 supported"](https://docs.wasmtime.dev/stability-tiers.html) in Wasmtime. For example aarch64, despite having a high-quality implementation, is not considered "tier 1" in Wasmtime because we don't have continuous fuzzing for it yet.

### Continuous Integration Testing

> All projects must run continuous integration (CI) tests on all pull requests and merges. Key project features must be covered by CI.
>
> If any part of the CI gates on merging changes that is not reproducible by external contributors, then the project must make affordances to support those external contributors.
>
> Implementing CI offers several benefits to software projects, helping ensure correctness and quality, making it an essential practice for modern software development.

Wasmtime is [using GitHub Actions for CI and CD](https://github.com/bytecodealliance/wasmtime/actions/workflows/main.yml), running extensive test suites and automated builds for all supported configurations and build targets. [As of this writing](https://github.com/bytecodealliance/wasmtime/actions/runs/12166939009/usage), before changes are merged into the `main` branch, they run through a set of tests and builds for a total of more than 12 hours (within a timeframe of about 16 minutes wall-clock time). As part of this, we generate binary artifacts for all supported platforms and build configurations, and run test suites covering
- Spec tests for all supported features
- Embedding API tests
- CLI tests
- Smoke tests ensuring that the fuzzing setup still works
- Unit tests for various parts of the code base
- `cargo vet` checks ensuring the security of our supply chain
- Generation of documentation and checking of examples to ensure they continue working

Everything happening in CI is fully public and reproducible by the public, ensuring full auditability by external parties of all code and the entire build process without active support by the project.

### Contributor Documentation

> All projects must have a `CONTRIBUTING.md` document in the root of their repository. This document must provide, or link to another form of project-specific documentation that provides, high-quality contributor documentation.
>
> See ["How to build a `CONTRIBUTING.md`" by the Mozilla Science Lab](https://mozillascience.github.io/working-open-workshop/contributing/) for more details on what a high-quality `CONTRIBUTING.md` file looks like.
>
> A `CONTRIBUTING.md` serves as a guide for potential contributors, outlining the expectations for individuals who wish to contribute to the project. The Bytecode Alliance is a community-driven software foundation and documents like `CONTRIBUTING.md` are necessary for fostering community contributions.

Wasmtime's repository contains a [CONTRIBUTING.md](https://github.com/bytecodealliance/wasmtime/blob/main/CONTRIBUTING.md) file, though that mainly links to the [contributing section](https://docs.wasmtime.dev/contributing.html) of Wasmtime's online documentation.

That section contains detailed information about how to [get started with building](https://docs.wasmtime.dev/contributing-building.html) and making changes to Wasmtime, [how changes are tested](https://docs.wasmtime.dev/contributing-testing.html), what to expect [when making a pull request](https://docs.wasmtime.dev/contributing-ci.html), [recommended guidelines](https://docs.wasmtime.dev/contributing-coding-guidelines.html) for code an dependencies, [which changes would be acceptable](https://docs.wasmtime.dev/contributing-development-process.html), [how to engage with the community](https://docs.wasmtime.dev/contributing.html), etc. Wasmtime also has documentation for maintainers such as [review guidelines](https://docs.wasmtime.dev/contributing-code-review.html) and how to [make a release](https://docs.wasmtime.dev/contributing-release-process.html) as part of the same documentation.

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
> All of the above types of documentation are required for core projects.
>
> Documentation is necessary for end-users to productively use the project; source code comments are not sufficient.

Wasmtime has extensive online documentation, which is required to keep up-to-date as part of changing the code base. Wherever possible, the correctness of documentation is checked during CI.

The documentation includes among other topics:
- [API Docs](https://docs.wasmtime.dev/lang.html)
- [Examples](https://docs.wasmtime.dev/examples.html)
- An [Architecture Overview](https://docs.wasmtime.dev/contributing-architecture.html)

The docs don't have a dedicated section for tutorials. Instead, the examples are documented in a way that makes it possible to follow them like tutorials.

### Following the Bytecode Alliance Operational Principles

> All projects must follow [the Bytecode Alliance Operational Principles](https://github.com/bytecodealliance/governance/blob/main/operational-principles.md).
>
> In pursuing our mission and vision, the Bytecode Alliance follows a set of operational principles aimed at keeping us aligned on three key aspects: what we want to create, how we want to work together, and how we want to work with others.

The Wasmtime project takes great care to uphold the standards set out in the BA's Operational Principles. Since the technical and procedural aspects are covered elsewhere in this application, here we want to focus on aspects related to norms we hold ourselves to, and how we engage with the outside world.

A major part of how Wasmtime interacts with other venues is as part of the standardization process of WebAssembly and in particular the Component Model, and WASI. Wasmtime is dedicated both to helping drive innovation in the standards process by spearheading new proposals and implementation techniques, as well as to staying faithful to the standards and consistently staying fully compliant with them.

This means that we invest substantially in engaging with the standards processes and maintain a strong presence and standing in the respective committees, since otherwise we'd not be able to satisify our users' and contributors' requirements. As described in the [requirements for enabling features by default](https://docs.wasmtime.dev/stability-wasm-proposals.html#feature-requirements)
* We do not implement Wasm-visible features, instructions, host calls, and language extensions that are not standards-track.
* We do not enable Wasm proposals by default until they are stage 4 or later[^1].
* We run the standard spec test suite and ensure that our behavior does not diverge from that which is required by the standard.
* We upstream new spect tests as we identify corners of the semantics that the existing suite does not exercise

### Issue Triage Process

> Core projects must use an issue tracker for tracking individual issues.
>
> Core projects must have a documented process for expeditiously triaging incoming issues and pull requests, and follow that process. Contributors should get prompt responses to their issues and pull requests, even if a response is not an immediate fix or review.
>
> For a successful community-driven project, expedient communication within issues and PRs encourages further collaboration and contribution.

Wasmtime uses GitHub Issues for issue tracking and has a [good track record of responsiveness](https://next.ossinsight.io/analyze/bytecodealliance?period=past_12_months&repoIds=101767772#issue), with the median issue being addressed within 5h. Additionally, the project [just introduced](https://github.com/bytecodealliance/meetings/pull/492/commits/b89c4edaf5fc60b253a57d24fdecb3282ef56d1e) a formal triage process as part of the bi-weekly project meetings.

### Leverage the Bytecode Alliance RFC Process

> A request for comments (RFC) is a technique for soliciting the community and contributors for feedback on proposed major changes and decisions.
>
> Core projects must follow [the Bytecode Alliance RFC process](https://github.com/bytecodealliance/rfcs/blob/main/accepted/rfc-process.md) for changes that significantly affect project stakeholders or contributors. The RFCs repo describes [when an RFC is needed](https://github.com/bytecodealliance/rfcs/#when-is-an-rfc-needed) in more detail:
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
> This is a best practice for aligning contributors, the community, and downstream project's needs with proposed technical implementations.

Wasmtime employs the RFC process for a wide range of decisions and proposed changes. Examples include among others
- the [definition of security issues](https://github.com/bytecodealliance/rfcs/blob/main/accepted/what-is-considered-a-security-bug.md) that require a vulnerability response process and [how to run](https://github.com/bytecodealliance/rfcs/blob/main/accepted/vulnerability-response-runbook.md) such a process
- the [design of a new embedding API](https://github.com/bytecodealliance/rfcs/blob/main/accepted/new-api.md)
- the introduction of a new [baseline code generator](https://github.com/bytecodealliance/rfcs/blob/main/accepted/wasmtime-baseline-compilation.md) and an [interpreter](https://github.com/bytecodealliance/rfcs/blob/main/accepted/pulley.md)
- the [scope and requirements for a 1.0 release](https://github.com/bytecodealliance/rfcs/blob/main/accepted/wasmtime-one-dot-oh.md) as well as how further stable releases should be done

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

Wasmtime fully complies with the BA's license requirements. All code in the Wasmtime repository is licensed under the Apache-2.0 WITH LLVM-exception, and all third-party dependencies use licenses on the permitted list.

Ongoing license compliance is [ensured in CI using `cargo deny`](https://github.com/bytecodealliance/wasmtime/blob/100e90bcca285d3b1146995b65105da91583c3d1/.github/workflows/main.yml#L102).

### Production Use

> Core projects must have demonstrated use in production by at least three independent organizations which are, in the TSC's judgement, of adequate quality and scope.
>
> It is recommended that projects track production usage by organizations in an `ADOPTERS.md` at the root of the project, for example see [`ADOPTERS.md`](https://github.com/bytecodealliance/wasmtime/blob/main/ADOPTERS.md) in Wasmtime.
>
> In order to become a core project, that project must demonstrate that it is practical, useful, and reliable enough to use in production.

Wasmtime maintains an [ADOPTERS.md](https://github.com/bytecodealliance/wasmtime/blob/main/ADOPTERS.md) which as of this writing lists 10 production uses. Together, these documented uses represent adoption at substantial scale, with Wasmtime being part of processes that many millions of people interact with daily. Besides these formally documented uses, the project is aware of wide-spread additional production use, evidence of which can be provided to the TSC as needed.

### Public Project Meetings and Notes

> Core projects must hold regular and public project meetings. Meeting times and frequency must be advertised publicly, for example in the project's `CONTRIBUTING.md`. To avoid spam and "Zoom bombing", the video conferencing link need not be public, but must be available upon request.
>
> Agendas for upcoming meetings and notes from past meetings must be published publicly. The notes should be in the `bytecodealliance/meetings` repository.
>
> Public meetings encourage open communication, collaboration, and engagement within the project's community. Notes allow community members who were not present to remain aligned and can document any decisions made during the meeting.

The Wasmtime project hosts a project meeting every other week. The meetings are open to the general public, with the signup process [fully](https://docs.wasmtime.dev/contributing.html#join-our-chat) [documented](https://github.com/bytecodealliance/meetings/blob/main/wasmtime/README.md). Agendas for the meeting are published ahead of time, and meeting notes afterwards—both in the BA's [meetings repository](https://github.com/bytecodealliance/meetings/tree/main/wasmtime).

### README

> All projects must have a `README.md` file in the root of the repository which begins with:
>
> * The project name and logo (if one exists)
> * A one-sentence description of the project
> * `<strong>A <a href="https://bytecodealliance.org/">Bytecode Alliance</a> core project</strong>`
>
> The most important information about the project should be "above the fold". Projects should identify themselves as Bytecode Alliance projects so that with time they associate the Bytecode Alliance with quality projects that they can rely on.

The Wasmtime project's repository contains a detailed [top-level README.md](https://github.com/bytecodealliance/wasmtime/blob/main/README.md) satisfying all requirements.

Additionally, many of the crates Wasmtime consists of include their own dedicated `README.md` files, containing information specifically about the crate in question.

### Release Process

> Documentation of a release process that any project maintainer may execute to create a new release version of the software.
>
> Multiple people must have permissions to publish releases. A github team must have access to publish packages and package ownership on the associated package repository when possible. For example a Rust project may have multiple owners on crates.io.
>
> Core projects must additionally leverage a fully-automated release process, where the only manual step performed by project maintainers is to trigger the process (for example by starting a github workflow or merging an automated pull request).
>
> Projects and their releases shouldn't be tied to any single user's machine or keys to ensure continuity of the project. A project isn't an open, community project if only one person can publish releases.
>
> Automation makes fewer mistakes than humans, and getting releases right is critical, since only releases are typically used downstream, not random commits from `main`.

Wasmtime's release process is [fully-automated](https://github.com/bytecodealliance/wasmtime/tree/main/.github/actions/github-release) using GitHub Actions, and for stable releases happens from dedicated branches for the respective versions. All released artifacts are fully built using this workflow, which can be fully reproduced (in the sense of being able to run the same process without limitations, not in the sense of "reproducible builds" with bit-identical artifacts) by external parties.

The official releases and the way they are published use GitHub Actions' key management, such that no single individual's participation is required to run the official release process. The release process is started through calendar-based automation by the [wasmtime-publish](https://github.com/wasmtime-publish) account opening a PR on the Wasmtime repository, which is then approved and merged by a maintainer.

This process is used both for regular stable releases and for patch releases, including those addressing security issues.

### Sanitizers and Code Analysis

> Static and dynamic code analysis tools (such as `valgrind` or `miri`) where applicable must be used by core projects.
>
> Core projects with non-trivial amounts of unsafe code (e.g. `unsafe` in Rust or any C/C++) must run tests and fuzzers with the relevant sanitizers: Address Sanitizer, Memory Sanitizer, Thread Sanitizer, etc.
>
> Automated code analysis is key to meeting our mission of developing runtime environments and language toolchains where security, efficiency, and modularity can all coexist.

Wasmtime's implementation language, Rust, is safe by default. Wasmtime has a nontrivial amount of `unsafe` code, however, and expects all unsafe code is thoroughly tested on CI. Integration beyond unit tests at this time is:

* The test suite, to the extent possible, is [run](https://github.com/bytecodealliance/wasmtime/blob/8df32f7fb2c0cd6295239471822f4032b8223c0e/.github/workflows/main.yml#L1054) through the Rust tool [Miri](https://github.com/rust-lang/miri), which is an undefined behavior detection tool for Rust. This has caught possible vulnerabilities in the past and is a requirement, where possible, for any new `unsafe` code in the repository.
* OSS-Fuzz compiles all of Wasmtime's fuzzers with ASAN by default. Wasmtime has comprehensive coverage through its fuzzing and thus indirectly through ASAN via this method.
* Wasmtime [runs](https://github.com/bytecodealliance/wasmtime/blob/8df32f7fb2c0cd6295239471822f4032b8223c0e/.github/workflows/main.yml#L460) the [Clippy](https://github.com/rust-lang/rust-clippy) tool for Rust with extra lints enabled for critical portions of the runtime to enable noisier-than-default lints such as conversions between integer types to ensure that portions of the codebase can be more thoroughly reviewed/analyzed than others.


### Security Process

> All projects must have a documented security process for reporting and disclosing vulnerabilities, managing patches that fix vulnerabilities, and announcing and making available security releases. Furthermore, projects must actually follow their documented processes.
>
> Core projects must request Common Vulnerability and Exposure (CVE) numbers for discovered vulnerabilities and report the CVE when disclosing the vulnerability.
>
> A tool like [dependabot](https://github.com/dependabot) should be used for security updates only, and not apply all updates indiscriminantly. Updating dependencies should otherwise be done with intention (never automatically). Automatic creation of pull requests is acceptable, but manual review is required to prevent supply chain attacks.
>
> Bytecode Alliance projects must be a secure foundation for others to build upon. Transparency and a managed security release process is key to being this foundation.

Wasmtime uses a carefully designed process for [handling vulnerabilities](https://github.com/bytecodealliance/rfcs/blob/main/accepted/vulnerability-response-runbook.md), based on a [specific definition](https://github.com/bytecodealliance/rfcs/blob/main/accepted/what-is-considered-a-security-bug.md) of what's considered a vulnerability.

The [security advisories](https://github.com/bytecodealliance/wasmtime/security/advisories?state=published) published by the project provide a view into how this process has been run over the last few years. The maintainers believe this process to be highly effective at properly and rapidly handling (potential) vulnerabilities.

Additionally, Wasmtime's CI [runs](https://github.com/bytecodealliance/wasmtime/blob/8df32f7fb2c0cd6295239471822f4032b8223c0e/.github/workflows/cargo-audit.yml) a workflow for [cargo audit](https://github.com/rustsec/rustsec/tree/main/cargo-audit), ensuring that published vulnerabilities in dependencies are noticed right-away.

### Semantic Versioning

> All projects must follow either standard semantic versioning or their ecosystem's local-dialect of semantic versioning (for example, Rust and `cargo`'s interpretation of semantic versioning slightly differs from the standard, but is acceptable for Rust Bytecode Alliance projects).
>
> A clear versioning scheme is necessary for end-users. We desire consistency across projects and so the Bytecode Alliance has adopted semantic versioning as a required best practice.

Wasmtime follows the Rust ecosystem's approach to semantic versioning, with API incompatible changes being limited to major versions. Moreover, since a new major release of Wasmtime is released monthly, maintainers take care to reduce and document breaking changes.

A more detailed description to Wasmtime's approach to versioning can be found in the [1.0 release RFC](https://github.com/bytecodealliance/rfcs/blob/main/accepted/wasmtime-one-dot-oh.md#stability-and-future-development).

### Secrets Management

> GitHub organization and repository level secrets should be used. Secrets must not be hard coded in source.
>
> For secrets like passwords for the project's associated social media account, these should be stored in the password service paid for by the Bytecode Alliance. Contact the TSC for access and ability to manage a given secret.
>
> Secure secret management is a requirement for a secure project. Additionally, projects and their associated accounts shouldn't be tied to any single user's machine or keys to ensure continuity of the project. A project isn't an open, community project if only one person can access its accounts.

All secrets required to fully maintain Wasmtime are under organizational control of the Bytecode Alliance, with no individual having ownership over keys required for any aspect of maintenance. For the most part, this is ensured by using GitHub's secrets management.

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
> Our mission of developing runtime environments and language toolchains where security, efficiency, and modularity can all coexist necessarily means that we have performed our due dilligence to mitigate software supply chain attacks.

In addition to following strict procedures for reviewing code and running release processes, wasmtime strictly enforces passing a [cargo vet](https://mozilla.github.io/cargo-vet/index.html) check as [part of CI](https://github.com/bytecodealliance/wasmtime/blob/8df32f7fb2c0cd6295239471822f4032b8223c0e/.github/workflows/main.yml#L125) before any code is permitted to land on `main`. Where required, Wasmtime's maintainers will supply audits to permit new (versions of) dependencies. For example, [this PR](https://github.com/bytecodealliance/wasmtime/pull/8476) swapped some dependencies and included an audit of the new dependency.

### Sustainable Contributor Base

> All projects must have regular contributions from multiple contributors.
>
> Core projects must have contributors affiliated with at least two different Bytecode Alliance organizations and the project leadership must have representation from at least two different Bytecode Alliance organizations.
>
> There must not be any private information necessary to fully contribute to the project.
>
> A project is not considered healthy with only one contributor. An open, community project requires input from multiple stakeholders and does not rely on a single person.

Wasmtime regularly receives contributions from people affiliated with dozens of organizations, including multiple Bytecode Alliance member organizations. Over the last 12 months, the project [received contributions](https://github.com/bytecodealliance/wasmtime/graphs/contributors?from=12%2F2%2F2023) from 37 individuals (not counting automated accounts), representing at least 20 different organizations.

Core project maintainers are also employed by multiple different Bytecode Alliance member organizations (including Fastly, Fermyon, and Intel), ensuring good ongoing alignment with the BA's mission as well as representation in the wider BA.

### Version Control

> All projects must be hosted on [the Bytecode Alliance Organization](github.com/bytecodealliance) on GitHub.
>
> Access controls are managed via the Bytecode Alliance organization on GitHub. This allows for continuity of the project when hosted in one place. Finally, this is the only way to reasonable manage the projects within the organization.

Wasmtime itself and most of its key dependencies are hosted by the Bytecode Alliance on Github, using `git`. Where dependencies aren't hosted by the BA, they are established parts of the Rust ecosystem.

[^1]: The one exception to this rule is the Component Model, which is fundamentally required for WASI support, and considered stable in the context of its use in WASIp2 and onwards.
