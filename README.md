# Are you getting Linker error related to micro-ecc for nrf52832, here is what I did

Hi there, 
After going through many post/forum I didn't get my solution, it was really confusing. After doing some R&D how can we fix this problem. This post especially for engineer, but expert also can take advantage of saving time.
   
This problem comes during linker time. After the compilation when linker start linking all file together but here few file missing which is related to micro-ecc. The file is missing linker not able to locate binary file. 

I am tested it on fallowing platform:  
OS: Windows 10  
IDE: Keil V5 and IAR Embedded  
DK: nrf52832 (official)  

In nrf 15.x.x SDK, there is not binary file, only micro-ecc source code available. Means you have to compile the source code to get binary file.
 
  *Many people having doubt and many post there on **devzone** but its confusing.*

 After doing some R&D I found how to compile the source code.  
 Here is list of the software which you will needed  
 - [ ] MinGW
 - [ ] GNU Arm Embedded Toolchain
 - [ ] git
 
 **Note** You will need GNU Arm Embedded Toolchain ***6-2017-q2***
Because this is version mentioned in script. 

I am using **nRF5_SDK_15.1.0_a8c0c4d** for nrf52832 development kit.

## Downloading the necessary software
MinGW [download link](https://sourceforge.net/projects/mingw/)  
GNU Arm Embedded Toolchain [download link](https://developer.arm.com/open-source/gnu-toolchain/gnu-rm/downloads)  
**Note:** look for ***6-2017-q2*** version. File name is *gcc-arm-none-eabi-6-2017-q2-update-win32-sha1.exe*  
Git [download link](https://git-scm.com/download/win)  
## Installation of Software
### Steps of installing  minGW and setup environment variable
 Step 1. Install minGW software  
 Step 2. Select ***mingq32-gcc*** packages from installer install  
 Step 3. Goto installed directory, default directory are, C:\MinGW\bin and make one copy and rename it to ***make.exe***   
 Step 4. Set environment variable, in order to access from anywhere from terminal, and set ***C:\MinGW\bin*** value.  
 Step 5. Now you can check your `make` command on terminal window like `make --version`. If it works then go further otherwise replete steps carefully.  

### Installing GNU Arm Embedded Toolchain
This is very simple installation, just fallow the installer instruction.  
Make sure you downloaded correct version. Even if any error during building then read the message and download package accordingly.

### Steps for installing Git
Step 1. Install git software, it simple. 
Step 2.  Set the PATH **C:\Program Files\Git\bin** in environment variable. 
Step 3. Very it by giving `git --version` command on terminal. 



If git not installed properly then you will get error like this


## ERRORS

 If git is not installed properly:
 
	 git is not installed. Please install and append to PATH.
If GNU Arm Embedded Toolchain not installed properly:


	process_begin: CreateProcess(NULL, "C:/Program Files (x86)/GNU Tools ARM Embedded/6 2017-q2-update/bin/arm-none-eabi-gcc" --version, ...) failed. 
	Cannot find: 'C:/Program Files (x86)/GNU Tools ARM Embedded/6 2017-q2-update/bin/arm-none-eabi-gcc'.
	Please set values in: "C:/Users/Rajan/Documents/MyWorkSpace/NordicSemi/nRF52832/nRF5_SDK_15.1.0_a8c0c4d/components/toolchain/gcc/Makefile.windows"
	according to the actual configuration of your system.
