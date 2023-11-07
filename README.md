# benchmark_cat_csv

Benchmark the concatenation of a large quantity of CSV files using a naive custom shell script, [csvtk](https://bioinf.shenwei.me/csvtk/), [mlr](https://miller.readthedocs.io/), [qsv](https://github.com/jqnatividad/qsv), and [xsv](https://github.com/BurntSushi/xsv).

## Dependencies

* All of the scripts requires [GNU Bash](https://www.gnu.org/software/bash/).
* `cat_csv_csvtk` requires [csvtk](https://bioinf.shenwei.me/csvtk/).
* `cat_csv_custom` requires GNU Bash [read](https://www.gnu.org/software/bash/manual/bash.html#index-read), GNU [cat](https://www.gnu.org/software/coreutils/manual/coreutils.html#cat-invocation), GNU [tail](https://www.gnu.org/software/coreutils/manual/coreutils.html#tail-invocation), and GNU [xargs](https://www.gnu.org/software/findutils/manual/html_mono/find.html#Invoking-xargs).
* `cat_csv_mlr` requires [mlr](https://miller.readthedocs.io/).
* `cat_csv_qsv` requires [qsv]()https://github.com/jqnatividad/qsv).
* `cat_csv_xsv` requires [xsv](https://github.com/BurntSushi/xsv).
* `run_tests` requires [Hyperfine](https://github.com/sharkdp/hyperfine). 
