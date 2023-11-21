# Slides Image

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
