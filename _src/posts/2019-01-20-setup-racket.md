    Title: Setup Racket
    Date: 2019-01-20T16:01:47
    Tags: Racket, setup

Setup and write the first "hello world" program, to a daily work ready "deploy".

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
8MB to run.

