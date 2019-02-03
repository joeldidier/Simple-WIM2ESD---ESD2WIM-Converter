# SCRIPT IS BUGGED ! (Index name empty, Not supporting folder with spaces, and others).
# An update is planned as soon as I have more free time.
----------
# Welcome to the Simple WIM2ESD / ESD2WIM Converter !
<p align="center">

**Current Script Version**<br/>0.5.0-beta

**Current Provided DISM Version in this Repository**<br/>10.0.17120.1000
</p>

<p align="center">
<a href="https://blog.studisys.net">
  <img  src="https://studisys.net/github/projects/Simple-WIM2ESD---ESD2WIM-Converter/2.png"></a>
  <br/>
 </p>
 
 <p>
This tool allows you to convert WIM Images to ESD Images and vice-versa.
<br/>
If you want to compress WIM Images so they can fit on your favorite Bootable FAT32-formatted USB Stick, this tool is for you.<br/>
If you can't install with an ESD Image and want to go back to the good old WIM Image, this tool is also for you.
  <br/>
 </p>




## Compatibility
This script only works on Windows systems.
This script is currently ***only*** tested on **Windows 10**.
It was last tested on ***Windows 10 Education Insider Preview Build 17634 (Skip Ahead)***
It will soon be tested on Windows Vista, 7, 8, 8.1, and Windows Server 2008 (R2), 2012 (R2), 2016.

# How to Use

1. Download both the script (`Simple-WIM2ESD---ESD2WIM-Converter.bat`) and DISM folder, containing the DISM tools
**IMPORTANT :** This tool does not currently support 'already-installed' DISM in the way that It can't detect yet the path to an installed DISM. The DISM tool and it's dependicies must be placed in a `DISM` folder located in the same folder as the batch file.

 2. Run the script ***`Simple-WIM2ESD---ESD2WIM-Converter.bat`***
 ***Note :*** If you didn't run the script as Administrator, you will be prompted for Administrator rights. You must grant Administrator rights because they are required for DISM to work.
 - Follow the steps shown in the script :
	3) Select the type of conversion you want
		-  `1` for WIM to ESD
		- `2` for ESD to WIM
	4) Choose if you want to change the path to the source image.
		-  `N`to keep the default path
			- The source image must be in the same folder as the script
		- `Y`to change the path to the source image
			- Please enter the full path to the source image, including filename and extension, without any quotes.

 
	5) Choose if you want to change the path to the destination image.
		-  `N`to keep the default path
			- The destination image will be saved in the same folder as the batch script.
		- `Y`to change the path to the destination image
			- Please enter the full path to the source image, including filename and extension, without any quotes.

	6) Choose if you want to change the type of Image Compression

		 - `1` -> None :  No Compression (Fastest) [Destination Image bigger than Source Image]
		 - `2` -> Fast :  Low Compression (Fast) [Destination Image 'may' be bigger than Source Image]
		 - `3` -> Maximum :  Very High Compression (Slow) [Destination Image WAY smaller than Source Image]
		 - `4` -> Recovery :  Insane Compression (Slowest) [Destination Image WAY smaller than Source Image]

	7) Select an option :
		- `1` to export a single Index
			- Enter the Index number you want to export
		- `2` to export all indexes

(these are the options available with the version 0.5.0-beta from April 1st 2018)

8. Validate and let the fun begin.



# Demo
Here is an actual demo.
I decide to use the provided files.
I will convert a WIM Image to an ESD Image.
All indexes will be exported.
The WIM Image will be located in the same folder as the Batch script, and the ESD Image will be saved in the same folder.


Here is the result :

<p align="center">
<a href="https://blog.studisys.net">
  <img  src="https://studisys.net/github/projects/Simple-WIM2ESD---ESD2WIM-Converter/3.gif"></a>
  <br/>
 </p>
 



# Important Notes
## Practical Notes
### Administrator-rights
 - This script ***requires*** Administrator rights to run

### Existing Destination File
- If the specified destination image already exists, it will be deleted once the extraction has begun.



# More about this project

  
  

## Origin

This tool is part of a much-bigger project which will help manage and customize Windows Installation Images and files. <br/>
Also, I had to recently reinstall many Windows PCs but the ISOs provided by Microsoft were too big for being properly booted over USB on UEFI systems (install.wim > 4GB), so I wanted a quick way of compressing install.wim images, which led to this tool.
  
## Upcoming features


- Allow to detect current Windows ADK installation to use preinstalled files
- Add an unattended mode (no interaction with user, allows for automated tasks)
- Add the possibility of choosing single or multiple Index range(s)
- Add the possibility of choosing specific but multiple indexes
 

## Modifications


### This script creates :

- %temp%\\\GetAdminRights.vbs

	- For the Administrator Rights if script was not run as Administrator

- An ESD or WIM image, which name and directory are provided by the user or let to default, in the same folder as the script



### This script runs :

- %temp%\\\GetAdminRights.vbs

	- Run cmd.exe as admin if the script was not executed as it

- %systemroot%\\system32\\cmd.exe

	- Runs as admin to operate if necessary

- /DISM/dism.exe
	- The Deployment Image Servicing and Management tool, required to convert WIM images to ESD and vice-versa


## Versioning

I'm tyring to keep versioning as clean as possible. Here is the system I'm using :

  

- 3-digit version [Major].[Beta].[Alpha]

- [Major] : number of the stable version

- [Beta] : number of the Beta version (number of bugs greatly reduced comparing to the Alpha version)

- [Alpha] : number of the Alpha version (highest number of bugs, features not properly working)

  

## Changelog

A changelog can be found [here](https://github.com/Studisys/Simple-WIM2ESD---ESD2WIM-Converter/blob/master/CHANGELOG).

  

## License [<img src="https://img.shields.io/badge/license-AGPL 3.0-blue.svg">](https://github.com/Studisys/Simple-WIM2ESD---ESD2WIM-Converter/blob/master/LICENSE)

This project is licensed under the AGPL 3.0 License.

The license file can be viewed [here](https://github.com/Studisys/Simple-WIM2ESD---ESD2WIM-Converter/blob/master/LICENSE).

Here are the great lines to remember of this license :

 - <img src="https://img.shields.io/badge/Commercial%20use%20:-Allowed-brightgreen.svg">
  - <img src="https://img.shields.io/badge/Distribution%20:-Allowed-brightgreen.svg">
  - <img  src="https://img.shields.io/badge/Modification%20:-Allowed-brightgreen.svg">
  - <img  src="https://img.shields.io/badge/Patent%20use%20:-Allowed-brightgreen.svg">
  - <img  src="https://img.shields.io/badge/Private%20use%20:-Allowed-brightgreen.svg">
 - <img  src="https://img.shields.io/badge/Disclose%20source%20:-Mandatory-blue.svg">
- <img  src="https://img.shields.io/badge/License%20and%20copyright%20notice%20:-Mandatory-blue.svg">
- <img  src="https://img.shields.io/badge/Network%20use%20is%20distribution%20:-Mandatory-blue.svg">
- <img  src="https://img.shields.io/badge/Same%20license%20:-Mandatory-blue.svg">
- <img  src="https://img.shields.io/badge/State%20changes%20:-Mandatory-blue.svg">
- <img  src="https://img.shields.io/badge/Liability%20:-None-red.svg">
- <img  src="https://img.shields.io/badge/Warranty%20:-None-red.svg">

## Contact and useful links

Thanks for browsing through this project !

Here a few links on how to reach me and/or find me online :

  
   - Twitter :  https://twitter.com/Studisys
   
   - LinkedIn :  https://linkedin.com/in/joel-didier
   
   - Email : studisys@protonmail.com

