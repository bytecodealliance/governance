# Exceptions to the Bytecode Alliance IP Policy

Per the Bytecode Alliance's [IP Policy](https://bytecodealliance.org/assets/ip-policy.pdf),
by default all hosted projects must use the [Project License](../../PROJECT_LICENSE) as their
outgoing license.

Per §4 of the IP Policy, the board may grant exceptions to this policy on a case-by-case basis.
As of now, the following exceptions have been granted:


## Wasm-tools

The [wasm-tools project](https://github.com/bytecodealliance/wasm-tools/) has received
[approval](https://github.com/bytecodealliance/wasm-tools/issues/1637#issuecomment-2192426077)
to use a triple license of `Apache-2.0 WITH LLVM-exception OR Apache-2.0 OR MIT` for the entire
code base.

### Motivation

Enabling easy integration of parts of the project into the Rust compiler.


## Wit-bindgen

The [wit-bindgen project](https://github.com/bytecodealliance/wit-bindgen/) has received
[approval](https://github.com/bytecodealliance/wit-bindgen/issues/987#issuecomment-2192426687)
to use a triple license of `Apache-2.0 WITH LLVM-exception OR Apache-2.0 OR MIT` for the entire
code base.

### Motivation

Enabling easy integration of parts of the project into the Rust compiler.


## StarlingMonkey

The [StarlingMonkey project](https://github.com/bytecodealliance/StarlingMonkey/) has received
[approval](https://github.com/bytecodealliance/StarlingMonkey/pull/103) to use the
[MPL 2.0 license](https://opensource.org/license/mpl-2-0) for part or all of the codebase.

### Motivation

Enabling easy use of upstream code from the [Servo project](https://servo.org/).

## Sightglass

### Overall license

The [Sightglass project](https://github.com/bytecodealliance/sightglass/) has received approval
to use a dual license of `Apache-2.0 OR MIT` for the entire code base.

#### Motivation

The Sightglass project was initially contributed under its current license by Fastly. The licensing
is a historic accident: the license should've been changed to the default Project License at the
time. Instead of going through a very time-consuming process to rectify this situation now, the
board grants a retroactive exception to retain the current license.

### Licenses for specific benchmark test cases under the `benchmarks` folder

The [Sightglass project](https://github.com/bytecodealliance/sightglass/) has received approval
to use any OSI approved license compatible with the overall licensing for code in individual test
cases under the [benchmarks](https://github.com/bytecodealliance/sightglass/tree/main/benchmarks)
folder, as long as that code is solely used for the purpose of being run as benchmark test cases,
not integration into any other project or product.

#### Motivation

Sightglass is a harness for running a set of benchmarks against WebAssembly runtimes. To facilitate
best coverage of scenarios, Sightglass needs the ability to run as large a set of pre-existing
benchmark test cases as possible. This requires being able to integrate code under a variety of
licenses, as long as these licenses are compatible with the overall project licenses.
