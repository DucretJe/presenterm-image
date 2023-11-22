# Slides Image [![Push on Merge](https://github.com/DucretJe/slides-image/actions/workflows/build.yaml/badge.svg?branch=main)](https://github.com/DucretJe/slides-image/actions/workflows/build.yaml) [![💫 Super-Linter](https://github.com/DucretJe/slides-image/actions/workflows/linter.yaml/badge.svg)](https://github.com/DucretJe/slides-image/actions/workflows/linter.yaml)

![Cute Robot Demo](https://github.com/DucretJe/slides-image/assets/5384298/d2ad647c-f22a-437b-85e7-0da1c7ac2a01)


This repository builds a docker image of [slides](https://github.com/maaslalani/slides).
Thanks to maaslalani for the work <3

## How to

Create an alias:

```sh
alias slide='docker run --rm --name slides -v `pwd`:/workdir -w /workdir -it ghcr.io/ducretje/slides-image'
```

Run it:

```sh
slide example.md
```
