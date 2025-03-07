# Changelog

Notable changes only.

## Unreleased

###  Added

- add new unique (non-shared) strings and byte vectors

### Changed

- refactor the backend to support unique

## [0.6.0] - 2024-10-08

### Changed

- implement `core::error:Error` for custom errors, rather than
  `std::error::Error` and bump msrv

### Fixed

- fix doc issue [#28](https://github.com/polazarus/hipstr/issues/28)
- fix MIRI check due to provenance loss
  [#32](https://github.com/polazarus/hipstr/pull/32)

- fix some new clippy lints (and some future lints)

## [0.5.1] - 2024-08-02

### Added

- add optional `bstr` crate support
- add `truncate`, `pop`, and `clear`
- add `concat` and `join`
- add `with_capacity`
- add `shrink_to_fit` and `shrink`

### Fixed

- some clippy lints
- fix truncating `set_len` on borrowed
- fix truncating `set_len` on allocated

## [0.5.0] - 2024-06-24

### Added

- new conversion to `Cow`s
- a niche to make `Option<HipStr>` the same size as `HipStr`

### Changed

- update MSRV to 1.77
- backend complete overall with its own custom RC implementation

### Fixed

- fixed some clippy lints

## [0.4.0] - 2023-12-01

### Added

- add `HipPath` and `HipOsStr` (#11)
- more methods to keep working with `Hip*` types when possible (#13)
- add pattern methods on `HipStr` (#17)
- more comparisons (#15)

Most of those addition are breaking because they shadows `str`'s methods.

### Changed

- make equality more efficient (#12 then #18)
- better coverage with more tests (#14)

## [0.3.3] - 2023-10-30

### Fixed

- fix clippy lint in `bytes/cmp.rs`
- fix missing `std::error::Error` impl for `string::SliceError`

## [0.3.2] - 2023-08-18

### Added

- Add trait impls for OsStr/Path compatibility
- Add push_str and push
- Add performance chart generation

## [0.3.1] - 2023-08-14

### Changed

- Improve overall performances
- Add more state of the art in the README

## [0.3.0] - 2023-08-12

### Added

- Add support for Copy On Write for any lifetime (like `std::borrow::Cow`)
- Add opt-in `borrow_deserialize`
- More tests

### Changed

- Normalize representation of short allocated string to inlined string

### Removed

- On-demand inlining with `inline`

## [0.2.0] - 2023-07-06

### Fixed

- Fix bad assert when taking full slice

### Added

- Add mutable accessor (may clone data) `to_mut_slice` for `HipByt`,
  `to_mut_str` for `HipStr`
- Add forced inlining (`inline` method)
- More docs
- More CI
- Set MSRV

### Changed

- Lower `serde` version requirement

## [0.1.0] - 2023-06-01

Initial release

<!-- [unreleased]: https://github.com/polazarus/hipstr/compare/0.6.1...HEAD -->
[0.6.0]: https://github.com/polazarus/hipstr/compare/0.5.1...0.6.0
[0.5.1]: https://github.com/polazarus/hipstr/compare/0.5.0...0.5.1
[0.5.0]: https://github.com/polazarus/hipstr/compare/0.4.0...0.5.0
[0.4.0]: https://github.com/polazarus/hipstr/compare/0.3.3...0.4.0
[0.3.3]: https://github.com/polazarus/hipstr/compare/0.3.2...0.3.3
[0.3.2]: https://github.com/polazarus/hipstr/compare/0.3.1...0.3.2
[0.3.1]: https://github.com/polazarus/hipstr/compare/0.3.0...0.3.1
[0.3.0]: https://github.com/polazarus/hipstr/compare/0.2.0...0.3.0
[0.2.0]: https://github.com/polazarus/hipstr/compare/0.1.0...0.2.0
[0.1.0]: https://github.com/polazarus/hipstr/releases/tag/0.1.0
