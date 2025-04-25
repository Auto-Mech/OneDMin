# OneDMin: A code for calculating Lennard-Jones parameters from intermolecular potentials via one-dimensional minimizations

## Authors
Ahren W. Jasper, Jim A. Miller, Kevin B. Moore III

# Download
We do not recommend this in-development GitHub repository to users. [Visit the Papr website for the stable version and user manual](https://tcg.cse.anl.gov/papr/codes/onedmin.html).

# Install

OneDMin can be easily installed using the Pixi package manager, which can be
installed using [this command](https://pixi.sh/latest/#installation).
Once Pixi is installed, you can install OneDMin as follows.
```
# 0. Navigate to this repository
cd /path/to/this/repo

# 1. Create Pixi environment
pixi install

# 2. Activate Pixi environment
pixi shell

# 3. Build and install OneDMin in Pixi environment
./build.sh
```
You can test that you installation worked by running one of the examples, such
as [this one](examples/ch4_he/gaussian/README.md).

# Functionality 
Lennard-Jones parameters are calculated from full-dimensional intermolecular potentials via one-dimensional minimizations averaged over the colliding partners' relative orientations. This method includes the effect of local anisotropy in the interaction potential and was shown to lead to very accurate predictions of Lennard-Jones collision rates as compared with tabulated values and with higher-level classical diffusion coefficients.

## Preferred Citation
(1) A. W. Jasper and J. A. Miller, "Lennard-Jones parameters for combustion and chemical kinetics modeling from full-dimensional intermolecular potentials," Combust. Flame, 161, 101 (2014).  

(2) A. W. Jasper and J. A. Miller, OneDMin, July 2014.  

## Further References
This method was validated in Ref. 1 by comparisions with tabulated collision rates. It was further validated by comparisions with exact classical diffusion coefficients. See  

(3) A. W. Jasper, J. A. Miller, and S. J. Klippenstein, "First-principles binary diffusion coefficients for H, H2, and four normal alkanes + N2," J. Chem. Phys. 141, 124313 (2014).  
By default, the code makes use of the "universal" TB+exp/6 potential for hydrocarbons and atomic and diatomic baths described in

(4) A. W. Jasper and J. A. Miller, "Theoretical unimolecular kinetics for CH4 + M = CH3 + H + M in eight baths, M = He, Ne, Ar, Kr, H2, CO, N2, and CH4," J. Phys. Chem. A 115, 6438 (2011)  
and validated for larger systems in  

(5) A. W. Jasper, C. M. Oana, and J. A. Miller, "'Third-body' collision efficiencies for combustion modeling: Hydrocarbons in atomic and diatomic baths," Proc. Combust. Inst. 34 197-204 (2015).  

## Contact
Ahren Jasper [ajasper@anl.gov]
