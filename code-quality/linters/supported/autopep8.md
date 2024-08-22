---
description: autopep8 is a linter for Python
layout:
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# autopep8

[**autopep8**](https://github.com/hhatto/autopep8#readme) is a linter for Python.

You can enable the autopep8 linter with:

```shell
trunk check enable autopep8
```

![autopep8 example output](../../configuration/supported/autopep8.gif)

## Auto Enabling

autopep8 will be auto-enabled if a `.pep8` config file is present.

## Settings

autopep8 supports the following config files:

* `.pep8`

You can move these files to `.trunk/configs` and `trunk check` will still find them. See [Moving Linter Configs](broken-reference) for more info.

## Links

* [autopep8 site](https://github.com/hhatto/autopep8#readme)
* autopep8 Trunk Code Quality [integration source](https://github.com/trunk-io/plugins/tree/main/linters/autopep8)
* Trunk Code Quality's [open source plugins repo](https://github.com/trunk-io/plugins/tree/main)