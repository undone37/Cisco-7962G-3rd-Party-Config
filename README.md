# Cisco-7962G-3rd-Party-Config
Cisco 7962G SIP Configuration Files (for 3rd party PBXs)

### TFTP/DHCP Configuration

During boot the handsets will discover the TFTP server via DHCP option 66 and/or DHCP option 150. Set option 66 of your DHCP to the IP address of your TFTP server. All of the configuration files, firmware files and other customisation files reside in the root directory of the TFTP server.

### Base Configuration Files

Each handset will require an SEP configuration file. The filename must be `SEP0123456789.cnf.xml` where the `0123456789` is the MAC address of the Cisco handset.

In the example SEP configuration file, the following values have been set:

    192.168.178.1	  <!-- This is the IP of the PBX or Fritzbox, it can also be a FQDN -->
    Phone_Label       <!-- This is the Label the handset will have (no spaces allowed!)-->
	621				  <!-- This is the extension the phone will have -->
    pbx-username      <!-- This is the register username for the extension -->
    Pa$$w0rd          <!-- This is the register password for the extension -->
    **600             <!-- This is the direct dial for the PBX's voicemail -->
    
All other settings can be ignored for the purpose of the inital configuration. You must change every occurance of the above settings throughout the configuration file.

### Firmware Versions and Upgrading

The firmware version that has been tested for these configuration files is `SIP75.9-4-2SR3-1S`. You can download the firmware files directly from Cisco - you will need to register for a free account. The link for the firmware files is [here](https://software.cisco.com/download/home/281346595/type/282074288/release/9.4(2)SR3).

### Dialplan

The dialplan file tells the handset how long to pause before dialling a number once it has been entered. Configured is now 5 sec