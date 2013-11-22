Megasource is a CMake-buildable collection of all [LÖVE][love2d] dependencies.

It currently only works on Windows, but will also work on OSX. It could certainly also work on Linux, but good package managers makes megasource less relevant there.

Prerequisites
-------------

 - Windows.
 - Visual Studio 2012 or 2013 (Express).
 - [DirectX SDK][dxsdk] (required for SDL2).
 - [CMake 2.8.11][cmake].
 - [NSIS][nsis] if you want to build the LÖVE installer.

Building
--------

To build just the dependecies:

	$ hg clone https://bitbucket.org/rude/megasource megasource
	$ cd megasource
	$ cmake -G "Visual Studio 11" -H. -Bbuild
	$ cmake --build build --target megatest --config Release

... or you can of course open the solution file in Visual Studio and build from there instead of invoking cmake --build.

If you want to build [LÖVE][love2d], clone LÖVE into the *libs* folder. Megasource will automatically look for it there. E.g.:

	$ hg clone https://bitbucket.org/rude/megasource megasource
	$ cd megasource
	$ hg clone https://bitbucket.org/rude/love libs/love
	$ cmake -G "Visual Studio 11" -H. -Bbuild
	$ cmake --build build --target love --config Release

The binaries can be found in *build/love/Release*.

If you want to build the installer, replace the previous build command with:

    $ cmake --build build --target PACKAGE --config Release

A zip with the binaries and the installer will appear in *build*.

[love2d]: http://love2d.org
[dxsdk]: http://www.microsoft.com/en-us/download/details.aspx?id=6812
[cmake]: http://www.cmake.org/
[nsis]: http://nsis.sourceforge.net
