# taco-simple

This repository implements several simple Snakemake workflows
("hello world" style) to illustrate how to define a 
[dahak-taco](https://github.com/dahak-metagenomics/dahak-taco)
workflow.


# Setting Up Taco

Before you can run any of these workflows, you must first 
install taco. See [dahak-taco documentation](https://dahak-metagenomics.github.io/dahak-taco)
for installation instructions. (Should be as simple as
`python setup.py install`.)

Once taco is installed, it will be available on the 
command line. The commands covered in this document
should be run from the top level directory in 
this repository.


# Quick Start

## List Available Actions

List the available workflows and rules 
defined by the rule files for each 
taco-simple workflow.

```
taco ls             # List available workflows

taco ls workflow1   # List rules in workflow 1

taco ls workflow2   # List rules in workflow 2
```

## Run Workflow

Include the `-n` flag to do a dry run first.

taco requires the `--config-json` and `--params-json` 
flags to point to the configuration and parameter
JSON/YAML files.

```
taco -n workflow1 \
    --config-json=workflow-config/workflow_1_config.json \
    --params-json=workflow-params/workflow_1_params.json
```

To run the workflow:

```
taco workflow1 \
    --config-json=workflow-config/workflow_1_config.json \
    --params-json=workflow-params/workflow_1_params.json
```



# Details

## Directory `rules/` 

The rules directory contains one folder per workflow.

Each workflow folder must include a `Snakefile`.
It is recommended to structure Snakefiles so that 
they import individual rule files. 

Individual rule files assemble rules using workflow 
parameters. These parameters will come from the 
user-defined parameters file. If no parameters value
is defined, the default value will be used from the 
workflow `*.settings` file.

## `workflow-config` Directory

The `workflow-config` directory contains workflow 
configuration files. These files contain the 
target files or rules (defined in the workflow 
Snakefile) that the user wishes to run.

## `workflow-params` Directory

The `workflow-params` directory contains workflow
parameter files. The workflow parameter file defines
values for variables used in running the workflow
rules.



# Links

[dahak-taco documentation](https://dahak-metagenomics.github.io/dahak-taco/)

[dahak-taco github repo](https://github.com/dahak-metagenomics/dahak-taco)
