# Template Organization
The template is organized as follows:

* AUTHORS
* CONTRIBUTING.md
* CMakeLists.txt
* COPYING
* ChangeLog
* Doxyfile
* INSTALL
* LICENSE
* Makefile
* README
* bin/
* build/
* configure
* docs/
* include/
* lib/
* share/
* src/
* test/
* thirdparty/
* tools/

## AUTHORS
This is where contributors to the project should sign their names.

## CONTRIBUTING.md
To help your project contributors do good work, you can add a file with contribution guidelines to your project repository's root, docs, or .github folder. When someone opens a pull request or creates an issue, they will see a link to that file. The link to the contributing guidelines also appears on your repository's contribute page.

## CMakeLists.txt
This is the top-level build configuration file. It is used by CMake for building the project. Please see the CMake Manual for the full list of available commands.

## COPYING
You should place a plaintext copy of your project's license in this file. Or, you can put an English explanation of the rules of copying your source code, and refer the reader to the "LICENSE" file for the official license agreement that they must follow.

## ChangeLog
For each version, you should annotate the changes between versions in this file.

## Doxyfile
This file configures Doxygen. Please see the Doxygen Configuration Manual on how to customize this file to fit your needs.

## INSTALL
This is where you should place instructions for how to install your product. If you use CMake's builtin "INSTALL(...)" commands for indicating which files to install and where those files should go, then the content of this file should be something along the lines of "Build the project using 'make', then install using 'sudo make install'".

## LICENSE
You should place a plaintext copy of your project's license in this file.

## Makefile
This is a simple Makefile wrapper for "CMakeLists.txt". It allows you to build the CMake project with the usual invocation of "make", without ever having to invoke cmake.

## README
This is where you should place basic documentation for your project. It should include instructions on building your project, instructions on how to use or invoke your project, a list of known bugs, and any other information that you would like users to know.

## bin/
This is where all executable files built by the project are generated. You can use the "ADD_EXECUTABLE" command in CMake to specify additional executables to generate.

## build/
This is where CMake will generate intermediate build products, including CMake's variable and configuration cache. You should generally not touch this folder.

## configure
This BASH script invokes CMake. It is there so that user's who are familiar with the "./configure", then "make", then "sudo make install" will feel comfortable using your project. You do not need to touch or edit this file. You can use "make" directly, without first invoking "./configure", since the configuration step will run if necessary.

## docs/
This is where the project's Doxygen documentation will be generated, if you invoke the "make docs" or "make doxygen" targets. 

## include/
You should place your project's public header files (i.e. the header files that you want the user's of your project to able to include) in a subfolder of "include/". The name of the subfolder should correspond to your project's name. The "include/" folder is automatically added to the header search paths, so if you create a master header file for your project named "projectname.h" and place it in "include/projectname/", then you will be able to include it from your source code using "#include ".

## lib/
This is where all library files built by the project are generated. You can use the "ADD_LIBRARY" command in CMake to specify additional libraries to generate.

## share/
You should place any data files that your project needs in a subfolder of this folder. The name of the subfolder should, in some way, correspond to your project's name.

## src/
You should place your source files in this folder or in a subfolder of this folder. The "CMakeLists.txt" file in this directory will automatically compile all sources in the folder into a single executable. You may need to edit this "CMakeLists.txt" file, so that the appropriate build targets are generated (e.g. if you have multiple different executable or library modules, so all sources should not be built into a single target).

## test/
You should place your test sources in this folder. The UnitTest++ unit-testing framework is currently being used by default. Using this particular framework is highly recommended.

## thirdparty/
If you would like to bundle thirdparty dependencies with your project, this would be a reasonable location to place them. Otherwise, you can delete this folder.

## tools/
This contains any scripts, CMake modules, or other components that are needed to build the project or which facilitate project building and development. If you create a script to stylize the code according to your project's specifications or if you create a script to validate that project guidelines are being followed, the "bin" subfolder of "tools" would be the appropriate location to place those scripts. If you need to add modules to CMake (e.g. to implement "FIND_PACKAGE" for an additional package), you should place those scripts in "tools/share/cmake". You can already find examples of such modules for locating Log4Cxx and UnitTest++.

```
$ tree
.
├── AUTHORS
├── CMakeLists.txt
├── CONTRIBUTING.md
├── COPYING
├── ChangeLog
├── Doxyfile
├── INSTALL
├── LICENSE
├── Makefile
├── README.md
├── bin
│   └── README.md
├── build
│   └── README.md
├── configure
├── docs
│   └── README.md
├── include
│   └── README.md
├── lib
│   └── README.md
├── share
│   └── README.md
├── src
│   ├── CMakeLists.txt
│   ├── README.md
│   ├── app.cpp
│   ├── app.h
│   ├── appinfo.h
│   ├── appinfo.h.in.cmake
│   └── main.cpp
├── test
│   ├── CMakeLists.txt
│   ├── README.md
│   ├── main.cpp
│   ├── sanity_check.cpp
│   └── test.h
├── thirdparty
│   ├── LICENSES.txt
│   ├── README.md
│   ├── include
│   │   └── README.md
│   ├── lib
│   │   └── README.md
│   └── share
│       └── licenses
│           ├── APACHE-1.1.txt
│           ├── APACHE-2.0.txt
│           ├── BSD-NEW.txt
│           ├── BSD-SIMPLIFIED.txt
│           ├── BSD.txt
│           ├── GPL-1.0.txt
│           ├── GPL-2.0.txt
│           ├── GPL-3.0.txt
│           ├── LGPL-2.0.txt
│           ├── LGPL-2.1.txt
│           ├── LGPL-3.0.txt
│           ├── MIT.txt
│           └── MPL-1.1.txt
└── tools
    ├── README.md
    ├── bin
    │   └── README.md
    ├── lib
    │   └── README.md
    └── share
        └── cmake
            ├── DocumentationTargets.cmake
            ├── FindLog4Cxx.cmake
            └── FindUnitTestPlusPlus.cmake

19 directories, 52 files
```