

Hello World in C++ tutorial: https://lappweb.in2p3.fr/~paubert/ASTERICS_HPC/2-2-100.html

Run it with Clang:
```
$ cd src
$ clang++ hello.cpp
$ ./a.out
Hello World!%
```

Run the build with CMake:
```
$ mkdir build
$ cd build
$ cmake ..
-- The C compiler identification is GNU 7.2.0
-- The CXX compiler identification is GNU 7.2.0
-- Check for working C compiler: /usr/bin/cc
-- Check for working C compiler: /usr/bin/cc -- works
-- Detecting C compiler ABI info
-- Detecting C compiler ABI info - done
-- Detecting C compile features
-- Detecting C compile features - done
-- Check for working CXX compiler: /usr/bin/c++
-- Check for working CXX compiler: /usr/bin/c++ -- works
-- Detecting CXX compiler ABI info
-- Detecting CXX compiler ABI info - done
-- Detecting CXX compile features
-- Detecting CXX compile features - done
-- Configuring done
-- Generating done
-- Build files have been written to: XXX/HelloWorldCMake/build
$ make
[ 50%] Building CXX object CMakeFiles/HelloWorld.dir/src/hello.cpp.o
[100%] Linking CXX executable HelloWorld
[100%] Built target HelloWorld
$ ./HelloWorld
Hello World%
```


For More Examples:
https://github.com/sonarsource-cfamily-examples


To Run the executable of this Project:
```
./build/HelloWorld
```

Run SonarScanner CLI on it on Mac with Compilation Database:
```
sonar-scanner -Dsonar.projectKey=your_project_key -Dsonar.sources=src -Dsonar.host.url=https://your.sonarqube_url.com/ -Dsonar.login=sqp_xxxxxxxxxxxxxxxxxxxxxxxxxxxx -Dsonar.cfamily.compile-commands=build/compile_commands.json
```
example:
```
sonar-scanner -Dsonar.projectKey=C-Hello-World -Dsonar.sources=src -Dsonar.host.url=https://mlw-megan-us.ngrok.io/ -Dsonar.login=sqp_2e415a0aef627c28141ffa43d62679ee8a8b4f3a -Dsonar.cfamily.compile-commands=build/compile_commands.json
```

Used this tutorial: https://learn.microsoft.com/en-us/cpp/build/walkthrough-compile-a-c-program-on-the-command-line?view=msvc-170

Used this tutorial: https://learn.microsoft.com/en-us/cpp/build/walkthrough-compiling-a-native-cpp-program-on-the-command-line?view=msvc-170

Run on Windows Developer Console:
```
$ cl src\hello.cpp
$ src\hello.exe
Hello World
```

In command line and sonar-project.properties
- sonar.cfamily.compile-commands
- sonar.cfamily.build-wrapper-output

Download Build Wrapper for Windows from {SonarQube URL}/static/cpp/build-wrapper-win-x86.zip

Download Build Wrapper for Windows from https://mlw-megan-us.ngrok.io/static/cpp/build-wrapper-win-x86.zip

Extract and add to path

Run SonarScanner CLI on Windows with Build-Wrapper
```
$ build-wrapper-win-x86-64.exe --out-dir  bw-output cl src\hello.cpp
$ sonar-scanner -Dsonar.projectKey=your_project_key -Dsonar.sources=src -Dsonar.host.url=https://your.sonarqube_url.com/ -Dsonar.login=sqp_xxxxxxxxxxxxxxxxxxxxxxxxxxxx -Dsonar.cfamily.build-wrapper-output=bw-output

```
example:
```
$ C:\Users\mlw-windows-megan\Downloads\build-wrapper-win-x86\build-wrapper-win-x86\build-wrapper-win-x86-64.exe --out-dir  bw-output cl src\hello.cpp
$ C:\Users\mlw-windows-megan\Downloads\sonar-scanner-cli-4.8.0.2856-windows\sonar-scanner-4.8.0.2856-windows\bin\sonar-scanner -Dsonar.projectKey=C-Hello-World -Dsonar.sources=src -Dsonar.host.url=https://mlw-megan-us.ngrok.io/ -Dsonar.login=sqp_2e415a0aef627c28141ffa43d62679ee8a8b4f3a -Dsonar.cfamily.build-wrapper-output=bw-output

```

Note: We don't really care about the build tool. MSBuild is just an example we put in the documentation to illustrate one case on Windows OS. You can even use a shell / bat script; it will also work.