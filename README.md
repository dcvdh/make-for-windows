# GNU Make for Windows

A mirror of [GNU Make](https://git.savannah.gnu.org/cgit/make.git) with some GitHub workflows added to produce binaries.

It's all automated and nothing's been changed other than adding this readme and the [workflow files](.github/workflows). GitHub's version of GCC produces binaries which depend on Microsoft's UCRT instead of the older and more ubiquitous MSVCRT, but you probably already have that from Windows Update.

You can get `make.exe` from releases. Here's the latest version:

https://github.com/dcvdh/make-for-windows/releases/latest

## Do It Yourself

1. Get a MinGW toolchain from [winlibs.com](https://winlibs.com) or something. You can also use Visual Studio apparently.
3. Reflect on the fact that the toolchain already includes `make` as `mingw32-make`.
4. Get the latest tarball from a [gnu.org mirror](https://ftpmirror.gnu.org/gnu/make), or clone either the [original repo](https://git.savannah.gnu.org/git/make.git) or this one.
5. **[unnecessary if you're working from the tarball]** Run `bootstrap.bat`. You will need [sed](https://www.gnu.org/software/sed) and [curl](https://curl.se/).
6. Run `build_w32.bat gcc`, which will produce `GccRel/gnumake.exe`.
7. **[optional]** Strip debugging symbols and rename it with `strip --strip-unneeded -o make.exe GccRel/gnumake.exe`
