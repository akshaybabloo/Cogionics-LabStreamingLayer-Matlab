# Cogionics LabStreamingLayer Matlab
Using Cogionics Matlab code.

> Note-1: This instillation is for Windows 64-bit.

> Note-2: `*.mexw64` files provided in this code were compiled on my system and should work on all 64-bit windows version.

## Compiling `mex` files for 32-bit system
If you are using 32-bit Windows system to run the code, you would have to convert `*.c` files into 32-bit MEX files. you would need a 32-bit Matlab for this. Enter the following code for the conversion.

`mex path-to-c-file/c-file.c`

This will create `c-file.mexw32` on the parent path.

## Check list
* Visual Studio 2010 Premium with SP1 (Matlab R2013b)
* Visual Studio Professional 2012 (Matlab R2014)
* Matlab R2013b or R2014.
* Cogionics Acquisition Software

## Installing Visual C++ via MEX installer
There are different ways to install Visual C++ in Matlab, the following seems to be easy.

Make sure you have installed everything from the *check list*.

### Matlab R2013b
* Open Matlab R2013b.
* Write the following command in the *Command Window* `>> mex -setup`, once entered the following is the output

<pre>
Welcome to mex -setup.  This utility will help you set up  
a default compiler.  For a list of supported compilers, see  
http://www.mathworks.com/support/compilers/R2013b/win64.html

Please choose your compiler for building MEX-files:

Would you like mex to locate installed compilers [y]/n?
</pre>

* Enter `y` to continue. If all the softwares are installed (Visual Studio) the following is the output

<pre>
Select a compiler:
[1] Microsoft Visual C++ 2012 in C:\Program Files (x86)\Microsoft Visual Studio 11.0
[2] Microsoft Visual C++ 2010 in C:\Program Files (x86)\Microsoft Visual Studio 10.0

[0] None

Compiler:
</pre>

* Doesn't matter which compiler you choose, I prefer `[2]`. Enter `2` to proceed. The following is the output

<pre>
Please verify your choices:

Compiler: Microsoft Visual C++ 2010  
Location: C:\Program Files (x86)\Microsoft Visual Studio 10.0

Are these correct [y]/n?
</pre>

* Enter `y` to proceed. The following is the output

<pre>
***************************************************************************
  Warning: MEX-files generated using Microsoft Visual C++ 2010 require
           that Microsoft Visual Studio 2010 run-time libraries be  
           available on the computer they are run on.
           If you plan to redistribute your MEX-files to other MATLAB
           users, be sure that they have the run-time libraries.
***************************************************************************


Trying to update options file: C:\Users\em8273\AppData\Roaming\MathWorks\MATLAB\R2013b\mexopts.bat
From template:              C:\PROGRA~1\MATLAB\R2013\bin\win64\mexopts\msvc100opts.bat

Done . . .

**************************************************************************
  Warning: The MATLAB C and Fortran API has changed to support MATLAB
           variables with more than 2^32-1 elements.  In the near future
           you will be required to update your code to utilize the new
           API. You can find more information about this at:
           http://www.mathworks.com/help/matlab/matlab_external/upgrading-mex-files-to-use-64-bit-api.html  
           Building with the -largeArrayDims option enables the new API.
**************************************************************************
 </pre>

* instillation is done.


### Matlab R2014

* Please follow the same steps from [Matlab R2013b](#matlab-r2013b)
* If a compiler is already installed the following ill be the output:

<pre>
MEX configured to use 'Microsoft Visual C++ 2012 (C)' for C language compilation.
Warning: The MATLAB C and Fortran API has changed to support MATLAB
	 variables with more than 2^32-1 elements. In the near future
	 you will be required to update your code to utilize the
	 new API. You can find more information about this at:
	 http://www.mathworks.com/help/matlab/matlab_external/upgrading-mex-files-to-use-64-bit-api.html.

To choose a different C compiler, select one from the following:
Microsoft Visual C++ 2010 (C)  mex -setup:'C:\Program Files\MATLAB\R2014b\bin\win64\mexopts\msvc2010.xml' C
Microsoft Visual C++ 2012 (C)  mex -setup:C:\Users\em8273\AppData\Roaming\MathWorks\MATLAB\R2014b\mex_C_win64.xml C
Microsoft Visual C++ 2013 Professional (C)  mex -setup:'C:\Program Files\MATLAB\R2014b\bin\win64\mexopts\msvc2013.xml' C

To choose a different language, select one from the following:
 mex -setup C++
 mex -setup FORTRAN
 </pre>

## Running Cogionics software with LabStreamingLayer

Click on "**StartLabStreaming Layer**" button on the software as shown in the figure below, so that the Matlab can take the real time data from the Cogionics headset.


## Matlab code

### Structure

<pre>
Cogionics-LabStreamingLayer-Matlab
|
+-- .git
+-- Screenshot
|   |
|   `- *.png
+-- src
|   |
|   +-- *.m (Matlab code)
|   +-- bin
|   |   |
|   |   +-- *.dll (Windows)
|   |   +-- *.dylib (Mac)
|   |   `-- *.so (Linux)
|   +-- examples
|   |   |
|   |   `-- *.m (Matlab code)
|   `-- mex
|       |
|       +-- *.mexw64 (Compiled Matlab MEX)
|       +-- *.c (C code)
|       +-- *.h (C/C++ header)
+ README.md
</pre>

### Running the code

* Go to [examples](https://github.com/akshaybabloo/Cogionics-LabStreamingLayer-Matlab/tree/master/src/examples) folder and open `ReceiveData.m`.
* Make sure your Cogionics headset is connected, Cogionics Acquisition software is running and LabStreaming Layer started.
* Run `ReceiveData.m`, the following will be the output:

<pre>
Loading the library...
Opening an inlet...
Now receiving data...
19485.773438	19741.779297	6674.514648	6623.163574	20691.462891	6199.680176	20167.275391	20685.126953	6924.809082	6192.976563	6675.769043	20267.355469	20231.251953	20662.804688	7397.237793	7199.717285	19946.298828	18647.792969	19228.863281	6209.264160	6137.953613	18366.271484	20491.544922	21065.767578	6444.163086	20681.554688	20029.085938	20010.667969	5983.314941	6012.062012	6325.457031	6124.861816	4987.716797	6074.905273	5197.524902	1.000000	0.000000	11236.27503
19708.207031	19863.417969	6886.106934	6952.495605	20584.455078	6310.559082	19912.994141	20138.935547	6726.181152	6194.583984	6666.457520	20144.380859	19848.751953	20016.361328	6850.826660	6961.275879	20171.779297	18535.423828	19087.242188	6016.764648	5894.255859	17926.568359	20411.574219	21206.007813	6374.832031	20544.937500	19862.681641	19956.236328	6122.464355	6436.485840	6369.718750	6173.652832	4987.716797	6074.905273	5197.524902	2.000000	0.000000	11236.27516
.
.
.
</pre>

* The output you see is the real time data from the headset, each line is 1 Hz.
