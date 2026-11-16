# Evening Startup

## Start Guider Eavesdrop

The MAGIQ observer GUI allows you to monitor the image from the guide camera in real time. To launch it:

Go to the telstatus VNC viewer window.  From the FVWM background menu, select `K1 Guider Eavesdropping > Start Observer UI`

## Start FACSUM

The “Facilities Summary” or FACSUM window is a real-time display of the telescope status. Waimea-based observers can see it on the large wall-mounted monitor. Remote observers can run the window under VNC as follows:

Go to the telstatus VNC desktop, from the FVWM background menu, select `K1 telescope status menu > FACSUM`

## Start Xmet

Xmet is a meteorological display showing current summit temperature/dewpoint data. 

Go to the telstatus VNC desktop, from the FVWM background menu, select `K1 telescope status menu > XMET`

## Open the MOSFIRE Hatch

Command the hatch open to allow MOSFIRE to receive light from the telescope:

If you have not enabled the dust cover (weather prevented cals for instance) you need to select from the window manager pulldown menu: `MOSFIRE Control Menu -> Enable Dust Cover`

On the MOSFIRE Desktop, locate the Calibration GUI sub-window. If it's not visible, then click the light bulb icon at the top of the desktop.  On the calibration GUI, click the OPEN button to open the hatch.

## Select first target

In the starlist shown on MAGIQ, click the middle mouse button on the target you wish to begin observing; this will highlight the line in yellow on your MAGIQ GUI and also on the Observing Assistant's MAGIQ GUI. Providing this information to the OA before opening the dome may allow him or her to save time by pre-positioning the telescope. If you have other needs (e.g., twilight flats), this is a good time to advise the OA. 

## Configure CSU with first mask with MIRA

Configure the CSU with the first alignment mask. This will save time on sky to preconfigure the mask in advance of opening.

On MAGMA
- Click on the desired mask
- Click the MIRA box to setup for telescope focus.
- Click Setup Alignment Mask to send bar positions
- Click Execute Mask to configure the mask. Note if MIRA is selected the center of the mask will have an imaging area configured. 

## Start SAT

Start the [SAT (Slitmask Alignment Tool)](maskalignment.md) software used to align both longslit and multi-object slitmasks.

In a VNC window, select from the background menu: `MOSFIRE Utilities -> Slitmask Alignment Tool`.

In the SAT's Guider Coarse Align tab, click Load Star List to load your keck formatted starlist. Your starlist must contain the rotator positions of the fields. See starlists

Click Retrieve all Guider Images to query the DSS server for your guider fields and store them in the data directory. 

## Begin Observing

The Observing Assistant (OA) is not permitted to open the dome until after sunset. Please be patient while the shutter opens and the OA checks the initial telescope pointing. 

When ready to move the telescope, the OA will ask you for your first target and load the coordinates from your starlist file. He or she will select a bright star near your target and will attempt to acquire that in the guider, then will double-check the accuracy of pointing by acquiring one or two additional stars from the SAO or GSC catalogs. 

If you have set up the Mira mask as described above, ask the OA to run the telescope focus procedure (MIRA) near your science field. 
