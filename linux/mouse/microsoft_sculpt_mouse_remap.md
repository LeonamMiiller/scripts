# Hardware

- Encontrar a id do hardware
`cat /sys/class/input/mouse1/device/modalias`

```c

input:b0005v045Ep07A2e0129-e0,1,2,4,k110,111,112,r0,1,6,8,B,C,am4,lsfw
```

- Encontrar os valores dos eventos
`sudo apt-get install evtest`

- Precisa descobrir qual é o input
`sudo evtest /dev/input/eventX`

## Exemplos Slide UP e Down

```c
Event: time 1721173156.000308, type 4 (EV_MSC), code 4 (MSC_SCAN), value 90004
Event: time 1721173156.000308, type 1 (EV_KEY), code 275 (BTN_SIDE), value 0
Event: time 1721173156.000308, -------------- SYN_REPORT ------------
Event: time 1721173159.249179, type 4 (EV_MSC), code 4 (MSC_SCAN), value 90005
Event: time 1721173159.249179, type 1 (EV_KEY), code 276 (BTN_EXTRA), value 1

```

- O valor q precisamos é o seguido por `"value"`.

```c

value 90004
value 90005

```

## Criar o reconhecimento do hardware

- Criar aquivo em:  `/etc/udev/hwdb.d/10-ms-sculpt-mouse.hwdb`
- Com os Seguinte valores:

```c

# remap MS Sculpt Comfort Mouse (Bluetooth)
evdev:input:b0005v045Ep07A2*
 KEYBOARD_KEY_700e3=reserved
 KEYBOARD_KEY_90004=reserved
 KEYBOARD_KEY_90005=reserved

```

- reserved = desabilitado

## Recarregar as infos de hardware

```c

sudo systemd-hwdb update
sudo udevadm trigger

```
