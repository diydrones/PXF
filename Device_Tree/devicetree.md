Each cape for the BeagleBone Black has it's own **device tree fragment** as a overlay to the existing device tree.   
The **lib/firmware** consists of all the possible *overlays*

```
am335x-pm-firmware.bin		    BB-BONE-BACON-00A0.dtbo	BB-I2C1A1-00A0.dtbo	  cape-bone-2g-emmc1.dtbo	    libertas_cs_helper.fw
am33xx_pwm-00A0.dtbo		    BB-BONE-BACONE-00A0.dtbo	BB-SPIDEV0-00A0.dtbo	  cape-bone-adafruit-lcd-00A0.dtbo  LICENCE.atheros_firmware
atmel_at76c502_3com.bin		    BB-BONE-BACONE2-00A0.dtbo	BB-SPIDEV1-00A0.dtbo	  cape-boneblack-hdmi-00A0.dtbo     LICENCE.broadcom_bcm43xx
atmel_at76c502_3com-wpa.bin	    BB-BONE-CAM3-01-00A2.dtbo	BB-SPIDEV1A1-00A0.dtbo	  cape-boneblack-hdmin-00A0.dtbo    LICENCE.rtlwifi_firmware.txt
atmel_at76c502.bin		    BB-BONE-eMMC1-01-00A0.dtbo	BB-UART1-00A0.dtbo	  cape-bone-dvi-00A0.dtbo	    LICENCE.ti-connectivity
atmel_at76c502d.bin		    BB-BONE-GPEVT-00A0.dtbo	BB-UART2-00A0.dtbo	  cape-bone-dvi-00A1.dtbo	    mwl8k
atmel_at76c502d-wpa.bin		    BB-BONE-GPS-00A0.dtbo	BB-UART4-00A0.dtbo	  cape-bone-dvi-00A2.dtbo	    rt2561.bin
atmel_at76c502e.bin		    BB-BONE-LCD4-01-00A0.dtbo	BB-UART5-00A0.dtbo	  cape-bone-exptest-00A0.dtbo	    rt2561s.bin
atmel_at76c502e-wpa.bin		    BB-BONE-LCD4-01-00A1.dtbo	bone_pwm_P8_13-00A0.dtbo  cape-bone-geiger-00A0.dtbo	    rt2661.bin
atmel_at76c502-wpa.bin		    BB-BONE-LCD7-01-00A2.dtbo	bone_pwm_P8_19-00A0.dtbo  cape-bone-hexy-00A0.dtbo	    rt2860.bin
atmel_at76c503-i3861.bin	    BB-BONE-LCD7-01-00A3.dtbo	bone_pwm_P8_34-00A0.dtbo  cape-bone-iio-00A0.dtbo	    rt2870.bin
atmel_at76c503-i3863.bin	    BB-BONE-LCD7-01-00A4.dtbo	bone_pwm_P8_36-00A0.dtbo  cape-bone-lcd3-00A0.dtbo	    rt3070.bin
atmel_at76c503-rfmd-0.90.2-140.bin  BB-BONELT-BT-00A0.dtbo	bone_pwm_P8_45-00A0.dtbo  cape-bone-lcd3-00A2.dtbo	    rt3071.bin
atmel_at76c503-rfmd-acc.bin	    BB-BONE-PRU-01-00A0.dtbo	bone_pwm_P8_46-00A0.dtbo  cape-bone-mrf24j40-00A0.dtbo	    rt3090.bin
atmel_at76c503-rfmd.bin		    BB-BONE-PRU-02-00A0.dtbo	bone_pwm_P9_14-00A0.dtbo  cape-bone-nixie-00A0.dtbo	    rt73.bin
atmel_at76c504_2958-wpa.bin	    BB-BONE-PRU-03-00A0.dtbo	bone_pwm_P9_16-00A0.dtbo  cape-bone-pinmux-test-00A0.dtbo   rtlwifi
atmel_at76c504a_2958-wpa.bin	    BB-BONE-PRU-04-00A0.dtbo	bone_pwm_P9_21-00A0.dtbo  cape-bone-replicape-00A2.dtbo     sd8385.bin
atmel_at76c504.bin		    BB-BONE-PWMT-00A0.dtbo	bone_pwm_P9_22-00A0.dtbo  cape-bone-replicape-00A3.dtbo     sd8385_helper.bin
atmel_at76c504c-wpa.bin		    BB-BONE-RS232-00A0.dtbo	bone_pwm_P9_28-00A0.dtbo  cape-bone-tester-00A0.dtbo	    sd8686.bin
atmel_at76c505a-rfmd2958.bin	    BB-BONE-RST-00A0.dtbo	bone_pwm_P9_29-00A0.dtbo  cape-bone-weather-00A0.dtbo	    sd8686_helper.bin
atmel_at76c505-rfmd2958.bin	    BB-BONE-RST2-00A0.dtbo	bone_pwm_P9_31-00A0.dtbo  carl9170-1.fw			    sd8688.bin
atmel_at76c505-rfmd.bin		    BB-BONE-RTC-00A0.dtbo	bone_pwm_P9_42-00A0.dtbo  DNIL-AMPCAPE-1-00R1.dtbo	    sd8688_helper.bin
atmel_at76c506.bin		    BB-BONE-SERL-01-00A1.dtbo	brcm			  htc_9271.fw			    ti-connectivity
atmel_at76c506-wpa.bin		    BB-BONE-SERL-03-00A1.dtbo	cape-bebopr-brdg-R2.dtbo  lbtf_usb.bin			    TT3201-001-01.dtbo
BB-ADC-00A0.dtbo		    BB-GPIOHELP-00A0.dtbo	cape-bebopr-ena-R2.dtbo   libertas			    usb8388.bin
BB-BONE-AUDI-01-00A0.dtbo	    BB-I2C1-00A0.dtbo		cape-bebopr-R2.dtbo	  libertas_cs.fw		    zd1211
```
Capemgr is used to detect installed expansion boards and load the appropriate device tree fragment at boot time.  
> A key feature of Capemgr is the ability to load Device Tree fragments as overlays to the existing Device Tree at runtime. On the BeagleBone, each cape has a Device Tree fragment which describes it.

In the beagleboard kernel, for the PixHawk Fire cape, a patch file named will have to be merged [here](https://github.com/beagleboard/kernel/tree/3.8/patches/capes).

```
/*
* Copyright (C) 2014 Anuj Deshpande	<anujdeshpande92@gmail.com>
*
* This overlay enables 
*
* This program is free software; you can redistribute it and/or modify
* it under the terms of the GNU General Public License version 3 as
* published by the Free Software Foundation.
*/

/dts-v1/;
/plugin/;

/{
	compatible = "ti,beaglebone","ti,beaglebone-black" ;

	/* identification */
	part-number = "cape-bone-pxf";
	version = "00A0" ;

	/* state the resources this cape uses */
	exclusive-use =
		/* the pin header uses */
		"uart4",
		"uart5" ;

	fragment@0 {
		target = <&am33xx_pinmux>;
		__overlay__ {
			bb_uart4_pins: pinmux_bb_uart1_pins {
				pinctrl-single,pins = <0x70 0x26 0x74 0x06>;
			};
			bb_uart5_pins: pinmux_bb_uart4_pins {
				pinctrl-single,pins = ;
			};
	
		
```
