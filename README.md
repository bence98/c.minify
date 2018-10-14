# c.minify
A C code minifier

## What
This script reads all files passed as parameters and outputs to the standard output.

## Who
c.minify was written by Bence Csókás. You are free to use it, but I take no liability.

## How
Pre-processing steps:
* remove `#include`-s that have quotation marks and not angled brackets (ex. `#include "foo.h"` but not `include <stdio.h>`)
* redact all text between `//@minify hide` / `//@minify !hide`
* remove import guards. `#ifndef FOO_H` must be the first line. `#define FOO_H` may be anywhere in the file. `#endif //FOO_H` must have the `//`-comment part. No leading or tailing whitespace, comments etc. are allowed

## Why
Uni requires that we submit our solutions via copy-paste. A multi-module project would've been tedious to copy file-by-file, plus the references to the local headers would trigger a compiler error on their side. Import guards also make the submission unnecessarily longer.
