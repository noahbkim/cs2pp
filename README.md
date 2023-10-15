# cs2pp
A framework for parsing Counter-Strike 2 demos.

# Shallow Submodules

https://stackoverflow.com/questions/2144406/how-to-make-shallow-git-submodules/17692710#17692710

```bash
# add shallow submodule
git submodule add --depth 1 <repo-url> <path>
git config -f .gitmodules submodule.<path>.shallow true

# later unshallow
git config -f .gitmodules submodule.<path>.shallow false
git submodule update <path>
```

## CMake Configuration

```
# Options
-DCMAKE_TOOLCHAIN_FILE=conan-build-debug\conan_toolchain.cmake

# Settings
Toolchain: Visual Studio
```

## Conan

```bash
# You will need a separate conan profile for release and debug builds
$ conan profile detect               # Automatically names it `default`
$ conan profile detect --name debug  # Edit this such that `build_type=Debug`

# Install everything
$ conan install . --build missing --output-folder conan-build-release
$ conan install . --build missing --output-folder conan-build-debug --profile debug
```
