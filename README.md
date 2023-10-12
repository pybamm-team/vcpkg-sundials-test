# vcpkg-sundials-test
compile a test sundials/klu code with vcpkg

Example configure step

```bash
mkdir build
cd build
cmake .. -DCMAKE_TOOLCHAIN_FILE=<vcpkg-root>/scripts/buildsystems/vcpkg.cmake
```

Example build step

```bash
cmake --build .
```
