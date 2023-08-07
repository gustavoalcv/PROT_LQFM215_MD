# PROT_LQFM215_MD
This repository includes the algorithms used for performing molecular dynamics studies of the interaction between the Proline Transporter (Slc6a7) - PROT and the inhibitor LQFM215. It is an open algorithm, allowing everyone to test and utilize it freely.

1. The first step is to install the NAMD molecular dynamics software, and the VMD visualization and analysis software. Available at the following links:
   - NAMD - https://www.ks.uiuc.edu/Development/Download/download.cgi?PackageName=NAMD
   - VMD - https://www.ks.uiuc.edu/Development/Download/download.cgi?PackageName=VMD

2. The second step is to access the CHARMM-GUI server and submit its structure and its ligand for the construction of inputs that will run on the NAMD command line. Available at the following link:
   - CHARMM-GUI - https://www.charmm-gui.org/

     A brief description for each step on CHARMM-GUI:

STEP1: Read biomolecular coordinate

You can download a coordinate from RCSB (PDB website) or upload a PDB file (RCSB or CHARMM formats) from your local machine.

STEP2: Solvate the biomolecule (Choose the best option for your sistem)

The biomolecule will be solvated with water molecules in this step. You can choose a shape (Rectangular or Truncated Octahedral [Octagonal]) of the system. You can specify the system dimension or let CHARMM to determine the system size based on the biomolecular extent. It is this step to add ions to neutralize the system.

STEP3: Setting periodic boundary conditions

The periodic boundary conditions are applied based on the system shape and size. And, FFT grid information of the Particle-mesh Ewald (PME) method is determined. Short steps of minimization are performed to remove bad contacts. You can increase the step later to minimize the system longer.

STEP4 and 5: Equilibration and Production

While NVT (constant volume and temperature) is used for equilibration (step4), you can specify either NVT or NPT (constant pressure and temperature) dynamics for production runs (step5). Because of excessive computing powers required for long simulations, you need to download the equilibration and production input files and run them on your local machines. You may want to change number of MD steps (nstep), print-out frequency (nprint), and the trajectory saving frequency (nsavc) for postprocessing of simulation runs.

3. After generating the inputs you will have a .rar file where you will extract it in a folder and through the command line access the NAMD folder and execute steps 4 and 5 which are balancing and production (dynamics).

   namd2 step4_equilibration.inp

   namd2 step5_production.inp

5. All NAMD and VMD running tutorials are available at the link: https://www.ks.uiuc.edu/Training/Tutorials/
6. We will make available all the files we use to run the dynamics in NAMD.
