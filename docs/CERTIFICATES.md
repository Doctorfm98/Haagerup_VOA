# Finding certificates C01–C21

[Back to the repository guide](../README.md) · [Running the checks](VERIFICATION.md)

All paths below are **inside the extracted release ZIP**, relative to its root. They are archive paths, not files stored separately on the repository's `main` branch.

Start with the corresponding calculation in the manuscript, then consult its guide for inputs, witnesses, programs, expected outputs, dependencies, and the precise finite assertion. The package's own `CERTIFICATES.md` and the manuscript's calculation registry connect the same labels.

| Label | Calculation | Guide inside the ZIP |
| --- | --- | --- |
| C01 | Definition, coset axes, and seed | `certificates/C01_definition_coset_axes_seed/README.md` |
| C02 | Positive form and lowering identity | `certificates/C02_positive_form_lowering/README.md` |
| C03 | Weight-two basis and closure | `certificates/C03_weight_two_basis_closure/README.md` |
| C04 | Weight-three basis and feedback | `certificates/C04_weight_three_basis_feedback/README.md` |
| C05 | Normal prefix and quotient | `certificates/C05_normal_prefix_quotient/README.md` |
| C06 | Bracket and Jacobi obstructions | `certificates/C06_bracket_jacobi_obstructions/README.md` |
| C07 | Coset-square identities | `certificates/C07_coset_square_identities/README.md` |
| C08 | Lattice tops and module distinction | `certificates/C08_lattice_tops/README.md` |
| C09 | Opposite-coset maps | `certificates/C09_opposite_charge_maps/README.md` |
| C10 | Affine extension and its blocks | `certificates/C10_affine_extension_source_blocks/README.md` |
| C11 | Lattice-state relations and Zhu coordinates | `certificates/C11_full_state_zhu_relations/README.md` |
| C12 | Eight vertex exclusions | `certificates/C12_vertex_exclusions/README.md` |
| C13 | Exact quadratic saturation | `certificates/C13_quadratic_saturation/README.md` |
| C14 | Integral finiteness | `certificates/C14_integral_finiteness/README.md` |
| C15 | Semisimple special fiber | `certificates/C15_semisimple_special_fiber/README.md` |
| C16 | Conformal trace and block profiles | `certificates/C16_conformal_trace_source_profiles/README.md` |
| C17 | Good prime and Galois arithmetic | `certificates/C17_good_prime_galois_arithmetic/README.md` |
| C18 | Finite-group and even Weil models | `certificates/C18_finite_group_weil_models/README.md` |
| C19 | Modular and condensation arithmetic | `certificates/C19_modular_condensation_arithmetic/README.md` |
| C20 | Classification equations and normalization scalars | `certificates/C20_classification_normalization/README.md` |
| C21 | Normalized Leavitt actions | `certificates/C21_leavitt_reconstruction/README.md` |

## Reading the package by topic

- **The definition and positive form:** C01–C02.
- **Finite calculations used for strong generation and C2-cofiniteness:** C03–C07.
- **The six lattice modules:** C08–C09.
- **Affine extension, Zhu relations, finite presentation, and descent inputs:** C10–C16.
- **Galois, modular, classification, and reconstruction calculations:** C17–C21.

C11 recomputes 920 highest-weight relation families. C13–C16 are four scopes of a single full rank-twelve replay. C20–C21 check the supplied classification equations and normalized action formulas; the argument connecting the actual VOA category to these formulas is in the manuscript.

## Common entry points

After setup, from the archive root:

```bash
python verify_certificate.py C01 --describe
python verify_certificate.py C01
python verify_all.py --jobs 3
```

Use the configured virtual-environment interpreter as described in [Verification](VERIFICATION.md). The `--describe` command prints the selected job and expected output conditions without executing the calculation.

## Files used by the certificates

| Archive path | Purpose |
| --- | --- |
| `certificates/` | Twenty-one reader guides and individual entry points |
| `shared/` | Actual programs, supplied data, witnesses, and reports |
| `shared/verification_jobs.json` | Configured job commands and required report fields |
| `shared/run_certificate.py` | Execution, output validation, and scope checks |
| `replay/` | Generated run records, logs, and intermediate work |
| `manuscript/appendices/` | Mathematical methods, coordinate conventions, and calculation registry |

Read the scope section of each guide together with the relevant manuscript argument. File integrity, a finite computation, and the mathematical deduction from that computation answer different questions.
