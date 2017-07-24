# **Finding Lane Lines on the Road**
# Udacity's Self-Driving Car NanoDegree - Project 1
[![Udacity - Self-Driving Car NanoDegree](https://s3.amazonaws.com/udacity-sdc/github/shield-carnd.svg)](http://www.udacity.com/drive)

<img src="readme_images/header_image.jpg" width="480" alt="Combined Image" />

Introduction
---

This repository hosts files for the ***"Detecting Lane Lines"*** project for **Udacity's** ***"Self Driving Car Nanodegree"***.

In this project I detect lane lines in images using Python and OpenCV and then apply it to videos.

Dependencies
---

This project requires python3 and Mac OS X to work. It also requires anaconda - a package dependency and environment manager. Click [here](https://conda.io/docs/download.html) to view instructions on how to install anaconda.

In addition to this, the project has a dependency on ***ffmpeg*** library to process video files. If ***ffmpeg*** is not installed on your machine you can install it by running the following commands in an appropriate conda environment:
```python
import imageio
imageio.plugins.ffmpeg.download()
```

Installing required packages
---

1. **Create project environment:** This project comes with an ***environment.yml*** file that lists all the packages required for the project. Running the following command will create a new `conda` environment that is provisioned with all libraries you need to be run this project.
```sh
conda env create -f environment.yml
```
2. **Verify:** Run the following command to verify that the carnd-term1 environment was created in your environments:
```sh
conda info --envs
```
3. **Cleanup:** Run the following command to cleanup downloaded libraries (tarballs, zip files, etc):
```sh
conda clean -tp
```
4. **Activate:** Run the following command to activate the `carnd-term1` environment:
```sh
$ source activate carnd-term1
```
5. **Deactivate:** Run the following command to deactivate the `carnd-term1` environment:
```sh
$ source deactivate
```
6. **Uninstalling:** Run the following command to uninstall the environment:
```sh
conda env remove -n carnd-term1
```
