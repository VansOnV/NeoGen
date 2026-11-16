<p align="center">
  <a href="NeoGenGUI.png"><img src="NeoGenGUI.png" alt="NeoGen GUI" width="720"></a>
</p>

# NeoGen GUI

**Open-Source GUI Toolkit for modding GTA V PS4**

[![License: MIT](https://img.shields.io/github/license/VansOnV/NeoGen)](LICENSE)
[![Latest release](https://img.shields.io/github/v/release/VansOnV/NeoGen?include_prereleases)](https://github.com/VansOnV/NeoGen/releases)
[![Stars](https://img.shields.io/github/stars/VansOnV/NeoGen?style=flat)](https://github.com/VansOnV/NeoGen/stargazers)
![Platform: Windows](https://img.shields.io/badge/platform-Windows-0078D6)
[![Discord](https://img.shields.io/badge/chat-Discord-5865F2)](https://discord.gg/buC9W643tQ)

---

## Table of contents

- [About](#about)
- [Features](#features)
- [Setup](#setup)
- [Building from source](#building-from-source)
- [Contributing](#contributing)
- [Support](#support)
- [Credits](#credits)
- [License](#license)

## About

Modding Grand Theft Auto V on the PlayStation 4 is now possible! With the help of homebrew plugins like Project V and Orbx Engine (by rfoodxmodz), modding is as easy as copy-pasting files. With the help of this tool, it will make it even easier!

## Features

### 📦 Resource Files Conversion (`.y##` ⇄ `.o##`)

**🎮 Model & Resource Formats (Patched & Converted)**

| Conversion Pair   | Description                                                      |
| :---------------- | :--------------------------------------------------------------- |
| `.ytd` > `.otd`   | Texture Dictionary (Also has custom compression options)         |
| `.yft` ⇄ `.oft`   | Fragment models (vehicles, destructible objects)                 |
| `.ydr` ⇄ `.odr`   | Drawable models (props, components)                              |
| `.ydd` ⇄ `.odd`   | Drawable dictionaries (multi-model collections)                  |
| `.ypt` ⇄ `.opt`   | Particle effect data                                             |
| `.ybn` ⇄ `.obn`   | Collision bounds                                                 |
| `.ybd` ⇄ `.obd`   | Bounds dictionaries                                              |
| `.yld` ⇄ `.old`   | Cloth simulation data                                            |
| `.yed` ⇄ `.oed`   | Expression dictionaries                                          |
| `.yfd` ⇄ `.ofd`   | Frame filter dictionaries                                        |
| `.ynd` ⇄ `.ond`   | Path nodes (AI navigation)                                       |
| `.ynv` ⇄ `.onv`   | Navigation meshes                                                |
| `.yvr` ⇄ `.ovr`   | Vehicle recording data                                           |
| `.ywr` ⇄ `.owr`   | Waypoint recordings                                              |
| `.ypdb` ⇄ `.opdb` | Pose matching databases                                          |

**🧵 vcWXML (embedded textures)**

| vcWXML                    | Description                                                                                                                          |
| :------------------------ | :----------------------------------------------------------------------------------------------------------------------------------- |
| Embedded Textures Removal | Models with embedded textures are currently UNSUPPORTED! That's why modders have been creative and instead removed them from the model |
| Embedded Textures to .otd | Fixes Texture Issues!                                                                                                                |

> *Embedded Textures have been worked on already. It's possible, but unstable. I'm sure we will have it working soon!*

**🗺️ Metadata & Scene Formats (Direct Processing / Renaming)**

| Conversion Pair   | Description           |
| :---------------- | :-------------------- |
| `.ycd` ⇄ `.ocd`   | Animation clips       |
| `.ymap` ⇄ `.omap` | Map placement files   |
| `.ytyp` ⇄ `.otyp` | Archetype definitions |
| `.ymt` ⇄ `.omt`   | Game metadata files   |
| `.ymf` ⇄ `.omf`   | Manifest files        |

### 🛠 RPF Tools (Builder/Extractor)

**🏗️ RPF Builder**

*Builds folders into PS4-Compatible .RPF Archives*

| Feature                   | Description                                       |
| :------------------------ | :------------------------------------------------ |
| **Batch/Single Building** | Packs folders into compatible .RPF Archives (AES) |

**📦 RPF Extractor**

*Unpack any .RPF Archive/s whether unencrypted or encrypted.*

| Feature              | Description                                                        |
| :------------------- | :----------------------------------------------------------------- |
| **All .RPF Support** | Supports PC/PS4/PS5 Encrypted/Unencrypted RPFs, except Enhanced!!! |

### ⚙️ PC to PS4 DLC (Add-On) Patcher

**🩹 DLC Patcher**

*Patch any PC Add-On (dlc.rpf) to a PS4-Compatible Add-On.*

| Feature                          | Description                                                                                                       |
| :------------------------------- | :---------------------------------------------------------------------------------------------------------------- |
| **Automatic & Batch Conversion** | Add-On/s will be converted and patched, to be PS4-Compatible.                                                     |
| **Custom Compression**           | Lets you choose between configs to compress Texture Dictionaries (.ytd) to a maximum size value for optimization. |

### 👥 Add-On Ped Builder

**🧍🏻 Ped to Add-On**

*Turn your custom ped files into a working add-on.*

| Feature                  | Description                                                                                                         |
| :----------------------- | :------------------------------------------------------------------------------------------------------------------ |
| **Multiple Ped Support** | Supports multiple peds and custom gender for each ped.                                                              |
| **Custom Add-On Name**   | Add your own custom ped name, and custom output add-on name.                                                        |
| **Custom Compression**   | Lets you choose between configs to compress Texture Dictionaries (`.ytd`) to a maximum size value for optimization. |

### 🚗 Vehicle Merging

**Combine multiple unconverted (PC) Vehicle Add-Ons into one!**

| Feature                      | Description                                                                                                                                       |
| :--------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Custom Vehicle Name**      | Will prompt user if they want to have a custom name for their vehicle.                                                                            |
| **Custom Add-On Name**       | Add your own custom ped name, and custom output add-on name.                                                                                      |
| **Custom Compression**       | Lets you choose between configs to compress Texture Dictionaries (`.ytd`) to a maximum size value for optimization.                               |
| **Multiple Vehicle Support** | Supports more than 2 vehicle add-ons.                                                                                                             |
| **Automatic Rename**         | Will only work if mode was set to "replace" in settings.ini. Will use the first word from the mod folder name to rename the vehicle to that name. |

### ™️ Extra Features

**Extra Useful Features!**

| Feature            | Description                                                     |
| :----------------- | :-------------------------------------------------------------- |
| **Extract DDS**    | Extract DDS Files from 1 or more .YTD Texture Dictionary Files. |
| **Build YTD**      | Build multiple .YTD Files from 1 or more folders.               |
| **Build OTD**      | Build multiple .OTD Files from 1 or more folders.               |
| **Compress DDS**   | Compress DDS Files inside different folders to a set config.    |
| **Config Creator** | Create configs for DDS Upscaling/Downscaling.                   |

## Setup

1. Extract the .zip archive
2. Run ***NeoGen_Dependencies.py*** script, let it run until it is done.
   ```
   python NeoGen_Dependencies.py
   ```
3. **Optional:** Run ***vcwXML_Installer.py*** to install vcwXML (for removing embedded textures).
   ```
   python vcwXML_Installer.py
   ```
4. Run ***NeoGen.py***
   ```
   python NeoGen.py
   ```
5. Enjoy! For more questions, message me on Discord, or directly in the [server](https://discord.gg/buC9W643tQ).

## Building from source

Requirements: Windows 10/11 (64-bit) and [Python 3.12](https://www.python.org/downloads/) from python.org (the Microsoft Store build of Python can cause packaging problems).

```
pip install -r requirements.txt
python main.py
```

To build the Windows executable and installer:

1. Put the external tools next to the build scripts in a `redist\` folder (`neogen_misc\`, `vcwxml_winx64\`, and your texture `.ini` configs). They are copied next to `NeoGen.exe`.
2. Run `build_pyinstaller.bat`. The result is `dist\NeoGen\NeoGen.exe`.
3. Optional installer: `winget install JRSoftware.InnoSetup`, then run `build_installer.bat`. The result is `installer\NeoGen_Setup.exe`.

Maintainers can also build releases with GitHub Actions; see [CONTRIBUTING.md](CONTRIBUTING.md).

## Contributing

Contributions are welcome. Please read [CONTRIBUTING.md](CONTRIBUTING.md) and the [Code of Conduct](CODE_OF_CONDUCT.md) first. Found a bug? [Open an issue](https://github.com/VansOnV/NeoGen/issues/new/choose).

## Support

Questions? Message me on Discord, or directly in the [server](https://discord.gg/buC9W643tQ). To report a security problem, see [SECURITY.md](SECURITY.md).

## Credits

- rfoodxmodz
- VansOnV / Vans
- To creators who greatly contributed to this tool

## License

Released under the [MIT License](LICENSE).
