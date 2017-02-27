KaHIP v1.00
=====

The graph partitioning framework KaHIP -- Karlsruhe High Quality Partitioning.

The graph partitioning problem asks for a division of a graph's node set into k equally sized blocks such that the number of edges that run between the blocks is minimized. KaHIP is a family of graph partitioning programs. It includes KaFFPa (Karlsruhe Fast Flow Partitioner), which is a multilevel graph partitioning algorithm, in its variants Strong, Eco and Fast, KaFFPaE (KaFFPaEvolutionary) which is a parallel evolutionary algorithm that uses KaFFPa to provide combine and mutation operations, as well as KaBaPE which extends the evolutionary algorithm. Moreover, specialized techniques are included to partition road networks (Buffoon), to output a vertex separator from a given partition as well as techniques geared towards the efficient partitioning of social networks.

Main project site:
http://algo2.iti.kit.edu/documents/kahip/index.html

Travis-CI Status [![Build Status](https://travis-ci.org/schulzchristian/KaHIP.svg?branch=master)](https://travis-ci.org/schulzchristian/KaHIP)

Installation Notes
=====

Before you can start you need to install the following software packages:

- Scons (http://www.scons.org/)
- Argtable (http://argtable.sourceforge.net/)
- OpenMPI (http://www.open-mpi.de/)

Once you installed the packages, just type ./compile.sh. Once you did that you can try to run the following command:

./deploy/kaffpa examples/delaunay_n15.graph --k 2 --preconfiguration=strong

For a description of the graph format please have look into the manual.

Install on Mac OS X
=====

- `brew reinstall gcc --without-multilib` (NB: this took almost 2 hours, I am now not 100% sure you need the --without-multilib option)
- `brew install scons`
- `brew install argtable`
- `brew install open-mpi`

(Provisional notes)
The default compiler on Mac OS X is clang, which overrides the gcc compiler


Footnote - Open MPI for OS X
=====

It looks like Open MPI works fine without having to do this.

See notes at https://www.open-mpi.org/faq/?category=osx#not-using-osx-bundled-ompi

[download and unzip the latest version of openmpi to a folder e.g.]
```sh
cd ~/ThirdPartyProjects/openmpi-2.0.2
alias g++='gcc-6'
alias gcc='gcc-6'
./configure --prefix=/usr/local/bin/openmpi 2>&1 | tee config.out
make -j 4 2>&1 | tee make.out
sudo make install 2>&1 | tee install.out
export PATH=/usr/local/bin/openmpi/bin:$PATH
ompi_info
export OMPI_CXX=gcc-6
export OMPI_CC=gcc-6
mpicxx
```







