# Protein-peptide-complex-prediction-by-High-T-MD

This repository contains files which can be used to run High-T MD simulations and perform clustering analysis in Accurate Prediction for **Protein-Peptide Binding Based on High-Temperature Molecular Dynamics Simulations**.

## Requirements
Amber16+AmberTools16

## Example
### Run MD simulations at 600 K with RSFF2C force field
```
export CUDA_VISIBLE_DEVICES=0
pmemd.cuda -O -i 600K.2o9v.in -p 2o9v.RSFF2C.parmtop -c 2o9v.equil.ncrst -r 2o9v.RSFF2C.600K.ncrst -o 2o9v.RSFF2C.600K.out -x 2o9v.RSFF2C.600K.nc -ref 2o9v.apo.refc
```

### Perform density peak clustering
```
cpptraj -i 2o9v.RSFF2C.600K.dpeaks.cpptraj
```

### Calculate the RMSDs between the sampled structures and the crystal structure
```
cpptraj -i 2o9v.RSFF2C.600K.rmsd.cpptraj
```
