# Proposal to Create SIG-Guest-Languages

This document is a proposal to create SIG-Guest-Languages as a formal Special Interest Group (SIG) under the auspices of the TSC of the Bytecode Alliance, as specified in the TSC’s charter.

The purpose of this group is to investigate how best to integrate Wasm and components into programming language ecosystems in a way that feels native to those ecosystems.

The group will do this by bringing together language ecosystem stakeholders, identifying common issues, and coordinating work on common tooling and solutions.

Any work the group does which involves engine extensions and runtime interfaces must enter the appropriate standardization process (e.g. Wasm CG, WASI) and not ship in production until they are at the appropriate point in the standardization process and are sufficiently stable.

## Deliverables

1. The group will produce a guide to supporting Wasm in languages based on identified common foundational issues (e.g. bundling standard libraries, linking runtime binaries) and common implementation patterns which address them.

1. The group will develop common tools (e.g. a file system virtualizer) for use in language guest projects. These tools must be designed so they can be integrated into different project's native language tooling (e.g. [wasm-tools](https://github.com/bytecodealliance/wasm-tools) being used in [jco](https://github.com/bytecodealliance/jco/tree/main)).

1. The group may develop new language guest projects. These projects must be designed to be used in and match the idioms of the source language's native tooling (e.g. [cargo component](https://github.com/bytecodealliance/cargo-component) being integrated into Rust & `cargo`). These projects must not fork existing languages; any/all required extensions to the source language must be coordinated with the languages maintainers and have a clear path to being upstreamed.

## Supporting Members

The following individuals support the creation of SIG-Guest-Languages

* Bedford, Guy (Fastly)
* Brown, Robin (SingleStore)
* Cabrera, Saúl (Shopify)
* Cannon, Brett (Microsoft)
* Chiarlone, Dan (Microsoft)
* Dice, Joel (Fermyon)
* Huene, Peter (Fastly)
* Sharp, Jamey (Fastly)
* Jiaxiao, Zhou (Microsoft)
* Smith, Kevin (SingleStore)
* Macovei, Danny (JAF Labs)
* Prewitt, Calvin (JAF Labs)
* Schneidereit, Till (Fermyon)
* Vetere, Peter (SingleStore)
* Wagner, Luke (Fastly)

