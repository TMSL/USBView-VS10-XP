# Usbview-VS10-XP
This is a 32-bit XP -compatible version of the Microsoft Usbview utility from the 2010 Windows DDK that has been refactored to build using Visual Studio 2010 Express. A .gitignore file that is useful for using GIT with Visual Studio 10 is also included in the source files.

Usbview provides a tree view of all the USB devices attached to the system and their properties. It's often used when developing USB programs or as an aid to debugging whether devices are installed and operating correctly. Later versions of Usbview are not compatible with XP.

The original version of Usbview was set up for compiling using "make" files and the toolset provided in the Windows DDK. This version has been reconfigured to build natively on XP using Visual Studio 2010 Express without installing the DDK. In addition to Visual Studio 2010 building requires .NET 4.0 to have been installed.

The most straightforward way to create the Visual Studio -compatible project was to copy all the necessary source, header, and library files from the DDK to the build directory and add corresponding local references to the project. Attempting to just change the header and library directories to point to the files in the DDK rather than duplicating the files leads to build errors due to conflicts between DDK and Windows SDK files that have the same names, as well as DDK header files that are not set up to pre-compile under Visual Studio.

---
