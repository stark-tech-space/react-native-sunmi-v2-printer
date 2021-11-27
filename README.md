# react-native-sunmi-v2-printer

[![GitHub license](https://img.shields.io/badge/license-MIT-blue.svg)](https://raw.githubusercontent.com/suraneti/react-native-sunmi-inner-printer/master/LICENSE)
[![npm version](https://badge.fury.io/js/react-native-sunmi-v2-printer.svg)](https://www.npmjs.com/package/react-native-sunmi-v2-printer)

## SUNMI V2 Printer for React-Native

### Caution: this is not the official project and forked form https://github.com/januslo/react-native-sunmi-inner-printer

Offical Demos refer: https://github.com/shangmisunmi/SunmiPrinterDemo

## Installation

**Step 1.**

Install via NPM

```bash
npm install react-native-sunmi-v2-printer --save
```

Install via Yarn

```bash
yarn add react-native-sunmi-v2-printer
```

Install from source

```bash
npm install https://github.com/suraneti/react-native-sunmi-v2-printer.git --save
yarn add https://github.com/suraneti/react-native-sunmi-v2-printer.git --save
```

**Step 2:** (For React-Native < 0.60)

Links this plugin to your project.

```bash
react-native link react-native-sunmi-v2-printer
```

or you may need to link manually

- modify settings.gradle

```javascript
include ':react-native-sunmi-v2-printer'
project(':react-native-sunmi-v2-printer').projectDir = new File(rootProject.projectDir, '../node_modules/react-native-sunmi-v2-printer/android')
```

- modify app/build.gradle,add dependenceie：

```javascript
compile project(':react-native-sunmi-v2-printer')
```

- adds package references to MainPackage.java

```java
import com.sunmi.v2.printer.SunmiV2PrinterPackage;
...

 @Override
    protected List<ReactPackage> getPackages() {
      return Arrays.<ReactPackage>asList(
          new MainReactPackage(),
          new SunmiV2PrinterPackage()
      );
    }
```

**Step 3:**

Import in React-Native:

```javascript
import SunmiV2Printer from 'react-native-sunmi-v2-printer';
```

## API

### Constants

|      Name       |  Type   |       Description       |
| :-------------: | :-----: | :---------------------: |
|    Constants    | string  |    Printer's status     |
|   hasPrinter    | boolean |  Is printer available   |
| printerVersion  | string  |    Printer's version    |
| printerSerialNo | string  | Printer's serial number |
|  printerModel   | string  |     Printer's model     |

### Printer Status

|           Name           |        Description         |
| :----------------------: | :------------------------: |
|   OUT_OF_PAPER_ACTION    |      Printer of paper      |
|       ERROR_ACTION       |       Printing error       |
|      NORMAL_ACTION       |      Printing normal       |
|    COVER_OPEN_ACTION     |  Printer's cover has open  |
|    COVER_ERROR_ACTION    | Printer's cover is unusal  |
|   KNIFE_ERROR_1_ACTION   |     切刀异常 1－卡切刀     |
|   KNIFE_ERROR_2_ACTION   |    切刀异常 2－切刀修复    |
|   OVER_HEATING_ACITON    |    Printer is overheat     |
| FIRMWARE_UPDATING_ACITON | Upgrade printer's firmware |

### Example

Please check on `example/` floder

# Label Printing AIDL + Functions

> Added by Jimmy 11/28/2021

Reference:
https://github.com/shangmisunmi/SunmiPrinterDemo/blob/fd6df42621eb8eb532635106c7dbc8e936684c4c/app/src/main/java/com/sunmi/printerhelper/utils/SunmiPrintHelper.java#L726-L786

```
getPrinterMode() //returns 0 thermal | 1 black mark | 2 label
labelLocate() //position label for next printing
labelOutput() //outputs all labels that haven't been printed yet
```
