# Profilin Phylogenetic Analysis

## Overview

This project investigates the evolutionary relationships within the Profilin protein family across diverse eukaryotic taxa. Profilins are actin-binding proteins involved in cytoskeletal organization, cell motility, and signal transduction. The objective was to construct a phylogenetic tree of profilin proteins using a reproducible workflow consisting of sequence retrieval, dataset curation, multiple sequence alignment, and phylogenetic reconstruction.

## Dataset Retrieval

Protein sequences were retrieved from UniProtKB using reviewed (Swiss-Prot) entries to ensure high annotation quality.

Search query used:

`profilin reviewed:true`

Sequences were selected from mammals, plants, fungi, amoebozoans and insects to capture broad evolutionary diversity.

## Dataset Curation

The initial dataset contained proteins associated with profilin but not belonging to the canonical profilin family.
The final curated dataset consisted of 24 profilin homologs representing animals, plants, fungi, amoebozoans, and insects.

Removed entries:

* SYP1_YEAST
* MYPOP_HUMAN
* MYPOP_MOUSE

Duplicate and redundant sequences were removed. Genuine profilin paralogs were retained to preserve evolutionary information.

## Multiple Sequence Alignment

Tool used: MAFFT

Parameters:

* Strategy: Auto
* Default settings

The resulting alignment was used for downstream phylogenetic reconstruction.

## Software Used

- UniProtKB (sequence retrieval)
- MAFFT (multiple sequence alignment)
- ClipKit (alignment curation)
- FastTree (phylogenetic reconstruction)
- Phylogeny.fr (workflow execution and visualization)

## Alignment Assessment

The alignment was inspected for poorly aligned and gap-rich regions.

Most profilin proteins exhibited similar lengths and strong conservation across the core profilin domain. No extensive ambiguous internal regions were observed. The phylogeny.fr workflow additionally applied ClipKit-based alignment curation before phylogenetic reconstruction.

## Phylogenetic Reconstruction

Pipeline used:

MAFFT → ClipKit → FastTree

Outputs generated:

* Newick tree (.nwk)
* Tree image (.png)
* Tree report (.pdf)

## Biological Interpretation

Profilin proteins clustered largely according to taxonomic relationships.

* Mammalian PFN1 proteins formed a conserved clade.
* Mammalian PFN2 proteins formed a separate clade, indicating divergence following gene duplication.
* Arabidopsis and maize profilins grouped into plant-specific clusters.
* Fungal profilins clustered together.
* Amoebozoan profilins formed distinct evolutionary groups.
* The observed topology supports diversification of profilin paralogs throughout eukaryotic evolution.
## Repository Structure

```text
Profilin_Phylogeny/
├── DATA/          # Raw and curated FASTA datasets
├── ALIGNMENT/     # Multiple sequence alignment files
├── RESULTS/       # Phylogenetic tree files and figures
├── SCRIPTS/       # Analysis scripts (if applicable)
└── README.md      # Workflow documentation
```
## Reproducibility

1. Retrieve reviewed profilin sequences from UniProtKB.
2. Curate the dataset by removing non-profilin proteins and redundant entries.
3. Perform multiple sequence alignment using MAFFT.
4. Assess alignment quality and apply ClipKit curation through phylogeny.fr.
5. Construct a phylogenetic tree using FastTree.
6. Interpret evolutionary relationships from the resulting topology.
