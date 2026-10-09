# Release record: 9 October 2026

[Back to the repository guide](../README.md) · [Verification instructions](VERIFICATION.md)

## Locate the snapshot

| Item | Value |
| --- | --- |
| Release tag | `snapshot-2026-10-09` |
| Release page | [Open release](https://github.com/Doctorfm98/Haagerup_VOA/releases/tag/snapshot-2026-10-09) |
| Attached package | [Haagerup_VOA_POST.zip](https://github.com/Doctorfm98/Haagerup_VOA/releases/download/snapshot-2026-10-09/Haagerup_VOA_POST.zip) |
| Publication time recorded by GitHub | 9 October 2026, 16:34:16 UTC |
| Asset size | 44,096,377 bytes, approximately 42.1 MiB |
| Manuscript inside the ZIP | `haagerup_readable_proof.pdf`, 135 pages |
| Editable source entry point | `manuscript/main.tex` |
| Calculation index | `CERTIFICATES.md`, covering C01–C21 |

The documentation on `main` was added separately from this release asset. Documentation updates do not replace the attached package or change the release tag.

## Archive identity

The SHA-256 of the complete attached ZIP is:

```text
db4c0eacdb188d3b0ae8704132b549d6f79597445bd4460bb4cbc3156b2bb09d
```

Check a downloaded copy before extraction:

**Windows PowerShell**

```powershell
Get-FileHash .\Haagerup_VOA_POST.zip -Algorithm SHA256
```

**Linux**

```bash
sha256sum Haagerup_VOA_POST.zip
```

**macOS**

```bash
shasum -a 256 Haagerup_VOA_POST.zip
```

Uppercase and lowercase hexadecimal output represent the same checksum.

## Filenames used in the announcement

Use the actual archive names when opening files or making download links:

| Name in the announcement | Location in this release |
| --- | --- |
| `Haagerup_VOA_Post.zip` | The release asset is named `Haagerup_VOA_POST.zip` |
| `Haagerup_VOA_Post.pdf` | The manuscript is named `haagerup_readable_proof.pdf` inside the ZIP |
| `manuscript/main.tex` | Present at that path inside the ZIP |
| `CERTIFICATES.md` and `certificates/` | Present at those paths inside the ZIP |

The filename clarification is supplied here without renaming or repacking the release asset.

## Upload and package checks

On 9 October 2026, the documentation check established the following:

| Check | Result |
| --- | --- |
| Release state | Published; not a draft |
| Asset state | Uploaded |
| Identity of the archive inspected | SHA-256 exactly matched GitHub's recorded asset digest |
| ZIP integrity | All 256 entries decompressed without CRC errors |
| Package manifest | All 255 listed file hashes and byte counts passed |
| Manuscript PDF | Readable, 135 pages; full text extraction completed without errors |
| Editable manuscript | `manuscript/main.tex` and 41 LaTeX source files present |
| Certificate index | C01–C21 all present; every linked guide exists |
| Guide links | All relative file links in the 21 certificate guides resolve |
| Verification commands | All 21 `--describe` commands completed; configured programs and explicit path inputs exist |
| Python source parsing | All 91 Python files parsed without syntax errors |

The checks above concern delivery, file integrity, and entry-point availability. **A complete replay of the finite certificate suite was not performed as part of this upload/documentation check.** These checks do not certify the mathematical theorem. Full replay instructions and the scope of mathematical review are in [Verification](VERIFICATION.md).

## Citation

For this package, cite Andrew Riesen, *A lattice construction of the Haagerup center*, working manuscript and computational certificates, snapshot `snapshot-2026-10-09`, 9 October 2026, with the release URL. This identifies the working package rather than assigning an arXiv identifier or DOI.

```bibtex
@misc{RiesenHaagerup2026Snapshot,
  author       = {Riesen, Andrew},
  title        = {A lattice construction of the {Haagerup} center},
  year         = {2026},
  month        = oct,
  howpublished = {Working manuscript and computational certificates},
  note         = {Snapshot snapshot-2026-10-09, 9 October 2026},
  url          = {https://github.com/Doctorfm98/Haagerup_VOA/releases/tag/snapshot-2026-10-09}
}
```

Machine-readable metadata is available in [CITATION.cff](../CITATION.cff).
