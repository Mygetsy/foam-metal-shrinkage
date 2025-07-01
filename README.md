# OpenFOAM based solver for modelling of metal melting with thermal and phase density variation
========

The OpenFOAM-v2306 is supported.

## Installation
-------
To build an augmented Docker image, run
```shell
    docker build -f Dockerfile.ubuntu -t my_openfoam-plus .
```
The new image can be used within an intermediate container as
```shell
    docker run -it --rm -u="$(id -u):$(id -g)" -v="$(pwd):/home/openfoam" my_openfoam-plus
```
To compile solver run
```shell
   cd solver/applications/slmMeltPoolFoam
   wmake -a
```

## MacOS pre-installation
-------
By default, MacOS uses case-insensitive file system, which can cause name conflicts in OpenFOAM.
To create a case-sensitive volume, run
```shell
    sudo curl -o /usr/local/bin/openfoam-macos-file-system http://dl.openfoam.org/docker/openfoam-macos-file-system
    sudo chmod 755 /usr/local/bin/openfoam-macos-file-system
    sudo openfoam-macos-file-system -v my_openfoam create
    mkdir my_openfoam
    sudo openfoam-macos-file-system -v my_openfoam mount
```

## Citation

If you use this solver or its results in your research or publications, please cite the accompanying article:
DOI:
