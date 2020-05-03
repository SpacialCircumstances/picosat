# PicoSAT

A version (965.1) of PicoSAT (based on source of version 965).
The following modifications were applied:

- Changed build system to CMake
- Made building on Windows possible
- Support running on Windows (without cygwin) by reimplementing Unix-dependent functionality
- Implemented runtime statistics

## Building

Building can be done by using CMake.

```sh
md build
cd build
cmake ../
cmake --build .
```

### Options

Common options for CMake, can be passed via `-DOptionName=Value`.

| Option Name | Description |
| --- | --- |
| CMAKE_INSTALL_PREFIX | Sets the directory for installing the build artifacts. |
| CMAKE_BUILD_TYPE | Default: Release. Sets the build configuration (applies optimization etc.) |
| SharedLib | Default: OFF. Builds a shared library instead of executables. |
| Logging | Default: OFF, Debug: ON. Enables additional logging. |
| Trace | Default: OFF, Debug: ON. Enables trace support. |
| Stats | Default: OFF, Debug: ON. Enables additional statistics. |

## License

The original PicoSAT source code was MIT-licensed, and so are the modifications.

See LICENSE.md for details.