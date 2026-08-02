<h1 align="center">Mem Reduct</h1>

<p align="center">
	<a href="https://github.com/henrypp/memreduct/releases"><img src="https://img.shields.io/github/v/release/henrypp/memreduct?style=flat-square&include_prereleases&label=version" /></a>
	<a href="https://github.com/henrypp/memreduct/releases"><img src="https://img.shields.io/github/downloads/henrypp/memreduct/total.svg?style=flat-square" /></a>
	<a href="https://github.com/henrypp/memreduct/issues"><img src="https://img.shields.io/github/issues-raw/henrypp/memreduct.svg?style=flat-square&label=issues" /></a>
	<a href="https://github.com/henrypp/memreduct/graphs/contributors"><img src="https://img.shields.io/github/contributors/henrypp/memreduct?style=flat-square" /></a>
	<a href="https://github.com/henrypp/memreduct/blob/master/LICENSE"><img src="https://img.shields.io/github/license/henrypp/memreduct?style=flat-square" /></a>
</p>

-------

<p align="center">
	<img src="/images/memreduct.png?cachefix" />
</p>

### Description:
Lightweight real-time memory management application to monitor
and clean system memory on your computer.

The program used undocumented internal system features (Native API) to clear system cache (system working set, working set, standby page lists, modified page lists) with variable result ~10-50%. Application it is compatible with <s>Windows XP SP3</s> Windows 7 SP1 and higher operating systems.

You can download either the installer or portable version. For correct working you are require administrator rights.

```
To activate portable mode, create "memreduct.ini" in application folder, or move it from "%APPDATA%\Henry++\Mem Reduct".
```

### Exclusions:
Applications can be excluded in **Settings → Exclusions → Add executable**. An excluded application keeps its working set when memory is cleaned manually, automatically, from the tray, by hotkey, or from the command line.

Exclusions apply only to the **Working set** cleanup region. System file cache, standby lists, modified page lists, registry cache, and combined memory lists are system-wide Windows operations and cannot exclude individual applications.

Executable paths are resolved to their canonical Windows path before matching. When exclusions are active, the cleanup result also reports how many process working sets were cleaned, excluded, or skipped because Windows did not allow access.

### GitHub Actions builds:
The [Build and release workflow](.github/workflows/build.yml) builds portable x64 and ARM64 packages:

- pushes to `master`, pull requests, and manual workflow runs create downloadable workflow artifacts;
- pushing a version tag such as `v3.5.3` or `v.3.5.3` also creates a GitHub Release with both packages and SHA-256 checksums.

The version in the tag must match `APP_VERSION` in `src/app.h`. Cloud-built binaries are not GPG-signed.

The workflow pins the public `henrypp/routine` dependency. To use that same dependency in a local MSBuild invocation, set `RoutineDir` to its `src` directory and set `RoutineLegacyApi=true`.

Automatic in-app installation is disabled in this fork so it cannot replace a fork build with an upstream binary. **Help → Check for updates** opens this fork's GitHub Releases page instead.

### System requirements:
- Windows 7, 8, 8.1, 10, 11 64-bit/ARM64
- An SSE2-capable CPU
- <s>KB2533623</s> [KB3063858](https://www.microsoft.com/en-us/download/details.aspx?id=47442) update for Windows 7 was required

### Donate:
- [Bitcoin](https://www.blockchain.com/btc/address/1LrRTXPsvHcQWCNZotA9RcwjsGcRghG96c) (BTC)
- [Ethereum](https://www.blockchain.com/explorer/addresses/eth/0xe2C84A62eb2a4EF154b19bec0c1c106734B95960) (ETH)
- [Yandex Money](https://yoomoney.ru/to/4100115776040583) (RUB)
- [Paypal](https://paypal.me/henrypp) (USD)

### GPG Signature:
Official upstream binaries have a GPG signature named `memreduct.exe.sig` in the application folder. Cloud-built binaries from this fork are unsigned.

- Public key: [pubkey.asc](https://raw.githubusercontent.com/henrypp/builder/master/pubkey.asc) ([pgpkeys.eu](https://pgpkeys.eu/pks/lookup?op=index&fingerprint=on&search=0x5635B5FD))
- Key ID: 0x5635B5FD
- Fingerprint: D985 2361 1524 AB29 BE73 30AC 2881 20A7 5635 B5FD
---
- Website: [github.com/henrypp](https://github.com/henrypp)
- Support: sforce5@mail.ru
---
(c) 2011-2026 Henry++
