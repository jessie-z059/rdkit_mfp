# RDKit: Morgan Fingerprint
Preliminary attempt at molecular similarity prediction with a simple VAE
-

Dataset:
-
Data downloaded directly from the ChEMBL library https://ftp.ebi.ac.uk/pub/databases/chembl/ChEMBLdb/latest/

Data preprocessing:
-
- sanitize(), function under rdkit.Chem.AllChem, assigns properties (aromaticity, bond orders, and formal charges) based on the molecular structure. and
checks for chemical errors or inconsistencies in the molecular representation.

1. Randomly pick a manageable batch of data (2500 molecules) from the enormous library for cleaning.
2. Filter according to Lipinski's Rule of 5 to get drug-like molecules.
3. Within the filtered and cleaned data, randomly pick a smaller batch (2000 molecules).

Method:
-
Training
- Molecules represented with "SMILES" were transformed into Morgan fingerprints.
- The binary representations of molecular properties were learned by the VAE and can be used to test similarity between drug-like molecules.
Majority of functions used were imported from the RDKit library.

Generation
- After verifying that the pre-existing set of molecules are learned, run the VAE decoder again to generate new molecules
- Theoretically, the generated molecules holds similar drug-like properties that would belong in the pre-existing set.
