# Arduino Nano Discovery

## Compile and Flash

### Update Makefile

Set the PORT to the USB device of your Arduino nano in `Makefile`.

Use this command to list all USB devices by port:
```
for sysdevpath in $(find /sys/bus/usb/devices/usb*/ -name dev); do
    (
        syspath="${sysdevpath%/dev}"
        devname="$(udevadm info -q name -p $syspath)"
        [[ "$devname" == "bus/"* ]] && continue
        eval "$(udevadm info -q property --export -p $syspath)"
        [[ -z "$ID_SERIAL" ]] && continue
        echo "/dev/$devname - $ID_SERIAL"
    )
done
```

### Compile main.hex
`make`

### Flash the main.hex
`make program`

## Disassembling

### Disassemble all (-D) with architecture AVR (-m avr)
`avr-objdump -D -m avr main.hex`
