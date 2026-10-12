# 🛸 FlyFishRC Atlas4 Deadcat — Custom 4" FPV Drone Build

> My first custom FPV build log: from receiving a box of components from AliExpress to diagnosing ESC phase failures with a multimeter. A hands-on project featuring soldering, hardware routing, Betaflight configuration, and troubleshooting.

---

## 📸 Assembly Gallery

| 1. Frame Half-Assembly | 2. Frame Completed | 3. Motors Mounted |
| :---: | :---: | :---: |
| <img width="1920" height="2560" alt="image" src="https://github.com/user-attachments/assets/6f35cd2f-86af-4f7f-8250-17be5e963bdc" /> | <img width="1920" height="2560" alt="image" src="https://github.com/user-attachments/assets/a07cfe71-4e85-4b7b-a1f1-0b42ffc0721d" /> | <img width="1920" height="2560" alt="image" src="https://github.com/user-attachments/assets/a0978966-ab41-496a-8e8d-0ab655a55ad7" />|
 

| 4. Stack Installation | 5. Motor Soldering | 6. Power & Capacitor |
| :---: | :---: | :---: |
| <img width="2560" height="1920" alt="image" src="https://github.com/user-attachments/assets/3633162b-0e9d-4f13-8d5e-cce999d63a12" /> | <img width="1920" height="2560" alt="image" src="https://github.com/user-attachments/assets/2043504f-aacd-4ec9-850a-394237ac4f85" /> | <img width="1920" height="2560" alt="image" src="https://github.com/user-attachments/assets/52316e04-a705-45a6-9957-cd6ea43ffc2c" />


| 7. Wiring & Peripherals | 8. Smoke Stopper Test | 9. First takeoff |
| :---: | :---: | :---: |
| <img width="2560" height="1920" alt="image" src="https://github.com/user-attachments/assets/c810276b-014a-4e30-806b-01274cd36ff4" /> | <img width="2560" height="1920" alt="image" src="https://github.com/user-attachments/assets/f7b9a0f9-61da-4791-9020-22afdf61cc54" /> | <img width="754" height="664" alt="photo_2026-10-12_10-20-45" src="https://github.com/user-attachments/assets/f1036eff-b92b-4415-97ba-1e460b5058eb" />






---

## 🛠️ Hardware Specifications

### 🚁 Frame & Propulsion
* **Frame:** FlyFishRC Atlas4 O4 PRO LR (Deadcat geometry, 4-inch)
* **Motors:** iFlight XING2 1404 3800KV (Unibell, 2S–4S)
* **Props:** Gemfan Hurricane 4024 2-blade (1.5mm shaft)
* **Battery:** CNHL MiniStar 4S 850mAh LiPo

### ⚡ Flight Electronics
* **Flight Controller & ESC Stack:** SpeedyBee F405 Mini Stack (20x20mm)
  * **FC:** SpeedyBee F405 Mini
  * **ESC:** SpeedyBee 35A BLHeli_S Mini V2 4-in-1 ESC
* **Radio Receiver (RX):** RadioMaster RP1 V2 2.4GHz ExpressLRS (ELRS) Nano Receiver (LBT)
* **Radio Transmitter (TX):** RadioMaster Pocket (ELRS, Hall Gimbals)

### 📹 Video System & FPV Gear
* **Camera:** Caddx Ratel 2 Micro (Starlight 1200TVL)
* **Video Transmitter (VTX):** RUSH TANK Ultimate MINI 5.8GHz (20x20mm, up to 800mW)
* **VTX Antenna:** Foxeer Lollipop 4 V4 5.8GHz (MMCX 85mm)
* **FPV Goggles:** EV800D 5.8G 40CH Diversity Headset with DVR

### 🔧 Tools & Workshop Equipment
* **Soldering Station:** QUICKO T12-951 LED Digital Station (P9 handle)
* **Solder Wire:** 60/40 Lead-Tin Flux Core (0.8mm)
* **Flux:** MECHANIC UV559 Lead-Free Solder Paste
* **Safety & Diagnostics:** VIFLY ShortSaver 2 V2 Smoke Stopper, ANENG Automatic Multimeter
* **Battery Charger:** ToolkitRC M4AC 30W (1-4S XT60)

