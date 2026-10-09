# Feedback and reproduction reports

[Back to the repository guide](README.md) · [Verification instructions](docs/VERIFICATION.md)

Mathematical comments, independent reproductions, expository suggestions, and corrections to references or attribution are welcome.

## Mathematical feedback

Identify the release tag, manuscript section or proposition, and the precise statement being discussed. If a calculation is involved, include its C01–C21 label and distinguish the finite assertion from the mathematical deduction that uses it.

Useful reports include a concrete missing hypothesis, a counterexample to a stated step, an independently checked identity, or a proposed clarification with enough surrounding context to assess it.

## Computational reports

Include:

- Release tag and archive SHA-256.
- Operating system, Python version, and installation command.
- Exact command and whether it was a complete run or a subset.
- Certificate or job label, including `RANK12` for C13–C16.
- Exit status and the relevant stdout, stderr, and run report paths.
- Whether the initial manifest check passed.

Reports are under `replay/` after execution; see [the log guide](docs/VERIFICATION.md#logs-and-troubleshooting). Share the relevant logs and reproduction details rather than unrelated local files or credentials.

## Documentation suggestions

The repository's documentation is maintained separately from the released ZIP. Reference the actual asset and internal manuscript filenames recorded in [the release record](docs/RELEASE.md). Proposed corrections to manuscript or certificate contents should identify the relevant release and file so they can be considered for a subsequent version.
