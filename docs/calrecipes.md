# Calibration Recipes

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
