Backlight control fix Sierra 

https://www.tonymacx86.com/threads/guide-laptop-backlight-control-using-applebacklightinjector-kext.218222/

1) Add SSDT-PNLF.aml to clover/ACPI/Patched
2) Add to Kernal and Kext Patches/ KextToPatch Name: com.apple.driver.AppleBacklight find: 46257554 25303478 00 Replace: 46257554 78787878 00
3) Install AppleBacklightInjector.kext to /L/E:
4) Remove IntelBackLight.kext in /L/E:
Reboot 

Rebuild kext
sudo kextcache -i /
