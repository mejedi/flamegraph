# flamegraph
Convenience wrapper for https://github.com/brendangregg/FlameGraph

Invoke `perf record`, render flame graph, upload resulting SVG and print public URI.

```
$ sudo flamegraph -- /tmp/usr/local/bin/tarantool benchmark.lua
RPS: 469529
[ perf record: Woken up 1 times to write data ]
[ perf record: Captured and wrote 0.048 MB /tmp/tmpMOlrGw (~2081 samples) ]
Processing samples...
Failed to open /tmp/perf-16549.map, continuing without symbols
https://gist.githack.com/anonymous/a1726139261e5a0b0df39075d39adc85/raw/a440785aa72175d535c5e564aec9b7d2482d891e/g.svg
```
