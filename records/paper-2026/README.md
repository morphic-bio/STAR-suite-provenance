# Paper benchmark evidence

These records normalize the paper-facing aggregate results without copying raw
data locations, collaborator manifests, or complete operational logs.

The perturb-seq record preserves the dataset-scale runtime and parity statistics
for A375, UCSF, and MSK. The bulk paired-end record uses the corrected matched
full-production comparison (1.81-fold) and explicitly excludes the faster
warm-cache pilot values from the headline claim.

## STAR Suite 1.9.4 manuscript records (2026-09-15)

The manuscript numbers come from STAR Suite 1.9.4 and are recorded in five new
records. Two of them are corrections that supersede the earlier paper records:

- `paper-2026-bulk-pe-v1.9.4` supersedes `paper-2026-bulk-pe-integrated-output`
  (1.6-fold and 4.2-fold against a Trim Galore + STAR + Salmon `-l A` pipeline).
- `paper-2026-perturbseq-v1.9.4` supersedes `paper-2026-perturbseq-full-depth`
  (A375 and MSK 30-KO ES only; the UCSF dataset is not part of the manuscript).
- `paper-2026-scrnaseq-pbmc10k-v1.9.4`, `paper-2026-flex-v1.9.4` and
  `paper-2026-slam-grandslam-100k-v1.9.4` are new.

Gene-level concordance in these records is Spearman over all genes plus Pearson
on raw per-gene totals. The earlier records are kept unchanged as published.

## STAR Suite 1.9.5 manuscript records (2026-09-21 to 2026-09-25)

The submitted manuscript reports STAR Suite 1.9.5 (tag `v1.9.5`, commit
`fb9f1f4e`). The six records made from the 1.9.5 re-timing campaign supersede
the 1.9.4 records: `bulk-pe-v1.9.5`, `scrnaseq-pbmc10k-v1.9.5`,
`perturbseq-v1.9.5`, `perturbseq-msk-v1.9.5`, `flex-v1.9.5` and
`slam-grandslam-100k-v1.9.5`.

Two later corrections carry the values in the manuscript:

- `paper-2026-perturbseq-msk-v1.9.5-lineage-caller` supersedes the MSK row of
  `perturbseq-v1.9.5` and the caller-off `perturbseq-msk-v1.9.5`. It re-times the
  MSK 30-KO ES three-library arm with the integrated LARRY caller on, so the
  reported run does all of its calling in one STAR pass. The run takes 1,594.27 s
  against Cell Ranger's summed 10,022.22 s, and its shared outputs are byte-identical.
- `paper-2026-flex-gse325982-included-probes-v1.9.5` supersedes the GSE325982 rows
  of `flex-v1.9.5`. It re-runs that dataset with every tool on Cell Ranger's default
  included-probe policy, on the local workstation and on both cloud storage classes.
