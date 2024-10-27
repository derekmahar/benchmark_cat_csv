# benchmark_cat_csv

Benchmarks the concatenation of a large quantity of CSV files using [Awk (The One True Awk)](https://github.com/onetrueawk/awk/), [csvtk](https://bioinf.shenwei.me/csvtk/), [GoAWK](https://github.com/benhoyt/goawk), [Miller](https://miller.readthedocs.io/), [qsv](https://github.com/jqnatividad/qsv), [xsv](https://github.com/BurntSushi/xsv), and a naive custom shell script.

## Dependencies

* All of the scripts require [GNU Bash](https://www.gnu.org/software/bash/).
* `cat_csv_awk` requires [awk](https://github.com/onetrueawk/awk/).
* `cat_csv_csvtk` requires [csvtk](https://bioinf.shenwei.me/csvtk/).
* `cat_csv_custom` requires GNU Bash [read](https://www.gnu.org/software/bash/manual/bash.html#index-read), GNU [cat](https://www.gnu.org/software/coreutils/manual/coreutils.html#cat-invocation), GNU [tail](https://www.gnu.org/software/coreutils/manual/coreutils.html#tail-invocation), and GNU [xargs](https://www.gnu.org/software/findutils/manual/html_mono/find.html#Invoking-xargs).
* `cat_csv_goawk` requires [goawk](https://github.com/benhoyt/goawk).
* `cat_csv_mlr` requires [mlr](https://miller.readthedocs.io/).
* `cat_csv_qsv` requires [qsv](https://github.com/jqnatividad/qsv).
* `cat_csv_xsv` requires [xsv](https://github.com/BurntSushi/xsv).
* `run_tests` requires [Hyperfine](https://github.com/sharkdp/hyperfine). 

## Generate Test Input CSV Files

Script `generate_test_data` creates the number of CSV files specified by argument FILE_COUNT, each containing a single row and column filled with the file number, in the directory specified by argument DATA_PATH.  For example:

```
$ ./generate_test_data
Usage: ./generate_test_data [DATA_PATH] [FILE_COUNT]
$ generate_test_data data 100000
$ find data -name '*.csv' | sort | head -n 5; echo "..."; find data -name '*.csv' | sort | tail -n 5
data/0000001.csv
data/0000002.csv
data/0000003.csv
data/0000004.csv
data/0000005.csv
...
data/0099996.csv
data/0099997.csv
data/0099998.csv
data/0099999.csv
data/0100000.csv
$ cat data/0000001.csv
Column
1
```
