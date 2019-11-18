# Linaro-Website-full

## Introduction

This is a __test__ repo, not intended for general use!

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

__Note__: the submodules are configured to track matching branches when possible. If that is not possible, the latest known good `tag` is used. If that is not possible, the `master` branch (tracking `HEAD`) is used.

## Usage

Please read an introduction to `git submodules` before using.

## Cloning

To get all source code, please add `--recurse-submodules` to your `git clone` options. If you only want to work on a subset of the available submodules, you should `git clone` this repository without using `--recurse-submodules`, then add the specific submodule(s) by appending them to `git submodule update --init --recursive`.

### Cloning example code

```bash
user@host:~/temp$ git clone https://github.com/morancj/linaro-website-full.git
Cloning into 'linaro-website-full'...
remote: Enumerating objects: 24, done.
remote: Counting objects: 100% (24/24), done.
remote: Compressing objects: 100% (17/17), done.
remote: Total 24 (delta 7), reused 11 (delta 3), pack-reused 0
Unpacking objects: 100% (24/24), done.
user@host:~/temp$ cd linaro-website-full/
user@host:~/temp/linaro-website-full$ du -hs ./
107K    ./
user@host:~/temp/linaro-website-full$ git submodule update --init --recursive jekyll-build-container jekyll-build-container-wiki jekyll-link-checker
Submodule 'jekyll-build-container' (https://github.com/linaro-its/jekyll-build-container.git) registered for path 'jekyll-build-container'
Submodule 'jekyll-build-container-wiki' (https://github.com/linaro-its/jekyll-build-container.wiki.git) registered for path 'jekyll-build-container-wiki'
Submodule 'jekyll-link-checker' (https://github.com/linaro-its/jekyll-link-checker.git) registered for path 'jekyll-link-checker'
Cloning into '/home/user/temp/linaro-website-full/jekyll-build-container'...
Cloning into '/home/user/temp/linaro-website-full/jekyll-build-container-wiki'...
Cloning into '/home/user/temp/linaro-website-full/jekyll-link-checker'...
Submodule path 'jekyll-build-container': checked out '272aa1d471786aef7118b6c5770e292b0ace963b'
Submodule path 'jekyll-build-container-wiki': checked out '67ac5c8d05261fc6f02fb6a8c6acf85edb6e4a98'
Submodule path 'jekyll-link-checker': checked out '0756477045025f9cda0400a5e157a39a5c15c254'
user@host:~/temp/linaro-website-full$ du -hs ./
829K    ./
user@host:~/temp/linaro-website-full$
```

You can `pull` __all__ submodules with `git submodule update --init --recursive`. This will be as slow as cloning each repository individually, but will ensure you have all related submodules locally. This may be useful if you're working across code bases, or offline.

Example:

```bash
user@host:~/temp/linaro-website-full$ git submodule update --recursive
Submodule 'jekyll-link-checker-wiki' (https://github.com/linaro-its/jekyll-link-checker.wiki.git) registered for path 'jekyll-link-checker-wiki'
Submodule 'jumbo-jekyll-theme' (https://github.com/linaro-marketing/jumbo-jekyll-theme.git) registered for path 'jumbo-jekyll-theme'
Submodule 'linaro-website-source' (https://github.com/Linaro/website.git) registered for path 'linaro-website-source'
Cloning into '/home/user/temp/linaro-website-full/jekyll-link-checker-wiki'...
Cloning into '/home/user/temp/linaro-website-full/jumbo-jekyll-theme'...
Cloning into '/home/user/temp/linaro-website-full/linaro-website-source'...
Submodule path 'jekyll-link-checker-wiki': checked out '98eebe4c45f8eb586fe68ca9c8796f5df7fc0c9e'
Submodule path 'jumbo-jekyll-theme': checked out '2b6403e8bad26a55d733d1d01e5e533f5aacf821'
Submodule path 'linaro-website-source': checked out '032aaf6bc8afdbf7b709717266a3cd33d90517fd'
user@host:~/temp/linaro-website-full$ du -hs
891M    ./
user@host:~/temp/linaro-website-full$

```

Please __note__ how this repository grows with the number of submodules cloned.

## Submodule status

Show the configured submodules and their tracking:

```bash
user@host:~/temp/linaro-website-full$ git submodule 272aa1d471786aef7118b6c5770e292b0ace963b jekyll-build-container (heads/develop)
67ac5c8d05261fc6f02fb6a8c6acf85edb6e4a98 jekyll-build-container-wiki (heads/master)
0756477045025f9cda0400a5e157a39a5c15c254 jekyll-link-checker (heads/master)
98eebe4c45f8eb586fe68ca9c8796f5df7fc0c9e jekyll-link-checker-wiki (heads/master)
2b6403e8bad26a55d733d1d01e5e533f5aacf821 jumbo-jekyll-theme (5.6.0)
032aaf6bc8afdbf7b709717266a3cd33d90517fd linaro-website-source (heads/develop)
user@host:~/temp/linaro-website-full$ git pull --recurse-submodules
Fetching submodule jekyll-build-container
From https://github.com/linaro-its/jekyll-build-container
   04e570d..1a3ae49  pcolmer-repo-detection-bugfix -> origin/pcolmer-repo-detection-bugfix
Fetching submodule jekyll-build-container-wiki
Fetching submodule jekyll-link-checker
Fetching submodule jekyll-link-checker-wiki
Fetching submodule jumbo-jekyll-theme
Fetching submodule linaro-website-source
Already up to date.
user@host:~/temp/linaro-website-full$ ```
