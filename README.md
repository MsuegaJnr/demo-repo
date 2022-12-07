###################################
        Online Compilers
###################################


1. Wandbox - https://wandbox.org/
2. Compiler explorer - https://godbolt.org/
3. Coliru - https://coliru.stacked-crooked.com/



##################################
 Using GCC and Clang Compilers
##################################

Installation

https://winlibs.com/
Download latest verion and extract into a folder 
(eg. GCC 12.2.0 + LLVM/Clang/LLD/LLDB 14.0.6 + MinGW-w64 10.0.0 (UCRT) - release 2   (LATEST))

C:\mingw64

set to path in environment variables
C:\mingw64\bin


To check g++ compiler verion
open command prompt with 'cmd'
g++ --version        --> 12.1.0


To check clang compiler version 
open command prompt with 'cmd'
clang++ --version    --> 14.0.6


####################################
Configuration in VScode (Windows OS)
####################################

Step0:-- Write a script eg 'hello_world.cpp' and configure a json tasks template file for compilation 

Step1:-- Select the hello_world.cpp file in explorer space
Step2:-- Terminal menu --> Configure tasks... --> compiler:C:\mingw\bin\g++.exe
Step3:-- A 'tasks.json' file is auto generated. Edit the file to become like the code below: 

//'tasks.json' file
{
	"version": "2.0.0",
	"tasks": [
		{
			"type": "cppbuild",
			"label": "Build with GCC 12.1.0",
			"command": "C:\\mingw64\\bin\\g++.exe",
			"args": [
				"-fdiagnostics-color=always",
				"-g",
				"-std=c++20",
				"${file}",
				"-o",
				"${fileDirname}\\${fileBasenameNoExtension}.exe"
			],
			"options": {
				"cwd": "${fileDirname}"
			},
			"problemMatcher": [
				"$gcc"
			],
			"group": "build",
			"detail": "compiler: C:\\mingw64\\bin\\g++.exe"
		}
	]
}

Step4:-- Select the hello_world.cpp --> Terminal menu --> Run task.. -->Build with GCC 12.1.0
      -- The 'hello_world.cpp' file is compiled and a 'hello_world.exe' file is generated.

Step5:-- Run the .exe file in the terminal
      -- .\hello_world.exe