---

## 💻 Software & Configuration

* **Flight Controller Firmware:** Betaflight (4.x)
* **ESC Firmware:** Bluejay `0.19.2` (`J-H-40` layout, 48kHz PWM frequency)
* **RC Protocol:** ExpressLRS (ELRS 2.4GHz)

---

## 📝 Build Notes & Personal Experience

### 1. Frame Assembly: The Lego Effect
Assembling the **FlyFishRC Atlas4 Deadcat** frame was pure joy — felt like building high-end LEGO for adults. The Deadcat arm geometry ensures propellers stay completely out of the camera's field of view.

### 2. The Soldering Evolution: Cold Joint Nightmare to T12 Pure Magic
* **Phase 1 (Pain):** Started soldering motor pads to the 4in1 ESC using a cheap, underpowered iron. The cold joints looked terrible, solder refused to flow properly, and it felt like total frustration.
* **Phase 2 (Salvation):** Switched to the **QUICKO T12-951** station paired with **MECHANIC UV559 flux** and 60/40 solder. The difference was night and day — solder formed clean, shiny, perfectly rounded pads instantly. Redid the entire board setup.

### 3. VTX Placement & Cable Management
Space inside a 4-inch frame is tight. The RUSH TANK Ultimate Mini didn't fit inside the rear section as planned, so I routed it to the bottom frame section, custom-designed cable runs, and secured the MMCX antenna mount cleanly.

### 4. The Magic Moment: Green Light on Smoke Stopper
Connecting the CNHL 4S battery for the first time through the **VIFLY ShortSaver 2**:
> Seeing the LED turn solid GREEN, hearing the startup chimes without smoke, and seeing live video feed directly from the Caddx Ratel 2 on the EV800D goggles was an incredible rush.

---

## 🔍 Diagnostics & Troubleshooting Log

During motor testing in Betaflight, Motor #4 failed to spin — it twitched, stuttered, made a heavy humming sound, and triggered an ESC safety cutoff.

### Diagnostic Steps Executed:
1. **Motor Swapping:** Soldered the non-working motor to a known good ESC channel. Motor spun fine, confirming the motor and windings were 100% healthy.
2. **Multimeter Diode Check:** Checked MOSFETs on all 12 motor pads (Black probe to `GND`, Red probe to pads). Measured **0.493V–0.495V** across all phases, confirming MOSFETs were not hard-shorted.
3. **ESC Configurator & Bluejay Flashing:** Read setup successfully (all 4 ESCs responded with `J-H-40` layout). Flashed Bluejay 48kHz. Motor still desynced upon spin-up.
4. **Conclusion:** Physical hardware failure on the gate driver circuit of ESC channel 4. Replacement 4in1 ESC ordered.

---

### 🛠️ Hardware Replacement & Maiden Flight:
5. **Replacement & Final Assembly:** Ordered a replacement 4-in-1 ESC board, installed it into the stack, resoldered all 4 motor leads using the T12 station, and re-verified phase continuity.
6. **Validation:** All 4 motors passed bidirectional spin-up tests with zero packet loss or desync.
7. **First Takeoff:** Successfully conducted line-of-sight hover tests and the maiden FPV flight. Stable attitude hold, responsive throttle curve, and zero desync issues detected.

---

## 🚀 Status & Project Milestones

- [x] Frame assembly & mechanical build
- [x] Component soldering & harness routing
- [x] VTX, RX binding & ExpressLRS link validation
- [x] Hardware failure isolation & oscilloscope/multimeter diagnostics
- [x] Replacement 4-in-1 ESC installation & verification
- [x] Successful maiden takeoff & flight stability tests
- [x] Betaflight PID & Filter tuning (RPM filtering / Dynamic notch)
- [x] Long-range link testing & endurance optimization

