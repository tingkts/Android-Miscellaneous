GPIO direction ：

  &ensp;&ensp;Is the direction from SoC to the Module.

  &ensp;&ensp;Output： SoC >> Module

  &ensp;&ensp;Input ： SoC << Module


</br>

  ---

</br>



Power pin：

&emsp; ⁍ &nbsp;`Regulator`

```
	reg_can2_stby: regulator-can2-stby {
		compatible = "regulator-fixed";
		regulator-name = "can2-stby";
		pinctrl-names = "default";
		pinctrl-0 = <&pinctrl_flexcan2_reg>;
		regulator-min-microvolt = <3300000>;
		regulator-max-microvolt = <3300000>;
		gpio = <&gpio4 27 GPIO_ACTIVE_HIGH>;
		enable-active-high;
		regulator-always-on;
	};
```

&emsp; ⁍ &nbsp;`GPIO` api
```
	//Touch Panel
        gt9xx_ts@14 {
            compatible = "goodix,gt9xx";
            reg = <0x14>;
            goodix,auto-update = <0>;
            goodix,driver-send-cfg = <1>;
            touchscreen-size-x = <4096>;
            touchscreen-size-y = <4096>;
            interrupt-parent = <&gpio1>;
            interrupts = <1 0>;
            pwr-gpios = <&gpio1 0 0>;   /* active high: */
            int-gpios = <&gpio1 1 1>;   /* active low: */
            rst-gpios = <&gpio4 14 1>;   /* active low: */    // power pin
            // ...
        };
```

</br>

  ---

</br>



Interrupt pin：

&emsp; ⁍ &nbsp;`interrupt-parent` & `interrupts`

```
    // RTC
    rtc_ds1337@68 {
        compatible = "dallas,ds1337";
        reg = <0x68>;
        interrupt-parent = <&gpio1>;  // GPIO1
        interrupts = <14 0>;          // IO14 GPIO_ACTIVE_LOW
        wakeup-source;
        i2cen-gpios = <&gpio4 12 GPIO_ACTIVE_HIGH>;
    };
```

&emsp; ⁍ &nbsp;`GPIO` api

```
    //Touch Panel
    gt9xx_ts@14 {
        compatible = "goodix,gt9xx";
        reg = <0x14>;
        goodix,auto-update = <0>;
        goodix,driver-send-cfg = <1>;
        touchscreen-size-x = <4096>;
        touchscreen-size-y = <4096>;
        interrupt-parent = <&gpio1>;
        interrupts = <1 0>;
        pwr-gpios = <&gpio1 0 0>;   /* active high: */
        int-gpios = <&gpio1 1 1>;   /* active low: */      // interrupt pin
        rst-gpios = <&gpio4 14 1>;   /* active low: */
        // ...
    };
```
