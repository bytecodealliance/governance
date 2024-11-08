# Bytecode Alliance Core and Hosted Project Requirements

This document defines the process for applying for adoption as a hosted project or promotion from hosted project to core project.

## What are Hosted and Core Projects?

The Bytecode Alliance holds itself and its projects, whether hosted or core, to exceptional standards. This is part of our principle of [curation](https://github.com/bytecodealliance/governance/blob/main/operational-principles.md?plain=1#L17-L23) and we do not believe we can accomplish our [mission](https://github.com/bytecodealliance/governance/blob/main/mission.md) otherwise.

Core projects are the Bytecode Alliance's flagships and are held to an even higher standard than hosted projects. In return, core projects are prominently advertised on the Bytecode Alliance webpage and can elect a delegate to the Bytecode Alliance's Technical Steering Committee, as per [the TSC charter](https://github.com/bytecodealliance/governance/blob/main/TSC/charter.md#composition).

Note that it is expected that most hosted projects will not become core projects, even if they satisfy the [technical requirements of core projects](../.github/ISSUE_TEMPLATE/core-project.md). Core project status is reserved for projects of exceptional strategic value to the Bytecode Alliance in the fulfillment of its mission. These projects typically have the following qualities:

* End-user facing and widely adopted
* Under active development and have long-term roadmaps
* Major-versioned releases

Core projects must further the mission of the Bytecode Alliance and be seen as vital to its success, as assessed by the TSC.

## Applying for Adoption as a Hosted Project

If you would like to propose that the Bytecode Alliance adopt your project as a new hosted project, you may perform the following steps:

* [ ] File an issue against [the Bytecode Alliance governance repository](https://github.com/bytecodealliance/governance) using [the "New Hosted Project" issue template](https://github.com/bytecodealliance/governance/issues/new/choose).
  * Fill in all of the `TODO`s.
  * Do not make unsubstantiated claims; provide evidence. For example, if you claim that your project performs code review, provide a handful of links to pull request reviews that demonstrate this.

The Bytecode Alliance Technical Steering Committee (TSC) will then perform the following steps:

* [ ] Provide timely acknowledgment of the application.
* [ ] Perform an in-depth review of the project, evaluate whether it meets the hosted project requirements, and decide based on consensus whether to accept the project.
* [ ] Reply in the issue with the results of the review, providing any feedback they might have, and whether the project has been accepted.
* [ ] If it has been accepted, then the TSC will work with maintainers on the logistics of moving the repository to the `bytecodealliance` github organization.

## Applying for Promotion from Hosted Project to Core Project

Once the project maintainers have come to a consensus agreement that they wish for their project's promotion to a core project, they may initiate the application process by performing the following steps:

* [ ] Create an issue within the [the Bytecode Alliance governance repository](https://github.com/bytecodealliance/governance) using [the "New Core Project" issue template](https://github.com/bytecodealliance/governance/issues/new/choose).
  * Fill in all of the `TODO`s.
  * Do not make unsubstantiated claims; provide evidence. For example, if you claim that your project has a CI job running tests under [AddressSanitizer](https://clang.llvm.org/docs/AddressSanitizer.html), provide links to its CI configuration, test infrastructure, and bugs caught.

The Bytecode Alliance Technical Steering Committee (TSC) will then perform the following steps:

* [ ] Provide timely acknowledgment of the application.
* [ ] Perform an in-depth review of the project:
  * The TSC will consider the strategic value of the project to the Bytecode Alliance, how it furthers the Bytecode Alliance's mission, as well as its value and influence in the broader community.
  * The TSC will evaluate whether it meets the technical requirements for core projects.
  * Finally, the TSC will decide based on consensus whether to promote the project.
* [ ] Reply in the issue with the results of the review, providing any feedback they might have, and whether the project has been promoted.
* [ ] If it has been promoted, then the project maintainers will [choose a delegate to represent the project on the TSC](https://github.com/bytecodealliance/governance/blob/d0310b2f4fab7d5bd076627b196dfc0ffe040ec1/TSC/charter.md#composition).

## Handling of Existing Projects

At the point of adoption of these requirements, all existing projects are implicitly treated as Hosted Projects. The TSC will over time work with project maintainers to ensure that they satisfy the requirements for Hosted Projects, and explicitly add their projects to the list of Hosted Projects.

Additionally, we encourage maintainers of existing projects to consider applying for Core Project status, if they believe their project is a good fit, of exceptional strategic Bytecode Alliance value, and in compliance with the stricter requirements.
