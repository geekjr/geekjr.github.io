# How to improve Machine Learning and Data Science performance using Intel Python

## In this article, I wil show you how you can get a huge speedup for Machine Learning/Data Science tasks using Intel Python. 

## What is Intel Python?
Intel Python is a version of Python that is optimized to run on Intel CPUs. This optimization yields significantly faster speeds when compared to normal Python, especially in Machine Learning/Data Science tasks. 

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

## What about packages that do not have prebuilt versions in the Intel Anaconda Channel?
Some packages might support Intel Optimizations but do not have prebuild versions in the Intel Anaconda channel. One example of this is OpenCV. In this case, you will have to build from source, and while you are building form source, you have to set certin flags. In the case of OpenCV, you will have to set the following flags. You will need to have Intel MKL(installed above) and [Intel TBB](https://anaconda.org/intel/tbb) installed:
```
DWITH_MKL=ON
DMKL_USE_MULTITHREAD=ON 
DMKL_WITH_TBB=ON
DWITH_TBB=ON
```
For other packages, you can consult the package's documentation. 

## Performance
All of these tests were conducted on a Late 2011 13 Inch MacBook Pro with:
* [Intel i7-2640M, ](https://ark.intel.com/content/www/us/en/ark/products/53464/intel-core-i7-2640m-processor-4m-cache-up-to-3-50-ghz.html) which is a 2.8GHz dual core processor
* 16GB RAM
* Samsung 860 EVO SSD
* macOS Mojave 10.14.6
During the tests, nothing else was running in the background. I ran the tests from the terminal no ensure that there was no IDE overhead. The benchmark scripts that I used can be found [here.](https://github.com/geekjr/intelPythonBenchmarks)


### Sklearn
![](sklearn.png?raw=true)
As seen above, the time it takes to run the [program ](https://scikit-learn.org/stable/auto_examples/cluster/plot_kmeans_digits.html) is reduced by an impressive 43% when using Intel Python


### PyTorch
![](pytorch.png?raw=true)
The training time for the [sample demo ](https://pytorch.org/tutorials/beginner/blitz/cifar10_tutorial.html#sphx-glr-beginner-blitz-cifar10-tutorial-py)is reduced by a modest 17% when using Intel Python. 


### TensorFlow
![](tensorflow.png?raw=true)
TensorFlow sees a large amount of improvement, with a whopping 75% reduction in training time when running the [sample ](https://www.tensorflow.org/tutorials/keras/classification) image classification demo. 


### Pandas
![](pandas.png?raw=true)
Pandas sees the largest improvement, with a staggering 200% reduction in training time when loading a 3.22GB CSV.


Overall, there was a 83% improvemnt to speed when using Intel Python. However, some libraries see larger improvements then others.
