# Lenovo Ideapad 330-15arr Hackintosh

# Still no Vega 8 support. 

For experiments or fun only. Not stable. At all. Possible to use for other laptops with same Ryzen 2500u/Vega 8  configuration

If you have any fixes related to that laptop or any Ryzen laptops - you are welcome

Currently possible to install High Sierra (not recommended), Mojave and latest Catalina (10.15.6 beta)
Possible to install High Sierra and Mojave with Clover, Catalina is bootable only with OpenCore

![photo_2020-06-20_05-41-51](https://user-images.githubusercontent.com/38903713/85189609-28b70b80-b2b9-11ea-982b-f5473eabc9e1.jpg)

## What's working (Catalina 10.15.6 beta 19G46c):

1) Intel Bluetooth (Realtek WiFi+bluetooth card was replaced with Intel one)
2) Intel WiFi (3165) - is working very stable with latest kext *itlwm* from @zxystd. Great work! 
2) Keyboard
3) SATA
4) Ethernet 
5) Battery icon (with patching or using SMCBattery.kext)
6) Camera 
7) Card-reader
8) USB-C
9) SMCAMDProcessor.kext is fully working now (managing PStates and etc is working well, except SMC Fans, ofc)

## What's partially working:

1) USB (it has random stuck while booting, we still don't know how to fix it. We already did USB mapping, tried SSDT and kext variants - it still randomly stuck on booting. Will try some trick with DSDT patching, might work)
Possible to reach stable booting only with GenericUSBXHCI.kext, but we won't be able to use USB tethering and no ports will appear for mapping (USB devices will work)

Somehow it's more stable with latest OC and latest Catalina, but it's still random

`You might won't have that issue if you have another brand of laptop (HP, Acer, e.t.c, because we have already seen some laptops (ex. MSI Alpha 15 has no problems with USB at all) with no problems at all even without USB mapping. That issue is surely related to dirty DSDT of Lenovo`

2) Graphics (lul, it has 7mb VRAM, so it's partially working, right? :D)
3) Audio is glitching and desynced

## What's not working:

1) DGPU is a no go, Radeon 535/540 is connected through Vega 8 to display, it has no connectors to HDMI or display at all. So, disable it in BIOS, if you have one (or make it disabled with SSDT patch)
2) Touchpad is a no go too, because it's connected to AMD controller, while VoodooI2C has support only for Intel controllers. Until there is no support for AMD based laptops - there will be no support for touchpads for sure. 
3) No brightness control = no graphics support
4) HDMI
