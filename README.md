### Automated Ensemble Photometry Pipeline for YSOs and AGN Variability Studies

A high-precision, automated Python-based data reduction and differential photometry pipeline designed for professional astrophysical applications. This software is specifically optimized for tracking millimagnitude-level flux variations in Young Stellar Objects (YSOs) before the Main Sequence (e.g., UX Orionis-type stars) and short-term optical variability in various classes of Active Galactic Nuclei (AGN). 

### Features

* **Instrumental Noise Calibration:** Full CCD/CMOS data reduction including master bias and master dark combining via sigma-clipped statistics, and normalized master flat-field division.
* **Cosmic Ray Rejection:** Built-in Laplacian cosmic ray detection using the **L.A.Cosmic** algorithm via astroscrappy to clean frames without degrading stellar PSF profiles.
* **Sub-pixel Image Alignment:** Automated spatial image registration using star-triangle pattern recognition via astroalign.
* **Relativistic Time & Airmass Correction:** Accurate transformation of UTC time-stamps from FITS headers into **BJD_TDB** (Barycentric Julian Date, Barycentric Dynamical Time) scale to eliminate light-travel time effects, along with mid-exposure geometric airmass estimation.
* **Ensemble Differential Photometry:** Automated detection of the brightest stable comparison stars to construct a virtual ensemble baseline, providing robust differential magnitude (Δ Mag) extraction immune to atmospheric extinction fluctuations.

### Software Architecture

The pipeline is structured within a unified Jupyter Notebook format across key scientific blocks: 

1. Data Reduction Module (Bias/Dark/Flat matrix operations)
2. Spatial Image Registration (Stellar alignment)
3. Barycentric Time Correction (BJD_TDB relativistic scaling)
4. Source Extraction & Aperture Photometry (DAOStarFinder implementation)
5. Dynamic Ensemble Differential Analysis & Light Curve Plotting

### Requirements

To deploy this environment on your system, install the core dependencies: 

bash

pip install astropy numpy ccdproc astroscrappy astroalign photutils pandas matplotlib scikit-image scipy astropy-iers-data

Използвайте кода внимателно.

### Data Input Structure

Organize your raw imaging data locally prior to runtime execution: 

📁 data
   └── 📁 raw
        ├── 📁 bias
        ├── 📁 darks
        ├── 📁 flats
        └── 📁 science

### License

This pipeline is open-source and available for the astronomical community under the MIT License.