    Title: Setup Racket and package management
    Date: 2019-01-20T16:01:47
    Tags: Racket, setup

Setup and write the first "hello world" program, to a daily work ready "deploy" with package management.

<!-- more -->

## Installing
Install Racket by download binary from Racket [https://racket-lang.org/](https://racket-lang.org/).
The current version is 7.1 (October 2018), the binary is 109MB, it is a bit
heavy but included also document, an IDE called DrRacket (which of course written
in Racket), and ton of useful libraries. Just to name some essential packages:

- json  `(require json)`
- http client `(require net/http-client)`
- command argument parser `(TODO)`
- string formatting, file I/O
- all functions to work with file/directories
- a HTTP server
- a GUI framework if you ever need.

## Running
- `racket` command is an interpreter, can be put on top of a script
`#!/usr/bin/env racket` or using interactively.
- DrRacket - a GUI IDE would be the daily tool for developing. It's not a fancy
IDE with all mega features but simple and nice. Support auto completing via
`COMMAND /` (MacOS) or `Ctrl /` if you on Windows/Linux. It supports multiple
tabs. DrRacket have default 2 panel, top one called `Definitions` where you put
code. Bottom one runs `racket` interpreter. A run button click to run the
code (Command R/Ctrl R). It may use ~ 1GB RAM, not tiny, but maybe less than
your browser.
- `raco` command is everything manager for Racket. Run command `raco doc` to
open local document. `raco pkg install packagename` to install a package.

DrRacket and `raco` is really good selling point for Racket, it's uesr-friendly,
just click and run, no error, searching, ...

A Racket 7.1 script takes minimum 36MB to run. A Python3.6 script takes minimum
8MB to run. Note that `Racket 7.1` is often faster than `Python3`, see
[https://benchmarksgame-team.pages.debian.net/benchmarksgame/faster/racket-python3.html]()

## Installing packages

`raco` can install package from **Planet package** or from git

```sh
$ raco pkg install drracket-vim-tool
Resolving "drracket-vim-tool" via https://download.racket-lang.org/releases/7.1/catalog/
Resolving "drracket-vim-tool" via https://pkgs.racket-lang.org
Downloading repository git://github.com/takikawa/drracket-vim-tool
raco setup: version: 7.1
raco setup: platform: x86_64-macosx [3m]
raco setup: installation name: 7.1
raco setup: variants: 3m
raco setup: main collects: /Applications/Racket v7.1/collects
raco setup: collects paths:
raco setup:   /Users/viethung.nguyen/Library/Racket/7.1/collects
raco setup:   /Applications/Racket v7.1/collects
raco setup: main pkgs: /Applications/Racket v7.1/share/pkgs
raco setup: pkgs paths:
raco setup:   /Applications/Racket v7.1/share/pkgs
raco setup:   /Users/viethung.nguyen/Library/Racket/7.1/pkgs
raco setup: links files:
raco setup:   /Applications/Racket v7.1/share/links.rktd
raco setup:   /Users/viethung.nguyen/Library/Racket/7.1/links.rktd
raco setup: main docs: /Applications/Racket v7.1/doc
raco setup: --- updating info-domain tables ---
raco setup: updating: /Users/viethung.nguyen/Library/Racket/7.1/share/info-cache.rktd
raco setup: --- pre-installing collections ---
raco setup: --- installing foreign libraries ---
raco setup: --- installing shared files ---
raco setup: --- compiling collections ---
raco setup: --- parallel build using 8 jobs ---
raco setup: 7 making: <pkgs>/drracket-vim-tool
raco setup: 7 making: <pkgs>/drracket-vim-tool/private
raco setup: 7 making: <pkgs>/drracket-vim-tool/tests
raco setup: --- creating launchers ---
raco setup: --- installing man pages ---
raco setup: --- building documentation ---
raco setup: --- installing collections ---
raco setup: --- post-installing collections ---
```

That package add vi-binding support in DrRacket, choose `Edit -> Vim Mode`
and enjoy.

Install `frog` for a static blog generator

```sh
$ raco pkg install frog
Resolving "frog" via https://download.racket-lang.org/releases/7.1/catalog/
Resolving "frog" via https://pkgs.racket-lang.org
Downloading repository git://github.com/greghendershott/frog
...
```

Then creates new blog via

```sh
$ raco frog
Frog 0.29
raco frog [ <option> ... ]
 where <option> is one of
  --doc :
    Browse full documentation for Frog.
  --init :
    Initialize current directory as a new Frog project, creating
    default files as a starting point.
...
```

Or from `git`:

```sh
$ raco pkg install https://github.com/stchang/redis
...
```
