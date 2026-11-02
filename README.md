# Brain cholesterol handling and astrocyte–neuron metabolic support across stages of Alzheimer's disease: analysis code

Code for every analysis, figure panel and supplementary item in:

> Paterson T, Rohrs J, McIntire LB, Hohman TJ, Mapstone M, Meikle PJ, Kaddurah-Daouk R, Golde TE, Levey AI, Hood L, ADNI, ADMC, Funk CC.
> *Brain Cholesterol Handling Is Coupled to Astrocyte–Neuron Metabolic Support Across Stages of Alzheimer's Disease.*
> Preprint: doi:10.1101/2024.07.23.604835 (earlier version).

## Contents

| File | What it is |
|---|---|
| `UH_analysis.nb` | Wolfram Mathematica notebook containing all analysis code, outputs removed |
| `EnrichR_lists/enrichr_background_somascan_panel_split.txt` | SomaScan 7k panel gene symbols, used as the enrichment background |
| `EnrichR_lists/perm/libraries/BioPlanet_2019.gmt` | BioPlanet 2019 gene-set library (from Enrichr), used for all pathway enrichment |

## Data (not included)

All participant-level data come from the Alzheimer's Disease Neuroimaging Initiative (ADNI) and **cannot be redistributed** under the ADNI Data Use Agreement. Qualified investigators can obtain them from ADNI (adni.loni.usc.edu) and the AD Knowledge Portal:

- plasma lipidomics (Baker Institute; AD Knowledge Portal syn5592519, syn24989039)
- CSF mass spectrometry proteomics (Emory)
- CSF SomaScan 7k proteomics (Cruchaga laboratory)
- Nightingale plasma NMR lipoprotein profiles
- ADNIMERGE clinical, imaging and demographic data
- harmonized genome-wide genotypes (quality control described in the Supplemental Methods)

The notebook reads these as one baseline dataset, `coreData_plusClusters.wl`, keyed on the ADNIMERGE subject identifier. Place that file in the same folder as the notebook.

## Requirements

- Wolfram Mathematica 14.1 or later
- R 4.3 or later, needed only for the Supplementary Figure 2 permutation test, which the notebook writes out and runs with `Rscript`

## Running

1. Open `UH_analysis.nb` and evaluate the **Setup** title. This defines the functions, loads `coreData`, and applies the post-load fixes.
2. Evaluate any figure or supplementary section. Sections are named by manuscript panel.
3. Exported tables and figures are written to the notebook's folder.
4. The Supplementary Figure 2 cell also writes a participant-level `Tier_1_4_PL_data.csv` for R. Do not commit it; `.gitignore` excludes it.
5. Random permutations are seeded, so they reproduce the reported p values.

## Where each result lives

| Manuscript item | Notebook section |
|---|---|
| Fig. 1A, Supplementary Table 1 (mass balance from published inputs) | Figure 1A; Supplementary Table 1 |
| Fig. 1B–E | Figure 1 |
| Fig. 2, Supplementary Fig. 1, Supplementary Tables 3–4 | Figure 2; Supplementary Figure 1; Supplementary Tables 3 and 4 |
| Fig. 3, Supplementary Fig. 3 | Figure 3; Supplementary Figure 3 |
| Fig. 4, Supplementary Table 5, CER.D19 screen controls | Figure 4; Supplementary Table 5; Statistical tests |
| Fig. 5, Supplementary Fig. 4, Supplementary Table 8, Li & Ji effective tests | Figure 5; Supplementary Figure 4; Supplementary Table 8; Statistical tests |
| Fig. 6, Cox models, Supplementary Fig. 6, Supplementary Table 7 | Figure 6 - Kaplan Meier Curves; Statistical tests |
| Supplementary Fig. 2 | Supplementary Figure 2 |
| Supplementary Fig. 5, Supplementary Tables 2 and 6 | Supplementary Figures and Tables |
| Quadrant median differences, APOE ε4 trend, compartment control | Statistical tests |

## External steps

- Genotype harmonization and QC (T.J. Hohman) were performed outside this notebook; see the Supplemental Methods.
- The rs686548 lookup used the Baker metabolomics PheWeb (metabolomics.baker.edu.au).

## License

MIT; see `LICENSE`.
