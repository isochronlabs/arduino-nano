# Arduino Nano Discovery

## Compile and Flash

### Compile main.hex
`make`

### Flash the main.hex
`make program`

## Disassembling

### Disassemble all (-D) with architecture AVR (-m avr)
`avr-objdump -D -m avr main.hex`
