# Mapping POKEY Registers to Modern API

This document explains how each POKEY register maps to a clean, modern API layer.  
Use this as a guide for building abstractions that hide POKEY quirks while preserving full fidelity.

---

## Audio System

### AUDF1–AUDF4 → AudioChannel.setFrequency(divisor)
POKEY:
- AUDFx is an 8‑bit divisor (N = AUDF + 1)

Modern API:
- `audio.channel[x].setFrequencyDivisor(value)`
- or `audio.channel[x].setFrequency(hz)` if you compute Fout internally

---

### AUDC1–AUDC4 → AudioChannel.setNoise(), setVolume(), setMode()
POKEY:
- Bits 7–5: noise/distortion type  
- Bit 4: volume‑only mode  
- Bits 3–0: volume (0–15)

Modern API:
- `audio.channel[x].setNoiseType(type)`
- `audio.channel[x].setVolume(level)`
- `audio.channel[x].enableVolumeOnlyMode(true/false)`

---

### AUDCTL → AudioEngine.setGlobalAudioMode()
POKEY:
- Controls clock sources, 16‑bit chaining, high‑pass filters, poly size

Modern API:
- `audio.setClockSource(channel, source)`
- `audio.enable16BitMode(pair)`
- `audio.enableHighPass(channel, true/false)`
- `audio.setPolySize(bits)`

---

## Keyboard Scanner

### KBCODE → KeyboardScanner.getKeyCode()
POKEY:
- Bits 5–0: key code  
- Bits 6–7: SHIFT / CONTROL flags

Modern API:
- `keyboard.getKeyCode()`
- `keyboard.getModifiers()`  
- `keyboard.onKey(callback)`

---

### SKCTL → KeyboardScanner.configure(), SerialPort.configure()
POKEY:
- Enables scanning, debounce, serial modes, two‑tone mode

Modern API:
- `keyboard.enableScanning(true/false)`
- `keyboard.enableDebounce(true/false)`
- `serial.configureMode(mode)`
- `serial.enableTwoTone(true/false)`

---

### SKSTAT → KeyboardScanner.getStatus(), SerialPort.getStatus()
POKEY:
- Reports keypress, BREAK, serial framing errors, overruns

Modern API:
- `keyboard.getStatus()`
- `serial.getStatus()`

---

## Pot (Analog) Inputs

### POT0–POT7 → PotScanner.getValue(index)
POKEY:
- Latched rise‑time values (0–228)

Modern API:
- `pots.read(index)`  
- or `analog.read(index)`

---

### ALLPOT → PotScanner.getValidityMask()
POKEY:
- Bitmask of valid pot lines

Modern API:
- `pots.getValidMask()`

---

### POTGO → PotScanner.startScan()
POKEY:
- Resets counter and begins charge timing

Modern API:
- `pots.startScan()`

---

## Random Number Generator

### RANDOM → RandomSource.getByte()
POKEY:
- High 8 bits of polynomial counter

Modern API:
- `random.nextByte()`

---

## Serial I/O

### SERIN → SerialPort.readByte()
POKEY:
- Received serial byte

Modern API:
- `serial.read()`

---

### SEROUT → SerialPort.writeByte()
POKEY:
- Byte to transmit

Modern API:
- `serial.write(byte)`

---

## Interrupts

### IRQEN → InterruptController.enable(type)
POKEY:
- Enables specific interrupt sources

Modern API:
- `interrupts.enable("timer1")`
- `interrupts.enable("serialIn")`
- etc.

---

### IRQST → InterruptController.getStatus()
POKEY:
- Reports active interrupts

Modern API:
- `interrupts.getStatus()`

---

## Timers

### STIMER → Timer.start()
POKEY:
- Reloads AUDF values and resets audio channels

Modern API:
- `timers.startAll()`
- or `timers.start(channel)`

---

# Summary

POKEY’s registers map cleanly to a modern API when grouped by subsystem:

- **Audio** → `audio.channel[x]`  
- **Keyboard** → `keyboard.*`  
- **Pots** → `pots.*`  
- **Timers** → `timers.*`  
- **Serial** → `serial.*`  
- **Interrupts** → `interrupts.*`  
- **Random** → `random.*`

This lets you expose a clean, modern interface while still supporting full POKEY fidelity underneath.

