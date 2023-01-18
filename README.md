# aoe2maps

Random map scripts and preprocessing utilities.

This project provides a convenient way to organize map mods while extending the scripting language with various macros and other features.
Features are implemented on an ad hoc basis as I come up with situations where I need useful features.
This repository should be considered as an experiment and not as a polished project.
In particular I make no attempt to construct a syntax tree of the rms files, but rather perform simple line-by-line processing that may break on files that do not follow the same formatting conventions that I do.

## Directory Structure

This repository contains a variety of random map scripts, as well as Rust utilities for working with them.

The `scripts` directory contains the map scripts.
Each subdirectory represents a local map.
The files in each subdirectory are the source files used for building the maps for those mods.

The `includes` directory contains map scripts that the preprocess may copy into other scripts.

The `xs` directory contains xs-scripts that map files may include.

The `maps` directory contains the Rust executable used for running the preprocessor.
When working on maps, I run this executable every time a map file is saved using the [Run on Save](https://github.com/emeraldwalk/vscode-runonsave) extension.
The executable may also be run manually (e.g. using `cargo run`), which may be useful for debugging.

To upload a mod, view the local mod with the in-game mod browser and click the button to open its local files.
Zip the `resources` directory and upload the zip file to the corresponding mod on the [ageofempires.com](https://www.ageofempires.com/) website.

## Project Features

- Uses `rms`, `rms2`, `png`, `dds`, `inc`, and `xs` files from the folders in this workspace to create map mods in the local mods folder.
- Minifies map scripts by stripping comments and removing excess whitespace.
- Gives macros for generating the locations of players lands with random placement, as circles, or as squares.
- Repeates code in indicated blocks (and supports nested repetition).
- Adds a macro that is equivalent to `set_place_for_every_player` while allowing for lands to be assigned directly to players using `land_id`, so that different objects and actor areas may be placed for each player.
- Provides a debugging tool for lifing `rnd` statements to the map preamble to ensure removing code from a map does not change the random generation of code preceeding it.
- Allows named actor areas in addition to numeric actor areas.
- Introduces the `#BREAK` macro to stop generating any code from the point where that macro appears.
