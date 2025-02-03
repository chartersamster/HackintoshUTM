# README.md
This guide will help you get emulated macOS working on your iOS / iPadOS device via UTM. The virtual machine relies on OpenCore from the [ultimate-macOS-KVM](https://github.com/Coopydood/ultimate-macOS-KVM/tree/main/resources/oc_store/compat_new) repository. 

macOS 10.14.1 Mojave is tested to work on an iPhone 13 mini (see image below):


# Requirements
First you'll need an iPhone or iPad capable enough to run the OS without any problems (iPhone 11 Pro / iPad Pro, to be exact). Then you (obviously) need UTM / UTM SE to run the VM and install macOS on.

Install [UTM SE](https://apps.apple.com/us/app/utm-se-retro-pc-emulator/id1564628856) from the App Store or [UTM](alt.getutm.app) from sideloading it via AltStore.

Note: UTM SE tends to not use JIT and other technical gimmicks in order to work properly but it's much slower and more time-consuming than the normal UTM app. So it's recommended to use UTM and know how to enable JIT for a more faster experience.

A macOS Installer ISO is necessary for this guide. You can download an installer .iso by clicking [here](https://archive.org/details/macos-collection).

# Setting up
You can download the template from the [Releases](https://www.nicksherlock.com/) page, or you can create your own if you'd like.
