# README.md

### PLEASE NOTE: This guide may not be accurate and will be depending on user feedback for updates.

This guide will help you get a Virtual Hackintosh working on your iOS / iPadOS device via UTM. The virtual machine relies on OpenCore from the [ultimate-macOS-KVM](https://github.com/Coopydood/ultimate-macOS-KVM/tree/main/resources/oc_store/compat_new) repository. 

Currently macOS 10.14.1 Mojave is tested to work on an iPhone 13 mini under this method.


# Requirements
First you'll need:
 - an iPhone or iPad (should be 4 GB or larger); Apple Vision Pro could work
 - UTM (with JIT) or UTM SE
 - a copy of the template from the Releases tab

Install [UTM SE](https://apps.apple.com/us/app/utm-se-retro-pc-emulator/id1564628856) from the App Store or [UTM](https://alt.getutm.app) from sideloading it via AltStore.

Note: UTM SE tends to not use JIT and other technical gimmicks in order to work properly but it's much slower and more time-consuming than the normal UTM app. So it's recommended to use UTM and know how to enable JIT for a more faster experience.

# Downloading a macOS Installer ISO
Can't put a direct link here, Apple will be *peeved*.

Google *macos collection*, and look for an *archive* 😏

# Setting up
You can download the template of the VM from the [Releases](https://github.com/chartersamster/macOSVM-iOS/releases) page. Unzip the file and copy/paste it to a folder/path you'd like it to be in. Then open in UTM, head to settings > Import Drive > Select the Installer .iso you downloaded. Now click save, start the VM, and profit.
Or you can create your own if you'd like. For me, I would make a UTM VM like this:

1. Head to UTM or UTM SE and click the (+) symbol.
   
2. (For UTM) Press the one with the turtle (Emulate). (For UTM SE) Just tap on New Machine.
   
3. Press Other and press Browse... for your ISO. Leave Legacy Hardware unchecked, unless otherwise.

4.  Set the RAM and CPU cores, I recommend 2048 MB as your RAM and 2 Cores as your CPU cores.

5. Set the disk to 128 GB or so.

6. Leave it as it is, no need to enable sharing as it is not supported.

7. Review your settings and if neccessary, rename "Virtual Machine" to the ones that best describes your VM, and press Save.

8. We're not done yet, head to the Settings icon. Then press Import Drive... and select the OpenCore disk (.qcow2) you downloaded from the [above source](https://github.com/Coopydood/ultimate-macOS-KVM/tree/main/resources/oc_store/compat_new) and the installer ISO you also downloaded. Now order OpenCore to the first set of the list so the BIOS can boot from the drive first.

9. Head to QEMU settings and scroll down until you see "New...". Press on that field and input the following:
* -device isa-applesmc,osk=ourhardworkbythesewordsguardedpleasedontsteal(c)AppleComputerInc (note: not putting this in will result in the VM failing to boot after installation!)

* -cpu SandyBridge-IBRS,vendor=GenuineIntel,+vmx,vmware-cpuid-freq=on,+invtsc,+hypervisor,+avx,+ssse3,+sse4.2,hv-relaxed (note: Other CPUs won't work! They may put the VM in a kernel panic or they may fail the FIPSPOST test!)
  
* -smbios type=2 (may be optional)


### 10: Save and boot up the virtual machine.

# Installing macOS
After you save and start the VM for the first time, just follow the steps as you normally would do when using OpenCore on real hardware.

# Info regarding using UTM for this guide 
If you want to use the UTM (not UTM SE) method you have to acknowledge that you must enable JIT every time you close the app. You can [refer to this site](https://jkcoxson.com/jitstreamer) (*deprecated, download StikDebug from the App Store, it's the easiest way) for steps on how to enable JIT. 

If you have an iPhone X or older, you can jailbreak with palera1n and enable JIT without any problems.

If you also have an iPad with an A11 chip or older you can also jailbreak with palera1n and enable JIT.

If you have iOS 16.6.1 or earlier and you have a device with an A16 chip or older (or an M1 or M2 chip for iPad), you can jailbreak with dopamine OR install TrollStore without jailbreak.
