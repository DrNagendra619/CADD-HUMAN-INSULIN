# CADD-HUMAN-INSULIN
# 🧬 CADD: Computational Analysis of Human Insulin and Drug Properties

## 📝 Overview

This project notebook demonstrates core concepts and basic tasks in **Computational-Aided Drug Discovery (CADD)** and **Structural Bioinformatics** using the **BioPython** and **RDKit** libraries. The focus is on analyzing the structure of **Human Insulin** (PDB ID: 1ZNI) and calculating properties of a small molecule drug (Aspirin).

## 🚀 Analysis Demonstrations

The Jupyter Notebook executes three main examples:

---

### Example 1: Protein Structure Retrieval and Inspection

* **Objective**: Download and perform initial inspection of a protein structure from the Protein Data Bank (PDB).
* **Target**: **Human Insulin** (PDB ID: **1ZNI**).
* **Steps**:
    1.  Uses `Bio.PDB.PDBList` to **download the structure** in `mmCIF` format (`1zni.cif`).
    2.  Uses `Bio.PDB.MMCIFParser` to parse the file into a BioPython `Structure` object.
    3.  Confirms the structure contains **1 Model** and **4 Chains**. *(Note: PDB construction warnings about discontinuous chains are common for complex or engineered structures like zinc-bound insulin.)*

---

### Example 2: Small Molecule Property Calculation

* **Objective**: Compute the molecular weight of a common drug molecule using RDKit.
* **Target Molecule**: **Aspirin** (represented by its SMILES string).
* **Steps**:
    1.  The Aspirin structure is defined using its **SMILES string** (`CC(=O)OC1=CC=CC=C1C(=O)O`).
    2.  `RDKit` converts the SMILES string into a molecule object (`mol`).
    3.  `Descriptors.MolWt()` is used to calculate the **Molecular Weight** (180.16 g/mol in the example output), a key physicochemical property in drug design (e.g., Lipinski's Rule of Five).

---

### Example 3: Biological Sequence Analysis

* **Objective**: Read the FASTA sequence data associated with the PDB entry and compute the GC content.
* **Input File**: Assumes a FASTA file named **`rcsb_pdb_1ZNI.fasta`** is available.
* **Steps**:
    1.  `Bio.SeqIO.parse()` iterates through the sequences in the FASTA file (corresponding to the different chains in the PDB).
    2.  `Bio.SeqUtils.gc_fraction()` calculates the GC content (Guanine-Cytosine ratio) for each sequence, converting the result to a percentage. GC contents of **87.50%** and **66.67%** are observed in the example output.

## 🛠️ Requirements

The notebook requires the following Python libraries for successful execution:

```bash
# Core bioinformatics library for structure and sequence handling
!pip install biopython

# Cheminformatics library for drug/molecule analysis
!pip install rdkit
