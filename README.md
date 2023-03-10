# Dev Container Feature: jemalloc

A feature for a dev container that installs the jemalloc allocator library.
It's meant as an addition to the swift 5.7 (and later) images to install the library to support
using [package-benchmark](https://github.com/ordo-one/package-benchmark) to benchmark swift code,
and capturing memory allocation data in those benchmarks.

Example using the feature:

```jsonc
{
    "image": "swift:5.7",
    "features": {
        "ghcr.io/heckj/jemalloc/jemalloc:1": {
        }
    }
}
```

## Testing

using the devcontainer CLI:

```
devcontainer features test --skip-autogenerated f jemalloc -i ubuntu:latest .
devcontainer features test --skip-scenarios -f jemalloc -i ubuntu:latest .
devcontainer features test --global-scenarios-only -i ubuntu:latest .
```

