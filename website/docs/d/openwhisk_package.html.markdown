---
layout: "ibm"
page_title: "IBM : OpenWhisk_package"
sidebar_current: "docs-ibm-data-source-openwhisk-package"
description: |-
  Get information on an IBM Cloud Open Whisk Package.
---

# ibm\_openwhisk_package

Import the details of an existing package for IBM Cloud Open Whisk as a read-only data source. The fields of the data source can then be referenced by other resources within the same configuration using interpolation syntax.

## Example Usage

```hcl
data "ibm_openwhisk_package" "package" {
    name = "package_name"
}
```

## Argument Reference

The following arguments are supported:

* `name` - (Required, string) Name of package.


## Attributes Reference

The following attributes are exported:

* `id` - The ID of the package.
* `version` - Semantic version of the item.
* `publish` - Whether the item is published or not.
* `annotations` - Annotations on the item.
* `parameters` - Parameter bindings included in the context passed to the package.
