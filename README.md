# spacescape
Spacescape, Copyright 2010 Alex Peterson, All Rights Reserved.

This file is part of Spacescape
For the latest info, see http://alexcpeterson.com/spacescape

"He determines the number of the stars and calls them each by name. "
Psalm 147:4 NIV

The MIT License

Copyright (c) 2010 Alex Peterson

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.

Thanks & attribution to FamFamFam for the icons!

http://www.famfamfam.com/lab/icons/silk/

## Build

Spacescape uses CMake and currently builds on Linux with Qt 5 and OGRE 14.

### Linux (Arch)

Install dependencies:

```bash
sudo pacman -S cmake gcc make pkgconf qt5-base qt5-x11extras ogre poco
```

Configure and build from the repository root:

```bash
cmake -S trunk -B build-linux -DCMAKE_PREFIX_PATH=/usr/lib/OGRE/cmake -DCMAKE_BUILD_TYPE=Release
cmake --build build-linux -j"$(nproc)"
```

The generated binaries are written into the source tree, not the build directory:

- `trunk/Spacescape/app/linux/bin/Spacescape.bin`
- `trunk/Spacescape/app/linux/bin/Plugin_Spacescape.so`

Run with:

```bash
QT_QPA_PLATFORM=xcb \
LD_LIBRARY_PATH="$(pwd)/trunk/Spacescape/app/linux/bin:$LD_LIBRARY_PATH" \
./trunk/Spacescape/app/linux/bin/Spacescape.bin
```

Notes:

- The current Linux port targets X11/XWayland.
- OGRE runtime plugins and codecs are loaded from the system install in `/usr/lib/OGRE`.
- If you are using another distro, install equivalent packages for CMake, Qt 5 Widgets/X11Extras, OGRE, Poco, and a C++ toolchain.
