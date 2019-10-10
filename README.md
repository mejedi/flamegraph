# flamegraph
Convenience wrapper for https://github.com/brendangregg/FlameGraph

Invoke `perf record`, render flame graph, upload resulting SVG and print public URI.

```
$ sudo -E flamegraph -p 4376 -- sleep 20
[ perf record: Woken up 242 times to write data ]
[ perf record: Captured and wrote 61.760 MB /tmp/tmpXk8vyl (961610 samples) ]
Processing samples...
https://gist.githack.com/mejedi/548339821df0d32ddc5e2eeddf670eaf/raw/065200c89de330b520204acbfa02e02e146b9393/g.svg
```

## Installation
```
git clone --recurse-submodules https://github.com/mejedi/flamegraph.git flamegraph.git
```

Consider doing `sudo ln -s $(pwd)/flamegraph.git/flamegraph /usr/bin/flamegraph` for convenience.
Further text assumes this step was performed.

## Usage
The tool forwards arguments to `perf-record` verbatim.

Examles:

 * profile `./foo` command: `flamegraph ./foo`

 * profile existing process with pid 4376 for 20 seconds: `flamegraph -p 4376 sleep 20`

## API Token

In order to produce a public URI, the tool uploads resulting flamegraph as a Gist to GitHub.
This action requires an API token; pass via `FLAMEGRAPH_API_TOKEN` environment variable.
