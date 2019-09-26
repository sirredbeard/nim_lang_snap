
# Snap of the Nim programming language

This repository is a set of GitHub Actions and Snapcraft snap templates that automates deployment of stable, LTS, and nightly builds of the [Nim programming language](https://nim-lang.org/) and [bundled tools](https://nim-lang.org/docs/tools.html).

Nim is a compiled, garbage-collected systems programming language with a design that focuses on efficiency, expressiveness, and elegance.

* [Learn Nim](https://nim-lang.org/learn.html) - Tutorial
* [Documentation](https://nim-lang.org/documentation.html) - Documentation
* [Nim in Action](https://www.manning.com/books/nim-in-action) - Book from Manning Publications
* [What Is Nim? A brief introduction to the Nim programming language](https://www.youtube.com/watch?v=nKTLsUF9oyU) - YouTube video

A snap is a bundle of an app and its dependencies that works without modification across many different Linux distributions.

* [Getting Started](https://snapcraft.io/docs/getting-started) - Tutorial
* [Documentation](https://snapcraft.io/docs) - Documentation
* [Snapcraft Store](https://snapcraft.io/store) - Snap app store

For a technical walkthrough of how this repository works, see [my blog post](boxofcables.dev/snaps-for-nim/).

## Branches

### Stable

Recommended for most users.

Install from the command line with: `$ snap install nim-lang`

[![Get it from the Snap Store](https://snapcraft.io/static/images/badges/en/snap-store-black.svg)](https://snapcraft.io/nim-lang)

Or visit the [Snapcraft Store](https://snapcraft.io/nim-lang).

See [Installing Snapd](https://snapcraft.io/docs/installing-snapd) if you do not have snap installed.

![stable status](https://github.com/sirredbeard/nim_lang_snap/workflows/stable/badge.svg)

[![nim-lang](https://snapcraft.io/nim-lang/badge.svg)](https://snapcraft.io/nim-lang)

### LTS 1.0.x

Recommended for Nim applications targeted to the [LTS 1.0.x LTS branch](https://nim-lang.org/blog/2019/09/23/version-100-released.html).

`$ snap install nim-lang-lts-1`

[Snapcraft Store](https://snapcraft.io/nim-lang-lts-1)

![lts status](https://github.com/sirredbeard/nim_lang_snap/workflows/lts-1/badge.svg)

[![nim-lang-lts-1](https://snapcraft.io/nim-lang-lts-1/badge.svg)](https://snapcraft.io/nim-lang-lts-1)

### Nightly

Recommended for testing nightly builds of Nim. Likely contains bugs.

`$ snap install nim-lang-nightly`

[Snapcraft Store](https://snapcraft.io/nim-lang-nightly)

![nightly status](https://github.com/sirredbeard/nim_lang_snap/workflows/nightly/badge.svg)

[![nim-lang-nightly](https://snapcraft.io/nim-lang-nightly/badge.svg)](https://snapcraft.io/nim-lang-nightly)

### Documentation

HTML documentation and examples.

`$ snap install nim-lang-docs`

[Snapcraft Store](https://snapcraft.io/nim-lang-docs)

![nightly status](https://github.com/sirredbeard/nim_lang_snap/workflows/docs/badge.svg)

[![nim-lang-nightly](https://snapcraft.io/nim-lang-docs/badge.svg)](https://snapcraft.io/nim-lang-docs)

## Repository Files

### GitHub Actions workflows

/github/workflows

* [stable.yml](https://github.com/sirredbeard/nim_lang_snap/tree/master/.github/workflows) - Pushes Nim stable  snap to snap store.

  * Gets latest release using [lastversion](https://github.com/dvershinin/lastversion).

* [lts-1.yml](https://github.com/sirredbeard/nim_lang_snap/tree/master/.github/workflows) - Pushes Nim LTS 1 snap to snap store.

  * Gets latest 1.0.x build using curl, jq, grep, awk, and tr directly from the GitHub API.

* [nightly.yml](https://github.com/sirredbeard/nim_lang_snap/blob/master/.github/workflows/nightly.yml) - Pushes Nim nightly snap to snap store.

### Snap template files

/stable/snap/

* [snapcraft.yaml](https://github.com/sirredbeard/nim_lang_snap/blob/master/stable/snap/snapcraft.yaml) - Nim stable snap file template (updated by data from lastversion in stable.yml).

/lts-1/snap/

* [snapcraft.yaml](https://github.com/sirredbeard/nim_lang_snap/blob/master/lts-1/snap/snapcraft.yaml) - Nim lts 1 branch snap file (updated by data from GitHub API in lts-1.yml).

/nightly/snap/

* [snapcraft.yaml](https://github.com/sirredbeard/nim_lang_snap/blob/master/nightly/snap/snapcraft.yaml) - Nim nightly snap file,

## Advanced Usage

### Installation

`$ snap install nim-lang`

### Binaries

Once installed, Stable binaries can be called as:

```bash
nim-lang.nim
nim-lang.nimcsources
nim-lang.nimgdb
nim-lang.nimpretty
nim-lang.testament
nim-lang.nimble
nim-lang.nimfind
nim-lang.nimgrep
nim-lang.nimsuggest
```

Nightly will be nim-lang-night.* and LTS will be nim-lang-lts-1.*.

### Compilers

Snaps include the latest gcc and clang from the Core18 distribution.

### Aliases

You can use snap to create aliases for more common names:

```bash
sudo bash -c 'snap alias nim-lang.nim nim ;\
    snap alias nim-lang.nimcsources nimcsources ;\
    snap alias nim-lang.nimgdb nimgdb ;\
    snap alias nim-lang.nimpretty nimpretty ;\
     snap alias nim-lang.testament testament ;\
     snap alias nim-lang.nimble nimble ;\
     snap alias nim-lang.nimfind nimfind ;\
     snap alias nim-lang.nimgrep nimgrep ;\
     snap alias nim-lang.nimsuggest nimsuggest'
```
