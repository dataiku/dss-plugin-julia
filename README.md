# dss-plugin-julia

## Summary
DSS plugin to add support for [Julia language](https://julialang.org/).


## Installation

After installing the plugin, an administrator has to run the Julia installation script `./$DSS_HOME/bin/dssadmin install-julia-integration`. The script will take a few minutes to create the code environment, download the required libraries, precompile them and create a Jupyter kernel.


## Usage

After the installation, it will be possible to create and execute Julia recipes the same way you would use any other code recipes. Jupyter notebooks will also be available in Julia.

Inside recipes and notebooks, use the package [Dataiku.jl](https://github.com/dataiku/Dataiku.jl) to interact with DSS. This package is a wrapper around the [DSS Public API](https://doc.dataiku.com/dss/api/7.0/rest/) and provides functions to read and write datasets and folders in DSS easily. See the documentation on the package's [README.md](https://github.com/dataiku/Dataiku.jl/blob/master/README.md)

## Code environment

For now, it is **not** possible to have multiple code environments in Julia. Therefore, all the julia recipes and notebooks will use the same environment that is located at `$DSS_HOME/code-envs/julia`. To install or remove packages, this environment has to be managed manually using the julia's built-in [package manager](https://docs.julialang.org/en/v1/stdlib/Pkg/index.html), there are 2 ways to do that : 

* By using Pkg inside a Jupyter notebook in DSS
* By running `julia` with the environment variable `JULIA_DEPOT_PATH=$DSS_HOME/code-envs/julia`


## Requirements

This plugin requires DSS >= 8.0.
The Julia language must be installed on the machine.
