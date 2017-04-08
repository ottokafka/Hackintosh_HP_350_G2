Fix usb speed 

step 1: install FakePCiid.kext and Fake_XHCIMUX.kext using kext utility


step 2: place FakePCiid.kext and Fake_XHCIMUX.kext
copy kext to EFI/Clover/kext

step 3: In the ACPI / FIXES section untick ‘FIXUSB’
In the DEVICES / USB section untick ‘Inject’ ‘Add ClockID’ ‘FixOwnership’ and ‘HighCurrent’
In the Rt Variables section set your booterconfig to 0x28 and CsrActiveConfig to 0x67

step 4: play ssdt-xosi in clover/acpi/patched

step 5:First open clover configurator and mount your EFI partition, open your config.plist. Under the ACPI section you need to add a DSDT Patch.

click the little + icon on the right
for comment put "change _OSI to XOSI"
for find* [HEX] put "5F4F5349"
for Replace* [HEX] put "584F5349"



reboot

If that fails follow this guide: https://www.tonymacx86.com/threads/usb-fixes.179056/#post1152921

