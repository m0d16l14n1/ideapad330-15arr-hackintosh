# Lenovo Ideapad 330-15arr Hackintosh

# Still no Vega 8 support. 

For experiments or fun only. Not stable. At all. Possible to use for other laptops with same Ryzen 2500u/Vega 8  configuration

If you have any fixes related to that laptop - you are welcome

Currently possible to install High Sierra (not recommended), Mojave and latest Catalina (10.15.4)
Possible to install High Sierra and Mojave with Clover, Catalina is bootable only with OpenCore

# What's working (Catalina 10.15.5 19F83c):

1) Intel Bluetooth (Realtek WiFi+bluetooth card was replaced with Intel one, i really hope for feature developments on IntelWifi.kext)
2) Keyboard
3) SATA
4) Ethernet 
5) Battery icon (with patching or using SMCBattery.kext)
6) Camera 
7) Card-reader
8) USB-C

# What's partially working:

1) USB (it has random stuck while booting, we still don't know how to fix it. We already did USB mapping, tried SSDT and kext variants - it still randomly stuck on booting. Will try some trick with DSDT patching, might work)
Possible to reach stable booting only with GenericUSBXHCI.kext, but we won't be able to use USB tethering and no ports will appear for mapping (USB devices will work)

`You might won't have that issue if you have another brand of laptop (HP, Acer, e.t.c, because we have already seen some laptops (ex. MSI Alpha 15 has no problems with USB at all) with no problems at all even without USB mapping. That issue is surely related to dirty DSDT of Lenovo`

2) Graphics (lul, it has 7mb VRAM, so it's partially working, right? :D)
3) Audio is glitching and desynced
4) SMCAMDProcessor.kext is working (AMD Power Gadget + sensors, AMD Power tool is not working /*force close*/)

# What's not working:

1) DGPU is a no go, Radeon 535/540 is connected through Vega 8 to display, it has no connectors to HDMI or display at all. So, disable it in BIOS, if you have one (or make it disabled with SSDT patch)
2) Touchpad is a no go too, because it's connected to AMD I2C controller, while VoodooI2C has support only for Intel controllers. Until there is no support for AMD based laptops - there will be no support for touchpads for sure. 
3) No brightness control = no graphics support
4) WiFi
5) HDMI
