# USBView-VS10-XP
This is a 32-bit XP -compatible version of the Microsoft USBView sample utility from the 2010 Windows DDK that has been refactored to build using Visual Studio 2010 Express. A .gitignore file that is useful for using GIT with Visual Studio 10 is also included in the source files.

USBView provides a tree view of all the USB devices attached to the system and their properties. It's often used when developing software or utilities that accessing USB devices or as an aid to debugging whether devices are installed and operating correctly. Later versions of USBView are not compatible with XP. 

##Why
I did this project as retro-computing hobby playing around to check out how difficult it would be to create basic native apps on XP compared to using the latest versions of Visual Studio in 2023. I decided to rebuild USBView because it's a handy utility for USB developers that I often use when checking out attached USB devices when developing or debugging software for microcontroller projects that uses USB. While I could have downloaded an older version of USBView.exe that works on XP it was more interesting to build it from source.

The original USBView sample application was set up for compiling using "make" files and the toolset provided in the Windows DDK (Driver Development Kit). The dependence on the DDK environment somewhat impedes the ability to use the USBView sample as a learning tool for understanding how to use the Windows APIs for accessing USB devices. Thus, this version has been reconfigured to build natively on XP using Visual Studio 2010 Express with .NET 4.0 without needing to install or learn how to use the DDK. 

##How
Development was done using a Windows 32-bit XP SP3 virtual machine running on VirtualBox. Building this project requires Visual Studio 10 Express and .NET Framework 4.0. (As of this writing Visual Studio 10 Express and .NET Framework 4.0 are still available for download from Microsoft.) Once this environment is present and functional, it should only be necessary to download the project from GitHub, extract it, and add it to Visual Studio as an existing solution or project.

#Extra
The most straightforward way to create the 'standalone' Visual Studio -compatible project was to not just copy the source files for the sample, but also copy all the required external header, and library files from the DDK to the build directory and add corresponding local references to the project. (Just changing the project configuration to include the directories for the header and library files in the DDK was tried, but this leads to messy build errors due to conflicts between DDK and Windows SDK files and functions that have the same names, as well as DDK header files that are not set up to compile as part of Windows apps under Visual Studio.) Since the DDK files are now included in the source, there should be no need to install the DDK to build the project given here.

---
