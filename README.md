OpenTTD built as a web application, with touchscreen improvements.

Build instructions:

Download and build Emscripten SDK, as described on their page: https://emscripten.org/

This build was compiled using Emscripten 2.0.15, but newer Emscripten version will probably work too.

Clone OpenTTD Android repo branch 1.11 (webapp code will eventually be merged into master):

    git clone https://github.com/pelya/openttd-android.git -b 1.11

Patch Emscripten to add liblzma support:

    cd emsdk/upstream/emscripten
    patch -p1 < ../../../openttd-android/os/emscripten/emsdk-liblzma.patch

Build it:

    cd openttd-android/os/emscripten
    ./emscripten-build.sh

You can use `./emscripten-build.sh debug` for debug builds, it compiles faster.

By default the script copies compiled files to `/var/www/html`
which is the default Apache2 web directory on Debian,
you can change the target directory using command:

    ./emscripten-build.sh release /path/to/your/html/files
