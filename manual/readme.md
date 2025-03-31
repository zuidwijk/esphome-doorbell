# How to use the ESPHome Doorbell
The ESPHome Doorbell is based on Wemos and a modified relay shield. The Wemos is powered via an integrated onboard dc-dc buck converter, so no extra power supply is required to use the ESPHome Doorbell. The ME3116 buck chip is rated for 45~50 volt max (don't go there ;-) ). I wouldn't go higher than 40 volt DC. The PCB has a rectifier bridge on it, so it can handles AC too.

## Placing the Wemos on the PCB
The headers on the PCB are placed in such way, that the Wemos fit's only one way on the PCB: the right way :-)
![IMG_3623](https://user-images.githubusercontent.com/10123063/133783247-1f415381-af50-4bee-bfa8-7108c4fa468a.jpeg)
![IMG_3624](https://user-images.githubusercontent.com/10123063/133783251-d041725d-ce94-4b68-a543-22d8312faa02.jpeg)

## RED connector: power connector
The red connector is the power connector. Here you connect the power source. This can be AC or DC and not more than 40 volts.

## BLACK connector: switch connector
The black connector is the switch connector. Here goes the doorbell switch.
Note: it’s designed to use a normally open switch (shortcut when pressed).

## BLUE/GREEN connector: Bell connector
Either the green or blue connecter, depends on which one I’ve used, is where the bell goes. The voltage provided on the red connector goes via the relay to this connector.

## Normal situation
![deurbel-oud](https://user-images.githubusercontent.com/10123063/133784959-ca84afcf-211a-4991-8807-17c4b3b47493.png)


## New situation with ESPHome Doorbell
![deurbel-nieuw](https://user-images.githubusercontent.com/10123063/133784973-a355223f-bcd9-4fb6-b6a5-7d66fc4bc4af.png)

## New situation with ESPHome Doorbell v3
![doorbell_v3_schematic](https://github.com/zuidwijk/esphome-doorbell/assets/19435932/5b5f1565-4c30-4055-b002-84d7e53ef913)
