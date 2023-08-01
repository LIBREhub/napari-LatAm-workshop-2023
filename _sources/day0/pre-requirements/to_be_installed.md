# Course preparation

# Prerequisites to be installed

Before attending the course, please install conda on your computer as explained in this [guide](https://biapol.github.io/blog/mara_lampert/getting_started_with_mambaforge_and_python/readme.html). Furthermore, please install [devbio-napari](https://github.com/haesleinhuepf/devbio-napari#installation) and [Github desktop](https://desktop.github.com/).

When you are done, you can test your setup by executing these commands from the command line:
```
conda activate devbio-napari-env

naparia
```

After Napari opens, click the menu `File > Open Samples > clEsperanto > blobs (from ImageJ)`. In the Panel on the right click on the `Label` button. If Napari then looks like this, you are ready to go:

![img.png](img.png)

## Troubleshooting: Napari jumping out of the screen

When using some plugins, the Napari window increases and jumps out of the screen. In this case, downgrade Napari to version 0.4.15:

```
mamba install napari=0.4.15 -c conda-forge
```

## Troubleshooting: DLL load failed

In case of error messages such as this one:
```
[...] _get_win_folder_with_pywin32
from win32com.shell import shellcon, shell
ImportError: DLL load failed while importing shell: The specified procedure could not be found.
```

Try this command, within the base environment:

```
conda activate base

pip install --upgrade pywin32==228
```

[Source](https://github.com/conda/conda/issues/11503)

## Troubleshooting: Graphics cards drivers

In case error messages contains "ImportError: DLL load failed while importing cl: The specified procedure could not be found" [see also](https://github.com/clEsperanto/pyclesperanto_prototype/issues/55) or ""clGetPlatformIDs failed: PLATFORM_NOT_FOUND_KHR", please install recent drivers for your graphics card and/or OpenCL device. Select the right driver source depending on your hardware from this list:

* [AMD drivers](https://www.amd.com/en/support)
* [NVidia drivers](https://www.nvidia.com/download/index.aspx)
* [Intel GPU drivers]()(https://www.intel.com/content/www/us/en/download/726609/intel-arc-graphics-windows-dch-driver.html)
* [Intel CPU OpenCL drivers](https://www.intel.com/content/www/us/en/developer/articles/tool/opencl-drivers.html#latest_CPU_runtime)
* [Microsoft Windows OpenCL support](https://www.microsoft.com/en-us/p/opencl-and-opengl-compatibility-pack/9nqpsl29bfff)

Sometimes, mac-users need to install this:

    mamba install -c conda-forge ocl_icd_wrapper_apple

Sometimes, linux users need to install this:

    mamba install -c conda-forge ocl-icd-system

In case installation didn't work in the first attempt, you may have to call this command line to reset the napari configuration:

```
napari --reset
```
