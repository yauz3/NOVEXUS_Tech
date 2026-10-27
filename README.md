# NOVEXUS Tech V0 — Scientific Software and Benchmark Resources

**NOVEXUS Tech V0** is a browser-accessible computational platform for molecular docking, structural bioinformatics, cheminformatics, and sequence analysis. This repository is intended to provide the **reproducibility materials for the NOVEXUS Tech V0 preprint**, rather than the entire production website or its private infrastructure.

**Platform:** https://www.novexus.tech/  
**Research tools:** https://www.novexus.tech/novexus-research-tools/  
**Repository:** https://github.com/yauz3/NOVEXUS_Tech

## Overview

The V0 platform documents a collection of 30 research tools spanning molecular descriptors, chemical-space analysis, ligand preparation, protein and peptide analysis, and DNA/genomics utilities. Its wider scientific workflow includes protein–ligand, protein–protein and peptide–protein docking, PDBminer structure selection and PDB-Quantifier reference-based structure assessment.

The accompanying audit distinguishes **functional correctness**, **agreement with external or independently implemented references**, and **predictive accuracy on genuinely held-out experimental data**. These are different claims and should not be conflated.

## Reported results in the V0 manuscript

| Evaluation category | Result reported in manuscript | Interpretation |
|---|---:|---|
| Research tools included | 30 | Module inventory; not 30 independent accuracy measurements |
| Research tools with completed reference-based evaluation | 27 | 3 research tools not measured in the original audit environment |
| Cross-cutting evaluations | 3 completed | Malformed-input handling, determinism and Free/Pro tier parity |
| Platform-service benchmark suites | 6 defined; 1 run | The remainder were not measured in that environment |
| Overall benchmark suites | 39 defined; 31 run | 8 recorded as not measured |
| Hostile/malformed inputs | 594 controlled outcomes | Not equivalent to penetration testing or proof of security |
| Free/paid-tier checks | 16 identical; 2 matching truncated outputs; 2 narrower catalogues | Local engine-configuration parity, not public subscription testing |

**Important:** These are values *reported by the accompanying manuscript and its audit record*. They are not newly re-measured by GitHub, and the live web deployment was not tested end-to-end in that study.

### Scientifically important findings

- The in-house primer screen's QC pass rate was reported as **3.0% before calibration and 58.9% afterward**; the separately available Primer3-based designer was evaluated with partially shared thermodynamic criteria.
- The simple SpCas9 guide ranking achieved **Spearman ρ = 0.152** against measured guide activity. PAM-site enumeration was correct, but this does **not** constitute a validated activity predictor.
- Charge-state assignment during ligand preparation improved from **23/34 to 30/34 reference compounds** in the audit's corrected variant.
- PDB-Quantifier's internal reference-score reproduction is **not independent proof of structure-quality prediction**. Missing structural validation descriptors and model-version portability issues were identified.
- The ESOL evaluation on the Delaney dataset is **not independent prospective validation**, because the ESOL equation originated from that dataset family. External evaluation requires non-overlapping measured-solubility data.

The audited source snapshots, corrected experimental variants and currently deployed website can differ. A corrected benchmark result must not be interpreted as evidence that the corresponding change has already reached production.

## Deployment and evidence status

The paper uses two separate labels:

- **Deployment status:** deployed, experimental, offline or planned.
- **Evidence tier:** A = quantitatively measured against a specified reference; B = benchmark specified/released but not executed in the audit environment; C = documented without a completed benchmark.

Most docking and structural services are documented in V0 but do not have completed accuracy measurements in the paper. NovDock is described as **experimental**; GraphMD and water-aware docking are not represented as validated production methods. De-TarDis is a target-prioritisation resource; automated panel-wide counter-screening is planned, not a demonstrated V0 capability.

## Repository materials and reproducibility

This repository should contain the complete reproducibility bundle described in the manuscript, including as applicable:

- The benchmark suite and run instructions, with the source revision used for the audit.
- Original and corrected **scientific engine snapshots kept separate**.
- Benchmark case definitions and curated reference labels.
- Reported measurements, status records for suites not run, figures/tables source data and relevant library versions.
- SHA-256 manifests and dataset provenance (download locations and digests where redistribution is not permitted).

**The definitive filenames, commands, operating-system dependencies, and Python environment are those documented inside the uploaded benchmark bundle.** Do not substitute a generic `pip install` or an unpinned environment for the manuscript's recorded versions. External molecular docking binaries and third-party data may require separate installation, retrieval or licensing.

### Checking a downloadable ZIP

If the benchmark is distributed as `NOVEXUS_ResearchTools_Benchmark_v1.zip` in the repository root:

```bash
unzip -t NOVEXUS_ResearchTools_Benchmark_v1.zip
unzip -q NOVEXUS_ResearchTools_Benchmark_v1.zip -d novexus_benchmark
find novexus_benchmark -maxdepth 3 -type f | sort | head -n 60
```

Then consult the extracted README and runner instructions. The name above is the archive name cited by the manuscript; adjust the command if your uploaded artifact has a different name, and update the manuscript accordingly. **No benchmark execution is implied by extracting or listing the archive.**

## Public software versus private operations

This repository is for scientific benchmarking and documentation. It is **not** a dump of the production WordPress site or Ubuntu-worker credentials. Do not commit `.env` files, passwords, authentication tokens, private keys, production backups, user jobs or personal research data. Review original as well as corrected snapshots before publication.

Third-party packages, scientific engines, datasets and structure files retain their own copyright and licensing terms. A repository's visibility by itself does not grant permission to redistribute software or data. Add an explicit licence for any code you own and intend others to reuse.

## How to cite

Until the preprint receives a DOI, cite the work by author, title and repository URL:

> Uğurlu, S. Y. (2026). *Novexus Tech V0: a web-based scientific computing platform for molecular docking, structural bioinformatics, cheminformatics and sequence analysis*. Preprint manuscript. https://github.com/yauz3/NOVEXUS_Tech

After ChemRxiv posts the manuscript, replace the provisional citation with its **official DOI and version**, and add a permanent repository release tag tied to the exact benchmark revision.

## Limitations and disclosures

This is a V0 platform-description and software-audit study. It does not demonstrate clinical utility, measured website-wide reliability, docking accuracy, experimental selectivity, or superiority to established scientific software. Some benchmarks have not been executed; missing results are explicitly marked rather than estimated.

The author is the founder of NOVEXUS Tech. See the manuscript's competing-interests disclosure for context.

## Contact

Scientific correspondence: **syavuzugurlu@akdeniz.edu.tr**  
Website: **https://www.novexus.tech/**
