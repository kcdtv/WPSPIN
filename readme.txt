
# This scripts is edited under the General Public License as defined by the Free software foundation. 
# This package is distributed in the hope that it will be useful, but without any warranty; It can be used and modified and shared but should be referenced to, it CANNOT be 
# sold or be used for a commercial-economical purpose.
# See the details in the file LICENCE.txt that is situated in the folder of the script or visit http://gplv3.fsf.org/ ) 
  






ABOUT WPSPIN




The first version was released in crack-wifi.com, lampiweb.com and auditoriaswireless.net the 8th december 2012
It was published to reveal the results of my studies about Huawei HG 532c from ISP FTE (orange - Spanish branch)
I found the way to derivate the default WPSPIN from bssid and essid 
Surprisely a variant of the same algorithm ( but just bazed  on the mac adress ) worked on belkin device and another huawei router
I thought I found another algorithm, but i realized that it had been parallely and previously by zhaochunsheng in a C. script named computepinC83A35
( http://gjkiss.info/2012/04/get-the-pin-in-router-mac-address-start-with-c83a35-00b00c-081075 )
Later i integrated aracdyan easybox PIN generation has revealed by Stefan Viehböck ( https://www.sec-consult.com/fxdata/seccons/prod/temedia/advisories_txt/20130805-0_Vodafone_EasyBox_Default_WPS_PIN_Vulnerability_v10.txt )
and the WPA key genration for the same device thanks to a full disclosure of Stefan wottan ( http://www.wotan.cc/?p=6 )
finally i used VodafoneXXXX Arcadyan Essid  by coeman76 that unifie both and correct errors from original codes

Everything was adapted to bash from the scrach thanks to the collaboration of antares_145, r00tnuLL and 1camaron1, thanks to them billion a billion time :)

It wouldn't have been possible neither without my beloved lampiweb.com work crew, maripuri, bentosouto, dirneet, betis-jesus, compota, errboricobueno, pinty_102 nad all users 
greetings to crack-wifi.com familly, yasmine, M1ck3y, spawn, goliate, fuji, antares has been already credited, koala, noireaude, vances1, konik etc... and all users
greetings to auditoriaswireless.net and thanks to the big chief papones for the hosting and greetings to everybody
This code uses wps reaver that has to be installed on it own, reaver is a free software (http://code.google.com/p/reaver-wps/) (GPL2) by Tactical Network Solutions. Thanks to 
them for this amazing work (especially Craig Heffner ) 
You also need aircrack-ng, thanks to Mister X and kevin devine for providing the best suite ever (http://www.aircrack-ng.org/)
Devlopped for debian bazed system such as Ubuntu, xubuntu, linux mint... and especially kali linux, tahnks to offensive security for theirs work and special grettings to g0tmi1k 

 

HOW TO USE WPSPIN?

- Unzip the package that you download
   < unzip WPSPIN >



- once situated in the created folder (cd WPSPIN) launch the script with
  < (sudo) bash WPSPIN.sh >


REQUIREMENTS

If you use WPSPIN as a simple generator no requierement. 

If you want to enjoy the scan and attack feature you need:
  - a wireless interface with a chipset compatible with mode monitor
  - aircrack-ng and dependecies installed in your system
  - WPS reaver installed

you can visit crack-wifi.com, lampiweb.com and auditroias-wireless.net to get indormattion and help about WPSPIN and others issues like thiese ones 


Just follow the script, it is very simple




CHANGELOG




# 1.1 (10-12-2012)
#	- Support for PIN beginning with one or several 0 thanks to the data of atim and tresal. 
#	- New MAC supported : 6A:C0:6F (HG566 default ESSID vodafoneXXXX )
# 1.2 (12/12/2012)
#	- Fixed output bugs in backtrack and other distributions
#	- Added support to the generic default PIN known
# 1.3 (23/01/2013)
#	- New supported devices:
#		- 7 bSSID vodafoneXXXX (HG566a) > 6A:3D:FF / 6A:A8:E4 / 6A:C0:6F / 6A:D1:67 / 72:A8:E4 / 72:3D:FF / 72:53:D4
#		- 2 bSSID WLAN_XXXX (PDG-A4001N de adbroadband) > 74:88:8B / A4:52:6F
#		- 2 new models affected:
#			1) SWL (Samsung Wireless Link), default ESSID SEC_ LinkShare_XXXXXX.  2 known affected BSSID > 80:1F:02 / E4:7C:F9
#			2) Conceptronic  c300brs4a  (default ESSID C300BRS4A ) 1 BSSID known  > 00:22:F7   
#	- Rules to check the validity of the mac address (thanks r00tnuLL and anteres_145 for your codes) 
#	- More filter for some case where several default ssid are possible,check the difference between ssid and bssid for FTE for possibles mismatch...
#       - More information displayed when a target is selected
#	- Display and colours problems are definitively solved for all distributions, one version
#	- Rewriting of code (tanks to r00tnuLL, antares_145, goyfilms and 1camron1 for their advices and feed back)
# 1.4 ( 22/05/2013)
#      - Complete Rewriting of code to provide new functions:
#          - Multi language         
#          - A automated mode using wash and reaver 
#          - Interfaces management (automatic if only one interface is present, acting as filter if no mode monitor is possible to reduce options) 
#          - New supported bssid
#              -  2 news bssid for FTE-XXXX (HG532c)   34:6B:D3 and F8:3D:FF 
#              -  17 new bssid for vodafone HG566a
#               62:23:3D 62:3C:E4 62:3D:FF 62:55:9C 62:7D:5E 62:B6:86 62:C7:14 6A:23:3D 6A:3D:FF 6A:7D:5E 6A:C6:1F 6A:D1:5E 72:3D:FF 72:53:D4 72:55:9C 72:6B:D3  72:A8:E4  
#          - New supported devices ( 9 models )    
#              -  TP-LINK  >  TD-W8961ND v2.1 default SSID TP-LINK_XXXXXX  3 known bssids ; F8:D1:11 B0:48:7A 64:70:02
#              -  EDIMAX  >  3G-6200n and EDIMAX  >  3G-6210n    bssid ; 00:1F:1F defaukt SSID : default
#              -  KOZUMI >  K1500 and   K1550  bssid : 00:26:CE 
#              -  Zyxel  >  P-870HNU-51B      bssid : FC:F5:28
#              -  TP-LINK  TP-LINK_XXXXXX  TL-WA7510N    bssid : 90:F6:52:
#              -  SAGEM FAST 1704 > SAGEM_XXXX    bssid :  7C:D3:4C:
#              -  Bewan iBox V1.0 > one bssid   00:0C:C3  for two ssids with different defaukt PIN   >   DartyBox_XXX_X and TELE2BOX_XXXX
# 1.5 ( 24/01/2014 )
#
#        - Imlemented bash adaptation of esay box arcadyan vodane PIN and WPA algorithm by coeman76
#        - Grafic changes and code optimization
#        - New filters for preventing permissions issues, directory issues, unisntalled tools isuues, interfaces issues
#        - Fixed the bug for FTE red  
#        - New option to define a sequence of PIN to try first ( thanks to Spawn for recursive_generator )
#        - New option to enter manually a different PIN then than one proposed
#        - -p option with reaver is not used any longuer due to lost of quality of attack and PIN are genrated live
#        - detection of processing error to backup the sesssion untill the PIN that could create a problem in order to avoid the "99,99% bug"
#        - function to adapt mode monitor managment with RT 3XXX chipsets
#        - Default WPA key is shown once target has been selected if the algorithm for default wpa is known ( still a lot to implement )
#        - prevent reaver failure when saving a sesssion
#        - bash adaptation of arcadyan easy box WPA and PIN generator by coeman76
#        - display the progress of a former sesssion before attacking the target again
#        - option to allow the user to customize the reaver command line 
#        - New supported bssid
#             - modification for 08863B with new devices, repeater N300 Dual-Band Wi-Fi Range Extender no compatible, with AP rate limit
#             - new bssid  F81A67 for TD-W8961ND with AP RATE LIMIT
#             - new vodafone-XXXX BSSID = 6296BF 6ACBA8 62:CB:A8 72:CB:A8.... 
#             - new bssid for PDG4100ND D0:D4:12 with refereed PIN 88202907  
#          - New supported devices
#             - NEW DEVICES, D-LINK, DSL-2730U (bssid = B8A386 | B8A386) & DSL-2750U C8:D3:A3 , with respectively generic PIN 20172527 &  #21464065
#             - NEW DEVICE, ZTE ; ZXHN_H108N , default generic 12345670 bssids: F8:1B:FA & F8:ED:80 default ssid = MOVISTAR_XXXX 
#             - 08:7A:4C E8:CD:2D 0C:96:BF NEW DEVICE   Orange-XXXX / HG530s ( Huawei )  
#             - E4:C1:46 for MOVISTAR_XXXX. Model : Observa Telecom - RTA01N_Fase2 comercialized by Objetivos y Servicios de Valor  
#             - new TP-LINK device affected TD-W8951ND with AP RATE LIMIT and known bssid A0:F3:C1:
#             - the last Bbox, with default ssid Bbox-XXXXXXXX, manufactures by SAMSUNG is vulnerable , known BSSID = 5C:A3:9D DC:71:44 D8:6C:E9
#             - VodafoneXXXX New device for mac 1C:C6:3C 50:7E:5D 74:31:70 84:9C:A6 88:03:55 full disclosure aracadyan PIN-WPA model : ARV7510PW22
#             - HG 532e from djibouti, default ssid HG532e-XXXXXX , mac  EC:23:3D
#             - DG950A from Arris Interactive  L.L.C, mac 00:1D:CF, default SSID ARRIS-XXXX 
#             - CDE-30364 from Hiltron - used by spanish ISP OnO with default ssid OnOXXX0 - mac : BC1401 68B6CF 00265B
