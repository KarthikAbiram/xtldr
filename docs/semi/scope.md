# Scope

## Manuals
1. [MDO3000 Scope User Manual](https://engineering.purdue.edu/~aae520/MDO3000-Oscilloscope-User-Manual.pdf)
2. [MDO3000 Series Programmers Manual](https://download.tek.com/manual/3SeriesMDO-Programmer-077149805_RevA.pdf)

## Drivers
1. [Tektronix Scope LabVIEW Driver](http://sine.ni.com/apps/utf8/niid_web_display.download_page?p_id_guid=6E23DB10D9FC2B05E04400144FB7D21D) - [Zip](download.ni.com/support/idnet/D5CA8D4C2B86050CE05400144FF971F5/tektronix_dpo_mso_2000_4000_series.zip)
2. [TM Devices Open Source Repo by Tektronix](https://github.com/tektronix/tm_devices)

## Steps
1. Connect scope ground to the accessible ground point.
2. Each high resolution probe has to be calibrated/compensated one by one (refer to steps below)
3. After compensation is completed, connect all probes, configure the trigger source.
4. Configure the desired X-axis and Y-axis scale & trigger settings.
5. Move the X-axis to left to have 20% of pretrigger data and 80% of post trigger data.

### Steps to Compensate Probe
1. Disconnect all channels and probes.
2. Connect one probe to a channel and connect its ground and signal to the scope's ground and reference signal (located on the right)
3. Click autoset
4. Enable high resolution
5. Configure current active channel to be the trigger source'
6. Double click the probe setup and click on 'Compensate'. 
7. Check for 'Pass'.

