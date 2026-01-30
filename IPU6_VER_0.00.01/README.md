### Get started Guide:
- follow the steps in the doc 828853_ArrowLakeUH_Ubuntu_Kernel_Overlay_GSG_3.1
- file:   $/etc/modprobe.d/ipu.conf 
           add one line:  options intel-ipu6 isys_freq_override=475
- retrieve the otocam-intel-driver:
	- $cd /home/user/intel-driver-release/otocam-intel-driver-v0.00.01/script/
	- $chmod 777 *.sh
	- $./install_image.sh
	- $reboot
	- $cd /home/user/intel-driver-release/otocam-intel-driver-v0.00.01/script/
	- $./install_deb.sh

### Steps to execute sensor preview 
(1) copy the ko & xml to the intel system:
	- $cd /home/user/intel-driver-release/otocam-intel-driver-v0.00.01/script/
	- $./install_script.sh

(2) reboot the intel machine 
	- enter BIOS
	- modify the HID for the specific sensor (UFEI Firmware Setting ->enter BIOS...
-> Intel advanced menu -> System Agent (SA) Configuration -> MIPI Camera Configuration -> Camera1 & camera2 Link options)
	- ex: otocam222 => INTC222M 
	      otocam223 => INTC223M	
(3) enter ubuntu
	- do following steps.
        - $cd /home/user/intel-driver-release/otocam-intel-driver-v0.00.01/script/
	- $sudo su
	- $./execute-otocam222-fps.sh
### Note
- 1.for display frame info
	- sudo apt install gstreamer1.0-plugins-base
