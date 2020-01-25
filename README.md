[![Sensu Bonsai Asset](https://img.shields.io/badge/Bonsai-Download%20Me-brightgreen.svg?colorB=89C967&logo=sensu)](https://bonsai.sensu.io/assets/sensu-plugins/sensu-plugins-vmstats)
[ ![Build Status](https://travis-ci.org/sensu-plugins/sensu-plugins-vmstats.svg?branch=master)](https://travis-ci.org/sensu-plugins/sensu-plugins-vmstats)
[![Gem Version](https://badge.fury.io/rb/sensu-plugins-vmstats.svg)](http://badge.fury.io/rb/sensu-plugins-vmstats)
[![Code Climate](https://codeclimate.com/github/sensu-plugins/sensu-plugins-vmstats/badges/gpa.svg)](https://codeclimate.com/github/sensu-plugins/sensu-plugins-vmstats)
[![Test Coverage](https://codeclimate.com/github/sensu-plugins/sensu-plugins-vmstats/badges/coverage.svg)](https://codeclimate.com/github/sensu-plugins/sensu-plugins-vmstats)
[![Dependency Status](https://gemnasium.com/sensu-plugins/sensu-plugins-vmstats.svg)](https://gemnasium.com/sensu-plugins/sensu-plugins-vmstats)

## Sensu Plugins vmstats Plugin

- [Overview](#overview)
- [Files](#files)
- [Usage examples](#usage-examples)
- [Configuration](#configuration)
  - [Sensu Go](#sensu-go)
    - [Asset registration](#asset-registration)
    - [Asset definition](#asset-definition)
    - [Check definition](#check-definition)
  - [Sensu Core](#sensu-core)
    - [Check definition](#check-definition)
- [Installation from source](#installation-from-source)
- [Additional notes](#additional-notes)
- [Contributing](#contributing)

### Overview

This plugin provides native vmstat instrumentation for metrics collection, including processes waiting, interrupts per second, and more.

### Files
 * bin/metrics-vmstat.rb
 
**metrics-vmstat**
Uses vmstat to collect basic system metrics and produces Graphite-formatted output.

## Usage examples

### Help

**metrics-vmstat.rb**
```
Usage: metrics-vmstat.rb (options)
        --scheme SCHEME              Metric naming scheme, text to prepend to .$parent.$child 
```

## Configuration
### Sensu Go
#### Asset registration

Assets are the best way to make use of this plugin. If you're not using an asset, please consider doing so! If you're using sensuctl 5.13 or later, you can use the following command to add the asset: 

`sensuctl asset add sensu-plugins/sensu-plugins-vmstats`

If you're using an earlier version of sensuctl, you can download the asset definition from [this project's Bonsai asset index page](https://bonsai.sensu.io/assets/sensu-plugins/sensu-plugins-vmstats).

#### Asset definition

```yaml
---
type: Asset
api_version: core/v2
metadata:
  name: sensu-plugins-vmstats
spec:
  url: https://assets.bonsai.sensu.io/5c97f93791b98b2542c5c9739e88ca28b76a95ac/sensu-plugins-vmstats_2.0.0_centos_linux_amd64.tar.gz
  sha512: 366eb41a1ad3b7750d7de5f510b6a17393729eac09d4b786e9af440b8036a737fa3ff8da1e137238edce8585898fa936cf096c4c12c226f628d998ca59769e6f
```

#### Check definition

```yaml
---
type: CheckConfig
api_version: core/v2
metadata:
  name: metrics-vmstats
  namespace: default
spec:
  check_hooks: null
  command: metrics-vmstat.rb -exporter-url http://localhost:8080/metrics
  output_metric_format: graphite
  output_metric_handlers:
  - graphite
  runtime_assets:
  - sensu/sensu-plugins-metrics-vmstats
  - sensu/sensu-ruby-runtime
  stdin: false
  subdue: null
  subscriptions:
  - linux
  timeout: 5
  ttl: 0
```

### Sensu Core

#### Check definition
```json
{
  "checks": {
    "metrics-vmstats": {
      "type": "metric",
      "command": "metrics-vmstat.rb -exporter-url http://localhost:8080/metrics",
      "subscribers": ["app_tier"],
      "interval": 10,
      "handler": "graphite"
    }
  }
}
```

## Installation from source

### Sensu Go

See the instructions above for [asset registration](#asset-registration).

### Sensu Core

Install and setup plugins on [Sensu Core](https://docs.sensu.io/sensu-core/latest/installation/installing-plugins/).

## Additional notes

### Sensu Go Ruby Runtime Assets

The Sensu assets packaged from this repository are built against the Sensu Ruby runtime environment. When using these assets as part of a Sensu Go resource (check, mutator, or handler), make sure to include the corresponding [Sensu Ruby Runtime Asset](https://bonsai.sensu.io/assets/sensu/sensu-ruby-runtime) in the list of assets needed by the resource.

## Contributing

See [CONTRIBUTING.md](https://github.com/sensu-plugins/sensu-plugins-vmstats/blob/master/CONTRIBUTING.md) for information about contributing to this plugin.
