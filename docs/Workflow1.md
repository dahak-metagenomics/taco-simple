# Workflow 1

## Goal

Workflow 1 illustrates the use of user parameters.
Specifically, we modify the name parameter to make it 
uppercase, and use the extension parameter to 
set output file names.

## Quick Start

To list available workflows:

```
$ taco ls
```

To get rules defined by a particular workflow:

```
$ taco ls workflow1
```

To run the workflow, use the included workflow configuration
and parameter files:

```
$ taco workflow1 \
    --config-yaml=workflow-config/workflow1_config_simple.yaml \
    --params-yaml=workflow-params/workflow1_params_simple.yaml 
```

By default, this will generate output files in the `data/` directory.
To change the output directory, use the `--prefix` flag:

```
$ taco --prefix=my_data \
    workflow1 \
    --config-yaml=workflow-config/workflow1_config_simple.yaml \
    --params-yaml=workflow-params/workflow1_params_simple.yaml 
```

If the directory does not exist, it will be created.

## Workflow Rules

Output of `taco ls workflow1`: 

```text
hello_target

    Shell commands to say hello to <name>

goodbye_target

    Shell commands to say goodbye to <name>

master

    Shell commands to say hello and goodbye to <name>
```

## Workflow Parameters

Default parameter dictionary defined in `workflow1.settings`:

```text
    config_default = {
        "name" : "buzz lightyear",
        "file_extension" : "txt"
    }
```

