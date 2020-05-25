# dss-plugin-julia

## Summary
DSS plugin to add support for [Julia language](https://julialang.org/).

## Installation

After installing the plugin, an administrator has to run the Julia installation script `$DSS_HOME/bin/dssadmin install-julia-integration`. The script will take a few minutes to create the code environment, download the required libraries, precompile them and create a Jupyter kernel.


## Usage

After the installation, it will be possible to create and execute Julia recipes the same way you would use any other code recipes. Jupyter notebooks will also be available in Julia.

Creation of a Julia recipe from the actions panel :

<img title="Julia icon in the action menu" src="https://github.com/dataiku/dss-plugin-julia/blob/master/screenshots/julia-recipe-icon.png" width="450" />

Creation of Julia notebooks :

<img title="create Julia notebooks" src="https://github.com/dataiku/dss-plugin-julia/blob/master/screenshots/create-julia-notebook.png" width="350" />

Inside recipes and notebooks, use the package [Dataiku.jl](https://github.com/dataiku/Dataiku.jl) to interact with DSS. This package is a wrapper around the [DSS Public API](https://doc.dataiku.com/dss/latest/publicapi/rest.html) and provides functions to read and write datasets and folders in DSS easily. See the documentation on the package's [README.md](https://github.com/dataiku/Dataiku.jl/blob/master/README.md)

Example of a Julia recipe : 

<img title="Julia Recipe example" src="https://github.com/dataiku/dss-plugin-julia/blob/master/screenshots/julia-recipe-example.png" width="800" />

## Code environment

For now, it is **not** possible to have multiple code environments in Julia. Therefore, all the julia recipes and notebooks will use the same environment that is located at `$DSS_HOME/code-envs/julia`. To install or remove packages, this environment has to be managed manually using the julia's built-in [package manager](https://docs.julialang.org/en/v1/stdlib/Pkg/index.html), there are 2 ways to do that : 

* By using Pkg inside a Jupyter notebook in DSS (see example below)
* By running `julia` with the environment variable `JULIA_DEPOT_PATH=$DSS_HOME/code-envs/julia`

Example of a Julia notebook for managing the code environment :

<img title="Admin Julia notebook" src="https://github.com/dataiku/dss-plugin-julia/blob/master/screenshots/admin-notebook-example.png" width="800" />

## Requirements

This plugin requires DSS >= 8.0.
The Julia language must be installed on the machine.
