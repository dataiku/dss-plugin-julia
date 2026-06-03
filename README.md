# Julia plugin

## Summary

This plugin adds [Julia](https://julialang.org/) support to DSS.

After installation, DSS users can:

- create Julia code recipes
- create Julia notebooks
- interact with DSS datasets and folders from Julia code

## Installation

Install the plugin in DSS, then run the Julia integration script as a DSS administrator:

```bash
$DSS_HOME/bin/dssadmin install-julia-integration
```

This script creates the Julia code environment, downloads the required libraries, precompiles them, and registers the Jupyter kernel used by DSS.

## Requirements

- DSS 8.0 or newer
- Julia installed on the DSS machine

## Usage

After the installation is complete, Julia appears as an available language for code recipes and notebooks.

Creation of a Julia recipe from the actions panel:

<img title="Julia icon in the action menu" src="https://github.com/dataiku/dss-plugin-julia/blob/master/screenshots/julia-recipe-icon.png" width="450" />

Creation of Julia notebooks:

<img title="create Julia notebooks" src="https://github.com/dataiku/dss-plugin-julia/blob/master/screenshots/create-julia-notebook.png" width="350" />

Inside recipes and notebooks, use the [Dataiku.jl](https://github.com/dataiku/Dataiku.jl) package to interact with DSS. It is a Julia wrapper around the [DSS Public API](https://doc.dataiku.com/dss/latest/publicapi/rest.html) and provides helpers to read and write datasets and folders.

Example of a Julia recipe:

<img title="Julia Recipe example" src="https://github.com/dataiku/dss-plugin-julia/blob/master/screenshots/julia-recipe-example.png" width="800" />

## Code environment and limitations

This plugin currently uses a single shared Julia environment located at:

```text
$DSS_HOME/code-envs/julia
```

It is not possible to configure multiple Julia code environments with this plugin.

To install or remove Julia packages in that environment, use Julia's built-in [package manager](https://docs.julialang.org/en/v1/stdlib/Pkg/index.html) either:

- from a Julia notebook in DSS
- from the command line by running `julia` with `JULIA_DEPOT_PATH=$DSS_HOME/code-envs/julia`

Example of a Julia notebook used to manage the code environment:

<img title="Admin Julia notebook" src="https://github.com/dataiku/dss-plugin-julia/blob/master/screenshots/admin-notebook-example.png" width="800" />
