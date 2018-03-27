# Nathan Ladd Work Log

## Tue Mar 27 2018
- Started work on new library, `benchmark-measure`
- Discovered a means of measuring elapsed time to the nanosecond, it should increase precision:
  * `Process.clock_gettime(Process::CLOCK_MONOTONIC, :nanosecond)`
- A decision needs to be made whether to depend on eventide libraries
  * Clock controls, dependency/subst-attr would both be used by this library
  * Leveraging them means that the benchmarking library couldn't measure them, since that would represent a circular dependency
  * As of now, I'm leaning towards avoiding library dependencies so that if we ever want to measure the lower level eventide libraries, we can do so without any setbacks

## Sat Mar 24 2018
- Began work on end-to-end benchmarking tooling
- Investigated benchmark-ips gem. Conclusions:
  * Interface is patterned after ruby's benchmark library
  * No readily available means to actuate benchmarking without using the top-level DSL
  * Therefore, is unsuitable for use as Eventide's standard benchmarking tool
