# Nathan Ladd Work Log

## Sat Mar 24 2018
- Began work on end-to-end benchmarking tooling
- Investigated benchmark-ips gem. Conclusions:
  * Interface is patterned after ruby's benchmark library
  * No readily available means to actuate benchmarking without using the top-level DSL
  * Therefore, is unsuitable for use as Eventide's standard benchmarking tool

## Tue Mar 27 2018
- Started work on new library, `benchmark-measure`
- Discovered a means of measuring elapsed time to the nanosecond, it should increase precision:
  * `Process.clock_gettime(Process::CLOCK_MONOTONIC, :nanosecond)`
