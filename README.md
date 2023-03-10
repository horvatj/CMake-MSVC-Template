# CMake-Template

Simple CMake Template for creating temporary MSVC projects (i.e. for tutorials, etc.)


## Puprose / Intention for this project
The reason behind starting this small project was to pursue a Vulkan tutorial while also having a simple approach to creating Microsoft Visual Studio projects with identical dependencies repeatedly.

## Using this CMake template

1. Just copy the contents and rename the resulting folder in anything you like.

2. Adopt CMakeLists.txt to fulfill your needs (add include directories, library directories, libraries, etc.).

3. Invoke CMake

- If you want to have the code and project files in the same directory, open a terminal window and execute the following command which will then create MSVC project files:
```
cmake .
```
- If you want to keep code and project files seperate, create a build directory and invoke cmake there:
```
mkdir build
cd build
cmake ..
```
4. Finally open the Microsoft Studio solution file and start coding.

*Happy coding!*

Johann Horvat <johann@indiecam.com>, March 2023