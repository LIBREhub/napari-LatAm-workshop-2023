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

<object data="https://github.com/LIBREhub/napari-LatAm-Workshop-2023/blob/napari-superres/docs/day3/napari-superres/napari-superres_installation_guide.pdf" type="application/pdf" width="900px" height="700px">
    <embed src="https://github.com/LIBREhub/napari-LatAm-Workshop-2023/blob/napari-superres/docs/day3/napari-superres/napari-superres_installation_guide.pdf">
        <p>This browser does not support PDFs. Please download the PDF to view it: <a href="https://github.com/LIBREhub/napari-LatAm-Workshop-2023/blob/napari-superres/docs/day3/napari-superres/napari-superres_installation_guide.pdf">Download PDF</a>.</p>
    </embed>
</object>
