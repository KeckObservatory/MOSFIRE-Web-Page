# Night Sky Lines

Night sky line spectra were acquired during May 2012 engineering. Below we present the flux from the night sky as measured by MOSFIRE. The first column of data is the flux density in units of (ergs/s/cm^2/Hz/arcsec^2) while the second column is the same data converted to ABmag/arcsec^2. The data are stored in FITS format.

These lists were developed and graciously provided by Dr. C. Steidel (mosfire team). 

| Band | Flux Density | AB Mag |
| ---- | ------------ | ------ |
| Y    | [FITS](figures/Ysky_psa_fnu.fits), [Plot](figures/y_psa_sky.jpg) | [FITS](figures/Ysky_abmag.fits), [Plot](figures/y_abmag_sky.jpg) |
| J    | [FITS](figures/Jsky_psa_fnu.fits), [Plot](figures/j_psa_sky.jpg) | [FITS](figures/Jsky_abmag.fits), [Plot](figures/j_abmag_sky.jpg) |
| H    | [FITS](figures/Hsky_psa_fnu.fits), [Plot](figures/h_psa_sky.jpg) | [FITS](figures/Hsky_abmag.fits), [Plot](figures/h_abmag_sky.jpg) |
| K    | [FITS](figures/Ksky_psa_fnu_long.fits), [Plot](figures/k_psa_sky.jpg) | [FITS](figures/Ksky_abmag.fits), [Plot](figures/k_abmag_sky.jpg) |

### NOTES

The FITS files contain the flux density and AB mag of the sky emission, respectively. The wavelength corresponding to the FITS data is stored in the FITS header. Two keywords are necessary to interpret the wavelength:

1. CRVAL1 - the wavelength for the first pixel.
2. CD1_1 or CDELT1 - the wavelength per pix scale.

The comments for both those keywords indicate that they refer to the RA. Ignore the comment and assume these two keywords are used to specify the wavelength. The plots above were created using the CRVAL1 and CD1_1 (CDELT1) keywords.
