OpenTTD built as a web application, with touchscreen interface.

https://pelya.github.io/openttd-touch-webapp

Build instructions:

Download and build Emscripten SDK, as described on their page: https://emscripten.org/

This build was compiled using Emscripten 3.0.0, but newer Emscripten version will probably work too.

Clone OpenTTD Android repo branch 1.11 (webapp code will eventually be merged into master):

    git clone https://github.com/pelya/openttd-android.git -b 12

Build it:

    cd openttd-android/os/emscripten
    ./emscripten-build.sh

You can use `./emscripten-build.sh debug` for debug builds, it compiles faster.

By default the script copies compiled files to `/var/www/html`
which is the default Apache2 web directory on Debian,
you can change the target directory using command:

    ./emscripten-build.sh release /path/to/your/html/files
