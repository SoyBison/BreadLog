---
title: BreadLog
author: Coen D. Needell (soybison)
date: 2022-10-02
---

# BreadLog

This is a place to store YAMLs about my bread-making adventures. Later I'll be making a series of scripts and tools for managing it.

## Rules:

1. All data must be stored as a YAML.
2. Every YAML must have a date, and a title.
3. Every data object will have a class, which is inferred from the directory name.
4. Each Directory should contain a class definition and will inherit rules in the directory structure.

## Class Definition

Each definition should contain a "pretty name", which has no restrictions, but in-code will be referred to by it's directory name (with directory-name restrictions).
The definition should tell us what fields are required by that class, and what fields are optional.
The "notes", field will be reserved by the system, and will always be optional. The "date" field is reserved and is always required. Programs should be written using some sort of permissive date parser, but ISO 8601 is preferred.

Vim shortcut:
`:r ! echo "date: $(date --iso)"`
or for more specificity
`:r ! echo "date: $(date --iso=seconds)"`

## Recipe Definition

A recipe should be written like a log. Each entry must contain a date and any defined required fields. Each entry may contain notes.
Log streams in YAML are written as a series of YAML files seperated by `---\n`.
Most recipes will have only one log in their stream. Sourdough starters are a notable counter-example. Recipes in the log format should begin the stream with metadata.
All measurements should be listed as an integer or a float in grams.[^1]

## Data Formats

Dates should be in iso format. They can be as specific as you want.
Time intervals should be recorded in the format "WdXhYmZs", and may also be exactly as specific as you want.[^2]
Bare numbers are assumed to be in grams or Fahrenheit.


[^1]: Volume measurements are allowed, but should be stored as a string and tools are not guaranteed to support them properly.
[^2]: No nanoseconds I know you're not that good of a baker.
