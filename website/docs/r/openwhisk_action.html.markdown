---
layout: "ibm"
page_title: "IBM : OpenWhisk_action"
sidebar_current: "docs-ibm-resource-openwhisk-action"
description: |-
  Manages IBM Cloud Open Whisk action.
---

# ibm\_openwhisk_action

Create, update, or delete action for IBM Cloud Open Whisk action.

## Example Usage

```hcl
resource "ibm_openwhisk_action" "nodehello" {
			name = "action-name"		  
			exec = {
			  kind = "nodejs:6"
			  code = "${file("hellonode.js")}"
			}
		  }
```

## Argument Reference

The following arguments are supported:

* `name` - (Required, string) Name of action.
* `limits` - (Optional, set) A nested block describing the limits assigned to . Nested `limits` blocks have the following structure:
    * `timeout` - (Optional, integer) The timeout LIMIT in milliseconds after which the action is terminated. Default value is 60000.
    * `memory` - (Optional, integer) The maximum memory LIMIT in MB for the action. Default is 256.
    * `log_size` - (Optional, integer) The maximum log size LIMIT in MB for the action. Default value is 10.
* `exec` - (Required, set) A nested block describing the exec assigned to . Nested `exec` blocks have the following structure:
    * `image` - (Optional, integer) Container image name when kind is 'blackbox'.
    * `init` - (Optional, integer) Optional zipfile reference when code kind is 'nodejs'.
    * `code` - (Optional, integer) The code to execute when kind is not 'blackbox'
    * `kind` - (Required, integer) The type of action. Possible values: nodejs, blackbox, swift, sequence.
    * `main` - (Optional, integer) The name of the action entry point (function or fully-qualified method name when applicable)
    * `components` - (Optional, integer) The List of fully qualified action.
* `publish` - (Optional, boolean) Whether to publish the item or not.
* `user_defined_annotations` - (Optional, string) User defined annotations on the item.
* `user_defined_parameters` - (Optional, string) User defined parameter bindings included in the context passed to the action.

## Attributes Reference

The following attributes are exported:

* `id` - The ID of the new action.
* `version` - Semantic version of the item.
* `annotations` -  Annotations on the item.
* `parameters` - Parameter on the item
