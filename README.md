# Improving Pseudo-Time Stepping Convergence for CFD Simulations With Neural Networks

This repository contains the training data for the paper

> Zandbergen, Anouk, Tycho van Noorden, and Alexander Heinlein. "Improving Pseudo-Time Stepping Convergence for CFD Simulations With Neural Networks." arXiv preprint arXiv:2310.06717 (2023).

The data on which the neural network has been trained can be found under `training_data-total.csv`

For each column in Table 3, please open the corresponding back-step geometry map.  In each map you will find a .csv file starting with the name of the geometry, followed by the last three numbers of the maximum element size in Table 3. In each of these .csv, the columns represent the variables in Table 1: 

lxi        mesh edge length (m) for i = 1,2,3,4.

lyi        mesh edge length (m) for i = 1,2,3,4.

lzi        mesh edge length (m) for i = 1,2,3,4

uij        velocity u (m/s) in element i, vertex j, for i = 1,2,3,4; j = 1,2,3

vij        velocity v (m/s) in element i, vertex j, for i = 1,2,3,4; j = 1,2,3

pij        pressure p (Pa) in element i, vertex j, for i = 1,2,3,4; j = 1,2,3

res(uij)   residual Ru in in element i, vertex j, for i = 1,2,3,4; j = 1,2,3

res(vij)   residual Rv in in element i, vertex j, for i = 1,2,3,4; j = 1,2,3

res(pij)   residual Rp in in element i, vertex j, for i = 1,2,3,4; j = 1,2,3

res_uij    residual ru (N/m^3) in in element i, vertex j, for i = 1,2,3,4; j = 1,2,3

res_vij    residual rv (N/m^3) in in element i, vertex j, for i = 1,2,3,4; j = 1,2,3

res_pij    residual rp (kg/(m^3 s)) in in element i, vertex j, for i = 1,2,3,4; j = 1,2,3

cell_rei   cell Reynolds number for i = 1,2,3,4

num_iter   non-linear iteration count

CFL_pred   CFL target

x          x-coordinate centroid element

y          y-coordinate centroid element

u_av       average velocity u (m/s) over element

v_av       average velocity v (m/s) over element

p_ap       average pressure p (Pa) over element


The results of the network performance for each considered simulation can be found in the folder Results. The results on the simulations with obstacle BO and CO are divided over three different .csv files, representing the circle (BO-1, CO-1), the ellipse with a-semiaxis < b-semiaxis (BO-2, CO-2), and the ellipse with a-semiaxis > b-semiaxis (BO-3, CO-3). There, the first five columns represent the used non-linear solver and the last two colums either represent the inflow velocity (u_in) and maximum element size (maxsize), or the coordinates of the obstacle (x, y):

NN         neural network

E          cfl_e

Iter       cfl_iter

Constant   Newton constant

Automatic  Newton automatic

ANDERSON   Anderson
