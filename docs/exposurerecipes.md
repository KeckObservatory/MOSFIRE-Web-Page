# Recommended Exposure Times

In determining the optimal exposure times for near-IR observations, observers must weigh the trade-offs between exposure cadence and the contribution of detector noise. The desire to accurately subtract the rapidly varying OH emission drives one toward shorter individual exposures; we (the MOSFIRE team) have found from experiment that the characteristic timescale for variation of OH lines by more than 0.1% is ~30s, meaning that to optimize for removing OH, the background needs to be sampled on < 30 s timescales, usually through short exposures with small offsets along the slit (or slits). However, such observations are not optimal for obtaining the highest S/N in spectral regions between OH emission lines where the background is much lower. To take advantage of the low background (see the minimum count rates in the table), the noise from counting statistics in the background must be larger than the noise associated with reading the detector.

As listed in the table on the MOSFIRE detector page, the effective read noise upi can achieve depends on the number of Fowler pairs (non-destructive reads) selected in MCDS readout mode; for example, 8 reads yields 7.7e- rms noise, 16 reads gives 5.8e-, and 32 reads allows 4.2e-. Because the clock time per non-destructive read is 1.455 seconds, larger numbers of reads translate into additional overhead equivalent to N_pairs×1.455s, or 11.6 s for 8 reads, 23.3 s for 16 reads, 46.6 s for 32, etc.

The bottom line is that if accurate subtraction of OH emission from the night sky is important to your observing program (e.g., if your targets are bright and detector noise is not an issue) then dwell times at each nod position should be short, <=30 s. In general, though, one would like to achieve accurate background subtraction with the lowest possible noise both near OH lines and between them, where the sky is quite dark. This requires a compromise. 

## Spectroscopic Mode

Accounting for the brightness of the OH lines in each atmospheric band, we recommend the following readout modes and integration times for spectroscopy of faint targets. These are examples that have been tested on-sky with MOSFIRE and demonstrated to yield clean OH subtraction while simultaneously being nearly background limited in the darkest portions of the band between OH lines.

Please note that the background numbers all assume MCDS16 sampling mode and the default 0.7” slits; please scale accordingly if you are using non-standard slit width.

| Filter | ExpTime<br>(s) | Overhead<br>(s) | Observing Efficiency | Sky Noise<br>(e-) | Total Noise<br>(e-) |
| ------ | ------- | -------- | ------------------ | ------- | --------- |
| Y      | 180     | 23.3     | 89%                | 7.8     | 9.7       |
| J      | 120     | 23.3     | 84%                | 6.0     | 8.3       |
| H      | 120     | 23.3     | 84%                | 8.3     | 10.1      |
| K      | 180     | 23.3     | 89%                | 8.4     | 10.2      |

Thus, for example, one might request a “mask nod” sequence of 10 repeats of a 2-position dither pattern in K (meaning a total of 20×180 s exposures, comprised of 10 exposures at position A and 10 at position B). This sequence would require 20×(180+23.3)=4066 s for MCDS16 mode, not including the time for offsetting the telescope (roughly 3-4 seconds per dither). The clock time would then be approximately 4150 s for 3600 s of integration on source. 

## Imaging Mode

Use these exposure times for on-sky observations of targets fainter than the night sky.  

| Filter | ExpTime<br>(s) | Sky Level<br>(ADU/pix) | Sky Brightness<br>(e-/pix/s) | Sky Brightness<br>(Vega mag/arcsec^2) | Sky Brightness<br>(AB mag/arcsec^2) |
| ------ | ------- | --------- | -------------- | -------------- | -------------- |
| Y      | 30      | 5,600     | 730-820        | 17.44          | 18.09 |
| J      | 10.2    | 11,700    | 950-1350       | 15.78          | 16.58 |
| H      | 2.9     | 13,600    | 4160-5570      | 13.74          | 15.14 |
| Ks     | 5.9     | 10,200    | 2300-2700      | 13.68          | 15.54 |
| J2     | 25      | 11,700    | 470            |  |  |
| J3     | 30      | 11,160    | 372            |  |  |
| H1     | 4.4     | 11,352    | 2640           |  |  |
| H2     | 4.3     | 11,910    | 2770           |  |  |

## Dome Flat Exposure Times

Use the exposure times listed below to obtain well-exposed images with the MOSFIRE spectral lamp on Keck I. The goal is to achieve a peak illimination of about 13,000 DN/px, which remains well within the regime in which the detector response is linear to within 1%. Note that the exposure times listed below apply to 0.7 arcsec slits; to derive appropriate values for other slit widths, please scale the listed exposure times inversely by slit width. 

| Filter | ExpTime<br>(s) | Actual ExpTime<br>(s) | Lamp Power Level | Count Rate<br>(ADU/pix/s) | Peak Counts<br>(ADU) |
| ------ | ------ | ------------- | ---------------- | ----- | ----------- |
| Y      | 17     | 16.004        | 4                | 800   | 12000-13000 |
| J      | 11     | 10.184        | 9                | 1200  | 12000-13000 |
| H      | 11     | 10.184        | 13.5             | 1200  | 12000-13000 |
| K      | 11     | 10.184        | 14               | 1200  | 12000-13000 |

Notes
- Exptime: Value you should enter into the MOSFIRE exposure control GUI.
- Actual ExpTime: The resulting “true” MOSFIRE integration time (quantized by 1.455 s).
- The MOSFIRE Calibration Tool opened through MAGMA will manage spectral flats including dome lamp control and power level settings. Other means to turn on the flat lamps include:
    - Via keyword, type: `domelamps mos K` (or appropriate filter) and this will set the power level automatically.
    - Or from the pulldown menu, `Telescope Status Menu --> Dome Lamp control GUI`
    - Power level applied to the MOSFIRE dome lamp (range 0-20) by the calibration script to achieve the desired signal level.


