
# Snap of the Nim programming language

This repository is a set of GitHub Actions and Snapcraft snap templates that automates deployment of stable, LTS, and nightly builds of the [Nim programming language](https://nim-lang.org/) and [bundled tools](https://nim-lang.org/docs/tools.html).

* [Learn Nim](https://nim-lang.org/learn.html)
* Snapcraft: [Stable](https://snapcraft.io/nim-lang), [LTS 1](https://snapcraft.io/nim-lang-lts-1), [Nightly](https://snapcraft.io/nim-lang-nightly)

# Status

![](https://github.com/sirredbeard/nim_lang_snap/workflows/stable/badge.svg)

![](https://github.com/sirredbeard/nim_lang_snap/workflows/lts-1/badge.svg)

![](https://github.com/sirredbeard/nim_lang_snap/workflows/edge/badge.svg)

# Files

/stable/snap/

* snapcraft.yml - nim stable snap file template (updated by data from lastversion in stable.yaml)

/lts-1/snap/

* snapcraft.yml - nim lts 1 branch snap file (updated by data from lastversion in stable.yaml)

/edge/snap/

* snapcraft.yml - nim nightly snap file

/github/workflows

* stable.yml - pushes nim stable release snap to snap store
* lts-1.yml - pushes nim lts 1 branch snap to snap store
* edge.yml - pushes nim nightly snap to snap store
