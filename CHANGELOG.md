# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic
Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added

### Changed

- Reorganized to a workspace ([#114](https://github.com/gadomski/stac-rs/pull/114))

## [0.2.0] - 2022-12-29

### Added

- `stac-async` ([#114](https://github.com/gadomski/stac-rs/pull/114))
- `description` to `Catalog::new` and `Collection::new` ([#102](https://github.com/gadomski/stac-rs/pull/102))
- jsonschema validation ([#105](https://github.com/gadomski/stac-rs/pull/105), [#106](https://github.com/gadomski/stac-rs/pull/106))
- `Extensions` trait ([#105](https://github.com/gadomski/stac-rs/pull/105))
- `ItemCollection` ([#107](https://github.com/gadomski/stac-rs/pull/107))
- `Value::type_name` ([#108](https://github.com/gadomski/stac-rs/pull/108))
- `Links::make_relative_hrefs_absolute` ([#110](https://github.com/gadomski/stac-rs/pull/110))

### Changed

- Signature of `Error::MissingHref` (no longer takes a String) ([#110](https://github.com/gadomski/stac-rs/pull/110))
- `Links` now requires `Href` ([#110](https://github.com/gadomski/stac-rs/pull/110))

### Fixed

- `Collections::new` sets a valid license ("proprietary") ([#104](https://github.com/gadomski/stac-rs/pull/104))

### Removed

- `Error::TypeMismatch`, depreacted since v0.1.1 ([#111](https://github.com/gadomski/stac-rs/pull/111))

## [0.1.2] - 2022-12-08

### Added

- `Links` trait ([#95](https://github.com/gadomski/stac-rs/pull/95), [#96](https://github.com/gadomski/stac-rs/pull/96), [#97](https://github.com/gadomski/stac-rs/pull/97), [#100](https://github.com/gadomski/stac-rs/pull/100))
- `Link::json` for making links with a JSON media type ([#100](https://github.com/gadomski/stac-rs/pull/100))
- Builder methods for `Link` ([#100](https://github.com/gadomski/stac-rs/pull/100))
- `Item::collection_link` ([#100](https://github.com/gadomski/stac-rs/pull/100))
- `Link::collection` for making `rel="collection"` links ([#100](https://github.com/gadomski/stac-rs/pull/100))
- `Link::self_` for making `rel="self"` links ([#101](https://github.com/gadomski/stac-rs/pull/101))

## [0.1.1] - 2022-12-01

### Deprecated

- `Error::TypeMismatch` ([#93](https://github.com/gadomski/stac-rs/pull/93))

## [0.1.0] - 2022-11-30

### Added

- `stac::read_json`

### Changed

- Module layout

### Removed

- `Item::set_collection` and `Item::collection_link`
- CI coverage
- `stac::read_from_url` and `stac::read_from_path`

### Fixed

- Documentation examples

## [0.0.5] - 2022-11-12

### Added

- `Href` trait
- `Value`

### Changed

- `Asset.type_` is now `Asset.r#type`
- `reqwest` is now an optional feature

### Removed

- `PathBufHref`
- `Href::into_string`
- `Stac`
- `Layout`
- `Reader`
- `Writer`
- `Object`
- `Href` struct
- benchmarks

## [0.0.4] - 2022-03-09

### Added

- Top-level convenience functions for reading all three object types directly to structures
- `Read::read_struct`
- `Error::TypeMismatch`
- Links to parent and root in `Stac` when adding a new object
- `Stac::href`
- `Href::file_name`
- `Stac::collections`
- Options to customize the `Walk` strategy
- `Stac::set_href`
- Coverage
- Crate-specific `Result`
- `Href::directory`
- `impl From<Href> for String`
- `Object::parent_link` and `Object::child_links`
- `Stac::add_link` and `Stac::children`
- `stac::layout`
- Pull request template
- Docs

### Changed

- Made `Handle`s innards private
- Generalized `Stac::find_child` to `Stac::find`
- Made `PathBufHref::new` public
- Cannot remove the root of a `Stac`
- `Href::make_relative` returns an absolute href if it can't be made relative
- Benchmark plots now have white backgrounds
- Reqwest test is ignored by default to speed up unit tests
- Use `impl` in function arguments instead of generic types
- The default walk iterator's Item is a `Result<Handle>`
- Set a walk's visit function as its own operation, rather than during the constructor

### Fixed

- Relative href generation

## [0.0.3] - 2022-02-22

### Added

- Doctesting for README.md
- `Href::rebase`
- `Object` and `HrefObject`
- Architecture diagram
- `Stac.add_child`
- Benchmarks
- `Walk`
- `Stac::remove`

### Changed

- Simplified `Render`'s href creation
- CI workflows
- `Stac::add_object` is now `add`
- `Stac::add_child_handle` is now `connect`
- `Stac::object` is now `get`

### Removed

- `stac::render`

## [0.0.2] - 2022-02-14

### Added

- More information to the README

### Removed

- Custom docs build

## [0.0.1] - 2022-02-14

Initial release.

[Unreleased]: https://github.com/gadomski/stac-rs/compare/v0.2.0...main
[0.2.0]: https://github.com/gadomski/stac-rs/compare/v0.1.2...v0.2.0
[0.1.2]: https://github.com/gadomski/stac-rs/compare/v0.1.1...v0.1.2
[0.1.1]: https://github.com/gadomski/stac-rs/compare/v0.1.0...v0.1.1
[0.1.0]: https://github.com/gadomski/stac-rs/compare/v0.0.5...v0.1.0
[0.0.5]: https://github.com/gadomski/stac-rs/compare/v0.0.4...v0.0.5
[0.0.4]: https://github.com/gadomski/stac-rs/compare/v0.0.3...v0.0.4
[0.0.3]: https://github.com/gadomski/stac-rs/compare/v0.0.2...v0.0.3
[0.0.2]: https://github.com/gadomski/stac-rs/compare/v0.0.1...v0.0.2
[0.0.1]: https://github.com/gadomski/stac-rs/releases/tag/v0.0.1
