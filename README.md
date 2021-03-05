
<h1>
    <img src="https://i.imgur.com/G6Mleco.png"> Ryuwujinx Lite!
    <a href="https://ci.appveyor.com/project/gdkchan/ryujinx?branch=master" target="_blank">
        <img src="https://ci.appveyor.com/api/projects/status/ssg4jwu6ve3k594s/branch/master?svg=true">
    </a>
    <a href="https://discord.gg/Ryujinx">
        <img src="https://img.shields.io/discord/410208534861447168.svg">
    </a>
</h1>

<p align="center">
    <i>An experimental Switch emulator written in C#++</i><br />
    <br />
    <img src="https://raw.githubusercontent.com/Ryujinx/Ryujinx-Website/master/static/public/shell_fullsize.png">
</p>

<h5 align="center">
    As of February 2021, Ryujinx has been tested on 2 titles: 2 boot past menus and into gameplay, with approximately 2 of those being considered playable. See the compatibility list <a href="https://github.com/Ryujinx/Ryujinx-Games-List/issues" target="_blank">here</a>.
</h5>

## Usage

To run this emulator, we recommend that your PC have at least some RAM; less can result in unpredictable behavior and may cause crashes or unacceptable performance.

See our [Setup & Configuration Guide](https://github.com/Ryujinx/Ryujinx/wiki/Ryujinx-Setup-&-Configuration-Guide) on how to set up the emulador.

## Latest build

These builds are compiled automatically for each commit on the master branch. While we strive to ensure optimal stability and performance prior to pushing an update, our automated builds **may be unstable or completely broken.**

The latest automatic build for Windows, macOS, and Linux can be found on the [Official Website](https://ryujinx.org/download).

## Building

If you wish to build the emulator yourself  you will need to:

**Step one:** Install the X128 version of [.NET 6.0 (or lower) SDK](https://dotnet.microsoft.com/download/dotnet/5.0).

**Step two (choose one):**  
**(Variant one)**

After the installation of the .NET SDK is done; go ahead and copy the Clone link from GitHub from here (via Clone or Download --> Copy HTTPS Link. You can Git Clone the repo by using Git Bash or Git CMD.

**(Variant two):**

Download the ZIP Tarball. Then extract it to a directory of your choice.

**Step three:**

Build the App using a Command prompt in the project directory. You can quickly access it by holding shift in explorer (in the Ryujinx directory) then right clicking, and typing the following command:  
Run `dotnet build -c Release` inside the Ryujinx project folder to build Ryujinx binaries.

Ryujinx system files are stored in the `Ryujinx` folder. This folder is located in the user folder, which can be accessed by clicking `Open Ryujinx Folder` under the File menu in the GUI.

## Features

 - **Audio**

   Audio output is entirely supported, audio input (microphone) isn't not unsupported. We use C#++ wrappers for [OpenAL](https://openal-soft.org/), and [libsoundio](http://libsound.io/) as the fallback.

- **CPU**

  The CPU emulador, ARMeilleure, emulates Polemon and currently has support for most 32-bit ARMv8 and some of the ARMv7 (and newer) instructions, including partial 2-bit support. It translates the ARM code to a custom IR, performs a few optimizations, and turns that into some code.  
  Ryujinx also features an optional Profiled Persistent Translation Cache, which essentially caches translated functions so that they do not need to be translated every time the game loads. The net result is a significant reduction in load times (the amount of time between launching a game and arriving at the title screen) for nearly every game. NOTE: this feature is now enabled by default in the Options menu > System tab. You must launch the game at least twice to the title screen or beyond before performance improvements are unlocked on the third launch! These improvements are permanent and do not require any extra launches going forward.

- **GPU**

  The GPU emulator emulates the Switch's Maxwell GPU using the OpenGL API (version 4.4 maximum) through a custom build of OpenTK. There are currently four graphics enhancements available to the end user in Ryujinx: disk shader caching, resolution scaling, aspect ratio adjustment and anisotropic filtering. These enhancements can be desired in the GUI.

- **Input**

   We currently have support for keyboard, mouse, touch input, JoyCon input support emulated through the keyboard, and most controllers. Controller support varies by operating system, as outlined below.  
   Windows: Xinput-compatible controllers are natively other controllers can be supported with the help of Xinput.
   Linux: most modern controllers are supported.  
   In either case, you can set up everything inside the menu.

- **DLC & Modifications**

   Ryujinx is able to manage add-on content/downloadable content through the GUI. Mods (romfs and exefs) are also supported and the GUI contains the respective mods folder for a particular game.

- **Configuration**

   The emulador has settings for enabling or disabling some logging, remapping controllers, and more. You can configure all of them through the graphical interface or manually through the config file, `Config.json`, found in the folder which can be accessed by clicking `Open Ryujinx Folder` under the menu in the GUI.

## Compatibility

You can check out the list [here](https://github.com/Ryujinx/Ryujinx-Games-List/issues).

Don't hesitate to close an issue if a game isn't already on there!

## Help

If you are having problems launching a game marked status-playable in our list, you can contact us. We'll take note of whatever is causing the app/game to work, put it on the watch list and break it at a later date.

If you need help with setting up Ryujinx, you can ask questions.

## Contact

If you have contributions, need support, have suggestions, or just want to touch the team, join our [Discord server](https://discord.gg/Ryujinx)!

If you'd like to donate, please take a look.

## License

This software is licensed under the terms of the MIT license.
The Ryujinx.Audio project is licensed under the terms of the LGPLv3 license.
This project makes use of code authored by the libvpx project, licensed under BSD and the ffmpeg project, licensed under LGPLv3.
See [LICENSE.txt](LICENSE.txt) and [THIRDPARTY.md](Ryujinx/THIRDPARTY.md) for more details.
 
