# Anvi'o pangenome analysis of *B. fragilis* and *E. coli*

Pangenomes, ANI, AMR / virulence / mobile elements and secretion systems for
4 *Bacteroides fragilis* and 3 *Escherichia coli* genomes.

The CAZyme (dbCAN) part of the project is a separate repository:
[kanwal-prog/CAZyme_analysis](https://github.com/kanwal-prog/CAZyme_analysis).

## Where to run

These scripts live in `~/Desktop/CAZyme_analysis/pangenome_analysis/`, but run them from
the main folder `~/Desktop/CAZyme_analysis`, where the genomes are (`ecoli/`, `bfragilis/`):

```bash
conda activate anvio-9
cd ~/Desktop/CAZyme_analysis
bash pangenome_analysis/anvio_pangenome.sh
```

## Scripts

| File | What it does |
|---|---|
| `Anvio_install.sh` | check the Anvi'o install and set up its databases (once) |
| `anvio_pangenome.sh` | contigs databases, completeness, and one pangenome per species (E. coli and B. fragilis kept separate) |
| `result_analysis.sh` | look at the results: completeness, taxonomy, ANI, open the pangenome viewer |
| `ani_heatmap.py` | ANI heatmap per species: `python pangenome_analysis/ani_heatmap.py bfragilis` |
| `amr_virulence_hgt_commands.sh` | AMR, virulence, plasmid and mobile-element hits on the pangenome (run section by section) |
| `HGT_map_hits_to_clusters.py` | puts those hits on gene clusters: core, accessory or singleton |
| `secretion_pipeline.sh` | secretion systems (TXSScan, ConjScan, ...) and AMR (RGI/CARD) |
| `secretio_system_detection_in_bacteria/installation.sh` | install TXSScan / MacSyFinder |

## Results (on the computer only, not on GitHub)

| | *B. fragilis* | *E. coli* |
|---|---|---|
| pangenome | `bfragilis/anvio/BFRAGILIS_PAN/BFRAGILIS_PAN-PAN.db` | `ecoli/anvio/ECOLI_PAN/ECOLI_PAN-PAN.db` |
| gene-cluster summary | `bfragilis/anvio/BFRAGILIS_PAN_SUMMARY_final/` | `ecoli/anvio/ECOLI_PAN_SUMMARY_final/` |
| ANI | `bfragilis/anvio/ANI/` | `ecoli/anvio/ANI/` |

Open a pangenome in the browser:

```bash
conda activate anvio-9
cd ~/Desktop/CAZyme_analysis
anvi-display-pan -g bfragilis/anvio/BFRAGILIS-GENOMES.db -p bfragilis/anvio/BFRAGILIS_PAN/BFRAGILIS_PAN-PAN.db
```

The installed environment is `anvio-9`; some script comments still say `anvio-8`.
