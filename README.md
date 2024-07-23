# Linux GNU Parallel

This repository demonstrates the usage of GNU parallel.
## Installation

```bash
sudo apt install parallel
```

## Usage

`parallel [options] [command [arguments]] ( ::: arguments | :::+ arguments | :::: argfile(s) | ::::+ argfile(s) ) ...`
```bash
# Basics
parallel echo ::: {1..10}
```

## Reference
- https://omgenomics.com/blog/parallel
- https://www.gnu.org/software/parallel/
