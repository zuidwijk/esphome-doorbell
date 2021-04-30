# ESPHome based DoorBell

![IMG_1103](https://user-images.githubusercontent.com/10123063/116728283-fcded900-a9e5-11eb-978b-8b40d48583d7.jpeg)
![IMG_1107](https://user-images.githubusercontent.com/10123063/116728290-fea89c80-a9e5-11eb-9854-68345eefaf21.jpeg)
![IMG_1104](https://user-images.githubusercontent.com/10123063/116728285-fe100600-a9e5-11eb-9384-1d0ea892d4a5.jpeg)
![IMG_1105](https://user-images.githubusercontent.com/10123063/116728287-fe100600-a9e5-11eb-8cc9-b60713add1b4.jpeg)

## The doorbell
The doorbell is a modified relay hat for a Wemos. It's adjusted so that the Wemos get the power from the doorbell powersupply. No extra powersupply needed to power the Wemos :)

## The code (for main bell)
I've created 2 versions of ESPHome yaml code for my [ESPHome based DoorBell](https://www.zuidwijk.com/esphome-based-doorbell/):
* [Normal/ring](https://github.com/zuidwijk/esphome-doorbell/blob/main/doorbell-ring.yaml) code (relay on when doorbell pressed, and off when released)
* [DingDong](https://github.com/zuidwijk/esphome-doorbell/blob/main/doorbell-dingdong.yaml) code (1 push on doorbell will make my dingdong go 3 times)

## The code for a secondary bell
When I'm working in my office (attic), I sometimes won't hear the bell on the main floor. I have therefore a second bell on the attic. To trigger the 2nd bell via an automation, I'm using an API service and a script to tidy it up

```YAML
api:
  services:
    - service: dingdong
      then:
        - script.execute: dingdong_script

script:
  id: dingdong_script
  then:
    if:
      condition:
        - switch.is_on: chime_active
      then:
        - switch.turn_on: relay
        - delay: 200ms
        - switch.turn_off: relay
        - delay: 600ms
        - switch.turn_on: relay
        - delay: 200ms
        - switch.turn_off: relay
        - delay: 600ms
        - switch.turn_on: relay
        - delay: 200ms
        - switch.turn_off: relay
```
That together with te rest of the esphome yaml code is the [dingdong.yaml](https://github.com/zuidwijk/esphome-doorbell/blob/main/dingdong.yaml) file
