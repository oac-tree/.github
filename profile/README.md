# oac-tree framework

This github organization contains the main packages for oac-tree, a C++ framework for creating and executing operational procedures using behavior trees, and its dependencies:

* `oac-tree`: main library and command line tools
* `oac-tree-server`: automation server for oac-tree
* `oac-tree-gui`: graphical user interface for creating, editing and executing procedures and connecting to the oac-tree server
* `oac-tree-epics`: oac-tree plugin to interact with EPICS
* `oac-tree-control`: oac-tree plugin that provides basic control node instructions
* `oac-tree-mathexpr`: oac-tree plugin for the evaluation of mathematical expressions

## Documentation

See [oac-tree documentation](https://oac-tree.github.io/oac-tree-docs/)

## Installation from source

### Prerequisites

The installation of the `oac-tree` packages requires a working installation of `epics-base` and `pvxs`. Furthermore, the following dependencies need to be installed: `cmake`, `libxml2`, `gtest`.

### Build and install steps

Build and install the packages from the following repositories in that order:

* `oac-tree`
* `oac-tree-server`
* `oac-tree-control`
* `oac-tree-epics`
* `oac-tree-mathexpr`

For each repository, run the following command in the shell

```bash
cd <REPOSITORY>
mkdir <BUILD_DIR>
cd <BUILD_DIR>
cmake -DCOA_FETCH_DEPS=ON -DCMAKE_INSTALL_PREFIX=<INSTALL_PREFIX> ..
make
make install
```

Where we used these variables:

* `<REPOSITORY>`: repository folder
* `<BUILD_DIR>`: build directory to use (e.g. `build`)
* `<INSTALL_PREFIX>`: installation prefix folder for cmake. This command line option can be omitted if you want to install into the default install location for your distribution

### GUI

Installation instrutions of the GUI package will follow later.
