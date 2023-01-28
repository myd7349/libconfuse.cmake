libconfuse.cmake
---------------

`CMakeLists.txt` for [```libconfuse```](https://github.com/martinh/libconfuse)

Test with [<kbd>2f7d120</kbd>](https://github.com/martinh/libconfuse/tree/2f7d120e170351cf424845ed27a532cce443247d).


Build & Install
---------------

**using conan (better)**

mkdir my_genimage && cd my_genimage

_install conan_
//pip uninstall conan
pip install conan --pre --user
pip install conan --user --upgrade

_Download test example_
git clone https://github.com/libconfuse/libconfuse

//put to original libconfuse/ folder files CMakeLists.txt and config.h.in (replace) and conanfile.txt

cd libconfuse/

rm -Rf build/

conan profile detect --force

conan install . --output-folder=build --build=missing

cd build

cmake .. -DCMAKE_TOOLCHAIN_FILE=conan_toolchain.cmake -DCMAKE_BUILD_TYPE=Release

cmake --build .

sudo checkinstall --pkgname="libconfuse" --nodoc --pkgversion="1" --default

//to remove use: dpkg -r build-libconfuse

**using cmake only**

mkdir my_genimage && cd my_genimage

mkdir build-libconfuse

git clone https://github.com/libconfuse/libconfuse

//put to original libconfuse/ folder files CMakeLists.txt and config.h.in (replace)

cd libconfuse/

cmake -S libconfuse/ -B build_libconfuse/ -DCMAKE_BUILD_TYPE=Release

cmake --build build_libconfuse/ --parallel 

cd build_libconfuse/

sudo checkinstall

//to remove use: dpkg -r build-libconfuse

License
---------------


MIT
