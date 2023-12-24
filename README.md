# Cloud Native Buildpack for C and C++ with CMake
[![Build and push](https://github.com/binary-craft/cmakepack/actions/workflows/build-and-push.yml/badge.svg)](https://github.com/binary-craft/cmakepack/actions/workflows/build-and-push.yml)

## About
This project is used to create a Cloud Native Buildpack for CMake that can be used for native applications such as C and C++.

## Using the buildpack
The published buildpack will be made available on Docker hub. This project contains the source and is used to build it.

See [Docker hub](https://hub.docker.com/r/bincraft/cmakepack).

```docker pull bincraft/cmakepack:<version>```

## Building images with the buildpack
There are two options for using this buildpack:
- Using a builder image that includes it, for example [binary-craft/hera-builder](https://github.com/binary-craft/hera-builder).
- Adding it directly on the commandline, this can be done like follows:

```pack build my-app -b bincraft/cmakepack:<version>```

### Arguments to pass to the build script
The buildpack has some environment variables / arguments that can be set to customise the build.

| Variable                | Description                                        | Default value     |
|-------------------------|----------------------------------------------------|-------------------|
| BP_CMAKE_ARGS           | Arguments to pass to CMake                         | -                 |
| BP_CMAKE_GENERATOR_ARGS | Arguments to pass to the generator (Make or Ninja) | -                 |

### Generator choice
CMake has a default but this can be overriden by passing the appropriate commandline argument to CMake. See the [CMake documentation](https://cmake.org/cmake/help/latest/manual/cmake.1.html) for more information.
This buildpack supports Make and Ninja generators.

### Compiler choice
CMake will choose a default compiler depending on the environment. At the present time it is not yet possible to override this.

## Maintaining
This project is aimed to have a straightforward maintenance by using all relevant automation that we can.

## Contributing
This project is open for any contributions that you might have. Bugfixes and feature enhancements are very welcome.

If you'd like to implement a major new feature or change some fundamentals of the project please send me a DM to discuss.

## License
This project is licensed under the Apache License, Version 2.0. See [LICENSE](LICENSE) for the full license text.