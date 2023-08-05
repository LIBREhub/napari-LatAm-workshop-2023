# Course preparation

Before the course starts, remember to install Napari and Jupyter - see sections of this page.
Make use of the [napari chatroom for troubleshooting](https://napari.zulipchat.com/#narrow/stream/393209-napari-latam-workshop-2023/) if you face installation issues.

Napari Installation Guide: https://napari.org/dev/tutorials/fundamentals/installation.html

Jupyter Installation Guide: https://jupyter.org/install

# Managing environments

First, you need to install a tool called an *environment manager* in your
computer. For this course we will use conda or its variants mamba and
micromamba. If you already have one of those tools, great! Skip to the next
section. Otherwise, we recommend installing micromamba. Follow the
instructions for your operating system:

## macOS

If you are a macOS user *and* have installed [Homebrew](https://brew.sh/), open
the Terminal application, and type:

```
brew install micromamba
```

And press Enter. If you don't have Homebrew, you'll see an error message:

```
zsh: command not found: brew
```

If that's the case, copy and paste this command into the Terminal:

```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

And follow the prompts. This will install Homebrew. Then you can try `brew
install micromamba` again.

After you have installed micromamba, you have to configure it.

First, we make sure that micromamba can create and activate environments in
your Terminal. To do this, type:

```
micromamba shell init -s zsh -p ~/micromamba
```

into your shell, then the following:

```
source ~/.zshrc
```

Finally, we configure the default *channels*, which is where micromamba looks
for Python packages to install. Copy the following lines:

```
channels:
  - conda-forge
  - ome
```

and type the following into your Terminal:

```
pbpaste > ~/.mambarc
```

(This creates a file called `.mambarc` in your home directory containing the
above lines of text, and they tell micromamba to look for packages in two
places: the conda-forge channel, and, if that fails, the ome channel.)

## Linux

Install micromamba by following the instructions
[here](https://mamba.readthedocs.io/en/latest/installation.html#linux-and-macos).

## Windows

Open a PowerShell terminal and type the following commands to install and
configure micromamba for Windows:

```
Invoke-Webrequest -URI https://micro.mamba.pm/api/micromamba/win-64/latest -OutFile micromamba.tar.bz2
tar xf micromamba.tar.bz2

MOVE -Force Library\bin\micromamba.exe micromamba.exe
.\micromamba.exe --help

$Env:MAMBA_ROOT_PREFIX=$HOME\envs

.\micromamba.exe shell init -s powershell -p $HOME\envs
```

# Creating the environment for this course

We have created an [environment
file](https://github.com/LIBREhub/napari-LatAm-workshop-2023/blob/main/environment.yml)
for this course that specifies all the software needed to run the content in
the course. You can use micromamba to install it.

You will need to [download and
unzip](https://github.com/LIBREhub/napari-LatAm-workshop-2023/blob/47802d90420a3d4f3d5d4d40c01c9937ea7d1ab9/docs/how_to_download.png)
this repository. Then, navigate to the root of the repository in your Terminal
(macOS/Linux) or PowerShell (Windows), and type:

```
micromamba create -f environment.yml
```

Follow the prompts, then type:

```
micromamba activate napari-latam
napari
```

After some time (napari takes time to launch the first time), you should see a
napari window open. You should be able to click the menu `File > Open Samples >
clEsperanto > blobs (from ImageJ)` and see an image appear.

# Troubleshooting

## Graphics cards drivers

In case error messages contains "ImportError: DLL load failed while importing
cl: The specified procedure could not be found" [see
also](https://github.com/clEsperanto/pyclesperanto_prototype/issues/55) or
""clGetPlatformIDs failed: PLATFORM_NOT_FOUND_KHR", please install recent
drivers for your graphics card and/or OpenCL device. Select the right driver
source depending on your hardware from this list:

* [AMD drivers](https://www.amd.com/en/support)
* [NVidia drivers](https://www.nvidia.com/download/index.aspx)
* [Intel GPU drivers]()(https://www.intel.com/content/www/us/en/download/726609/intel-arc-graphics-windows-dch-driver.html)
* [Intel CPU OpenCL drivers](https://www.intel.com/content/www/us/en/developer/articles/tool/opencl-drivers.html#latest_CPU_runtime)
* [Microsoft Windows OpenCL support](https://www.microsoft.com/en-us/p/opencl-and-opengl-compatibility-pack/9nqpsl29bfff)

Sometimes, mac-users need to install this:

    micromamba install -c conda-forge ocl_icd_wrapper_apple

Sometimes, linux users need to install this:

    micromamba install -c conda-forge ocl-icd-system

In case installation didn't work in the first attempt, you may have to call this command line to reset the napari configuration:

```
napari --reset
```
