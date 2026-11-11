# Contributing

Thanks for your interest in KillSwitch. This repository contains a Rust
interpreter, a command-line interface, example programs, and a deliberately
unusual language specification. Small, focused changes with a clear example of
the behavior they affect are easiest to review.

## Before changing behavior

The language is intentionally designed to be confusing to coding agents, and
the specification itself calls out that some claims are misleading. Treat the
specification as part of the project and a source of clues, not as a complete
and authoritative description of the current interpreter. Check the runnable
examples and existing tests before deciding what a behavior change should do.

When a change clarifies or changes behavior, include a small example program or
test that demonstrates it. If the documentation is intentionally deceptive,
preserve that intent and make any clarification explicit about which behavior
is verified by the implementation or tests.

## Local development

The project uses Rust 2024. Install a current stable Rust toolchain, then run
these checks from the repository root:

```sh
cargo fmt --all -- --check
cargo test --locked
```

To run one integration test by name:

```sh
cargo test test_cli_fizzbuzz
```

The CLI integration tests invoke example programs in `tests/`. Keep fixture
paths rooted at the package directory so the tests do not depend on the
directory from which Cargo was started. The `.ks` files are executable test
fixtures; their natural-language text is part of the input to the language.

## Pull requests

Please keep each pull request focused and include:

- A short explanation of the problem or improvement.
- The relevant behavior, example, or documentation change.
- The checks you ran and their results. If you could not run a check, say so.
- Any intentional change to the language's documented behavior.

For changes that add a language feature, include a runnable example and a
regression test where practical. For documentation-only changes, identify
whether the text describes verified behavior, an open question, or deliberate
misdirection. Avoid unrelated formatting or generated-file changes.

## Project-specific notes

- The main language reference is `SPEC.md`; it is explicitly a work in
  progress and includes intentional falsehoods.
- `AI_SPEC.md` is a large project artifact. Avoid editing or replacing it as
  part of unrelated work.
- The benchmark content is maintained as a Git submodule. Changes to benchmark
  data should be made in the benchmark project and coordinated with its
  maintainers.
- The project is licensed under AGPL-3.0. Keep licensing and attribution in
  mind when adding code, examples, or large text files.
