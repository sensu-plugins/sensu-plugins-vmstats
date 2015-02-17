## Sensu-Plugins-vmstats

[![Build Status](https://travis-ci.org/sensu-plugins/sensu-plugins-vmstats.svg?branch=master)](https://travis-ci.org/sensu-plugins/sensu-plugins-vmstats)
[![Gem Version](https://badge.fury.io/rb/sensu-plugins-vmstats.svg)](http://badge.fury.io/rb/sensu-plugins-vmstats)
[![Code Climate](https://codeclimate.com/github/sensu-plugins/sensu-plugins-vmstats/badges/gpa.svg)](https://codeclimate.com/github/sensu-plugins/sensu-plugins-vmstats)
[![Test Coverage](https://codeclimate.com/github/sensu-plugins/sensu-plugins-vmstats/badges/coverage.svg)](https://codeclimate.com/github/sensu-plugins/sensu-plugins-vmstats)
[![Dependency Status](https://gemnasium.com/sensu-plugins/sensu-plugins-vmstats.svg)](https://gemnasium.com/sensu-plugins/sensu-plugins-vmstats)

## Functionality

## Files
 * bin/metrics-vmstats

## Usage

## Installation

Add the public key (if you haven’t already) as a trusted certificate

```
gem cert --add <(curl -Ls https://raw.githubusercontent.com/sensu-plugins/sensu-plugins.github.io/master/certs/sensu-plugins.pem)
gem install sensu-plugins-vmstats -P MediumSecurity
```

You can also download the key from /certs/ within each repository.

#### Rubygems

`gem install sensu-plugins-vmstats`

#### Bundler

Add *sensu-plugins-disk-checks* to your Gemfile and run `bundle install` or `bundle update`

#### Chef

Using the Sensu **sensu_gem** LWRP
```
sensu_gem 'sensu-plugins-vmstats' do
  options('--prerelease')
  version '0.0.1'
end
```

Using the Chef **gem_package** resource
```
gem_package 'sensu-plugins-vmstats' do
  options('--prerelease')
  version '0.0.1'
end
```

## Notes
