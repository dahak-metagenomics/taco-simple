# Workflow 1

## Goal

Workflow 1 illustrates the use of user parameters.
Specifically, we modify the name parameter to make it 
uppercase, and use the extension parameter to 
set output file names.

## Quick Start

To list available workflows:

```text
$ taco ls
```

To get rules defined by a particular workflow:

```text
$ taco ls workflow1
```

To run the workflow, use the included workflow configuration
and parameter files:

```text
$ taco workflow1 \
    --config-yaml=workflow-config/workflow1_config_simple.yaml \
    --params-yaml=workflow-params/workflow1_params_simple.yaml 
```

By default, this will generate output files in the `data/` directory.
To change the output directory, use the `--prefix` flag:

```text
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
```

The two rules above are just echoing text to a file.

```text
master

    Shell commands to say hello and goodbye to <name>
```

This is a master rule that runs the two other rules
by requiring their output files.


## Workflow Configuration

The output files of the above rules are simple
and hard-coded: `hello.{ext}` and `goodbye.{ext}`

In the workflow configuration file, specify a
workflow target like `hello.txt` (note that this
requires you set the extension to "txt", see next 
section).

**YAML:**

```text
workflow_targets: "goodbye.txt"
```

or as a list:

```text
workflow_targets: 
  - "hello.txt"
  - "goodbye.txt"
```

(Note that this rule, as structured, does not do wildcards - 
that's left for [Workflow 3](Workflow3.md) - so we must specify
the extension ".txt" in our workflow parameters file.

## Workflow Parameters

The user defines two keys:

* `name` - the name to print to the file
* `file_extension` - the extension to use for the hello/goodbye files being created

Here is the default paramter dictionary
defined in `workflow1.settings`:

```text
    {
        "name" : "buzz lightyear",
        "file_extension" : "txt"
    }
```

