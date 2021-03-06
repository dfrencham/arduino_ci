# Change Log
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](http://keepachangelog.com/)
and this project adheres to [Semantic Versioning](http://semver.org/).

## [Unreleased]
### Added

### Changed

### Deprecated

### Removed

### Fixed

### Security


## [0.1.7] - 2018-03-07
### Changed
- Queue and Table are now ArduinoCIQueue and ArduinoCITable to avoid name collisions


## [0.1.6] - 2018-03-07
### Added
- `CppLibrary` can now report `gcc_version`

### Changed
- `arduino_ci_remote.rb` now formats tasks with multiple output lines more nicely
- Templates for CI classes are now pass-by-value (no const reference)

### Fixed
- Replaced pipes with `Open3.capture3` to avoid deadlocks when commands have too much output
- `ci_config.rb` now returns empty arrays (instead of nil) for undefined config keys
- `pgmspace.h` explictly includes `<string.h>`
- `__FlashStringHelper` should now be properly mocked for compilation
- `WString.h` bool operator now works and is simpler

### Security


## [0.1.5] - 2018-03-05
### Added
- Yaml files can have either `.yml` or `.yaml` extensions
- Yaml files support select/reject critera for paths of unit tests for targeted testing
- Pins now track history and can report it in Ascii (big- or little-endian) for digital sequences
- Pins now accept an array (or string) of input bits for providing pin values across multiple reads
- FlashStringHelper (and related macros) compilation mocks
- SoftwareSerial.  That took a while.
- Queue template implementation
- Table template implementation
- ObservableDataStream and DataStreamObserver pattern implementation
- DeviceUsingBytes and implementation of mocked serial device

### Changed
- Unit test executables print to STDERR just in case there are segfaults.  Uh, just in case I ever write any.

### Fixed
- OSX no longer experiences `javax.net.ssl.SSLKeyException: RSA premaster secret error` messages when downloading board package files
- `arduino_ci_remote.rb` no longer makes unnecessary changes to the board being tested
- Scripts no longer crash if there is no `test/` directory
- Scripts no longer crash if there is no `examples/` directory
- `assureTrue` and `assureFalse` now `assure` instead of just `assert`ing.


## [0.1.4] - 2018-02-01
### Added
- Support for all builtin Math functions https://www.arduino.cc/reference/en/
- Support for all builtin Bits and Bytes functions https://www.arduino.cc/reference/en/
- Support for GODMODE and time functions
- Support for Character functions https://www.arduino.cc/reference/en/
- Mocks for `random` functions with seed control
- Many original Arduino `#define`s
- Mocks for pinMode, analog/digital read/write
- Support for WString
- Support for Print
- Support for Stream (backed by a String implementation)
- All the IO stuff (pins, serial port support flags, etc) from the Arduino library
- Support for Serial (backed by GODMODE)

### Changed
- Made `wget` have quieter output


## [0.1.3] - 2018-01-25
### Added
- C++ functions for `assure`; `assert`s will run tests and continue, `assure`s will abort on failures
- Missing dotfiles in the `DoSomething` project have been committed

### Changed
- `arduino_ci_remote.rb` doesn't attempt to set URLs if nothing needs to be downloaded
- `arduino_ci_remote.rb` does unit tests first
- `unittest_main()` is now the macro for the `int main()` of test files

### Fixed
- All test files were reporting "not ok" in TAP output.  Now they are OK iff all asserts pass.
- Directories with a C++ extension in their name could cause problems.  Now they are ignored.
- `CppLibrary` had trouble with symlinks. It shoudn't anymore.
- `CppLibrary` had trouble with vendor bundles.  It might in the future, but I have a better fix ready to go if it's an issue.


## [0.1.2] - 2018-01-25

### Fixed
- Actually package CPP and YAML files into the gem.  Whoops.

## [0.1.1] - 2018-01-24

### Added
- README documentation for the actual unit tests


## [0.1.0] - 2018-01-24
### Added
- Unit testing support
- Documentation for all Ruby methods
- `ArduinoInstallation` class for managing lib / executable paths
- `DisplayManager` class for managing Xvfb instance if needed
- `ArduinoCmd` captures and caches preferences
- `ArduinoCmd` reports on whether a board is installed
- `ArduinoCmd` sets preferences
- `ArduinoCmd` installs boards
- `ArduinoCmd` installs libraries
- `ArduinoCmd` selects boards (compiler preference)
- `ArduinoCmd` verifies sketches
- `CppLibrary` manages GCC for unittests
- `CIConfig` manages overridable config for all testing

### Changed
- `DisplayManger.with_display` doesn't `disable` if the display was enabled prior to starting the block

### Fixed
- Built gems are `.gitignore`d
- Updated gems based on Github's security advisories


## [0.0.1] - 2018-01-10
### Added
- Skeleton for gem with working unit tests


[Unreleased]: https://github.com/ifreecarve/arduino_ci/compare/v0.1.7...HEAD
[0.1.7]: https://github.com/ifreecarve/arduino_ci/compare/v0.1.6...v0.1.7
[0.1.6]: https://github.com/ifreecarve/arduino_ci/compare/v0.1.5...v0.1.6
[0.1.5]: https://github.com/ifreecarve/arduino_ci/compare/v0.1.4...v0.1.5
[0.1.4]: https://github.com/ifreecarve/arduino_ci/compare/v0.1.3...v0.1.4
[0.1.3]: https://github.com/ifreecarve/arduino_ci/compare/v0.1.2...v0.1.3
[0.1.2]: https://github.com/ifreecarve/arduino_ci/compare/v0.1.1...v0.1.2
[0.1.1]: https://github.com/ifreecarve/arduino_ci/compare/v0.1.0...v0.1.1
[0.1.0]: https://github.com/ifreecarve/arduino_ci/compare/v0.0.1...v0.1.0
[0.0.1]: https://github.com/ifreecarve/arduino_ci/compare/v0.0.0...v0.0.1
