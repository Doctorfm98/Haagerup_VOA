# Running the certificate package

[Back to the repository guide](../README.md) · [Certificate index](CERTIFICATES.md) · [Release record](RELEASE.md)

These instructions describe the unchanged asset `Haagerup_VOA_POST.zip` attached to release `snapshot-2026-10-09`.

## Before starting

1. [Download the attached package](https://github.com/Doctorfm98/Haagerup_VOA/releases/download/snapshot-2026-10-09/Haagerup_VOA_POST.zip) and extract it completely.
2. Open a terminal in the extracted folder containing `verify_all.py`, `MANIFEST.json`, and `requirements.txt`. This is the **archive root**.
3. Use **Python 3.12**. Keep assertions enabled: do not use `-O`, `-OO`, or an environment configuration that disables assertions.
4. Keep the downloaded ZIP as the original snapshot and run the checks in a writable extracted copy. Replays write logs under `replay/` and regenerate some reports under `shared/`.
5. Allow several GB of disk and RAM. Runtime depends on the calculation and machine; the lattice computations can take tens of minutes or longer.

## Install and run: Linux or macOS

From the archive root:

```bash
python3.12 --version
bash setup_unix.sh
.venv/bin/python verify_manifest.py
.venv/bin/python verify_all.py --jobs 3
```

The setup script creates `.venv` and installs the exact versions in `requirements.txt`. Virtual-environment activation is unnecessary when using the explicit interpreter paths above.

## Install and run: Windows PowerShell

From the archive root:

```powershell
py -3.12 --version
.\setup_windows.ps1
.\.venv\Scripts\python.exe verify_manifest.py
.\.venv\Scripts\python.exe verify_all.py --jobs 3
```

If local PowerShell settings prevent running the setup script, the equivalent manual setup is:

```powershell
py -3.12 -m venv .venv
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
.\.venv\Scripts\python.exe verify_manifest.py
.\.venv\Scripts\python.exe verify_all.py --jobs 3
```

## Understand the results

| Check | Expected result | Scope |
| --- | --- | --- |
| ZIP SHA-256 | Matches the [release record](RELEASE.md#archive-identity) | Identifies the complete archive |
| `verify_manifest.py` | `PASS cleaned manifest: 255 file hashes and byte counts.` | Checks the delivered files against the package manifest |
| `verify_all.py --jobs 3` | Successful exit, PASS for C01–C21, and `all_passed: true` in `replay/verify_all_report.json` | Replays the configured finite calculations |
| Manuscript review | Check each argument and its stated hypotheses | Assesses the mathematical deductions using those calculations |

A stored JSON status is a supplied record, rather than evidence that a fresh replay has just occurred. Read the fresh run reports and logs when assessing a reproduction.

The complete runner schedules **18 jobs covering 21 certificates**. **C13–C16 share one full rank-twelve job**, named `RANK12`. A run of any one of those four certificates invokes that shared computation.

For lower peak memory, replace `--jobs 3` with `--jobs 1`.

## Inspect or run one certificate

The following examples assume `python` is the Python 3.12 interpreter from the configured virtual environment. Otherwise substitute `.venv/bin/python` on Linux/macOS or `.\.venv\Scripts\python.exe` on Windows.

Inspect the configured steps and expected output fields without running the calculation:

```bash
python verify_certificate.py C11 --describe
```

Run one certificate:

```bash
python verify_certificate.py C11
```

Replace `C11` with any label `C01` through `C21`. Each guide also supplies a `verify.py` entry point to run from its own certificate directory.

The `--describe` option checks that the job description can be loaded; it does not perform the calculation.

Individual-certificate commands do not automatically replay every prerequisite certificate. Read the dependency and input sections of the relevant guide. For the complete configured replay, use `verify_all.py`.

The full runner also accepts a subset, for example:

```bash
python verify_all.py --jobs 1 --only C01 C02
```

This runs only the selected jobs. Omitted prerequisite jobs are not automatically added, so a subset run does not establish completion of the entire certificate suite.

## Logs and troubleshooting

| Situation | What to check |
| --- | --- |
| Python-version error | Use the configured Python 3.12 interpreter; `execute()` enforces that version. |
| Import or dependency error | Install `requirements.txt` into the same virtual environment used to run the checks. |
| Manifest mismatch before any replay | Extract a fresh copy and compare its archive checksum with the release record. |
| Manifest mismatch after a replay | Some report files are regenerated. Check the manifest in a fresh extraction of the original ZIP. |
| A calculation is slow or memory is limited | Use `--jobs 1` and inspect the active job's logs. |
| A certificate fails | Retain its stdout, stderr, run report, command, Python version, and release tag. See [reporting guidance](../CONTRIBUTING.md). |

Per-job summaries are `replay/C01_latest.json`, etc. The shared C13–C16 job uses `replay/RANK12_latest.json`. Each summary identifies a run under `replay/executions/` with its command logs. The full-suite summary is `replay/verify_all_report.json`.

Detailed job definitions are in `shared/verification_jobs.json`. The runner and additional scope checks are in `shared/run_certificate.py`.

## Compile the manuscript

Reading the supplied PDF requires no Python or LaTeX installation.

To compile the source, install a LaTeX distribution containing the packages listed in `manuscript/preamble.tex`, change into `manuscript/`, and run:

```bash
pdflatex -no-shell-escape -interaction=nonstopmode -halt-on-error main.tex
pdflatex -no-shell-escape -interaction=nonstopmode -halt-on-error main.tex
pdflatex -no-shell-escape -interaction=nonstopmode -halt-on-error main.tex
```

This produces `main.pdf` in that working directory. The supplied manuscript PDF is `haagerup_readable_proof.pdf` at the archive root.
