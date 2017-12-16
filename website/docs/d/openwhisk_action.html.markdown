---
layout: "ibm"
page_title: "IBM : OpenWhisk_action"
sidebar_current: "docs-ibm-datasource-openwhisk-action"
description: |- Get information on a IBM Cloud Open Whisk action.
---

# ibm\_openwhisk_action

Import the details of an existing Action as a read-only data source. You can then reference the fields of the data source in other resources within the same configuration using interpolation syntax.

## Example Usage

```hcl
data "ibm_openwhisk_action" "nodehello" {
			name = "action-name"		  
		  }
```

## Argument Reference

The following arguments are supported:

* `name` - (Required, string) Name of action.

## Attributes Reference

The following attributes are exported:

* `id` - The ID of the new action.
* `version` - Semantic version of the item.
* `annotations` -  Annotations on the item.
* `parameters` - Parameter on the item
* `limits` - A nested block describing the limits assigned to . Nested `limits` blocks have the following structure:
    * `timeout` -  The timeout LIMIT in milliseconds after which the action is terminated. Default value is 60000.
    * `memory` -  The maximum memory LIMIT in MB for the action. Default is 256.
    * `log_size` - The maximum log size LIMIT in MB for the action. Default value is 10.
* `exec` - (Required, set) A nested block describing the exec assigned to . Nested `exec` blocks have the following structure:
    * `image` -  Container image name when kind is 'blackbox'.
    * `init` -  Optional zipfile reference when code kind is 'nodejs'.
    * `code` - The code to execute when kind is not 'blackbox'
    * `kind` -  The type of action. Possible values: nodejs, blackbox, swift, sequence.
    * `main` -  The name of the action entry point (function or fully-qualified method name when applicable)
    * `components` - The List of fully qualified action.
* `publish` - (Optional, boolean) Whether to item will published or not.