## Spectrophotometry Dome Flat Exposure Times

For a 15 arcsecond wide slit, use the exposure times listed below to obtain well-exposed data with the MOSFIRE spectral lamp on Keck I when using wide slits. This is a manual procedure. The goal is to achieve a peak illimination of about 13,000 DN/px, which remains well within the regime in which the detector response is linear to within 1%. 

| Filter | ExpTime<br>(s) | Actual ExpTime<br>(s) | Lamp Power Level | Count Rate<br>(ADU/pix/s) | Peak Counts<br>(ADU) |
| ------ | ------- | -------------- | ---------------- | -------------- | ----------- |
| K      | 2 s     | 1.455 s        | 17.5             | 6900           | 10000-11000 | 

#### Procedure

- Insert Dark filter
- Setup CSU
- Open the hatch
- Turn on flat lamps: `flatlamp on 17.5`
- Acquire flats
- Turn off flat lamps: `flatlamp off`
- Insert Dark filter 

## Imaging Dome Flats

Use these exposure times to obtain well-exposed images with the Dome Lamps (new), the same lamps used for spectroscopy. The goal is to achieve a peak illimination of less than 18,000 DN/px, which remains well within the regime in which the detector response is linear to within 1%. 

| Filter | ExpTime<br>(s) | Actual ExpTime<br>(s) | Lamp Power Level | Count Rate<br>(ADU/pix/s) | Peak Counts<br>(ADU) |
| ------ | ------ | ------------- | ---------------- | ----- | ----- |
| Y      | 6      | 5.8           | 20               | 2400  | 14000 |
| J      | 15     | 14.3          | 19.5             | 900   | 15000 |
| H      | 6      | 5.8           | 20               | 2300  | 13500 |
| Ks     | 2      | 1.455         | off              | 5500  | 8000  |

Please note that the dome flat lamp brightness varies and the J- and H-band imaging flats may saturate. If this happens, we recommend taking twilight flats instead. For twilight flats, we can use the box9 command in a mosfire server terminal to take flat images with 9-point dithering.

# A0V Calibrators

Spectral type A0V stars are typically preferred for calibrating IR spectra because they have a minimum of instrinsic lines in their spectra. A handy list of such stars suitable for observing with MOSFIRE appears below. The recommended exposure times were scaled from the values determined for 20s exposures acquired during commissioning. 

| Target    | V mag | Filter | ExpTime<br>(s) | Continuum Rate<br>(ADU/pix/s) | OH Peak Rate<br>(ADU/pix/s) |
| --------- | ----- | ------ | ------ | ----------- | ------ |
| HD 22859  | 7.80  | Y      | 10     | 575         | 575    |
|           |       | J      | 10     | 550         | 575    |
|           |       | H      | 2      | 1550        | 1750   |
|           |       | K      | 10     | 700         | 750    |
| HD 199006 | 9.10  | H      | 10     | 425         | 700    |

Notes:

- Data from I. McLean and G. Mace (UCLA)
- All data were taken with the default 0.7" slit width. 

## A0V Throughput List

The list below is used by MOSFIRE instrument scientists to monitor thoughput of the instrument. These stars are AO stars and were selected to span a range of RA and have declinations near +19 deg. Typical exposure times for these standards are 6-10s for all bands. This list of stars is stored in the starlist file `/kroot/starlists/mosfire/standards`.

```
HIP13917           02 59 16.76 +01 14 40.4  2000.0 vmag=8.64  rotmode=pa rotdest=0
HIP17971           03 50 32.03 +29 44 41.7  2000.0 vmag=8.80  rotmode=pa rotdest=0
HIP23226           04 59 53.07 +27 19 13.5  2000.0 vmag=9.11  rotmode=pa rotdest=0
HIP24508           05 15 25.79 +15 37 48.4  2000.0 vmag=9.12  rotmode=pa rotdest=0
HIP30155           06 20 43.29 +15 41 39.1  2000.0 vmag=8.98  rotmode=pa rotdest=0
HIP43018           08 45 59.26 +13 15 48.6  2000.0 vmag=8.70  rotmode=pa rotdest=0
HIP55627           11 23 46.47 +34 14 33.7  2000.0 vmag=9.26  rotmode=pa rotdest=0
HIP56736           11 37 57.81 +15 46 36.8  2000.0 vmag=8.80  rotmode=pa rotdest=0
HIP61138           12 31 41.27 +22 07 24.4  2000.0 vmag=8.85  rotmode=pa rotdest=0
HIP64248           13 10 04.72 +12 19 13.2  2000.0 vmag=9.53  rotmode=pa rotdest=0
HIP68767           14 04 30.38 +21 23 17.3  2000.0 vmag=8.53  rotmode=pa rotdest=0
HIP87643           17 54 07.86 +16 56 37.8  2000.0 vmag=8.91  rotmode=pa rotdest=0
HIP98400           19 59 35.11 +11 53 21.7  2000.0 vmag=9.02  rotmode=pa rotdest=0
HIP98640           20 02 04.94 +12 19 19.5  2000.0 vmag=9.38  rotmode=pa rotdest=0
```

# Acknowledgements

Many thanks to the MOSFIRE team, especially Dr. C. Steidel, for providing these recomendations for our user community. 