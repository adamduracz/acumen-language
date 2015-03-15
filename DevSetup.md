# Getting Started #

  1. [Install sbt](http://code.google.com/p/simple-build-tool/wiki/Setup) (simple build tool)
  1. Checkout the repository; in a unix shell, type:
```
   svn co https://svn.rice.edu/r/rap/project/Acumen-Scala
```
> Or, if you don't have access to the Rice svn, unzip an acumen release and go to the source directory.
  1. Launch sbt; in a unix shell positioned in `Acumen-Scala`, type:
```
   sbt
```
> > and wait until the prompt appears (this will take some time only once).
  1. Get the dependencies; in the sbt console, type:
```
   update
```
> > and wait for a while (this has to be done only once).
  1. Compile acumen; in the sbt console, type:
```
   compile
```
  1. (Optional) Test acumen; in the sbt console, type:
```
   test
```
  1. Run acumen GUI; in the sbt console, type:
```
   run
```
  1. Edit the code
  1. Compile again ...

# Development Cycle #

Automatic compilation in the background is enabled by typing
```
~ compile
```
in the sbt console.

To get a scala console with acumen's classes loaded, type:
```
console
```

To upload a new release, type:
```
upload <username> <password>
```
where `username` is you google username and `password` you **google code** (and not google account) password. The google code password is different for each acumen developer and is found at https://code.google.com/hosting/settings .

See [sbt documentation](http://code.google.com/p/simple-build-tool/wiki/RunningSbt) for more options.

# Project Structure (or "where are the examples?") #

The project structure follows the one proposed by sbt which in turn follows that of Maven:

```
 src/
    main/
      resources/
         <files to include in main jar here>
      scala/
         <main Scala sources>
      java/
         <main Java sources>
    test/
      resources
         <files to include in test jar here>
      scala/
         <test Scala sources>
      java/
         <test Java sources>
```

In particular, the example files are situated in:
```
src/main/resources/acumen/examples
```

# Development Scripts #

The `demo` directory contains a bunch of scripts aimed at debugging and benchmarking. They all take an acumen filename as an argument, with two exceptions:
  1. `bench.sh` also takes two more arguments, namely the lowest number of threads and the highest number of threads benchmarked;
  1. `onevar.sh` takes a variable name before the filename.

Short description of each script:

  * `trace.sh`: output a trace of the simulation
  * `last.sh`: display only the last state of the simulation
  * `bench.sh`: run a benchmark of the parallel version
  * `onevar.sh`: plot the value of one variable (has to appear once at each step)
  * `demo2d.sh`: 2d animation of x,y coordinates using python's matpotlib
  * `demo3d.sh`: plot the x,y,z coordinates as 3d traces using python's vtk bindings
  * `demoj2d.sh`: 2d animation of x,y coordinates using java3d
  * `demoj3d.sh`: 3d animation of x,y,z + m(mass) coordinates using java3d
  * python sripts are helper scripts for the shell scripts and shall not be called

Example usage 1:
```
./demo2d.sh ../src/main/resources/acumen/examples/bouncing_ball_2d.acm
```

Example usage 2:
```
./bench.sh ../src/main/resources/acumen/examples/internal/big.acm 1 4
```