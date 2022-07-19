# Optimizing Waveguide Crossing

## I. MEEP Simulations
## II. IonSim Noise Simulations

# Single Ion Addressing

## I. Ion Imager

The Zeemax simulations for the prototype design are located: 

The Zeemax simulations, Fusion360 model, quote, and order documentation for the Photon Gear Imager are located:

## II. Arbitrary Wave Generator

The code for controlling the Spectrum AWG is located on the Haeffner Lab Github:

## III. Simple PID
As a side project, I designed a simple op-amp based PID controller for stabilizing the laser intensity of STAQ's M-Squared Ti:sapph laser. After construction, the PID was tested with the Ti:sapph on 2 occasions. 

(1) During the first test, cycling the power to the PID off-and-on with the PID connected in feedback resulted in an electrical short and fried the piezo of an AOM. We learned that, in addition to following better procedure with electrical components (i.e. not power cycling with all components connected), *that a fused should be placed on the output of the PID.* (2) In the second test, the laser intensity displayed rapid oscillations when connected in feedback, suggesting that the PID works but that the parameters need to be tuned. Due to time constraints, we were not able to determine if the PID parameters could be tuned. The PID was not ultimately integrated into STAQ. 

In general, I believe the PID schematic is a cheap and versatile device for use-cases where a simple feedback controller is needed.

The documentation, including schematics, for the Simple PID is located on the Haeffner Lab Github: [https://github.com/HaeffnerLab/Simple-PID](https://github.com/HaeffnerLab/Simple-PID)

# BEM Simulations for QuantNET

In my simulations of the QuantNET trap, I created a fork of the [haeffnerlab/bem](https://github.com/haeffnerlab/bem) called BEM-Savio (bem-s). This is intended to be a leaner, and better documented version of the BEM with further support/documentation for running BEM on Berkeley's high performance computing cluster (BRC-HPC) called Savio.

## I. Installing BEM for QuantNET on Local Computer

Clone the [bem-s](https://github.com/yzhuj/bem-s) directory and create a new conda environment. Note: we choose to use python 3.6 because it seems to cause fewer issues with Savio. 

```conda create -n bem36 python=3.6  ```

Activate the environment. You should see the command prompt change to reflect this (e.g. from base to bem36)

```conda activate bem36```

Navigate to the BEM directory containing ```setup.py``` and install BEM


```pip install .```

To optionally install Mayavi (for 3D visualization)

## II. BRC-HPC Savio

## III. Installing BEM for QuantNET on BRC-HPC (Savio)

### Accessing Savio
Our lab is granted 300,000 yearly service units via Hartmut's faculty allowance. To check that you have access to this computing allowance, login to [MyBRC](https://mybrc.brc.berkeley.edu/user/login) and check that the BRC Cluster Project ```fc_haeffnerbem``` appears on your dashboard. To be added to the project, please contact Hartmut or Yi.

To ssh into the BRC cluster, 

```ssh your_BRC_username@hpc.brc.berkeley.edu```

*The password is not your BRC pin*. One-time password authentication via your phone is required. If you have not already, set up OTP via Google Authenticator by following these [directions](https://docs-research-it.berkeley.edu/services/high-performance-computing/user-guide/setting-otp/). The password you must enter is ```XY``` where ```X``` is your BRC pin and immediately following with no spaces is ```Y``` the 6-digit one-time code from Authenticator. 

### Installation

The ```bem36``` conda environment and the BEM-S repository should be preinstalled in the shared group directory ```/global/home/groups/fc_haeffnerbem```. To check, navigate to the group directory and,

```
module load python
conda env list
```

## IV. Running BEM

### Remeshing

### BEM Electrostatics

### Running BEM on Savio

## V. Multipole Expansion and Control 

## TODO:

1. Where are the voltages and frequencies set for calculating the RF psuedopotential



