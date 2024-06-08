# Tunerpo-aldl-wb-plugin
Tunerpro RT data acquistion plugin for ALDL and wideband O2

Version 1.3 simplified data handling, compatibility enhanced with different ECM models

* 8192 baud ALDL
* Innovate or Aem WB with serialport connection
* Plx WB. Not tested, please report all tests, success or failure!

* Tested with 1989 TPI engine, should work with other 8192baud ALDL vehicles
* Tested with 16197427 ECM
* Tested with Innovate MTX-L, should work with other models
* Tested with Aem X-series Uego, should work with other models

* Warning! Beta software. No warranty! Use at your own risk!
  * Requires VC++ 2019 runtime: https://support.microsoft.com/en-us/help/2977003/the-latest-supported-visual-c-downloads vc_redist.x86.exe

Instructions:

- modify datastream definition, add AFR to datastream:

- Uncheck ADX Header Data: "RSR232 Echo"
- Setup Values, Wideband AFR:
  - Packet offset: 60 (Or other value, will replace original bytes 60 & 61)
  - Source Data size: 16 Bit
  - Conversion for Innovate : (X/1000 + 0.5)*14.7 
  - Conversion for Aem: X/10
  - Conversion for Plx: (X/25.5) + 10

You can also replace another value in datastream with AFR value, setup "AFR word position" in plugin settings.
* Warning! beta software

If Tunerpro crash, remove file ??\Documents\TunerPro Files\Plugins\Aldl-WB-Plugin.dll
