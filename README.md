## Practical 5: Integrating structural modelling with genomics
### [Integrative modelling of biomolecular interactions](https://meetings.embo.org/event/25-biomol-interactions)

1. Use [ProtVar](https://www.ebi.ac.uk/ProtVar/) to look up the following four missense variants on the EHD3 gene:
M60V, S68F, L79R and V151I.
Which variants (if any) have evidence of pathogenicity, what could be the structural mechanism?

2. In the lecture, we used AlphaFold 3 to
[comprensively model all protein-protein interactions](https://www.biorxiv.org/content/10.1101/2025.07.01.662654v2) in Mgen, a small bacterium with 476 proteins.
In particular, modelling proteins in randomly sampled pools recapitulated known interactions better than modelling proteins as individual pairs.
Here we try to recapitulate this on a
[tRNA pseudouridine synthase](https://www.sciencedirect.com/science/article/pii/S009286742400059X#figs3)
that consistently forms a homodimer across the tree of life.
We'll use AlphaFold 3 to predict structures using pairs/pools from different species, and ask whether interface confidence (ipTM) scores from pairs/pools re-identify the native pairing.
Use
[this notebook](https://colab.research.google.com/github/jurgjn/25-biomol-interactions/blob/master/pairs_vs_pools.ipynb)
to run AlphaFold 3, and
[this Google Spreadsheet](https://docs.google.com/spreadsheets/d/1103OWovkE-2Whte-4H-9LV1mvKfQS9mXqgFhY45PTGI/edit?usp=sharing)
to gather your results.

3. AlphaFold 3 can model covalent bonds between a ligand and a polymer (protein, DNA, RNA) but cannot model covalent bonds between polymers (e.g. cyclic peptide, ubiquitination, zero-crosslinks, NA-protein covalent bonds).
We can bypass this limitation by treating one of the residues/nucleic acids as a ligand. 
The
[example notebook](https://colab.research.google.com/github/jurgjn/25-biomol-interactions/blob/master/polymer_bonds.ipynb)
illustrates this on
[cycloviolacin O1](https://www.rcsb.org/structure/1DF6),
a macrocyclic peptide, and a
[K11/K48-linked tri-ubiquitin](https://www.rcsb.org/structure/6OQ1).
Compare the baseline (sequence-only) and covalently bonded AlphaFold 3 predictions to the corresponding experimental structures.
