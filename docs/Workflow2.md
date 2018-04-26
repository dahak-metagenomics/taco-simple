# Workflow 2

## Goal

Workflow 2 illustrates the use of user parameters
and wildcards to match more general output targets.

## Quick Start

To list available workflows:

```
$ taco ls
```

To get rules defined by a particular workflow:

```
$ taco ls workflow2
```

To run the workflow, use the included workflow configuration
and parameter files:

```
$ taco workflow2 \
    --config-yaml=workflow-config/workflow2_config_simple.yaml \
    --params-yaml=workflow-params/workflow2_params_simple.yaml 
```

By default, this will generate output files in the `data/` directory.
To change the output directory, use the `--prefix` flag:

```
$ taco --prefix=my_data \
    workflow2 \
    --config-yaml=workflow-config/workflow2_config_simple.yaml \
    --params-yaml=workflow-params/workflow2_params_simple.yaml 
```

If the directory does not exist, it will be created.

## Workflow Rules

Output of `taco ls workflow2`: 

```text
```

## Workflow Parameters

Default parameter dictionary defined in `workflow2.settings`:

```text
```

