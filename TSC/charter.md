# Bytecode Alliance Technical Steering Committee Charter

This document outlines the role, scope, and composition of the Bytecode Alliance Technical Steering Committee.

# The Committee

## Role

The Bytecode Alliance Foundation (“BA”) Technical Steering Committee (“TSC”) is a committee established by the BA’s Board of Directors (“Board”) to act as the top-level governing body for projects and Special Interest Groups hosted by the BA, to ensure that they further the BA’s [mission](https://bytecodealliance.org/mission), and to ensure that they are conducted in accordance with the BA’s [values and principles](https://bytecodealliance.org/mission#values).

The TSC operates in accordance with this Charter, material[^1] changes to which require approval by the Board per section 4.11.c.x of the BA’s [bylaws](https://bytecodealliance.org/assets/bylaws.pdf). Changes to this document are proposed via GitHub Pull Requests, where they can be discussed. To ensure interested parties can comment on them, material changes will be kept open for a time. The deadline for input will be listed in the Pull Request, but is recommended to be no less than 10 days unless the board concludes there is a strong reason to do otherwise. Any input will be considered and where seen as valid by the board reflected in changes to the Pull Request before merging.

At any point, the operational version of the charter is the one in the governance repository’s default branch.

## Responsibilities

### Setting the overall direction of BA technology, projects, and groups

Hosted projects and groups are key ways in which the BA pursues its mission. The TSC is tasked with setting an overall direction for hosted projects and groups that furthers this mission.

### Identifying gaps and future trends in the BA landscape

As both the outer landscape and existing hosted projects evolve, the BA’s portfolio of projects will over time show gaps that would decrease the BA’s impact. The TSC is tasked with proactively identifying these gaps and forming strategies for closing them.

This might involve reaching out to existing projects to work with them towards hosting them in the BA.

### Forming or adopting new projects and providing ongoing oversight

In coordination with the Board, the TSC will evaluate project donations, and, if they are a good fit for the BA’s portfolio, work with their communities to onboard them into the BA.

The TSC will establish the required onboarding processes, and steer project maintainers through them.

The TSC will work with leadership and communities of hosted projects to ensure ongoing alignment with the BA’s mission. See the section on [Project Governance](#project-governance) for details.

### Authoring or adopting formal statements or positions about the Bytecode Alliance’s position or technologies

In coordination with the Board, the TSC will author or adopt papers that articulate the strategic or technical positions of the Bytecode Alliance and its activities.

### Forming Special Interest Groups and providing ongoing oversight

In coordination with the Board, the TSC will establish [Special Interest Groups](#special-interest-groups) to facilitate collaboration on specific domains of interest.

The TSC will work with groups to ensure ongoing alignment with the BA’s mission.

### Coordinating between BA projects and groups

The TSC will provide both formal and informal channels for fostering communication between various projects and groups. This may include facilitating conflict resolution.

### Defining and fostering healthy community norms

* CoC enforcement, either directly or by delegation to a CoC committee.

* Conflict resolution across projects, and, when necessary, within a project.

### Formal governance responsibilities

Per the BA [bylaws](https://bytecodealliance.org/assets/bylaws.pdf), the TSC is tasked with multiple aspects of community representation:

* Nominating the TSC Director per section 4.4.b.iii

* Filling vacancies on the Board of Directors per section 4.7.a

* Establishing the Recognized Contributors Program per section 5.5.c

### Determining a member of the TSC to serve as the TSC Chair

Per section 5.5.b of the BA bylaws, the TSC is led by a TSC Chair. The TSC Chair leads the TSC, ensures that the TSC meets at a regular cadence, runs those meetings, and manages the RC program.

The TSC Chair is chosen by the members of the TSC. Selection begins by nominating candidates from the current TSC members. Unopposed candidates are seated by default. If there are multiple candidates, the contest is decided by a vote using the Condorcet-IRV method through the [Cornell online service](https://civs.cs.cornell.edu/).

The selection process runs whenever the TSC composition changes, the Chair steps down, or the current Chair’s tenure reaches a multiple of two years.

### Nominating the TSC Director to represent the TSC to the Board of Directors

The TSC Director acts as liaison between the Board of Directors and the TSC, both representing the TSC to the Board and updating the TSC on Board matters of relevance to the TSC.

Per section 5.5.b of the BA [bylaws](https://bytecodealliance.org/assets/bylaws.pdf), the TSC determines the process of choosing the nominee for the role of TSC Director. In the absence of a defined process, the role of TSC Director shall be filled by the TSC Chair.

### Defining minimum standards and framework for project or group operations (e.g. voting, formal roles, etc.)

A core responsibility of the TSC will be to define these minimum standards, which will be maintained in a separate document.

## Non-Responsibilities

### Exhaustively defining all aspects of project or group governance

The TSC is tasked with establishing **minimum** standards for governance and operations of hosted projects and groups. Within that framework, projects and groups are free to define their governance structure and operations in ways that best facilitate their goals.

### Overseeing all technical and architectural decisions

The TSC is tasked with ensuring alignment with the BA’s mission, and adherence to its operating principles. It is not responsible for tightly overseeing technical decisions or day-to-day operations of hosted projects or groups.

### Engaging with and maintaining relationships with external communities, organizations, and standards bodies

The TSC’s primary role is inward-facing. The task of providing governance for hosted projects and groups is different from that of external engagement and communication; the BA doesn’t put responsibility for both on a single group of people, and instead will establish a separate mechanism for assembling a dedicated body for the latter task.

## Composition

The TSC is composed of project representatives and individuals elected by [Recognized Contributors](#recognized-contributors); member organizations don’t have direct representation.

The way TSC members are determined differs by the type of representation:

* The Recognized Contributors elect 3 TSC delegates

* Each Core Project appoints, by a process of its choosing, a delegate to represent the project to the TSC

There are no required entry qualifications for someone to be a TSC delegate—projects and Recognized Contributors are free to determine/elect delegates of their choosing without constraints beyond being in good standing with the BA and community.

The TSC operates on a two-year term cycle. An individual may be reelected or renominated to serve multiple terms.

When a new project is adopted or changes status from Hosted to Core Project, the project’s maintainers can immediately appoint a delegate to the TSC, who will then serve out the remainder of the current 2 year term.

When a project moves from Core to Hosted status, or stops being a hosted project altogether, its direct representation to the TSC ends with the change in status.

If a project is adopted or changes tier during a vote, the vote will be concluded before any changes to voting members are made.

The TSC should strive to attain balance of representation, not giving undue control to a single company. Future revisions to the charter may define mechanisms by which this balance is attained.

# Project Governance

## Core and Hosted Projects

By default, a project adopted by the BA is considered a Hosted Project. The BA board designates specific projects as Core Projects, requiring adherence to heightened standards around project governance, mission alignment, communication, and security. In exchange, Core Projects get more support, and stronger representation in the TSC — see the [section on TSC composition](#composition) above. Core Projects must meet all the requirements of Hosted Projects, but each project has exactly one status — Hosted or Core.

## Requirements for Hosted Projects

* Alignment with BA mission and goals

* Open governance

* Correct licenses or ability to change license to correct one

* Apache 2.0 or exception granted by the board

* No processes that give any organization an elevated position

* Stricter alignment and process requirements for Core than Hosted projects

* Good software development (pull requests, issue maintenance) and security practices (reporting, responding to issues)

* Including compliance with the [BA’s security policies](https://bytecodealliance.org/security)

* Under active development or maintenance

* BA ownership of name/trademark/social media channels, etc

## Hosted Project Review

The TSC may instigate a review of a Hosted Project at any time. In part, this review will evaluate whether the project continues to meet the requirements above. If it feels it necessary, it can remove or replace a chair, make binding recommendations regarding the project’s operation, or archive the project.

Projects that are unmaintained or see very little activity for prolonged periods (a year or more) are candidates for archiving.

If project archiving is being considered, the project will be informed at least two weeks before a decision is made, to give participants an opportunity to provide input.

If, during review, it is determined that a project is best continued outside of the Bytecode Alliance, the TSC will work with project leadership and the Board to determine the appropriate steps.

# Recognized Contributors

Per section 5.5.c of the BA’s bylaws, the TSC is tasked with establishing and overseeing the Recognized Contributors Program (“RC Program”). The RC Program governs how individual contributors to the BA participate in governance, including through nominating candidates and voting in elections for the At-Large Director(s) on the BA’s Board per section 4.4.b.iv of the BA’s bylaws, and through participating in elections to the TSC.

A Recognized Contributor (“RC”) is an individual who is actively involved in the Bytecode Alliance and/or its hosted projects or groups and helps further the BA’s goals. While it is expected that many RCs will be tightly associated with specific hosted projects or groups, the RC status is not tied to projects or groups, and there are no per-project or -group quotas for RCs.

Because there are many ways to support the BA’s goals, and not all of them are easy to capture in strict definitions, what “actively involved” means is intentionally kept vague. Similarly, the process for determining RCs is intentionally low-friction:

An individual contributor can, independently of affiliation with any BA member organization, be nominated or self-nominate for RC status by opening a Pull Request on the BA’s governance repository, adding their name and information (including project affiliations/roles/etc where applicable) to the list of Recognized Contributors. The Pull Request should include an informal description of the nature of the candidate’s ongoing involvement, and may optionally include further information, such as endorsements by existing RCs.

The process for merging or closing such a Pull Request is as follows:

* For non-self-nominations, the nominee needs to sign off on the Pull Request for it to be merged

* If the nominee doesn’t sign off within 15 days from the date the Pull Request was opened, it is closed without merging

* If at least two TSC members who are not both affiliated with the same organization sign off on the Pull Request, and no TSC member objects, the Pull Request is merged after at least 10 days from the date the Pull Request was opened

* Otherwise, a decision is made during the next meeting of the TSC where space on the agenda can be found, via consensus or simple-majority vote if consensus can’t be achieved. If consensus is reached, a Pull Request can also be merged sooner than 10 days after opening

* If no positive decision is made, the TSC may choose to provide feedback to the candidate on how to amend the application, or close the Pull Request unmerged with an explanation for why the application was not accepted at this time

While membership in the RC Program doesn’t require active renewal, the TSC will from time to time, and at least before elections to the TSC or for the At-Large Director positions evaluate the list of current RCs to determine whether all members are still actively involved. Since the principal duty of an RC is to participate in the BA’s governance, voting in the relevant elections is considered a requirement for retaining RC status in addition to active involvement. An RC might be determined inactive if they fail to vote in 2 or more consecutive elections, and would have to be nominated again to regain RC status. If any current members are determined not to be active anymore, the TSC will at a meeting ratify (or modify) this determination and then update the list accordingly.

The RC Program will be established and run by a bootstrapping task force appointed by the board (proto-TSC) until the first TSC election.

# Special Interest Groups

The Bytecode Alliance is focused on creating secure, foundational technology for WebAssembly, including WASI. However, it’s become clear that there is significant community interest in discussions around the application of that technology to vertical use cases.

To accommodate those discussions and assure that the community’s valuable feedback can be channeled into the Bytecode Alliance’s core functions, this document proposes the formation of Interest Groups.

## What is an Interest Group?

A Interest Group is a group of Bytecode Alliance members (and invited participants; see below) who share an interest in a particular application or aspect of the technology that the Bytecode Alliance is working on. IGs serve as a channel for practitioners and users of BA technology to give feedback and input to the development of its technology, as well as a space for them to discuss how to use it.

## Creating an Interest Group

Any member of the Bytecode Alliance can propose the creation of an Interest Group. Proposals should be made in writing, clearly identify the scope and goals of the IG, and list the member(s) supporting its creation.

The TSC will consider the proposal and make a decision in a reasonable timeframe. It may adopt the proposal as made, but it can also modify the proposal if it believes it necessary.

## Interest Group Membership

Each Interest Group will have one or more Chairs, appointed by the TSC. Any member of the Bytecode Alliance as well as hosted projects can send one or more representatives to the IG. Additionally, the IG may decide to invite individual persons who are not affiliated with a member or a hosted project to join an IG. Such Invited Participants are able to participate in the IG, but while positive contributions to an IG’s activities can lead to becoming a Recognized Contributor, simply being an Invited Participant does not automatically confer the status of Recognized Contributor or any other formal roles in Bytecode Alliance governance.

## Interest Group Operation

The Board of Directors will create resources (such as mailing lists and repositories) for an Interest Group.

Interest Group decisions should be made based upon consensus; if someone has strong objections, they should be heard and considered before being overridden. If a decision cannot be made by consensus, a simple majority vote of participating Bytecode Alliance members will decide the matter.

The IG Chair(s) are responsible for arranging meetings, distributing agendas and minutes, and recording decisions. All IG business is to be conducted in public. The existence and charter of an interest group are to be made public, but the interest group may decide for itself whether its ongoing activity is made public.

Interest Groups must operate in a manner that ensures ongoing alignment with the mission and operating principles of the Bytecode Alliance. Disagreement on whether specific aspects of the IG’s operations or outputs adhere to this requirement can be escalated to the TSC, which will provide an evaluation and, where it deems it necessary, recommend or request specific remediative measures. Additionally, the TSC might on its own accord engage with an IG to address potential alignment issues.

## Interest Group Deliverables

Interest Groups cannot create technical specifications, but they may publish Notes - descriptive documents that might be use cases, requirements, descriptions of current practice, etc. Such documents must be clearly labeled as the output of the IG, and must state that they do not necessarily represent the Bytecode Alliance or its members.

Likewise, while IGs can create software, tests or other technical artefacts, they must clearly represent themselves as originating from the IG, not the Bytecode Alliance. This extends to package names.

All deliverables from the IG must abide by the [Bytecode Alliance IP policy](https://bytecodealliance.org/assets/ip-policy.pdf), including the licensing of any software or documentation produced by the IG.

An IG can propose turning some or all of its deliverables into projects hosted by the Bytecode Alliance. In such a case, the TSC will work with the IG to determine whether the project(s) will be Core or Hosted Projects, and work through ensuring that all conditions for the chosen tier are met.

An IG can furthermore propose that other artifacts, such as published Notes, be adopted as Bytecode Alliance artifacts. In such a case, the TSC will work with the IG to transform the material into a formal Bytecode Alliance document (position, recommendation, note).

## Interest Group Review

The TSC may instigate a review of an Interest Group at any time. If it feels it necessary, it can remove or replace a chair, make binding recommendations regarding the IG’s operation, or close the group.

Interest Groups that are inactive or see very little activity for prolonged periods (three months or more) are candidates for closure.

If group closure is being considered, the IG will be informed at least two weeks before a decision is made, to give participants an opportunity to provide input.

## Notes
[^1]: I.e., those changing the meaning of the text, as opposed to trivial changes such as spelling or punctuations fixes
