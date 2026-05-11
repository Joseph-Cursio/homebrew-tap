# homebrew-tap

Homebrew tap for [SwiftUMLBridge](https://github.com/Joseph-Cursio/SwiftUMLStudio) — a Swift-native CLI that generates architectural UML diagrams from Swift source code.

## Installation

```bash
brew tap Joseph-Cursio/tap
brew install swiftumlbridge
```

> **macOS 26 note.** The formula builds from source via `swift build` and requires the Swift 6.2 toolchain that ships with Xcode 26+. If `brew install` reports a "Tier 2 configuration" warning, install the Command Line Tools matching your Xcode version (Xcode → Settings → Locations, or download from [developer.apple.com](https://developer.apple.com/download/all/)). The build will succeed without the CLT, but Homebrew prefers them.

## Usage

```bash
swiftumlbridge classdiagram ./Sources/MyLib
swiftumlbridge sequence ./Sources/MyLib --entry MyController.start
swiftumlbridge component --package ./MyPackage
```

See the [user guide](https://github.com/Joseph-Cursio/SwiftUMLStudio/blob/main/docs/user/user-guide.md) and [CLI reference](https://github.com/Joseph-Cursio/SwiftUMLStudio/blob/main/docs/user/reference.md) for the full subcommand and flag set.

## Formula source

`Formula/swiftumlbridge.rb` here is mirrored from `homebrew/Formula/swiftumlbridge.rb` in the upstream repository. To update for a new release:

1. Cut and publish a new GitHub release on `Joseph-Cursio/SwiftUMLStudio`.
2. Bump the `url`, `sha256`, and `--version` assertion in `Formula/swiftumlbridge.rb` here.
3. Commit and push — the tap is consumed live, no extra publish step.

## License

The formula is MIT-licensed. SwiftUMLBridge itself is also MIT-licensed; see [LICENSE](https://github.com/Joseph-Cursio/SwiftUMLStudio/blob/main/LICENSE) in the upstream repo.
