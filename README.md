# RDkit_morgan Fingerprint
Preliminary attempt at molecular similarity prediction with a simple VAE
-
- Molecules represented with "SMILES" were transformed into Morgan fingerprints.
- The binary representations of molecular properties were learned by the VAE and can be used to test similarity between drug-like molecules.

Data downloaded directly from the ChEMBL library https://ftp.ebi.ac.uk/pub/databases/chembl/ChEMBLdb/latest/

Majority of functions used were imported from the RDKit library.

Data preprocessing:

- sanitize(), function under rdkit.Chem.AllChem, assigns properties (aromaticity, bond orders, and formal charges) based on the molecular structure. and
checks for chemical errors or inconsistencies in the molecular representation.

1. Randomly pick a manageable batch of data (700 molecules) from the enormous library for cleaning.
2. Filter non-drug-likely molecules, according to Lipinski's Rule of 5.
3. Within the filtered and cleaned data, randomly pick a smaller batch (500 molecules).
