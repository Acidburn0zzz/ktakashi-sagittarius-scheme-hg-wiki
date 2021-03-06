R6RS/R7RS Scheme system.

[![Build status](https://ci.appveyor.com/api/projects/status/8axfxf8dvr8pdtjk/branch/default?svg=true)](https://ci.appveyor.com/project/ktakashi/sagittarius-scheme/branch/default)
[![Build Status](https://travis-ci.org/ktakashi/sagittarius-scheme.svg?branch=master)](https://travis-ci.org/ktakashi/sagittarius-scheme)

## NEWS

- Sagittarius Scheme 0.9.6 has been released (Jun 5, 2019) [Release Notes](https://bitbucket.org/ktakashi/sagittarius-scheme/wiki/Release%20Note%200.9.6)
- Sagittarius Scheme 0.9.5 has been released (Dec 25, 2018) [Release Notes](https://bitbucket.org/ktakashi/sagittarius-scheme/wiki/Release%20Note%200.9.5)
- Sagittarius Scheme 0.9.4 has been released (Aug 31, 2018) [Release Notes](https://bitbucket.org/ktakashi/sagittarius-scheme/wiki/Release%20Note%200.9.4)
- Sagittarius Scheme 0.9.3 has been released (Jun 25, 2018) [Release Notes](https://bitbucket.org/ktakashi/sagittarius-scheme/wiki/Release%20Note%200.9.3)
- Sagittarius Scheme 0.9.2 has been released (May 19, 2018) [Release Notes](https://bitbucket.org/ktakashi/sagittarius-scheme/wiki/Release%20Note%200.9.2)
- Sagittarius Scheme 0.9.1 has been released (Mar 24, 2018) [Release Notes](https://bitbucket.org/ktakashi/sagittarius-scheme/wiki/Release%20Note%200.9.1)
- Sagittarius Scheme 0.9.0.1 has been released (Feb 17, 2018) [Release Notes](https://bitbucket.org/ktakashi/sagittarius-scheme/wiki/Release%20Note%200.9.0.1)
- Sagittarius Scheme 0.9.0 has been released (Feb 16, 2018) [Release Notes](https://bitbucket.org/ktakashi/sagittarius-scheme/wiki/Release%20Note%200.9.0)

[Old NEWS](https://bitbucket.org/ktakashi/sagittarius-scheme/wiki/Old%20NEWS)

## Features

- R6RS/R7RS Scheme implementation
- Builtin CLOS
- Common Lisp like reader macro
- Cryptographic libraries
- CL like keyword lambda syntax
- Builtin regular expression
    - Mostly works O(n)
- Replaceable reader
- Supporting R7RS-large RedEdition

## Supporting OS

- Windows
- Cygwin
- Linux
- Mac OS X
- Free BSD

To build Sagittarius from source archive, see [README.md](https://bitbucket.org/ktakashi/sagittarius-scheme/src)

## Document

- [Sagittarius Users' Reference](http://ktakashi.github.io/sagittarius-online-ref.html)
- [Sagittarius Users' Reference(One file)](http://ktakashi.github.io/sagittarius-ref.html)

## Build tips
If you are using Ubuntu 11.10 (which I tested from scratch), you need to install these packages.

`cmake`, `libgc-dev`, `zlib1g-dev` and `libffi-dev`.

`cmake` must be installed the other can be installed during building, however it is not managed by package manager so it might cause problems.

On Debian Linux, default `cmake` version is 2.8.2 and Sagittarius requires 2.8.4 so it might complain. If you got the problem, please change the version number to 2.8.2 in the `CMakeLists.txt`.

### For QNX environment
QNX environment has been supported (only x86 has been tested). To build Sagittarius on it, you need to use CMake tool chain like this;

```
#!shell
cmake -DCMAKE_TOOLCHAIN_FILE=cmake/Toolchain-QNX-8.0.0.cmake .
```

Then patch Boehm GC with following command before build;


```
#!shell
patch -p < cmake/patches/gc.qnx.patch
```

If you are building with out of tree, then adjust above commands.

## Building from repository

You may want to build the developing version of Sagittarius retrieved from the developing repository. It requires the latest release version of Sagittarius. Following steps describe how to do it:

1. Download the latest Sagittarius from download page and install it (if you already have installed the latest version this is not required).
2. Clone the repository.
3. Run `./dist.sh gen` in the cloned source directory.
4. Execute CMake described above section.

If you don't do this steps, you will get an error during CMake process something like the following:

```
CMake Error at src/CMakeLists.txt:102 (ADD_LIBRARY):
  Cannot find source file:

    regex_stub.c

  Tried extensions .c .C .c++ .cc .cpp .cxx .m .M .mm .h .hh .h++ .hm .hpp
  .hxx .in .txx
```

## Misc

- [External Links](https://bitbucket.org/ktakashi/sagittarius-scheme/wiki/External%20Links)
- [Google group](https://groups.google.com/forum/#!forum/sagittarius-scheme)
- [Google group for CI](https://groups.google.com/forum/#!forum/sagittarius-ci)

## Memos (for developers)

[Release process](https://bitbucket.org/ktakashi/sagittarius-scheme/wiki/Release%20process)
[TODOs](https://bitbucket.org/ktakashi/sagittarius-scheme/wiki/TODOs)