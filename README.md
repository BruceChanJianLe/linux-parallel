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
parallel echo {} '>' file{}.txt ::: {1..10}
# Every combination
parallel echo {2}{1} '>' file_{2}{1}.txt ::: {1..10} ::: a b c
# file_a10.txt  file_a2.txt  file_a4.txt  file_a6.txt  file_a8.txt  file_b10.txt  file_b2.txt  file_b4.txt  file_b6.txt  file_b8.txt  file_c10.txt  file_c2.txt  file_c4.txt  file_c6.txt  file_c8.txt
# file_a1.txt   file_a3.txt  file_a5.txt  file_a7.txt  file_a9.txt  file_b1.txt   file_b3.txt  file_b5.txt  file_b7.txt  file_b9.txt  file_c1.txt   file_c3.txt  file_c5.txt  file_c7.txt  file_c9.txt
# Link inputs
parallel --link echo {2}{1} '>' file_{2}{1}.txt ::: {1..10} ::: a b c
# file_a1.txt  file_b2.txt file_c3.txt file_a4.txt  file_b5.txt file_c6.txt file_a7.txt file_b8.txt file_c9.txt file_a10.txt 
```

For file arguments use four colons `::::`, otherwise three colons `:::`.

## Reference
- https://omgenomics.com/blog/parallel
- https://www.gnu.org/software/parallel/
