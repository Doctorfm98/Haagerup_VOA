# Haagerup VOA at central charge eight

**Andrew Riesen — working manuscript and computational certificates**

The manuscript *The Haagerup VOA at central charge eight* presents an explicit vertex operator algebra inside the lattice VOA associated with $E_6\oplus A_2$, together with an argument identifying its representation category with the Drinfeld center of the Haagerup fusion category. The construction has central charge eight and weight-one Lie algebra $\mathfrak{sl}_2\oplus\mathfrak{sl}_2$ at levels 1 and 39.

## Download and read

**[Download the manuscript and certificate package — Haagerup_VOA_POST.zip](https://github.com/Doctorfm98/Haagerup_VOA/releases/download/snapshot-2026-10-09/Haagerup_VOA_POST.zip)**  
[Open the release page](https://github.com/Doctorfm98/Haagerup_VOA/releases/tag/snapshot-2026-10-09) · Snapshot: **9 October 2026**

1. Download **`Haagerup_VOA_POST.zip`** from the release's **Assets**.
2. Extract the entire ZIP to a local folder.
3. Open **`haagerup_readable_proof.pdf`** for the 135-page working manuscript.
4. Open **`CERTIFICATES.md`** in that folder for the C01–C21 calculation index.

Choose the specifically named attachment above. GitHub's automatically generated **Source code (zip)** and **Source code (tar.gz)** contain repository files at the release tag; they do not include the separately attached manuscript-and-certificates ZIP.

**Filename note:** the announcement uses `Haagerup_VOA_Post.zip` and `Haagerup_VOA_Post.pdf`. The actual uploaded asset is `Haagerup_VOA_POST.zip`, and its manuscript is `haagerup_readable_proof.pdf`. Use these actual filenames when locating files. See the [release record](docs/RELEASE.md).

## Find what you need

| Purpose | Where to go |
| --- | --- |
| Read the mathematical argument | `haagerup_readable_proof.pdf` inside the extracted ZIP |
| Edit or compile the manuscript | `manuscript/main.tex` inside the ZIP |
| Locate a calculation C01–C21 | [Certificate navigation](docs/CERTIFICATES.md), then the corresponding guide inside the ZIP |
| Install dependencies and run checks | [Verification instructions](docs/VERIFICATION.md) |
| Identify the exact archive and see the upload checks | [Release record and SHA-256](docs/RELEASE.md) |
| Cite this snapshot | [Citation information](docs/RELEASE.md#citation) or [CITATION.cff](CITATION.cff) |
| Report a mathematical or software issue | [Feedback guide](CONTRIBUTING.md) |

The files on `main` provide navigation and instructions. The release attachment contains the complete manuscript source, certificate guides, witnesses, programs, and pinned Python requirements.

## Verification

Use **Python 3.12 with assertions enabled**. From the extracted archive root, the supplied setup scripts create a virtual environment:

**Linux/macOS**

```bash
bash setup_unix.sh
.venv/bin/python verify_manifest.py
.venv/bin/python verify_all.py --jobs 3
```

**Windows PowerShell**

```powershell
.\setup_windows.ps1
.\.venv\Scripts\python.exe verify_manifest.py
.\.venv\Scripts\python.exe verify_all.py --jobs 3
```

Run in a writable extracted copy. The complete replay can take substantial time and memory; use `--jobs 1` to reduce simultaneous work. See [verification instructions](docs/VERIFICATION.md) for individual certificates, logs, expected results, and troubleshooting.

A successful manifest check establishes file identity. The certificate programs check their specified finite calculations. The all-weight induction, integral descent, module survival, and categorical identification are mathematical arguments explained in the manuscript and require their own review.

## Status and contributions

This is a working manuscript, with ongoing refinement of its arguments, exposition, and computational presentation for human inspection. Mathematical feedback, computational reproduction, and corrections to attribution or references are welcome.

Generative AI proposed the candidate and produced substantial portions of the initial arguments, code, and text under the author's direction. The author formulated the objective and constraints, contributed mathematical ideas and guided the proof strategy, including the use of Lagrangian algebras arising from holomorphic $E_8$ extensions. A central contribution of the author has been the sustained refinement and honing of the arguments, notation, organization, and exposition for human understanding and verification, together with directing independent and adversarial checks.

The author takes responsibility for the mathematical claims and presentation. The manuscript's introduction provides the fuller account, and its appendices and certificate guides specify the scope of the computations.
