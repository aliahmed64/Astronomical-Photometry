# Astronomical Photometry

## Abstract
This project explores the statistical properties of Differential Photometry using a photometric routine calibration. We processed 433 FITS files to filter out bad images and extract photometry values for a Type Ia Supernova (SN) and reference stars. Our analysis involved applying a power-law fit to determine the maximum brightness of the SN and the epoch of the first light. The maximum brightness was found to be $22.12 \pm 0.53$ on 2015-10-08 at 05:01:12. The epoch of first light was estimated to be $t_1: -17.5 \pm 0.56$ using power-law fitting, compared to $t_1: -20.0 \pm 0.28$ from Minimum Chi-Square estimation.

## Introduction
Photometry is crucial in astronomy for measuring the light intensity from celestial objects. Differential photometry, which measures an object's brightness relative to a reference star, is used to study varying brightness over time. This lab focuses on creating a personalized photometry routine to analyze the light curve of a Type Ia supernova using the following equations:

- **Magnitude Calculation**: 
  $m_2 - m_1 = 2.512 \log \left(\frac{I_2}{I_1}\right)$
  where $m_1$ and $I_1$ are the magnitude and intensity of the SN, and $m_2$ and $I_2$ are those of the reference star.

- **Power-Law Fit**: 
  $I(t) = c (t - t_1)^2$
  where $t$ is time, $C$ is a fitting coefficient, and $t_1$ is the epoch of the first light.

- **Chi-Square Calculation**: 
  $\chi^2 = \sum_{i=1}^N \left(\frac{x_i - \mu_i}{\sigma_i}\right)^2$
  where $\mu_i$ are expected values and $x_i \pm \sigma_i$ are observed values.

## Observations and Data
The data for this lab consisted of 433 CCD images in FITS format, capturing a Type Ia supernova (AST325-326-SN) from September 20 to October 30, 2015. The images were centered at (RA, DEC) = (00:57:03.19, -37:02:23.6). The reference stars used for photometric calibration are listed in the table below:

| Reference Star | (RA, DEC)          | B-band Magnitude | (x, y) Coordinates    |
|----------------|---------------------|------------------|-----------------------|
| REF 1          | 00:56:49.70, -37:01:38.31 | 16.32 ± 0.07    | (1532.79, 1242.23)   |
| REF 2          | 00:56:46.43, -37:02:29.50 | 17.16 ± 0.08    | (1634.05, 1114.32)   |
| REF 3          | 00:56:58.27, -36:58:16.60 | 15.61 ± 0.02    | (1263.80, 1747.94)   |

## Data Reduction & Methods
The data was processed using Python packages like NumPy and Matplotlib. The analysis included:

1. **Centroiding Function**: Identified the centroid and intensity of reference stars. Bad images (with errors or missing stars) were discarded.
2. **Aperture Photometry Function**: Measured the photometry values of reference stars and the SN. Images with invalid aperture sizes were removed.
3. **Photometry Calculation**: Analyzed the intensity values and performed a light curve analysis.

After filtering, 357 good images remained out of 433.

## Data Analysis & Modelling
The magnitude of the SN was calculated and fitted using a power-law model. The best-fit line indicated a maximum brightness of $22.12 \pm 0.53$ on 2015-10-08. The epoch of first light was estimated at $t_1: -17.5 \pm 0.56$ using power-law fitting and $t_1: -20.0 \pm 0.28$ from Minimum Chi-Square estimation.

## Discussion & Conclusion
The photometric routine allowed us to estimate the SN's maximum brightness and the epoch of first light. The estimated values align with historical data suggesting typical Type Ia SN behavior. Future work should focus on improving filtering techniques to reduce errors and refine the data analysis.

## Appendix
- [Data Source](http://www.astro.utoronto.ca/astrolab/)
- Test images for Centroiding and Aperture Photometry Functions
- Magnitude calculations with different reference stars

## References
1. Dae-Sik Moon, "Lab 3 Astronomical Photometry". [Lab Document](http://www.astro.utoronto.ca/astrolab/)
2. Astronomy 325/326 Course Website. [Course Website](http://www.astro.utoronto.ca/astrolab/)
