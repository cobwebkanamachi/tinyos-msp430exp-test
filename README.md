# tinyos-msp430exp-test
Mainly This repository contains documents only.
Basic Procedures are shown bellow.
https://0x7d.com/2013/12/running-tinyos-on-msp430-launchpads/
Procedures wrote on the above URL,I did, but not blink on my case.
So, I make https://github.com/tgtakaoka/tinyos-msp430 
and https://github.com/tinyos/tinyos-release merge, then tweak codes.

Test Environment:
Target Board: MSP-EXP430G2 (Rev.1.5 with M430G2452)
Build Environment: VirtualBox on MacOSX
Linux XubunTOS 3.2.0-38-generic #61-Ubuntu SMP Tue Feb 19 12:20:02 UTC 2013 i686 i686 i386 GNU/Linux
Firmware Writing Environment:
Windows8.1 with MSP-EXP430G2 Software Examples v2.03.00
TinyOS Version: 2.1.2 (tinyos-release)
added 2015/06/09:
I test mspdebug in the "Prebuilt GNU toolchain for msp430" distributed bellow.
http://gnutoolchains.com/msp430/
Invoke mspdebug with tilib option.
You could debug main.elf(rename main.ihex to main.elf) and load main.elf.
Then you can run.
I test Blink of Tinyos with this.

synopsis
1. download these zip files from each github repository.
   https://github.com/tinyos/tinyos-release
   https://github.com/tgtakaoka/tinyos-msp430 
2. Then, copy each files on tinyos-msp430 on tinyos-release
3. cd apps/Blink
4. make msp430g2452
5. copy Produced main.ihex to Windows8.1
6. ihex to tihex(.txt) with python with python-msp430-tools(ver.0.6)
   python -m msp430.memory.convert -i ihex -f titext main.ihex > main.txt
7. execute MSP-EXP430G2 Software Examples\Binary\OutOfBox_MSP-EXP430G2\MSP-EXP430G2-LaunchPad\
   Program MSP-EXP430G2-LaunchPad (before execute, you tweak each command is right)

documents(T.B.D.)
a. release to msp430 diff list
b. blink change diff list
c. experimental Program MSP-EXP430G2-LaunchPad script(batch file)

reference
http://nslab.ee.ntu.edu.tw/courses/wsn-labs-fall-07/slides/TinyOS.ppt<BR>
https://0x7d.com/2013/12/running-tinyos-on-msp430-launchpads/<BR>
https://github.com/tgtakaoka/tinyos-msp430<BR>
https://github.com/tinyos/tinyos-releas<BR>
http://tinyos.stanford.edu/tinyos-wiki/index.php/Installing_XubunTOS_%28with_TinyOS_from_tp-freeforall/prod_repository%29_in_VirtualBox<BR>
http://gnutoolchains.com/msp430/

notices
1. Please check your launchpad's jumper pins.
   I did not know how to configure jumpers.
   So I fail test for few days.
   If you have version 1.5 above of launchpad, you follow silk print around jumper.
2. I have version 1.5 launchpad, bellow is my case.
   First all jumper make short, then change rx, tx jumpers are dependent on your used MCU.
   If G2553 you use, rx and tx jumper should be horizontal.
   Like = = || || || (ver.1.5 board)
   If G2452 you use, rx and rx jumper should be vertical.
   Like || || || || || (ver.1.5 board)
3. http://processors.wiki.ti.com/index.php/MSP430_-_G2xx_BSL
   "Flashing BSL code" shows jumper direction for board revision.
  

