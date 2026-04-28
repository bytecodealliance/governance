# Bytecode Alliance AI Tool Use Policy

## Policy

Contributors may use whatever tools they would like to craft their contributions, but there must be a human in the loop. Contributors must read and review all LLM-generated code or text before they ask other project members to review it. The contributor is always the author and is fully accountable for their contributions. Contributors should be sufficiently confident that the contribution is high enough quality that asking for a review is a good use of scarce maintainer time, and they should be able to answer questions about their work during review.

We expect that new contributors will be less confident in their contributions, and our guidance to them is to start with small contributions that they can fully understand to build confidence. We aspire to be a welcoming community that helps new contributors grow their expertise, but learning involves taking small steps, getting feedback, and iterating. Passing maintainer feedback to an LLM doesn’t help anyone grow, and does not sustain our community.

As a consequence of our position that the contributor proposing changes is fully accountable for their contributions, contributors aren't required to explicitly mention the use of any tools, AI or otherwise. If a contributor thinks there is value in highlighting tool use, they *may* do so in their pull request description, commit message, or using a commit message trailer like `Assisted-by: <tool>:<model>`. They **MUST NOT**, however, list any tool, AI or otherwise, as a co-author: only human contributors can be authors and take on the accountability that comes with it.

This policy includes, but is not limited to, the following kinds of contributions:
 - Code, usually in the form of a pull request
 - RFCs or design proposals
 - Issues or security vulnerabilities
 - Comments and feedback on pull requests

## Details

To ensure sufficient self review and understanding of the work, it is strongly recommended that contributors write PR descriptions themselves (if needed, using tools for translation or copy-editing). The description should explain the motivation, implementation approach, expected impact, and any open questions or uncertainties to the same extent as a contribution made without tool assistance.

An important implication of this policy is that it bans agents that take action in our digital spaces without human approval, such as the GitHub [@claude agent](https://github.com/claude/). Similarly, automated review tools that publish comments without human review are not allowed. However, an opt-in review tool that **keeps a human in the loop** is acceptable under this policy. As another example, using an LLM to generate documentation, which a contributor manually reviews for correctness, edits, and then posts as a PR, is an approved use of tools under this policy.

AI tools must not be used to fix GitHub issues labelled good first issue. These issues are generally not urgent, and are intended to be learning opportunities for new contributors to get familiar with the codebase. Whether you are a newcomer or not, fully automating the process of fixing this issue squanders the learning opportunity and doesn’t add much value to the project. **Using AI tools to fix issues labelled as “good first issues” is forbidden**.

## Extractive Contributions

The reason for our “human-in-the-loop” contribution policy is that processing patches, PRs, RFCs, and comments to Bytecode Alliance projects is not free – it takes a lot of maintainer time and energy to review those contributions! Sending the unreviewed output of an LLM to open source project maintainers extracts work from them in the form of design and code review, so we call this kind of contribution an “extractive contribution”.

Our **golden rule** is that a contribution should be worth more to the project than the time it takes to review it. These ideas are captured by this quote from the book [Working in Public](https://press.stripe.com/working-in-public) by Nadia Eghbal:

> “When attention is being appropriated, producers need to weigh the costs and benefits of the transaction. To assess whether the appropriation of attention is net-positive, it’s useful to distinguish between extractive and non-extractive contributions. Extractive contributions are those where the marginal cost of reviewing and merging that contribution is greater than the marginal benefit to the project’s producers. In the case of a code contribution, it might be a pull request that’s too complex or unwieldy to review, given the potential upside.”
> – Nadia Eghbal

Prior to the advent of LLMs, open source project maintainers would often review any and all changes sent to the project simply because posting a change for review was a sign of interest from a potential long-term contributor. While new tools enable more development, it shifts effort from the implementor to the reviewer, and our policy exists to ensure that we value and do not squander maintainer time.

## Handling Violations

If a maintainer judges that a contribution doesn’t comply with this policy, they should paste the following response to request changes:

> This PR doesn't appear to comply with our policy on tool-generated content, and requires
> additional justification for why it is valuable enough to the project for us to review it.
> Please see our developer policy on AI-generated contributions:
> https://github.com/bytecodealliance/governance/blob/main/AI_TOOL_POLICY.md

The best ways to make a change less extractive and more valuable are to reduce its size or complexity or to increase its usefulness to the community. These factors are impossible to weigh objectively, so the determination is left up to the maintainers of the project, i.e. those who are doing the work of sustaining the project.

If or when it becomes clear that a GitHub issue or PR is off-track and not moving in the right direction, maintainers should close it with an appropriate explanation.

If a contributor repeatedly fails to make their changes meaningfully less extractive, maintainers should escalate to the TSC.

## Copyright

Artificial intelligence systems raise many questions around copyright that have yet to be answered. The Bytecode Alliance's policy on AI tools is that contributors are responsible for ensuring that they have the right to contribute code under the terms of our license, typically meaning that either they, their employer, or their collaborators hold the copyright. Using AI tools to regenerate copyrighted material does not remove the copyright, and contributors are responsible for ensuring that such material does not appear in their contributions. Contributions found to violate this policy will be removed just like any other offending contribution.

## Exceptions

Project maintainers might identify use cases for AI tools that don't fit this policy, such as fully automated reviews run as part of a CI pipeline. In such a case, maintainers should reach out to the TSC, e.g. using a Pull Request updating this section to list their use as an exception. The TSC will consider the use case and either approve it or provide feedback.

## Examples

A highly successful use of AI tools for finding security and correctness issues in the Wasmtime project is described in [this blog post](https://bytecodealliance.org/articles/wasmtime-security-advisories).

## References

This policy is a lightly adapted copy of the [LLVM Project's AI Tool Use Policy](https://github.com/llvm/llvm-project/blob/347dc1321ed50578bb09da6fa10ccec581d8a2b6/llvm/docs/AIToolPolicy.md) (fetched 2026-04-21), licensed under the [Apache 2.0-WITH-LLVM-Exception] license, itself based on the [Fedora Council's Policy on AI-Assisted Contributions](https://communityblog.fedoraproject.org/council-policy-proposal-policy-on-ai-assisted-contributions/) (fetched 2025-10-01), licensed under the [Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/). These links serves as attribution.
