# Stb-cmake

This repo is a FetchContent wrapper for [stb](https://github.com/nothings/stb).

## Usage

```cmake
include(FetchContent)
FetchContent_Declare(stb
    GIT_REPOSITORY https://github.com/LunarWatcher/stb-cmake)
FetchContent_MakeAvailable(stb)
...
target_link_libraries(your-lib stb::stb)
```

By default, the master branch is specified as the git tag. To change it, use
```cmake
set(STB_TAG "v1.2.3 or a hash" CACHE STRING "" FORCE)
```
before the above code to use a different version.
