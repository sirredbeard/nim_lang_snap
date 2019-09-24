
# Snap of the Nim programming language

This repository is a set of GitHub Actions and Snapcraft snap templates that automates deployment of stable, LTS, and nightly builds of the [Nim programming language](https://nim-lang.org/) and [bundled tools](https://nim-lang.org/docs/tools.html).

Nim is a compiled, garbage-collected systems programming language with a design that focuses on efficiency, expressiveness, and elegance.

* [Learn Nim](https://nim-lang.org/learn.html)

## Branches

### Stable

Recommended for most users

`$ snap install nim-lang`

[Snapcraft Store](https://snapcraft.io/nim-lang)

![stable status](https://github.com/sirredbeard/nim_lang_snap/workflows/stable/badge.svg)

### LTS 1.0.x Branch

Recommended for Nim applications targeted to the LTS 1.0.x LTS branch

`$ snap install nim-lang-lts-1`

[Snapcraft Store](https://snapcraft.io/nim-lang-lts-1)

![lts status](https://github.com/sirredbeard/nim_lang_snap/workflows/lts-1/badge.svg)

### Nightly

Recommended for testing nightly builds of Nim. Likely contains bugs

`$ snap install nim-lang-nightly`

[Snapcraft Store](https://snapcraft.io/nim-lang-nightly)

![nightly status](https://github.com/sirredbeard/nim_lang_snap/workflows/nightly/badge.svg)

## Files

### Snap Templates

/stable/snap/

* snapcraft.yml - nim stable snap file template (updated by data from lastversion in stable.yml)

/lts-1/snap/

* snapcraft.yml - nim lts 1 branch snap file (updated by data from GitHub API in lts-1.yml)

/nightly/snap/

* snapcraft.yml - nim nightly snap file

### GitHub Actions

/github/workflows

* stable.yml - pushes nim stable release snap to snap store

  * gets latest release using [lastversion](https://github.com/dvershinin/lastversion)

* lts-1.yml - pushes nim lts 1 branch snap to snap store

  * gets latest 1.0.x using curl, jq, and awk directly from the GitHub API

* nightly.yml - pushes nim nightly snap to snap store

  * gets latest Nim code directly from the development branch of the nim GitHub repository
