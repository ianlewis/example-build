# Example project for SLSA

Example project that builds a simple go binary using GitHub Actions and
generates [SLSA] provenance.

The recipe is the GitHub Actions Workflow [.github/workflows/build.yaml], which:

1.  Builds via `bazelisk build`:
    *   Bazelisk reads [.bazelversion], fetches the correct version of Bazel,
        and then runs `bazel build`.
    *   Bazel reads [WORKSPACE], fetches the rules_go module, and then compiles
        the `hello` binary.
2.  Generates [provenance] using [slsa-framework/github-actions-demo].
3.  Uploads the binary and the provenance using [actions/upload-artifact].

[.bazelversion]: .bazelversion
[.github/workflows/build.yaml]: .github/workflows/build.yaml
[SLSA]: https://github.com/slsa-framework/slsa
[WORKSPACE]: WORKSPACE
[provenance]: https://github.com/in-toto/attestation/blob/main/spec/predicates/provenance.md
[setup-bazelisk]: https://github.com/marketplace/actions/setup-bazelisk
[slsa-framework/github-actions-demo]: https://github.com/slsa-framework/github-actions-demo
[actions/upload-artifact]: https://github.com/actions/upload-artifact
