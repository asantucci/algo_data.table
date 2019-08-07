# algo_data.table
A place to work on documenting recent algorithmic improvements to data.table.

Motivated by [a tweet by Marianna Foos](https://twitter.com/MariannaFoos/status/1158113003465842688) referring to a [closed Stack Overflow question](https://stackoverflow.com/questions/23760229/what-are-the-algorithmic-programming-optimizations-that-make-data-table-fast).
Matt Dowle then issued an [RFH (request-for-help)](https://twitter.com/MattDowle/status/1158902738828374017).

Tips on where to start: https://github.com/Rdatatable/data.table/wiki/Presentations

## Brainstorming / no bad ideas / no ranking yet
#### truelength-clobber
*  find the commit in base R which initialized truelength to zero. That was instigated by Matt asking Simon Urbanek off list to make that change. Once that groundwork was in place, data.table could then start to rely on it given a dependency on that R release. (R's own misuse of truelength assumed to be positive sign only.)
* counting in truelength with sign bit on
* clobber now promoted to R but not on by default yet (another proposal needed to be accepted first).
* proposals for improvement to reduce complexity/risk
* benchmark is easy and compelling > 10x (which is why it made it to base R)
  
#### parallel ordering, finding the groups, high cardinality focus

#### factor vs character from parallelism's perspective

#### overcoming OpenMP's ordered clause non-parallel after ordered section in the GNU implementation

#### overcoming no #pragma omp cancel in older versions of OpenMP (to support them)

#### Literature review

#### The short-circuits from Terdiman and Herf, and how data.table applied them.

#### Benchmarks
* 1st and 2nd run times on big data (0.5GB, 5GB and 50GB), like https://h2oai.github.io/db-benchmark/.
* Call-overhead for iterating many small queries could be an aspect to write about too.
