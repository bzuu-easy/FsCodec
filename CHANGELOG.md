# Changelog

The repo is versioned based on [SemVer 2.0](https://semver.org/spec/v2.0.0.html) using the tiny-but-mighty [MinVer](https://github.com/adamralph/minver) from [@adamralph](https://github.com/adamralph). [See here](https://github.com/adamralph/minver#how-it-works) for more information on how it works.

All notable changes to this project will be documented in this file. The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).

The `Unreleased` section name is replaced by the expected version of next release. A stable version's log contains all changes between that version and the previous stable version (can duplicate the prereleases logs).

## [Unreleased]

### Added
### Changed
### Removed
### Fixed

<a name="1.2.0"></a>
## [1.2.0] - 2019-09-26

### Added

- `FsCodec.Box.Codec.Create`: an API equivalent substitute for `FsCodec.NewtonsoftJson.Codec.Create` for use in unit and integration tests [#25](https://github.com/jet/FsCodec/pull/25)

### Changed

- Generalized `Codec.Create` to no longer presume `Data` and `Metadata` should always be `byte[]` [#24](https://github.com/jet/FsCodec/pull/24)

### Removed

- Removed accidentally pasted `setting` and `allowNullaryCases` in `Codec.Create`  [#23](https://github.com/jet/FsCodec/pull/23)

<a name="1.1.0"></a>
## [1.1.0] - 2019-09-19

### Added

- Polished overloads of `Codec.Create` and `NewtonsoftJson.Codec.Create` to be more navigable, and usable from C# [#23](https://github.com/jet/FsCodec/pull/23)

<a name="1.0.0"></a>
## [1.0.0] - 2019-09-17

### Added

- Defined `CorrelationId` and `CausationId` properties for `IEventData` [#21](https://github.com/jet/FsCodec/pull/21)
- Added `context : 'Context option` param to `IUnionEncoder.Encode`, enabling `down` to enrich events with `correlationId` and `causationId` values without reference to external state [#21](https://github.com/jet/FsCodec/pull/21)

### Changed

- Removed comparison support from `EventData` [#19](https://github.com/jet/FsCodec/pull/19)
- Changed `IndexedEventData` ctor to `.Create` and aligned with `EventData` [#19](https://github.com/jet/FsCodec/pull/19)
- Renamed `IEvent` to `IEventData` (to avoid clashes with `FSharp.Control.IEvent`) [#20](https://github.com/jet/FsCodec/pull/20)
- Renamed `IIndexedEvent` to `ITimelineEvent` (to avoid clashes with `FSharp.Control.IEvent`) [#20](https://github.com/jet/FsCodec/pull/20)
- Renamed `IndexedEventData` to `TimelineEvent` [#20](https://github.com/jet/FsCodec/pull/20)
- Updated `TypeShape` dependency to `8.0.0`
- Updated `MinVer` internal dependency to `2.0.0`

<a name="1.0.0-rc2"></a>
## [1.0.0-rc2] - 2019-09-07

### Added

- `tests/FsCodec.NewtonsoftJson.Tests/examples.fsx` counterpart to the `README.md`
- Exposed `TypeSafeEnum`
- `IndexedEventData` type to replace usage of impromptu objects
- overload with `up`/`down` arguments on `FsCodec.NewtonsoftJson.Codec.Create` facilitating surfacing index, metadata, and other such information in the event as surfaced to the programming model functions [#17](https://github.com/jet/FsCodec/pull/17)

### Changed

- `IUnionEncoder.TryDecode` now operates on `IIndexedEvent` (which moves to `FsCodec` from `FsCodec.Core`) instead of `IEvent`

### Removed

- `FsCodec.NewtonsoftJson.Codec.Create` overload with `genMetadata` and `genTimestamp` arguments (equivalent functionality can be achieved via `up`/`down` arguments) [#17](https://github.com/jet/FsCodec/pull/17)

### Fixed

- Pushed `TypeShape`'s `PackageReference` down into `FsCodec.NewtonsoftJson`

<a name="1.0.0-rc1"></a>
## [1.0.0-rc1] - 2019-08-30

Initial release based on merge of [Jet.JsonNet.Converters v0](https://github.com/jet/FsCodec/tree/v0) and the codecs formerly known as `Equinox.Codec` from [Equinox](https://github.com/jet/equinox) [#15](https://github.com/jet/FsCodec/pull/15)

<a name="0.2.2."></a>
## Jet.JsonNet.Converters [0.2.2]

Final release of Jet.JsonNet.Converters archived on [v0 branch](https://github.com/jet/FsCodec/tree/v0)

[Unreleased]: https://github.com/jet/equinox/compare/1.2.0...HEAD
[1.2.0]: https://github.com/jet/FsCodec/compare/1.1.0...1.2.0
[1.1.0]: https://github.com/jet/FsCodec/compare/1.0.0...1.1.0
[1.0.0]: https://github.com/jet/FsCodec/compare/1.0.0-rc2...1.0.0
[1.0.0-rc2]: https://github.com/jet/FsCodec/compare/1.0.0-rc1...1.0.0-rc2
[1.0.0-rc1]: https://github.com/jet/FsCodec/compare/0.2.2...1.0.0-rc1
[0.2.2]: https://github.com/jet/FsCodec/compare/0eb459b3aca873a40492d6a6c19cab4111d8f53e...0.2.2