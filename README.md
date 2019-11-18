# Linaro-Website-full

## Introduction

This is a _test_ repo, not intended for general use!

## Prerequisites

* Git client
* Outgoing HTTPS (for `git pull`)
* Outgoing SSH (for `git push`)

## Submodules

Source code for:

* [Linaro website](https://www.linaro.org/)
* Dockerised Jekyll build
* Link checker
* Jekyll theme
* Wiki documentation for the above, when available.

_Note:_ the submodules are configured to track matching branches when possible. If that is not possible, the latest known good `tag` is used. If that is not possible, the `master` branch (tracking `HEAD`) is used.

## Usage

Please read an introduction to `git submodules` before using.

```bash
➜ git submodule 272aa1d471786aef7118b6c5770e292b0ace963b jekyll-build-container (heads/develop)
67ac5c8d05261fc6f02fb6a8c6acf85edb6e4a98 jekyll-build-container-wiki (heads/master)
0756477045025f9cda0400a5e157a39a5c15c254 jekyll-link-checker (heads/master)
98eebe4c45f8eb586fe68ca9c8796f5df7fc0c9e jekyll-link-checker-wiki (heads/master)
2b6403e8bad26a55d733d1d01e5e533f5aacf821 jumbo-jekyll-theme (5.6.0)
032aaf6bc8afdbf7b709717266a3cd33d90517fd linaro-website-source (heads/develop)
➜ git pull --recurse-submodules
Fetching submodule jekyll-build-container
From https://github.com/linaro-its/jekyll-build-container
   04e570d..1a3ae49  pcolmer-repo-detection-bugfix -> origin/pcolmer-repo-detection-bugfix
Fetching submodule jekyll-build-container-wiki
Fetching submodule jekyll-link-checker
Fetching submodule jekyll-link-checker-wiki
Fetching submodule jumbo-jekyll-theme
Fetching submodule linaro-website-source
Already up to date.
➜
```
