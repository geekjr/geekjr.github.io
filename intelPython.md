# How to get a huge speedup with Machine Learning/Data Science Tasks on computers with an Intel CPU

## In this article, I wil show you how you can get a huge speedup for Machine Learning/Data Science tasks using Intel Python. 

## What is Intel Python?
Intel python is a version of Python that is optimized to run on Intel CPUs. This optimization yields significantly faster speeds when compared to normal Python, especially in Machine Learning/Data Science tasks. 

## Windows installation
1. Download the files from [here](https://software.intel.com/content/www/us/en/develop/tools/distribution-for-python.html)
2. Extract the zip file downloaded
3. Open command promt as administrator and change directory to the location of the extracted folder and type `cd intelpython3`
4. type `setup_intel_python.bat`
5. COMMAND TO ACTIVATE

## macOS installation
1. Download the tarball from [here](https://software.intel.com/content/www/us/en/develop/tools/distribution-for-python.html)
2. Extract the tarball file downloaded with `tar -xvzf<NAME_OF_TARBALL>`
3. type `cd intelpython3`
4. type `bash setup_intel_python.sh`
5. COMMAND TO ACTIVATE

## Linux installation
1. Download the tarball from [here](https://software.intel.com/content/www/us/en/develop/tools/distribution-for-python.html)
2. Extract the tarball file downloaded with `tar -xvzf<NAME_OF_TARBALL>`
3. type `cd intelpython3`
4. type `bash setup_intel_python.sh`
5. COMMAND TO ACTIVATE

## Installing Intel Python optimized packages
Once we have Intel Python installed, its time to install some Intel Python Optimized Packages. Intel has a Anaconda Cloud [channel](https://anaconda.org/intel/repo) that has a number of prebuilt Intel Python optimized packages. Lets install some:
1. First, we need update Conda:
 `conda update conda`
 2. Next, we need to add the Intel channel to our Conda sources:
 `conda config --add channels intel`
 3. Then, we need to install some libraries that allow us to take advantge of our Intel CPU:
 `conda install mkl mkl-devel mkl-static mkl-include`
 4. Finally lets install a package, in this case modin, which will allow us to take advantage of our Intel CPU in Pandas:
 `conda install -c intel modin`
 5. Make sure that it was installed sucessfully:
 ```python
 python
 import modin.pandas as pd
 ```
If you dont get any error, that means that modin was installed sucessfully. Above, we just installed **one** of the many Intel Python optimized packages. You can view the full list in the above list. Note: For some reason, not all of the packages show up in the above list. To find a package that may not be listed in the above list, you can search on Google for the name of the package, followed by Intel Anaconda. For example, "sklean Intel Anaconda". The result should be one of the first links. You can install that pacakge with the command provided on that specific page. 
