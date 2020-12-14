# chamois-singularity
A recipe file for a singularity containerized version of [Moose](https://github.com/idaholab/moose) and [Chamois](https://github.com/matthiasneuner/chamois).
Chamois requires the constitutive model library [Marmot]().
The container environment is based on on Centos 8, GCC-9, CMake 3.18, and OpenMPI 4.0.2.
Note that libMesh is built only in opt mode.

Instructions:
 - Ensure that `moose`, `chamois` and `Marmot` repositories are available
 - Build: `MOOSE_DIR=/moose/repo/dir MARMOT_DIR=/marmot/repo/dir CHAMOIS_DIR=/chamois/repo/dir sudo singularity build chamois-singularity.simg chamois-singularity.def`
 - Execute: `singularity exec chamois-singularity.simg /projects/chamois/chamois-opt -i inputfile.i`
 - Execute with MPI: `mpiexec -np XX singularity exec chamois-singularity.simg /projects/chamois/chamois-opt -i inputfile.i`
