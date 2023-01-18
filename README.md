# aoe2maps

Random map scripts and preprocessing utilities.

## Directory Structure

This repository contains a variety of random map scripts, as well as Rust utilities for working with them.

The `scripts` directory contains the map scripts.
Each subdirectory represents a local map.
The files in each subdirectory are the source files used for building the maps for those mods.

The `includes` directory contains map scripts that the preprocess may copy into other scripts.

The `maps` directory contains the Rust executable used for running the preprocessor.
When working on maps, I run this executable every time a map file is saved using the [Run on Save](https://github.com/emeraldwalk/vscode-runonsave) extension.
The executable may also be run manually (e.g. using `cargo run`), which may be useful for debugging.

## Project Features

TODO
