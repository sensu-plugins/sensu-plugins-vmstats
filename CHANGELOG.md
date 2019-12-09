#Change Log
This project adheres to [Semantic Versioning](http://semver.org/).

This CHANGELOG follows the format listed at [Keep A Changelog](http://keepachangelog.com/)

## [Unreleased]

### Added
- Updated asset build targets to support centos6

## [2.0.0] - 2018-05-07
### Breaking Changes
- Bump `sensu-plugin` dependency from `~> 1.2` to `~> 4.0` you can read the changelog entries for [4.0](https://github.com/sensu-plugins/sensu-plugin/blob/master/CHANGELOG.md#400---2018-02-17), [3.0](https://github.com/sensu-plugins/sensu-plugin/blob/master/CHANGELOG.md#300---2018-12-04), and [2.0](https://github.com/sensu-plugins/sensu-plugin/blob/master/CHANGELOG.md#v200---2017-03-29)

### Changed
- Removed Ruby 2.0, 2.1, and 2.2 support

### Added
- Ruby 2.4.1 testing
- Travis build automation to generate Sensu Asset tarballs that can be used in conjunction with Sensu provided ruby runtime assets and the Bonsai Asset Index

## [1.0.0] - 2016-06-16
### Added
- metric-vmstat: added CPU steal metric

### Changed
- Loosen dependency on sensu-plugin from `= 1.2.0` to `~> 1.2`
- Update Rubocop to 0.40, apply auto-correct

### Removed
- Remove Ruby 1.9.3 support; add Ruby 2.3.0 support in test matrix.

## [0.0.3] - 2015-07-14
### Changed
- updated sensu-plugin gem to 1.2.0

## [0.0.2] - 2015-06-03
### Fixed
- added binstubs

### Changed
- removed cruft from /lib

## 0.0.1 - 2015-05-20
### Added
- initial release

[Unreleased]: https://github.com/sensu-plugins/sensu-plugins-vmstats/compare/2.0.0...HEAD
[2.0.0]: https://github.com/sensu-plugins/sensu-plugins-vmstats/compare/1.0.0...2.0.0
[1.0.0]: https://github.com/sensu-plugins/sensu-plugins-vmstats/compare/0.0.3...1.0.0
[0.0.3]: https://github.com/sensu-plugins/sensu-plugins-vmstats/compare/0.0.2...0.0.3
[0.0.2]: https://github.com/sensu-plugins/sensu-plugins-vmstats/compare/0.0.1...0.0.2
