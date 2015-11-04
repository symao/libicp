####################################################################################
# Copyright 2011. All rights reserved.                                             #
# Institute of Measurement and Control Systems                                     #
# Karlsruhe Institute of Technology, Germany                                       #
#                                                                                  #
# This file is part of libicp.                                                     #
# Authors:  Andreas Geiger                                                         #
#           Please send any bugreports to geiger@kit.edu                           #
#                                                                                  #
# libicp is free software; you can redistribute it and/or modify it under the      #
# terms of the GNU General Public License as published by the Free Software        #
# Foundation; either version 3 of the License, or any later version.               #
#                                                                                  #
# libicp is distributed in the hope that it will be useful, but WITHOUT ANY        #
# WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A  #
# PARTICULAR PURPOSE. See the GNU General Public License for more details.         #
#                                                                                  #
# You should have received a copy of the GNU General Public License along with     #
# libicp; if not, write to the Free Software Foundation, Inc., 51 Franklin         #
# Street, Fifth Floor, Boston, MA 02110-1301, USA                                  #
####################################################################################

+++++++++++++++++++++++++++++++++++
+          INTRODUCTION           +
+++++++++++++++++++++++++++++++++++

Libicp (LIBrary for Iterative Closest Point fitting) is a cross-platfrom C++
library with MATLAB wrappers for fitting 2d or 3d point clouds with respect to
each other. Currently it implements the SVD-based point-to-point algorithm as well
as the linearized point-to-plane algorithm. It also supports outlier rejection
and is accelerated by the use of kd trees as well as a coarse matching stage
using only a subset of all points.

If you distribute a software that uses libicp, you have to distribute it under GPL
with the source code.

+++++++++++++++++++++++++++++++++++
+    COMPILING MATLAB WRAPPERS    +
+++++++++++++++++++++++++++++++++++

If you want to use libicp directly from MATLAB you can easily do this by using
the MATLAB wrappers provided. They also include some demo files for testing your
configuration. First, configure your MATLAB MEX C++ compiler, if it is not yet
configured (mex -setup). Under Linux you might use g++, under Windows I compiled
it successfully with the Microsoft Visual Studio Express 2008 compilers.

1) Change to the libicp/matlab directory
2) After running 'make.m' you should have a MEX file called 'icpMex'
3) Now try to run 'demo_2d.m' or 'demo_3d.m'

+++++++++++++++++++++++++++++++++++
+     BUILDING A C++ LIBRARY      +
+++++++++++++++++++++++++++++++++++

Prerequisites needed for compiling libicp using c++:
- CMake (available at: http://www.cmake.org/)
- Boost (available at: http://www.boost.org/)

Note:

Please make sure that the boost headers can be found!
(Add /usr/local/include to your include path if you have
installed them locally)

Linux:

1) Move to libicp root directory
2) Type 'cmake .'
3) Type 'make'
4) Run './icp' (demo program)

Windows:

1) Start CMake GUI
2) Set directories to libicp root directory
3) Run configure, configure and generate
4) Open the resulting Visual Studio solution with Visual Studio
5) Switch to 'Release' mode, build all and run the demo program

For more information on CMake, have a look at the CMake documentation.

For more information on the usage of the library, have a look into the MATLAB wrappers and
into the documentation of the header file icp.h.

Please send any feedback and bugreports to geiger@kit.edu
Andreas Geiger

