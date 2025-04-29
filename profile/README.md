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

The installation of the `oac-tree` packages requires a working installation of `epics-base` and `pvxs`. This includes defining the environment variables `EPICS_BASE`, `PVXS_DIR` and making their executables and libraries available in the standard search paths.

Furthermore, the following dependencies need to be installed: `cmake`, `libxml2`, `gtest`.

### Build and install steps

#### Using a single super build

Fetch the repo for the super build:

```bash
git clone --recurse-submodules https://github.com/oac-tree/oac-tree-bundle.git
```

Create a build directory

```bash
mkdir <BUILD_DIR>
cd <BUILD_DIR>
```

Run cmake and make (NOTE: this will install everything into the specified install prefix!):

```bash
cmake -DCMAKE_INSTALL_PREFIX=<INSTALL_PREFIX> <SOURCE_DIR>
make
```

Where we used these variables:

* `<SOURCE_DIR>`: top folder of the `oac-tree-bundle` repository
* `<BUILD_DIR>`: build directory to use (e.g. `build`)
* `<INSTALL_PREFIX>`: installation prefix folder for cmake. This command line option can be omitted if you want to install into the default install location for your distribution

The `oac-tree` plugins will be installed in `<INSTALL_PREFIX>/lib/oac-tree/plugins` (or a similar folder where `lib` is replaced by a distribution specific folder name, e.g. `lib64`). To be able to load these plugins at runtime, this folder needs to be added to the library search path by setting `LD_LIBRARY_PATH` or adding a file with this folder to `/etc/ld.so.conf.d/` and running `ldconfig`.
