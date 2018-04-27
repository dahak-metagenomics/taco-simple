# taco-simple

This repository implements several simple Snakemake workflows
("hello world" style) to illustrate how to define a 
[dahak-taco](https://github.com/dahak-metagenomics/dahak-taco)
workflow.


## Setting Up Taco

Before you can run any of these workflows, you must first 
install `taco`. See [dahak-taco documentation](https://dahak-metagenomics.github.io/dahak-taco)
for installation instructions.

Once `taco` is installed, it will be available on the 
command line. The `taco` commands covered in this document
should be run from the main workflow repository directory. 


## What's In This Repository

Workflow files:

* rules
* workflow-config
* workflow-params
* docker

Documentation files:

* docs
* mkdocs-material-dib
* mkdocs.yml


## Workflows

List of workflows:

[Workflow 1](Workflow1.md) - illustrates how to modify user parameters
    and use them to assemble input/output names.

[Workflow 2](Workflow2.md) - illustrates how to modify user parameters
    and use wildcards to assemble input/output names.

[Workflow 3](Workflow3.md) - (in progress) illustrates how to use custom Docker images
    as part of a `taco` workflow.

[Workflow 4](Workflow4.md) - (in progress) illustrates how to use the `--clean` 
    option to check parameters dictionary

