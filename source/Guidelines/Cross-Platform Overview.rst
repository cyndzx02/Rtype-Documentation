***********************
Cross-Platform Overview
***********************
    .. note:: This document encompasses how the cross-platform works and how you can
        get started with.

Dear developers, please make yourself a nice cup of tea and 
start installing Visual Studio (via Visual Studio Installer) 
on your Windows environment. your Windows environment.
The cross-platform or multiplatform software is a type of application/software that works on
various operating systems or devices, which are often called platforms.
A platform means an operating system such as Windows or Linux.
In our context, Our program must be able to run on both windows and linux.

Choice of Package Manager
=========================
Conan is an open-source package manager designed specifically for C and C++ developers.
It's a powerful tool that helps manage dependencies, binaries, and build configurations
across different platforms and build systems.
Here are some key features of Conan:

Features of Conan
=================
1. Universal and Portable: Works on all major operating systems, including Windows, Linux, macOS, FreeBSD, and more.
2. Decentralized: You can host your own packages on your server, privately
3. Integration: Works seamlessly with various build systems like CMake, MSBuild, Makefiles, Meson, and SCons
4. Binary Management: Can create, upload, and download binaries for different configurations and platforms
5. Community and Support: Backed by a large community and a team of full-time maintainers


=====
Steps
=====

1. Install conan if you don't already have it:
==============================================

    .. code-block:: bash

        pip install conan #(on windows and linux).

2. Then create a conan profile for each environment:
====================================================
- Linux: 
  
    .. code-block:: bash

        conan profile detect --name=linux_profile

- Windows:

    .. code-block:: bash

      conan profile detect --name=windows_profile

This step is specific to your machine.

  .. warning:: 
    1. Don't modify the conanfile I've put in the root directory.
    everything.

3. Install the dependencies at the root of the project.
=======================================================
4. To do this, use on :
=======================

a. Linux
********

   .. code-block:: bash

        conan install . --profile:host=linux_profile --build=missing

b. Windows:
***********

    .. code-block:: bash

        conan install . --profile:host=windows_profile --build=missing

    .. warning:: Never push the files generated by this command. They
        can create serious conflicts between machines and are too
        voluminous.

5.  Create a build folder and enter :
=====================================

    .. code-block:: bash

            mkdir build
            cd build

    .. note:: Thanks to the root CMAKE, we will control all the CMAKEs in the
        project and get the result of their compilation here (I didn't put Engine
        in there as it doesn't compile)

6.  The Linux build
===================
If you didn't like linux before, this is the part that will make you love and respect it.
respect it if you ever have the misfortune to go through what I did.

a. 

    .. code-block:: bash

        cmake .. -DCMAKE_TOOLCHAIN_FILE=conan_toolchain.cmake -DCMAKE_BUILD_TYPE=Release

b. 

    .. code-block:: bash

        cmake --build . #(or simply make. But the first is recommended)

That's all there is to it. Simple, effective, precise in case of error.

7. Windows build
================
If you want a reason never to mix Windows (with its visual
studio) and programming, take the last commit before my series of
cross-plateform commits and launch the build.

a. 

    .. code-block:: bash

        cmake . -DCMAKE_TOOLCHAIN_FILE=...\conan_toolchain.cmake -G “Visual Studio 17 2022” -A x64

It's because the Visual Studio I'm using (this 03/11/2024) is from
version 17 of 2022 that I have put “Visual Studio 17 2022” when
version precision. You can find the version of your Visual
Studio in Visual Studio Installer.
The -DCMAKE_TOOLCHAIN_FILE=...\conan_toolchain.cmake for its part
specifies that the toolchain file generated when installing
dependencies is located at the root of the project.

b.

    .. code-block:: bash

        cmake --build . --config Release

If all goes well, you'll get a message telling you
the location of the .exe files
That's it for cross-plateform. Thank you for reading it, and I hope it will help you
compile the project easily.

