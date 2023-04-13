# Usbview-VS10-XP
32-bit XP -compatible build of the Microsoft Usbview utility from the 2010 Windows DDK. A .gitignore file that is useful for using GIT with Visual Studio 10 is also included.

Usbview provides a tree view of the USB devices attached to the system and enables viewing the device properties. Later versions of Usbview are not compatible with XP.

The original version was configured for compiling using the toolset provided in the Windows DDK. This version has been configured to build natively on XP using Visual Studio 2010 Express.

The most straightforward way to create the Visual Studio project was to copy all the necessary source, header, and library files from the DDK to the build directory and add corresponding local references to the project. Attempting to just change the header and library directories to point to the files in the DDK rather than duplicating the files leads to build errors due to conflicts between DDK and Windows SDK files that have the same names, as well as DDK header files that are not set up to pre-compile under Visual Studio.

---

