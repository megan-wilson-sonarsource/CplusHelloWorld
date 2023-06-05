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
sonar-scanner -Dsonar.projectKey=your_project_key -Dsonar.sources=src -Dsonar.host.url=https://your.sonarqube_url.com/ -Dsonar.token=sqp_xxxxxxxxxxxxxxxxxxxxxxxxxxxx -Dsonar.cfamily.compile-commands=build/compile_commands.json
```
example: 
```
sonar-scanner -Dsonar.projectKey=C-Hello-World -Dsonar.sources=src -Dsonar.host.url=https://mlw-megan-us.ngrok.io/ -Dsonar.token=sqp_2e415a0aef627c28141ffa43d62679ee8a8b4f3a
```