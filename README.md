# phi4-Critical-Casimir-Force
Data of Monte Carlo simulations of the Critical Casimir Force in 3D O(N)-models

## What is it?

We have performed Monte Carlo simulations of a classical $\phi^4$-type lattice model, to the end of extracting the Casimir force. The details can be found in the accompanying [Masters thesis](Masters_Thesis_Jonas_Wattendorff_422461.pdf).

### In short:

We simulated a cuboidal lattice of size $L_z \times L_{yx} \times L_{yx}$ with a variety of boundary conditions. The aspect ratio is $\rho = L_z / L_{yx} = L_{\perp}/L_{||}$ and various values of $L_z$ were used for finite-size scaling analyses. We use two methods to extract the Casimir force:
1. The coupling parameter method is used to accurately determine the Casimir force at the critical temperature $\beta_c$.
2. The temperature integration method is used to determine the Casimir force for a range of temperatures around $\beta_c$.

## How is it sorted?

### `'data/Coupling parameter method/'`

Contains data obtained using the coupling parameter method. The file names indicate the spin degree of freedom ($N=2,3,4$), aspect-ratio $\rho$ and boundary conditions (see Masters thesis for details). In the plain text files, the header contains information about the parameters used in the simulation. Next, the free energy difference per surface
area at criticality $I(\beta_c,L_{\perp},L_{||})$ is given for various values of $L_{\perp}$ at constant $\rho$, as well as the corresponding statistical errors.

### `'data/Temperature integration method/'`

Contains data obtained using the temperature integration method. The file names indicate the kind of system (`bulk` or `film`), the spin degree of freedom ($N=2,3$), the aspect-ratio $\rho$, the boundary conditions and the value of $L_z$ and $L_{yx}$.

- The `bulk_...` files contain the energy density $E_{\mathrm{bulk}}(\beta,L)$ for fully periodic cubical systems of size $L \times L \times L$. The files `bulk_N=2_merged.csv` and `bulk_N=3_merged.csv` contain merged data for $N=2$ and $N=3$, respectively (more details in the Masters thesis).

- The `film_...` files contain the energy density $E(\beta,L_z,L_{yx})$, as well as various parameters. The Casimir scaling function $\theta$ is computed with the bulk energy density, boundary values $I(\beta_0)$ and $I_{\mathrm{bulk}}(\beta_0)$, and scaling correction $c$, as described in the Masters thesis. The correlation length $\xi_0^+$ is also provided to convert $\beta$ to $\tilde{x}_t$.

### `'raw data/'`

__Unsorted files, the relevant data is in `data/`__. Contains hdf5 files and config files used in the simulations and data analysis. For the temperature integration method, there are a few more observables stored here, such as magnetization, susceptibility, etc. For the coupling parameter method, there was some data loss, so not all raw data is available.
