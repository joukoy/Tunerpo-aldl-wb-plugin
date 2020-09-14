# Tunerpo-aldl-wb-plugin
Tunerpro RT data acquistion plugin for ALDL and wideband O2

* 8192 baud ALDL
* Innovate or Aem WB with serialport connection

* Tested with 1989 TPI engine, should work with other 8192baud ALDL vehicles
* Tested with Innovate MTX-L, should work with other models
* Tested with Aem X-series Uego, should work with other models

* Warning! Beta software. No warranty! Use at your own risk!
  * Requires VC++ 2019 runtime: https://support.microsoft.com/en-us/help/2977003/the-latest-supported-visual-c-downloads vc_redist.x86.exe

Instructions:

- modify datastream definition, add AFR to END of datastream:

- Uncheck ADX Header Data: "RSR232 Echo"
- Mode 1 dump reply: Add 2 bytes to Body size (67 => 69)
- Mode 1 dump reply: Add 3 bytes to Payload size (63 => 66)
- Setup Values, Wideband AFR:
  - Packet offset: 64 (AFR word position - 3 header bytes)
  - Source Data size: 16 Bit
  - Conversion for Innovate : (X/1000 + 0.5)*14.7 
  - Conversion for Aem: X/10

You can also replace another value in datastream with AFR value, in this case leave Body size & Payload size unmodified and setup "AFR word position" in plugin settings.
* Warning! beta software

If Tunerpro crash, remove file ??\Documents\TunerPro Files\Plugins\Aldl-WB-Plugin.dll
