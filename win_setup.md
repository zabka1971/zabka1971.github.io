# Windows machine environment setup #

## A: Specific considerations for nuc8i7hnk computer ##

Former manufacturer's Support Site: [Intel Driver Support Assistant](https://www.intel.com/content/www/us/en/support/intel-driver-support-assistant.html)

Current manufacturer's Support Site: [ASUS Support Site](https://www.asus.com/us/supportonly/nuc8i7hnk/helpdesk_download/)

After Window clean install reinstall drivers from `\\zabkanas\software\drivers\nuc87hnk\` (to eliminate entries with question marks from Device manager)

## B: Setup standard working environment on Windows machine ##

### Steps during Windows setup ###

1. Windows instance is linked to Microsoft account <roman.miskovsky@gmail.com>
2. OneDrive is activated during Windows setup
3. backed up settings and apps are restored from previous Windows installation

### Important locations ###

User profile folder is `%USERPROFILE%`

OneDrive folder is `%OneDrive%`, its content is being synced against OneDrive

Root backup folder is `%OneDrive%\backup\` - copy everything into it that has to be backed up

### Portable applications ###

All portable applications are located on same drive as Total Commander, drive can be obtained by `%COMMANDER_DRIVE%` (TC pseudo-environment variable)

Global files and setting that should be outside of application folders are located in `%COMMANDER_DRIVE%\_` folder

#### Set environmental variables in batch ####

Batch file `%COMMANDER_DRIVE%\_\set_environment.cmd` creates all environmental variables needed for portable applications [(based on this explanation)](<https://stackoverflow.com/questions/21606419/set-windows-environment-variables-with-a-batch-file>)

### Restore network shortcuts ###

1. copy everything in `%OneDrive%\backup\Network Shortcuts\` into `%APPDATA%\Microsoft\Windows\Network Shortcuts\`

## C: Relevant utilities ##

### Actively used ###

| Utility                                       | Link                                               | Comment                                                                                 |
| --------------------------------------------- | -------------------------------------------------- | --------------------------------------------------------------------------------------- |
| [Total Commander](#total-commander)           | <https://www.ghisler.com/>                         | file manager for Windows                                                                |
| JetBrains Mono                                | <https://www.jetbrains.com/lp/mono/>               | a typeface for developers                                                               |
| Microsoft 365                                 | Microsoft Store                                    |                                                                                         |
| [Visual Studio Code](#visual-studio-code)     | <https://code.visualstudio.com/>                   | Code Editing. Redefined                                                                 |
| [Git](#git)                                   | <https://git-scm.com/downloads>                    | --distributed-is-the-new-centralized                                                    |
| [LosslessCut](#losslesscut)                   | <https://mifi.github.io/lossless-cut/>             | ultimate cross platform FFmpeg GUI                                                      |
| [MKVToolnix](#mkvtoolnix)                     | <https://mkvtoolnix.download/>                     | Matroska tools for Linux/Unix and Windows                                               |
| MKVCleaver                                    | <https://blogs.sapib.ca/apps/mkvcleaver/>          | front end (GUI) for MKVExtract.exe - more features when compared with gMKVExtractGUI    |
| gMKVExtractGUI                                | <https://sourceforge.net/projects/gmkvextractgui/> | GUI for mkvextract utility                                                              |
| [JMkvpropedit](#jmkvpropedit)                 | <https://github.com/BrunoReX/jmkvpropedit>         | Batch GUI for mkvpropedit                                                               |
| [MKV Muxing Batch GUI](#mkv-muxing-batch-gui) | <https://github.com/yaser01/mkv-muxing-batch-gui>  | a robust application for muxing (merging) videos                                        |
| Subtitle Edit                                 | <https://www.nikse.dk/subtitleedit>                | free (open source) editor for video subtitles                                           |
| Imagine                                       | <https://www.nyam.pe.kr/dev/imagine/>              | Freeware Image & Animation Viewer for Windows                                           |
| [XnView MP](#xnview-mp)                       | <https://www.xnview.com/en/xnviewmp/>              | versatile and powerful photo viewer, image management, image resizer                    |
| [PotPlayer](#potplayer)                       | <https://potplayer.tv/>                            | Multimedia software player                                                              |
| PicPick                                       | <https://picpick.app>                              | All-in-one design tool for everyone                                                     |
| PeaZip                                        | <https://peazip.github.io/peazip-portable.html>    | free file archiver utility                                                              |
| Sumatra PDF                                   | <https://www.sumatrapdfreader.org/>                | PDF, eBook (epub, mobi), comic book (cbz/cbr), DjVu, XPS, CHM, image viewer for Windows |

### Non-actively used ###

| Utility              | Link                                               | Comment |
| -------------------- | -------------------------------------------------- | ------- |
| Tidal                | <https://listen.tidal.com/>                        | High Fidelity Music Streaming |
| Plex                 | <https://www.plex.tv/>                             | Streaming media service |
| Sysinternals         | <https://learn.microsoft.com/en-us/sysinternals/>  | advanced system utilities |
| File Converter       | <https://www.freeconvert.com/>                     | Easily convert files from one format to another, online |
| Rufus                | <https://rufus.ie/en/>                             | Create bootable USB drives the easy way |
| UniGetUI             | <https://github.com/marticliment/UnigetUI>         | intuitive GUI for the most common CLI package managers for Windows |
| stacher.io           | <https://stacher.io/>                              | A Beautiful, Modern GUI for YT-DLP |
| Advanced IP Scanner  | <https://www.advanced-ip-scanner.com/>             | scans LAN for IP of connected devices |
| Radeon GPU           | <https://drivers.softpedia.com/get/GRAPHICS-BOARD/AMD/Intel-AMD-Radeon-RX-Vega-M-Graphics-Driver-30-0-13037-4001-64-bit.shtml> | |
| Intel HD Graphics    | <https://drivers.softpedia.com/get/GRAPHICS-BOARD/INTEL/Intel-HD-630-CPU-Graphics-Driver-31-0-101-2130.shtml> | |

## Total Commander ##

After Windows clean install run it from `%OneDrive%\backup\TotalCMD\Total Commander_from_E.lnk`, pin it to taskbar

[TC Internal File Associations Tutorial](https://ghisler.ch/wiki/index.php/Internal_File_Associations_Tutorial)

## Visual Studio Code ##

1. install from ZIP file
2. activate [VS Code portable mode](https://code.visualstudio.com/docs/editor/portable) by creating `data` folder in installation folder of VS Code (user settings will be in `data\user-data\User\` folder)
3. create `tmp` folder in `data` folder to force temporary files of VS Code to be stored in portable location
4. Put `zabkanas` into Allowed UNCHosts setting - to be able to [work with UNC paths in VS Code](https://stackoverflow.com/questions/76267211/vs-code-cannot-open-unc-path-files-because-of-allowed-unchosts-case-sensitivity) without mapping it to logical drives

## Git ##

1. install from ZIP file, to make Git fully portable continue with next step
2. to avoid global config file to be created in `%USERPROFILE%` create new user environment variable [GIT_CONFIG_GLOBAL](https://git-scm.com/docs/git-config#ENVIRONMENT) (created as part of [batch environment variables setting](#set-environmental-variables-in-batch))
3. set VS code setting variable git.path using double slashes in path name (according to <https://www.diaryfolio.com/2022/01/vs-code-portable-git-shell-integration.html>)

### Useful Git commands ###

[Displaying where GIT configuration settings of all scopes is stored:](https://stackoverflow.com/questions/12254076/how-do-i-show-my-global-git-configuration)

```console
git config --list --show-origin --show-scope
```

[Setting Global Git Username and Email](https://linuxize.com/post/how-to-configure-git-username-and-email/) - prerequisite for commit changes to remote repository

```console
git config --global user.name "Your Name"
git config --global user.email "youremail@yourdomain.com"
```

## LosslessCut ##

1. config file is set to program directory as described [here](https://mifi.github.io/lossless-cut/installation.html)

## MKVToolnix ##

[User forum](https://help.mkvtoolnix.download/)

## JMkvpropedit ##

requires OPEN JDK [Adoptium](https://adoptium.net/en-GB/)

## MKV Muxing Batch GUI ##

settings are in `%APPDATA%\MKV Muxing Batch GUI\setting.json`, there is not known how to change its location so far

## XnView MP ##

1. install from ZIP file, setting file `xnview.ini` is in the same directory as application (to be set up on first run)

2. internal association in Total Commander defined via saved search "bitmap graphics", it includes following extensions: `JPG,JPEG,PNG,TIFF,BMP,GIF,WEBP`

## PotPlayer ##

1. install portable as [instructed here](https://www.portablefreeware.com/index.php?id=2483), same method for PotPlayer Codec Pack 64-bit

2. internal association in Total Commander defined via saved search "video files", it includes following extensions: `AVI,WMV,WMP,WM,ASF,MPG,MPEG,MPE,M1V,M2V,MPV2,MP2V,TS,TP,TPR,TRP,VOB,IFO,OGM,OGV,MP4,M4V,M4P,3GP,3GPP,3G2,3GP2,MKV,RM,RAM,RMVB,RPM,FLV,MOV,QT,AMR,NSV,DPG,M2TS,M2T,MTS,DVR-MS,K3G,SKM,EVO,NSR,AMV,DIVX,WEBM,WTV,F4V,MXF,WVX,WMX,MPLS,MPL,BIK`

## Sumatra PDF ##

1. install from ZIP file, setting file `SumatraPDF-settings.txt` is in the same directory as application

2. internal association in Total Commander defined via saved search "eBook files", it includes following extensions: `PDF,EPUB,MOBI,AZW,FB2,FB2Z,ZFB2,PDB,TCR,CBZ,CBR,CBT,CB7,DJV,DJVU,CHM,XPS,OXPS,XOD`

## For further processing ##

### [FileInfo.com](https://fileinfo.com/) ###

### Foobar ###

1. settings are in %APPDATA%\foobar2000-v2\ folder

### MusicBrainz Picard ###

1. settings are in  %APPDATA%\MusicBrainz\ folder

pushd popd to work with UNC paths in command prompt

The Portable Freeware Collection                                            <https://www.portablefreeware.com/>

GitHub Pages documentation <https://docs.github.com/en/pages>
Writing on GitHub <https://docs.github.com/en/get-started/writing-on-github>

### Create directory Junction ###

1. `mklink /J "%OneDrive%\backup\extra\MKVToolnix" "%LOCALAPPDATA%\bunkus.org\mkvtoolnix-gui"`

### Restore procedure before portable application being used ###

1. Install all relevant applications

2. copy backup of all relevant configuration files into corresponding folders: (run batch file, file to be created)

3. Create symbolic links from all relevant configuration files to dedicated OneDrive folder: run file  %OneDrive%\backup\create_links.bat in elevated command prompt (Run as administrator...)
