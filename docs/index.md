# taco-simple

A taco workflow repo to illustrate simple "hello world" workflow definitions. 

This repository implements simple "Hello World" 
Snakemake rules to define a [dahak-taco](https://github.com/dahak-metagenomics/dahak-taco)
workflow.



# Quick Start

## List Available Actions

```
taco ls             # List available workflows

taco ls workflow1   # List rules in workflow 1

taco ls workflow2   # List rules in workflow 2
```

## Run Workflow

Include the `-n` flag to do a dry run first.
Include the `--config-json` and `--params-json` 
flags to point taco to the configuration and parameter
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

## `rules/` Directory

The rules directory contains one folder per workflow.

Each workflow folder must include a `Snakefile`.
It is recommended to structure Snakefiles so that 
they import individual rule files. Individual rule
files then use workflow parameters from the parameters
file the user passed in.

## `workflow-config` Directory

The config files define the target files or rules for Snakemake to run.

## `workflow-params` Directory

The parameter files define values for the workflow parameters 
used to define the Snakemake rules.



# Links

[dahak-taco documentation](https://dahak-metagenomics.github.io/dahak-taco/)

[dahak-taco github repo](https://github.com/dahak-metagenomics/dahak-taco)

[taco-simple github repo](https://github.com/dahak-metagenomics/taco-simple)



## License

BSD 3-Clause License

Copyright (c) 2018, Charles Reid
All rights reserved.

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions are met:

* Redistributions of source code must retain the above copyright notice, this
  list of conditions and the following disclaimer.

* Redistributions in binary form must reproduce the above copyright notice,
  this list of conditions and the following disclaimer in the documentation
  and/or other materials provided with the distribution.

* Neither the name of the copyright holder nor the names of its
  contributors may be used to endorse or promote products derived from
  this software without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS"
AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE
IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE
DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE
FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL
DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR
SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER
CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY,
OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.

