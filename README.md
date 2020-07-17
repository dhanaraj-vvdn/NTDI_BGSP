# NTDI_BGSP
#Guiding steps for source code of NTDI_KAA2 project

OS and system configuration
==============================

Host machine version for flashing software onto Jetson devices.
Ubuntu 14.04 (amd64 distribution)
Ubuntu 16.04 (amd64 distribution)
Supported Linux kernel version
4.4.38(ubuntu 16.04)
4.4.15(ubuntu 14.04)
Supported ARM architecture
aarch64
The board/module name, used in flashing and paths in the software.
Jetson TX1: jetson-tx1
The board/module number
Jetson TX1: p2371-2180

2.Where to get source code
The source code is maintained in the Git repository
To download, follow the below command
git clone https://github.com/netradyne/vvdn-release-28.2.git

3.Where to get Toolchain
Toolchain is available in s3 server.
s3://netradyne-vvdn-sharing/ntdi_icdc_toolchain.tar.gz -Extract this in /opt folder.
Toolchain is also available in SVN.
https://192.168.100.150/viewvc/ntdi_icdc/toolchain/

4.Steps for Compilation
A. 	Base directory = /Linux_for_Tegra_28.2/
B. 	Get the tar file of Root-Filesystem from the following path
s3://netradyne-vvdn-sharing/ NTDI_Linux_Root-Filesystem_R28.2_v3.0.2.1_20190423_aarch64.tar.bz2
Extract the tar file in the Base directory
sudo tar –xvjf NTDI_Linux_Root-Filesystem_R28.2_v3.0.2.1_20190423_aarch64.tar.bz2
C.	Change to the Sources directory
Sources directory = /Linux_for_Tegra_28.2/sources
Run the below commands:
*make all
D.	Go to Base directory and run the below command:
sudo./apply_binaries.sh

5.Steps to flash image
Run the flash.sh script that is in the top-level directory of this release. The script must be supplied with the target board (jetson-tx1) for the root file system:

sudo ./flash.sh  

Where  depends on where the root file system is located.

sudo ./flash.sh jetson-tx1 mmcblk0p1


6.Files add in .gitignore
We are already clean the code before pushing in git.
So there is no file to add in the .gitignore.
