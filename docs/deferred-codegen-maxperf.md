# Rust Codegen and Maxperf Track

Rust workflow code generation and `maxperf` live in this optional repository,
outside the Backend / IR Interpreter Complete milestone of `velvet-ballistics`.

## Scope

This repository may carry:

1. `vb_codegen` as an optional workspace crate.
2. `velvet-ballistics compile <workflow.yaml> --emit rust` experiments.
3. Generated Rust execution for accepted workflow artifacts.
4. Generated Rust semantic equivalence against IR execution for:
   - terminal result,
   - typed error variants and fields,
   - final program counter,
   - slot values,
   - slot taints,
   - step states,
   - journal event sequence,
   - action tickets,
   - retry counts,
   - wait/ask scheduling,
   - replay behavior.
5. Generated Rust compile-fail tests forbidding unsafe, unwrap, expect, panic,
   unchecked indexing/slicing/casts/arithmetic, runtime YAML, JSON, HTTP, and runtime string lookup.
6. `maxperf` profile acceptance.
7. PGO training and `target-cpu=native` benchmark workflows.
8. Public generated-mode speed claims.

## Reactivation Contract

Codegen may return to the main `velvet-ballistics` scope only through a dedicated
architecture/spec bead. That bead must define:

- why IR interpreter performance is insufficient,
- which IR node families are accepted,
- how unsupported IR fails closed before emission,
- the exact equivalence harness,
- the compile-fail suite,
- the benchmark matrix,
- rollback behavior if generated execution diverges,
- evidence required before `maxperf` becomes a release gate.
