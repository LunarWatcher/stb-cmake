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
set(STB_TAG "commit hash" CACHE STRING "" FORCE)
```
before the above code to use a different version.

It is strongly recommended to manually pick a hash to use to avoid accidental breakage from breaking updates. Because stb doesn't have any tags, this wrapper does not specify a version. It's up to the end-user to sanely pick tags.
