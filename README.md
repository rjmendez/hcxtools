hcxtools
==============

Small set of tools to capture (active and passive) and convert packets from WLAN devices
for the use with hashcat. The tools are 100% compatible with hashcat
and recommended by hashcat.

Brief description
--------------

Multiple stand-alone binaries.

All of these utils are designed to execute only one specific function.


Detailed description
--------------

| Tool          | Description                                                                                          |
| ------------- | -----------------------------------------------------------------------------------------------------|
| wlandump-ng   | Small, fast and simple but powerfull WLAN scanner (replace wlandump and wlandump-sts)                |
| wlandump      | Small, fast and simple but powerfull active WLAN scanner (deprecated: program will be removed later) |
| wlandump-sts  | Small, fast and simple but powerfull active WLAN scanner (deprecated: program will be removed later) |
| wlanscan      | Small, fast and simple passive WLAN scanner (no status output)                                       |
| wlanscan-sts  | Small, fast and simple passive WLAN scanner (status output)                                          |
| wlanrcascan   | Small, fast and simple passive WLAN channel assignment scanner (status output)                       |
| wlandumpfix   | Small, fast and simple but powerfull active WLAN scanner (fix channel - status output)               |
| pioff         | Turns Raspberry Pi off via GPIO switch                                                               |
| wlancapinfo   | Shows info of pcap file                                                                              |
| wlancap2hcx   | Converts cap to hccapx (recommended for use with wlandump (many options and pcapng support))         |
| wlanhcx2cap   | Converts hccapx to cap                                                                               |
| wlanhc2hcx    | Converts hccap to hccapx                                                                             |
| wlanhcx2essid | Merges hccapx containing the same ESSID                                                              |
| wlanhcx2ssid  | Strips BSSID, ESSID, OUI                                                                             |
| wlanhcx2john  | Converts hccapx to format expected by John the Ripper                                                |
| wlanhcxinfo   | Shows detailed info from contents of hccapxfile                                                      |
| wlanhcxmnc    | Manually do nonce correction on byte number xx of a nonce                                            |
| whoismac      | Show vendor information                                                                              |
| pwhash        | Generate hash of a word by using a given charset                                                     |


Compile
--------------

Simply run:

```
make
make install
```

or (with GPIO support - hardware mods required)

```
make GPIOSUPPORT=on
make GPIOSUPPORT=on install
```


Requirements
--------------

* Linux (recommended Arch, but other distros should work, too). Don't use Kernel 4.4 (rt2x00 driver regression)

* libpcap and pcap-dev installed

* libopenssl and openssl-dev installed

* librt and librt-dev installed (should be installed by default)

* libcurl and curl-dev installed (used by whoismac)

* Raspberry Pi: additionally libwiringpi and wiringpi dev installed (Raspberry Pi GPIO support)

* Chipset must be able to run in monitor mode. Recommended: RALINK chipset (good receiver sensitivity), rt2x00 driver (stable and fast)

* Raspberry Pi (Recommended: A, A+, B, B+ - A & A+ = very low power consumption)


Useful scripts
--------------

| Script       | Description                                              |
| ------------ | -------------------------------------------------------- |
| bash_profile | Autostart for Raspberry Pi (copy to /root/.bash_profile) |
| pireadcard   | Back up a Pi SD card                                     |
| piwritecard  | Restore a Pi SD card                                     |
| makemonnb    | Example script to activate monitor mode                  |
| killmonnb    | Example script to deactivate monitor mode                |


Notice
--------------

Most output files will be appended to existing files (with the exception of .cap files).

