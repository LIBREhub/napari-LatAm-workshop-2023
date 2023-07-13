# napari-superres

A plugin for super-resolution microscopy FF-SRM methods.

Open-source implementation of methods for Fluorescence Fluctuation based Super Resolution Microscopy (FF-SRM):

Review: [Alva et al., 2022. “Fluorescence Fluctuation-Based Super-Resolution Microscopy: Basic Concepts for an Easy Start.” Journal of Microscopy, August.](https://onlinelibrary.wiley.com/doi/10.1111/jmi.13135)

MSSR article: [Torres-García, E., Pinto-Cámara, R., Linares, A. et al. Extending resolution within a single imaging frame. Nat Commun 13, 7452 (2022).](https://doi.org/10.1038/s41467-022-34693-9)

ESI article: [Idir Yahiatene, Simon Hennig, Marcel Müller, Thomas Huser (2015/2016). "Entropy-based Super-resolution Imaging (ESI): From Disorder to Fine Detail" ACS Photonics 8, 2 (2015)](https://doi.org/10.1021/acsphotonics.5b00307)

SOFI article: [T. Dertinger, R. Colyer, G. Iyer, and J. Enderlein. Fast, background-free, 3D super-resolution optical fluctuation imaging (SOFI). PNAS 52, 106 (2009) ](https://doi.org/10.1073/pnas.0907866106)

SRRF article: [Salsman, J.,  and, Dellaire, G., Super-Resolution Radial Fluctuations (SRRF) Microscopy, Methods in Molecular Biology 2440 (2022)](https://link.springer.com/protocol/10.1007/978-1-0716-2051-9_14)

MUSICAL article: [K. Agarwal and R. Machan, Multiple Signal Classification Algorithm for super-resolution fluorescence microscopy, Nature Communications, vol. 7, article id. 13752, (2016)](https://www.nature.com/articles/ncomms13752)



Methods implemented:
- MSSR
- ESI
- SOFI
- SRRF
- MUSICAL
- Split channels

Repositories available:
- [ESI](https://github.com/biophotonics-bielefeld/ESI) GitHub repository
- [PySOFI](https://github.com/xiyuyi-at-LLNL/pysofi) GitHub repository
- [MUSICAL](https://sites.google.com/site/uthkrishth/musical) Google site

----------------------------------

## Installation
First install napari viewer:

    conda create -y -n napari-env -c conda-forge python=3.9
    conda activate napari-env
    pip install "napari[all]"

For details check: https://napari.org/stable/


o install latest development version :

    pip install git+https://github.com/RoccoDAnt/napari-superres.git

You might need to install [git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) first.

Alternatively you can install the plugin graphically:

<object data="napari-superres_installation_guide.pdf" type="application/pdf" width="1200px" height="700px">
    <embed src="napari-superres_installation_guide.pdf">
        <p>This browser does not support PDFs. Please download the PDF to view it: <a href="napari-superres/napari-superres_installation_guide.pdf">Download PDF</a>.</p>
    </embed>
</object>


----------------------------------
Examples of use:

| **Original**  | **tMSSR** |
| --- | --- |
| <p align="center"> <img src="https://raw.githubusercontent.com/RoccoDAnt/napari-superres/main/docs/single-frame-good-exposure.png" width=100% height=100%> </p>| <p align="center"> <img src="https://raw.githubusercontent.com/RoccoDAnt/napari-superres/main/docs/tmssr-mean-mag2.png" width=48% height=48%> </p>|
| Parameters: | Amplification: 2, Order: 0, PSF FWHM: 6, <br> Interpolation: Bicubic, Statistical integration: CV*sigma |

| **Original**  | **ESI** |
| --- | --- |
| <p align="center"> <img src="https://raw.githubusercontent.com/RoccoDAnt/napari-superres/main/docs/synt.png" width=40% height=40%> </p> | <p align="center"> <img src="https://raw.githubusercontent.com/RoccoDAnt/napari-superres/main/docs/ESI.png" width=50% height=50%> </p> |
| Parameters: | image in output: 2, bins: 2, Order: 2 |

| **Original**  | **SOFI** |
| --- | --- |
|<p align="center"> <img src="https://raw.githubusercontent.com/RoccoDAnt/napari-superres/main/docs/noSOFI.png" width=100% height=100%> </p> | <p align="center"> <img src="https://raw.githubusercontent.com/RoccoDAnt/napari-superres/main/docs/SOFI.png" width=100% height=100%> </p> |
| Parameters: | Amplification factor: 2, Moment Order: 4, lambda parameter: 1.5, No. Iterations: 20, Window size: 100|

| **Original**  | **SRRF** |
| --- | --- |
|<p align="center"> <img src="https://raw.githubusercontent.com/RoccoDAnt/napari-superres/main/docs/synt.png" width=50% height=50%> </p> | <p align="center"> <img src="docs/SRRF.png" width=50% height=50%> </p>|
| Parameters: | Amplification: 2, Spatial radius: 5, Symmetry Axis: 6, Start frame: 0, End frame: 48|

| **Original**  | **MUSICAL** |
| --- | --- |
| <p align="center"> <img src="docs/musical_mean.png" width=70% height=100%> </p> | <p align="center"> <img src="docs/MUSICAL-CardioMyoblast_Mitochondria.png" width=70% height=100%> </p>|
| Parameters: | Emission [nm]: 510 NA: 1.4, Mag: 100, Pizel size: 8000, Threshold: -0.5, Alpha: 4, Subpixels per pixel: 20|
----------------------------------
