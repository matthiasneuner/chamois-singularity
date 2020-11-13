# chamois-singularity
A recipe file for a singularity containerized version of [Moose](https://github.com/idaholab/moose) and [Chamois](https://github.com/matthiasneuner/chamois).
Chamois requires the constitutive model library [bftUserLibrary]().
The container environment is based on on Centos 8, GCC-9, CMake 3.18, and OpenMPI 4.0.2.
Note that libMesh is built only in opt mode.

Instructions:
 - Ensure that `moose`, `chamois` and `bftUserLibrary` are present the current working directory
 - Build: `sudo singularity build chamois-singularity.simg chamois-singularity.def`
 - Execute: `singularity exec chamois-singularity.simg /projects/chamois/chamois-opt -i inputfile.i`
 - Execute with MPI: `mpiexec -np XX singularity exec chamois-singularity.simg /projects/chamois/chamois-opt -i inputfile.i`
