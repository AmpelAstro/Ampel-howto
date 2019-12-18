# Ampel-interact-fixDB

This repositories contains examples for how to use processed Ampel data that has been exported from the live processing instance. This can be useful when developing units, when interacting with mirrored data as well as when doing offline analysis of archived data. Two offline modes exists. These differ in that the first relies on a fixed set of exported transient summaries ("transient views") while the second uses a local copy of a complete Ampel DB. These modes are described in order below.

## Analysis a fixed set (tar) of transient summaries (views)

### Install

Step 1: Python environment

These instructions assume that a dedicated conda environment can be created. This, including requirements, can be created using the environment.yml contained in this repository:

conda env create -f environment.yml

This will create a conda environment called ampelstatic, which can be activated through

conda activate ampelstatic


Step 2: Ampel repositires

Clone the follwing AmpelProject main repositories:
AmpelProject/Ampel-core
AmpelProject/Ampel-base
AmpelProject/Ampel-base-ZTF
AmpelProject/Ampel-ZTF

The sample notebook demonstrates analysis modules from 

AmpelProject/Ampel-contrib-HU

which is thus also needed. After cloning each needs to be added to system environment, e.g. through  "pip install -e {rep}". 


### Usage

A transient view collection will be needed (a sample such is included in this repository). Next try executing the "run_t2Sncosmo_transientview" jupyter notebook, which will beform lightcurve model fits using the SNCosmo python module. This analysis usage appears in Tier 2 of Ampel. The code for setting up the fit is contained in the T2SNcosmo module, which is part of the Ampel-contrib-HU repository:
https://github.com/AmpelProject/Ampel-contrib-HU/blob/master/ampel/contrib/hu/t2/T2SNCosmo.py

The sample notebook also includes a setup to use the kilonova models of Bulla+ (19). (Note that the sharp rise of these models make fit convergence unstable.)


## Analysis of transients contained in a local DB

### Install

This requires, in addition to what is described above, a local MongoDB client. Tools such as Robo 3T are very useful for inspecting the local DB content.


## Usage

### Obtain and restore DB

The DB will be distributed as a file. Once downloaded locally this can be restored to a running mongod client through mongorestore. 

### Run sample notebook

A sample notebook is again included.



