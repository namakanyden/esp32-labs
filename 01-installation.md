---
title: Inštalácia
authors:
	- mirek (mirek@cnl.sk)
---

# Inštalácia

## About

Pre prácu s _ESP32_ v jazyku _Micropython_ budeme potrebovať vykonať tieto kroky:

* nahrať do mikrokontroléra firmvér pomocou nástroja `esptool`
* nainštalovať editor _Mu_

V prípade, že používate operačný systém _Windows_, môžete si nainštalovať vývojové prostredie _uPyCraft IDE_, pomocou ktorého viete nahrať do mikrokontroléra firmvér a rovnako tak aj programovať. 

## Inštalácia nástroja `esptool`

`esptool` je otvorený, platformovo nezávislý nástroj napísaný v jazyku _Python_ na komunikáciu s ROM bootloader-om v čipoch _ESP8266_ a _ESP32_. Najnovšiu verziu nástroja je možné vždy nainštalovať z repozitára [pypi](http://pypi.python.org/pypi/esptool) pomocou nástroja `pip`:

```bash
pip3 install esptool
```

## Inštalácia firmvéru

* najprv treba stiahnuť firmvér zo stránky [micropython.org](http://micropython.org/) 
    * časť [Download](http://micropython.org/download)
    * doska [ESP32](http://micropython.org/download)
    * z časti _Standard firmware_ stiahnuť druhý v poradí (prvý je nočné zostavenie)

* pustite terminál a presuňte sa do priečinku, do ktorého ste stiahli firmvér

* ak firmvér nahrávate prvýkrát, vymažte obsah flash pamäte:

  ```bash
  esptool.py --chip esp32 --port /dev/ttyUSB0 erase_flash
  ```


Firmvér nahráte do mikrokontroléra z príkazového riadku pomocou nástroja `esptool` nasledovne:

```bash
esptool.py --chip esp32 --port /dev/ttyUSB0 --baud 460800 write_flash \
    -z 0x1000 esp32-20190125-v1.10.bin
```

Po úspešnom nahratí firmvéru sa mikrokontrolér  _ESP32_ reštartuje.


## Editor Mu

* editor stiahnite z [domovskej stránky](https://codewith.mu/) z časti [Downloads](https://codewith.mu/en/download)

* stiahnite si **nie stabilnú** verziu, ale **alfa verziu** !!!
    * podpora pre ESP32
    * slovenčina
    * iné mocné veci

* Linuxáci - uistite sa, že ste v skupine `dialout`


### Windowsaci

* používatelia windowsu si musia stiahnuť ovládač pre _CP210x USB to UART Bridge_
  * [download drivers](https://www.silabs.com/products/development-tools/software/usb-to-uart-bridge-vcp-drivers)

## Ďalšie zdroje

* [Code with Mu](https://codewith.mu/) - domovská stránka editora _Mu_
* [Micropython](https://micropython.org/) - domovská stránka jazyka _Micropython_
* [Install uPyCraft IDE](https://randomnerdtutorials.com/install-upycraft-ide-windows-pc-instructions/) - Windows PC Instructions
* [`esptool`](https://github.com/espressif/esptool) - ESP8266 and ESP32 serial bootloader utility        

## Licencia

Pokiaľ nie je uvedené inak, obsah tohto dokumentu je licencovaný licenciou [Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International (CC BY-NC-SA 4.0)](https://creativecommons.org/licenses/by-nc-sa/4.0/).




