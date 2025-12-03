# asdf-firefox (ESR)

[Firefox](https://www.mozilla.org/pl/firefox/) plugin for [asdf](https://github.com/asdf-vm/asdf) version manager
or the [asdf backend of mise](https://mise.jdx.dev/dev-tools/backends/asdf.html).



## Context

The goal of this project is primarily to support testing and our CI infrastructure.


## Install

```
asdf plugin-add firefox https://github.com/DrTom/asdf-firefox.git

```

or with mise:

```
mise plugin install firefox https://github.com/DrTom/asdf-firefox.git
```

## Usage Notes

Listing available versions with `asdf list-all firefox` will **only output ESR
versions**, and hence the shortcut `latest` points to the most recent ESR
version.

It is still possible to **install any available version** (not only ESRs) which
can be found under https://ftp.mozilla.org/pub/firefox/releases/.


### Geckodriver

Firefox version 52 and later requires https://github.com/mozilla/geckodriver to
be driven from external tools. See https://github.com/DrTom/asdf-geckodriver for
the corresponding asdf plugin.

See https://firefox-source-docs.mozilla.org/testing/geckodriver/Support.html
for a compatibility list between Geckodriver and Firefox.


## Limits

### Supported Platforms and Architectures

This plugin is used and known to work on **linux** (AMD64 architecture) and
**MacOS**. Other platforms and architectures not supported and will most likely
fail to install.

The provided MacOS version should run both on AMD64 (Intel) or ARM64 (M1, M2,
etc).

There seems (yet) to be no official support for ARM64 on linux even though
distributions generally provide Firefox on this platform.


### Notes to MacOS

The **MacOS install is partially manual** but relatively easy to perform. The
`install` command **guides** through the manual steps.


### Preventing Automatic Updates

Some (recent) versions of Firefox (for MacOS in particular) try to aggressively
update themself. Automatic updates can be prevented by (some rather cumbersome
and apparently unstable) configuration within Firefox itself.

We found **restricting the application folder** more reliable. On MacOS: "Get
Info", then set "Locked". Note that the `uninstall` command requires the lock
to be lifted beforehand.


## Credits

This work is heavily inspired by https://github.com/vincentvanbush/asdf-firefox.git.
