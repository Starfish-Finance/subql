# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

All logs must start with the format: [x.y.z] - yyyy-mm-dd

## [Unreleased]

## [1.6.0]
### Changed
- Change max connection to 10 ms and query timeout to 10000 ms. (#1322)
### Added
- Added hot-schema reload, query-service no longer needs to restart to see schema changes. (#1321)

## [1.5.0] - 2022-08-11
### Fixed
- Fix db selection in configuration when subscription is enabled (#1241)
- Fork OrderByAggregatesPlugin and modify to be compatible with historical feature (#1242)
- Fix block height being applied to all queries (#1238)
### Changed
- Move aggregation feature out from `unsafe` and apply it by default, can be control though `aggregate` flag.

## [1.4.0] - 2022-07-27
### Added
- Add `query-explain` flag, by enable this console will log actual SQL statement been queried. (#1192)

## [1.3.0] - 2022-07-05
### Changed
- Try to catch error if create server failed, also give retry build schema (#1153)
### Fixed
- Fix tests (#1160)

## [1.2.1] - 2022-06-27
### Fixed
- Fixed subql-query doesn't show all help docs issue (#1137)

## [1.2.0] - 2022-06-22
### Added
- added `max-connection` and `query-timeout` configuration for pg pool (#1108)

## [1.1.1] - 2022-06-02
### Changed
- Now query-complexity is indicated in header (#1088)

## [1.1.0] - 2022-05-31
### Added
- Experimental feature: Support query by block number, require enable by indexing node (#992)

## [1.0.0] - 2022-05-11
- Major release

## [0.16.1] - 2022-05-06
### Changed
- Bump with `@subql/utils`

## [0.16.0] - 2022-05-02
### Added
- Add utils package (#928)
- Allow set query-complexity for query (#923)

## [0.15.0] - 2022-04-26
### Added
- Add support for querying historical state (#859)

## [0.14.1] - 2022-04-04
### Changed
- Bump with `subql/common`

## [0.14.0] - 2022-04-04
### Changed
- move subscription to dedicate flag (#867)

## [0.13.0] - 2022-03-22
### Added
- Add GraphQL subscription support (#846)

## [0.12.0] - 2022-02-09
### Added 
- Add `dynamicDatasources` in metadata (#773)

## [0.11.0] - 2022-01-21
### Added 
- Enable full aggregates support when `--unsafe`, and group-by only when `--unsafe=false` (#765)

## [0.10.0] - 2022-01-13
### Added 
- Add rowCountEstimate to Metadata (#736)
- Support allocate port automatically (#739)


## [0.9.0] - 2021-12-16
### Changed
- Limit query record size to 100, though by using `--unsafe` can remove this limit. (#644)
- Update `getProjectSchema` to handle when subqueries table has been deprecated (#683)
- Update `Dockerfile` to use `node:16-alpine` (#640)
### Added
- Add query log to file (#667)
### Fixed
- Fix fetch metadata (#700)

## [0.8.0] - 2021-11-19
### Added
- Support enum in postgraphile plugin (#551)
### Changed
- Update `GetMetadataPlugin` to support fetch from both api and table (#555)

## [0.7.4] - 2021-11-03
### Changed
- Bump dependencies (#584)

## [0.7.3] - 2021-09-25
Upgrade priority: High. Any project rely on query `_metadata` should upgrade.
### Fixed
- Change `_metadata` back, and use `smartTagPlugin` to omit node `metadata` class. By doing this, previous project that rely on query `_metadata` won't be affected, such as Dictionaries.

## [0.7.2] - 2021-09-22
Upgrade priority: High. This fix the entities name conflict issue, for users who used node 0.21.0 or higher should update to query 0.7.2.
### Changed
- Changed query indexer `_metadata` to `_meta`, current `_metadata` is created from indexer service included `blockOffset` data (#489)

## [0.7.1] - 2021-08-27
### Fixed
- Deprecated warnings (#448)

## [0.7.0] - 2021-06-25
### Changed
- Update dependencies (#358)

## [0.6.0] - 2021-06-22
### Added
- Allow query service to query indexer metadata though add `--indexer <indexer-meta-api>` (#327)
- Add `_Metadata` in the query schema (#327)
### Changed
- change `lastProcessedHeight` and `targetHeight` type to `Int`. (#347)


## [0.5.0] - 2021-04-20
### Added
- Remove `condition` in query schema, please use `filter` instead (#260)
- `@jsonField` annotation is now supported in `graphql.schema` which allows you to store structured data JSON data in a single database field
  - We'll automatically generate coresponding JSON interfaces when querying this data (#275)
  - Read more about how you can use this in our [updated docs](https://doc.subquery.network/create/graphql.html#json-type)

## [0.4.0] - 2021-03-25
### Added
- support filter for condition search (#240)

## [0.3.2] - 2021-03-11
### Fixed
- add dependency of @subql/common for @subql/query (#233)

## [0.3.1] - 2021-03-11
### Fixed
- fix wrong cross package imports (#231)

## [0.3.0] - 2021-03-11
### Added
- refactor logger: support --output-fmt and --log-level (#220)
- use read db host (DB_HOST_READ from env) as priority (#221)

## [0.2.0] - 2021-02-05
### Added
- init query service project
- customise first/last plugin to give max record to query (#114)
- disable debug mode in production (#115)
- overwrite plugin to fix one to one unique key check
- update query publish and docker build process

[Unreleased]: https://github.com/subquery/subql/compare/query/0.12.0...HEAD
[0.12.0]: https://github.com/subquery/subql/compare/query/0.11.0...query/0.12.0
[0.11.0]: https://github.com/subquery/subql/compare/query/0.10.0...query/0.11.0
[0.10.0]: https://github.com/subquery/subql/compare/query/0.9.0...query/0.10.0
[0.9.0]: https://github.com/subquery/subql/compare/query/0.8.0...query/0.9.0
[0.8.0]: https://github.com/subquery/subql/compare/query/0.7.4...query/0.8.0
[0.7.4]: https://github.com/subquery/subql/compare/query/0.7.3...query/0.7.4
[0.5.0]: https://github.com/subquery/subql/compare/v0.4.0...v0.5.0
[0.4.0]: https://github.com/subquery/subql/compare/v0.3.2...v0.4.0
[0.3.2]: https://github.com/subquery/subql/compare/v0.3.1...v0.3.2
[0.3.1]: https://github.com/subquery/subql/compare/v0.3.0...v0.3.1
[0.3.0]: https://github.com/subquery/subql/compare/v0.2.0...v0.3.0
