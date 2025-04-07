# Linux Files for the Surface-Slab Models of Fe<sub>3</sub>GeTe<sub>2</sub> for computing the Gibb's Free Energy of Hydrogen Adsorption 

## 1) Cloning the Repository

To clone the **FGT_HER** repository, use the following command:

```sh
git clone https://github.com/johan-yapo/FGT_HER.git
```

## 2) Computational Details

The density functional theory (DFT) was used to determine the H-binding energy (ΔEh¬) on the modeled {001} surface of Fe3GeTe2. The total energy calculations for the surfaces were done using the projector augmented wave coded in the Vienna ab initio simulation package (VASP). In addition, all the VASP calculations done here employed the generalized gradient approximation (GGA) with the exchange and correlation functionals treated by the Perdew-Burke-Enzerhoff (PBE) and revised PBE methods for the structure relaxations and single-point energy calculations respectively. The convergence threshold for the ionic relaxation loop was set to 0.02 eV/Å in force and the cutoff energy for the plane wave calculations was set to 500 eV. Spin polarization functions were also calculated just for the single-point energy calculations of the surface. The Brillouin zone integrations were carried out with a 7 x 7 x 1 k-point mesh using the Monkhorst-Pack automatic grid generation mode.

To construct the FGT surface (Figure 1), first the unit cell of FGT was obtained and the cell shape, volume and positions of all the atoms were all optimized in VASP. Then we needed to cleave the bulk Fe3GeTe2 in the c direction and then add vacuum spacing in that same direction to create 2D slabs (surface supercells) with the proper surface exposed. In this work, a 2 x 2 x 2 supercell was created from the unit cell of FGT and about 20 Å of vacuum space was added in the [001] direction of the supercell in order to ensure that there would be no inter-slab interactions. This resulted in a 2D FGT surface supercell with 4 layers of FGT with a Van der Waals gap of around 4.5 Å between each layer. During the structural relaxation step, the cell shape and volume were kept frozen while the position of all the atoms were allowed to move. 

To calculate the Gibbs free energy (ΔG<sub>H</sub>) for H adsorption to predict the HER activity of the different HER active sites on the surface the equation ΔG<sub>H</sub> = ΔE<sub>H</sub> + ΔE<sub>ZPE</sub> – TΔS  was used, where ΔE<sub>H</sub> is the H-surface binding energy computed from DFT, ΔEZPE is the zero-point energy difference between adsorbed H and free H2 and TΔS are the temperature and entropy contribution terms. One thing to note here is that ΔEZPE is usually very small, between 0.01 to 0.05 eV(5) which is less than to around the chemical accuracy target of 1 kcal∙mol 1 or 0.043 eV that is desired for ab initio computational methods, so we have chosen to neglect it here and the equation can be simplified to 〖ΔG〗_H  = ΔE_H  – TΔS. TΔS is calculated with the approximation TΔS ≈  (1 )/2 TS°(H<sub>2</sub>), where T = 298.15 K  and S°(H<sub>2</sub>) = 130.7 J∙mol<sup>-1</sup>∙K<sup>-1</sup>. Lastly, the equation used to solve for the binding energy of hydrogen ΔE<sub>H</sub> was ΔE<sub>H</sub> = E[surface + nH]-E[surface+(n-1)H]-1/2 E[H<sub>2</sub>]. Here E[surface + nH] and E[surface+(n-1)H] are the total energies of the surface with n and n-1 hydrogen atoms adsorbed on it respectively and calculated using VASP, and 1/2 E[H_2] is half of the energy of one gas phase, diatomic hydrogen molecule.

![Image](https://github.com/user-attachments/assets/d5f5e955-8931-405c-9334-56290b6ece62)

**Figure 1.** Surface slab model of FGT used for DFT calculations.

## Citation  
If you use this work, please cite:  

Rezaie, A. A., Lee, E., Luong, D., Yapo, J. A. & Fokwa, B. P. T.  
Abundant active sites on the basal plane and edges of layered van der Waals Fe₃GeTe₂ for highly efficient hydrogen evolution.  
*ACS Materials Lett.*, **313–319** (2021).  
[DOI:10.1021/acsmaterialslett.1c00048](https://doi.org/10.1021/acsmaterialslett.1c00048)




