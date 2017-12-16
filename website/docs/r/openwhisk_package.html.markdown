---
layout: "ibm"
page_title: "IBM : OpenWhisk_package"
sidebar_current: "docs-ibm-resource-openwhisk-package"
description: |-
  Manages IBM Cloud Open Whisk package.
---

# ibm\_openwhisk_package

Create, update, or delete package for IBM Cloud Open Whisk action.

## Example Usage

```hcl
resource "ibm_openwhisk_package" "package" {
   	name = "package-name"
	user_defined_annotations = <<EOF
	[
    {
        "key":"description",
        "value":"Count words in a string"
    },
    {
        "key":"sampleOutput",
        "value": {
			"count": 3
		}
    },
    {
        "key":"final",
        "value": [
			{
				"description": "A string",
				"name": "payload",
				"required": true
			}
		]
    }
]
EOF

}
```

## Argument Reference

The following arguments are supported:

* `name` - (Required, string) Name of package.
* `publish` - (Optional, boolean) Whether to publish the item or not.Default is false
* `user_defined_annotations` - (Optional, string) User defined annotations on the item.
* `user_defined_parameters` - (Optional, string) User defined parameter bindings included in the context passed to the action.
* `bind_package_name` - (Optional, string) Name of package to be binded.

## Attributes Reference

The following attributes are exported:

* `id` - The ID of the new package.
* `version` - Semantic version of the item.
* `annotations` -  Annotations on the item.
* `parameters` - Parameter on the item
