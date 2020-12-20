# OpenCV 3.2.0 Archive

This repository contains my personal backup of OpenCV 3.2.0 with a couple of fixes to make it compile properly.

## Installation:

This installation guide assumes Ubuntu based system.

Start by installing [neccessary dependencies](https://docs.opencv.org/master/d7/d9f/tutorial_linux_install.html):
```
sudo apt update && sudo apt install -y cmake g++ wget unzip
```

Then we are going to build opencv with a very long cmake command, this will automatically compile opencv_contrib as well, and will exclude some troublesome modules:
```
cd opencv
mkdir build
cd build
cmake -DOPENCV_EXTRA_MODULES_PATH=../../opencv_contrib/modules -DOPENCV_ENABLE_NONFREE=ON -DENABLE_PRECOMPILED_HEADERS=OFF -DBUILD_opencv_xfeatures2d=ON -DBUILD_opencv_python3=OFF ..
```

Then finally compile and install using the full power of your processor:
```
make -j `nproc` && sudo make install
```

This might take a bit, but at the end you should have no errors and an installed version of OpenCV and OpenCV contrib 3.2.0. Submit a bug on this repository if you have problems, and add me to the bug @TheCynosure.

## Resources used:

Might need these for later.

- https://stackoverflow.com/questions/46884682/error-in-building-opencv-with-ffmpeg
- https://stackoverflow.com/questions/46884682/error-in-building-opencv-with-ffmpeg
- https://answers.opencv.org/question/65548/cmake-error-at-cmakeopencvdetectcxxcompilercmake/
