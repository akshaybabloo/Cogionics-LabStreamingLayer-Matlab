# Cogionics LabStreamingLayer Matlab
Using Cogionics Matlab code.

> Note: This instillation is for Windows 64-bit.

## Check list
* Visual Studio 2010 Premium with SP1 (Matlab R2013b)
* Visual Studio Professional 2012 (Matlab R2014)
* Cogionics Acquisition Software

## Installing Visual C++ via MEX installer
There are different ways to install Visual C++ in Matlab, the following seems to be easy.

Make sure you have installed everything from the *check list*.

### Matlab R2013b
1. Open Matlab R2013b.
2. Write the following command in the *Command Window* `>> mex -setup`, once entered the following is the output

<pre>
Welcome to mex -setup.  This utility will help you set up  
a default compiler.  For a list of supported compilers, see  
http://www.mathworks.com/support/compilers/R2013b/win64.html

Please choose your compiler for building MEX-files:

Would you like mex to locate installed compilers [y]/n?
</pre>

3. Enter `y` to continue. If all the softwares are installed (Visual Studio) the following is the output

<pre>
Select a compiler:
[1] Microsoft Visual C++ 2012 in C:\Program Files (x86)\Microsoft Visual Studio 11.0
[2] Microsoft Visual C++ 2010 in C:\Program Files (x86)\Microsoft Visual Studio 10.0

[0] None

Compiler:
</pre>

4. Doesn't matter which compiler you choose, I prefer `[2]`. Enter `2` to proceed. The following is the output

<pre>
Please verify your choices:

Compiler: Microsoft Visual C++ 2010  
Location: C:\Program Files (x86)\Microsoft Visual Studio 10.0

Are these correct [y]/n?
</pre>

5. Enter `y` to proceed. The following is the output

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

 6. instillation is done.
