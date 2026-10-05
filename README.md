# Check-PC

# 💻 Used Laptop Inspection Checklist

A complete practical checklist for inspecting a **used laptop before buying**.

This guide covers:

* Physical condition
* CPU
* RAM
* SSD/HDD
* Battery
* Display
* Keyboard
* Touchpad
* Ports
* Wi-Fi & Bluetooth
* Camera & Microphone
* Speakers
* BIOS/UEFI
* BIOS password
* Computrace / Absolute
* Windows activation
* Temperature
* Fan
* Charger
* RAM testing
* SSD health
* Stress testing
* Warranty & Serial Number
* Final buying decision

---

## 📋 Table of Contents

1. [Before Starting](#-before-starting)
2. [Physical Body Check](#-1-physical-body-check)
3. [Model and Specifications](#-2-model-and-specifications)
4. [Display Check](#-3-display-check)
5. [Keyboard Check](#-4-keyboard-check)
6. [Touchpad Check](#-5-touchpad-check)
7. [Ports Check](#-6-ports-check)
8. [Battery Check](#-7-battery-check)
9. [SSD/HDD Check](#-8-ssdhdd-check)
10. [RAM Check](#-9-ram-check)
11. [CPU Check](#-10-cpu-check)
12. [GPU Check](#-11-gpu-check)
13. [Temperature Check](#-12-temperature-check)
14. [Fan Check](#-13-fan-check)
15. [Speaker Check](#-14-speaker-check)
16. [Microphone Check](#-15-microphone-check)
17. [Webcam Check](#-16-webcam-check)
18. [Wi-Fi Check](#-17-wi-fi-check)
19. [Bluetooth Check](#-18-bluetooth-check)
20. [BIOS/UEFI Check](#-19-biosuefi-check)
21. [BIOS Password Check](#-20-bios-password-check)
22. [Computrace / Absolute](#-21-computrace--absolute)
23. [Windows Activation](#-22-windows-activation)
24. [Serial Number Check](#-23-serial-number-check)
25. [Warranty Check](#-24-warranty-check)
26. [Device Manager](#-25-device-manager)
27. [Event Viewer](#-26-event-viewer)
28. [RAM Test](#-27-ram-test)
29. [SSD SMART Test](#-28-ssd-smart-test)
30. [CPU Stress Test](#-29-cpu-stress-test)
31. [GPU Stress Test](#-30-gpu-stress-test)
32. [Charger Check](#-31-charger-check)
33. [Charging Port](#-32-charging-port)
34. [Sleep/Restart/Shutdown](#-33-sleeprestartshutdown)
35. [Fingerprint Reader](#-34-fingerprint-reader)
36. [Smart Card Reader](#-35-smart-card-reader)
37. [Linux Live USB Test](#-36-linux-live-usb-test)
38. [Laptop Internal Inspection](#-37-laptop-internal-inspection)
39. [Original Parts Check](#-38-original-parts-check)
40. [Performance Test](#-39-performance-test)
41. [Recommended Tools](#-40-recommended-tools)
42. [Final Checklist](#-41-final-checklist)
43. [Red Flags](#-42-red-flags)
44. [Final Buying Decision](#-43-final-buying-decision)

---

# 🧰 Before Starting

Take these items when checking a used laptop:

* USB Flash Drive
* USB Mouse
* Headphones
* Phone
* Charger
* Internet connection
* Small flashlight
* Optional external SSD/HDD
* Optional Linux Live USB

### Recommended Software

```text
CPU-Z
GPU-Z
HWiNFO
CrystalDiskInfo
CrystalDiskMark
MemTest86
Cinebench
OCCT
BatteryInfoView
```

---

# 🔍 1. Physical Body Check

Turn the laptop OFF and inspect the entire body.

### Check:

* [ ] Screen frame
* [ ] Display panel
* [ ] Hinges
* [ ] Keyboard
* [ ] Touchpad
* [ ] Palm rest
* [ ] Bottom cover
* [ ] Screws
* [ ] Rubber feet
* [ ] USB ports
* [ ] Charging port
* [ ] HDMI port
* [ ] Audio jack
* [ ] Ethernet port
* [ ] SD card slot

### Look for:

* [ ] Cracks
* [ ] Bent body
* [ ] Broken hinge
* [ ] Missing screws
* [ ] Water damage
* [ ] Rust
* [ ] Severe scratches
* [ ] Loose bottom cover

> ⚠️ A broken hinge or damaged body can indicate previous physical damage.

---

# 🖥️ 2. Model and Specifications

Open:

```cmd
msinfo32
```

Check:

* [ ] Manufacturer
* [ ] Model
* [ ] CPU
* [ ] RAM
* [ ] BIOS version
* [ ] System type
* [ ] Windows version

You can also use PowerShell:

```powershell
Get-CimInstance Win32_ComputerSystem
```

Make sure the actual specifications match the seller's advertisement.

### Example

Seller says:

```text
Ryzen 7
16GB RAM
512GB SSD
```

Verify:

```text
CPU  → Ryzen 7
RAM  → 16GB
SSD  → 512GB
```

---

# 🖥️ 3. Display Check

Test the screen using:

* White background
* Black background
* Red background
* Green background
* Blue background

### Check:

* [ ] Dead pixels
* [ ] Stuck pixels
* [ ] Bright spots
* [ ] Dark spots
* [ ] Backlight bleeding
* [ ] Flickering
* [ ] Horizontal lines
* [ ] Vertical lines
* [ ] Color problems
* [ ] Screen brightness

Test:

```text
Brightness 0%
Brightness 50%
Brightness 100%
```

---

# ⌨️ 4. Keyboard Check

Test every key.

### Important keys:

```text
A-Z
0-9
F1-F12
Esc
Tab
Caps Lock
Shift
Ctrl
Alt
Windows
Enter
Backspace
Space
Arrow Keys
Home
End
Delete
Insert
Page Up
Page Down
```

If available:

* [ ] Numpad
* [ ] Function keys
* [ ] Keyboard backlight

Check for:

* [ ] Keys not working
* [ ] Double typing
* [ ] Sticky keys
* [ ] Damaged keycaps

---

# 🖱️ 5. Touchpad Check

Test:

* [ ] Cursor movement
* [ ] Left click
* [ ] Right click
* [ ] Two-finger scrolling
* [ ] Two-finger click
* [ ] Pinch zoom
* [ ] Multi-touch gestures

Make sure the cursor does not move randomly.

---

# 🔌 6. Ports Check

Test every available port.

### USB

Use a USB flash drive or mouse.

* [ ] USB-A Port 1
* [ ] USB-A Port 2
* [ ] USB-C
* [ ] Other USB ports

### Other ports

* [ ] HDMI
* [ ] DisplayPort
* [ ] Ethernet
* [ ] SD Card
* [ ] Audio Jack
* [ ] Thunderbolt
* [ ] Charging Port

> ⚠️ Do not assume that every USB-C port supports charging, display output, or Thunderbolt. Check the specific laptop model.

---

# 🔋 7. Battery Check

Generate a Windows battery report:

```cmd
powercfg /batteryreport
```

Windows will show the location of the report.

Usually:

```text
C:\Users\YourName\battery-report.html
```

Open the HTML file.

### Check:

```text
Design Capacity
Full Charge Capacity
```

### Example

```text
Design Capacity       : 50,000 mWh
Full Charge Capacity  : 38,000 mWh
```

Approximate battery health:

```text
38,000 / 50,000 × 100
= 76%
```

### General guide

| Battery Health | Condition            |
| -------------- | -------------------- |
| 90–100%        | Excellent            |
| 80–89%         | Good                 |
| 70–79%         | Acceptable           |
| 50–69%         | Weak                 |
| Below 50%      | Consider replacement |

> Battery health naturally decreases as a laptop gets older.

---

# 💾 8. SSD/HDD Check

Use:

```text
CrystalDiskInfo
```

Check:

* [ ] Health Status
* [ ] Temperature
* [ ] Power On Hours
* [ ] Power On Count
* [ ] Total Host Reads
* [ ] Total Host Writes

### SSD

Look for:

```text
Health Status: Good
```

### HDD

Pay special attention to:

* Reallocated Sector Count
* Current Pending Sector Count
* Uncorrectable Sector Count

> ⚠️ Serious SMART errors are a major warning sign.

---

# 🧠 9. RAM Check

Open:

```text
Task Manager
→ Performance
→ Memory
```

Check:

* [ ] Total RAM
* [ ] RAM speed
* [ ] Slots used
* [ ] Slots available
* [ ] Upgrade possibility

Example:

```text
RAM: 8GB
Speed: 3200 MHz
Slots: 1 of 2 used
```

This means another RAM module may be possible, depending on the laptop.

> Some laptops have soldered RAM, so always check the exact model.

---

# ⚙️ 10. CPU Check

Open:

```text
Task Manager
→ Performance
→ CPU
```

Check:

* [ ] Exact CPU model
* [ ] Base speed
* [ ] Number of cores
* [ ] Logical processors

Example:

```text
AMD Ryzen 7 4750U
8 Cores
16 Threads
```

Make sure it matches the seller's information.

---

# 🎮 11. GPU Check

Open:

```text
Device Manager
→ Display adapters
```

Check whether the GPU is detected correctly.

Example:

```text
Intel Graphics
AMD Radeon
NVIDIA GeForce
```

If the laptop has a dedicated GPU:

* [ ] GPU detected
* [ ] No driver errors
* [ ] Stress test completed
* [ ] No graphical artifacts

---

# 🌡️ 12. Temperature Check

Use:

```text
HWiNFO
```

or:

```text
HWMonitor
```

Check CPU/GPU temperatures during:

### Idle

```text
Normal Windows usage
```

### Load

Run:

* YouTube 4K
* Cinebench
* OCCT
* Game/GPU test if appropriate

Watch for:

* [ ] Excessive temperature
* [ ] Thermal throttling
* [ ] Sudden shutdown
* [ ] Performance drops

> Temperature limits depend on the exact CPU/GPU, so compare against the manufacturer's specifications.

---

# 🌀 13. Fan Check

Listen to the fan.

Normal:

```text
Low load → Quiet
High load → Faster
```

Warning signs:

```text
Grinding
Clicking
Rattling
Constant maximum speed
```

---

# 🔊 14. Speaker Check

Play a video or music.

Test:

* [ ] Left speaker
* [ ] Right speaker
* [ ] Maximum volume
* [ ] Low volume
* [ ] Bass
* [ ] Crackling/distortion

---

# 🎤 15. Microphone Check

Go to:

```text
Settings
→ System
→ Sound
→ Input
```

Test the microphone.

You can also use Windows Voice Recorder.

Check:

* [ ] Microphone detected
* [ ] Recording works
* [ ] No excessive noise

---

# 📷 16. Webcam Check

Open:

```text
Camera
```

Check:

* [ ] Camera detected
* [ ] Image quality
* [ ] Focus
* [ ] Color
* [ ] Flickering

---

# 📶 17. Wi-Fi Check

Connect to Wi-Fi.

Test:

* [ ] Wi-Fi detection
* [ ] Internet connection
* [ ] 2.4 GHz
* [ ] 5 GHz
* [ ] Connection stability

---

# 🔵 18. Bluetooth Check

Test with a phone or Bluetooth device.

* [ ] Bluetooth ON
* [ ] Device discovery
* [ ] Pairing
* [ ] Connection
* [ ] Audio/data transfer

---

# 🔐 19. BIOS/UEFI Check

Restart the laptop and enter BIOS/UEFI.

Common keys:

```text
F1
F2
F10
F12
Delete
Esc
```

The exact key depends on the manufacturer.

Check:

* [ ] CPU
* [ ] RAM
* [ ] SSD
* [ ] BIOS version
* [ ] Serial number
* [ ] Secure Boot
* [ ] TPM
* [ ] BIOS password

---

# 🔒 20. BIOS Password Check

This is especially important for:

* ThinkPad
* Dell Latitude
* HP EliteBook
* Other business laptops

Check whether there is:

```text
Supervisor Password
Administrator Password
BIOS Password
UEFI Password
```

If BIOS settings are locked, ask the seller to remove the password properly before purchasing.

> ⚠️ Do not buy a business laptop with an unknown BIOS password.

---

# 🔐 21. Computrace / Absolute

Check BIOS for options such as:

```text
Computrace
Absolute
Absolute Persistence
```

For a used corporate laptop, verify that the device has been legitimately released from any previous organization's management/ownership.

---

# 🪟 22. Windows Activation

Run:

```cmd
slmgr /xpr
```

Also check:

```text
Settings
→ System
→ Activation
```

Check:

* [ ] Windows activated
* [ ] Correct Windows edition
* [ ] No suspicious activation

For more information:

```cmd
slmgr /dlv
```

---

# 🔢 23. Serial Number Check

Use PowerShell:

```powershell
Get-CimInstance Win32_BIOS | Select-Object SerialNumber
```

Compare the serial number with:

* Laptop label
* BIOS
* Manufacturer information
* Seller's documentation

---

# 🛡️ 24. Warranty Check

Use the manufacturer's official support/warranty page.

Examples:

* Lenovo
* Dell
* HP
* ASUS
* Acer

Check:

* [ ] Warranty status
* [ ] Original model
* [ ] Serial number
* [ ] Support status

---

# 🧩 25. Device Manager

Open:

```cmd
devmgmt.msc
```

Look for yellow warning symbols.

Pay special attention to:

```text
Unknown Device
Network Controller
PCI Device
SM Bus Controller
Display Adapter
```

Yellow warning symbols may indicate missing drivers or hardware problems.

---

# 📋 26. Event Viewer

Open:

```cmd
eventvwr.msc
```

Go to:

```text
Windows Logs
→ System
```

Look for repeated:

* Disk errors
* WHEA errors
* Hardware errors
* Kernel-Power errors

A single error does not automatically mean the laptop is faulty. Repeated hardware-related errors deserve investigation.

---

# 🧪 27. RAM Test

Windows built-in test:

```cmd
mdsched.exe
```

Restart and perform the memory test.

For advanced testing:

```text
MemTest86
```

Check for:

```text
Memory Errors = 0
```

> ⚠️ RAM errors are a serious warning sign.

---

# 💽 28. SSD SMART Test

Use:

```text
CrystalDiskInfo
```

Check:

* [ ] Health
* [ ] Temperature
* [ ] Power-on hours
* [ ] Total writes
* [ ] SMART attributes

Also run:

```text
CrystalDiskMark
```

to check storage performance.

> SSD speeds vary significantly depending on the exact SSD and interface, so compare against the manufacturer's specifications rather than a single universal number.

---

# 🧪 29. CPU Stress Test

Recommended tools:

```text
Cinebench
OCCT
```

During testing watch:

* [ ] CPU temperature
* [ ] CPU frequency
* [ ] Stability
* [ ] Crashes
* [ ] Shutdowns
* [ ] Severe throttling

Stop the test if temperatures become unsafe.

---

# 🎮 30. GPU Stress Test

For laptops with dedicated graphics:

```text
3DMark
Unigine Heaven
OCCT
```

Check:

* [ ] No graphical artifacts
* [ ] No crashes
* [ ] No abnormal temperature
* [ ] Stable performance

---

# 🔌 31. Charger Check

Check the charger:

* [ ] Original charger
* [ ] Correct voltage
* [ ] Correct wattage
* [ ] Correct connector
* [ ] Cable condition
* [ ] Stable charging

Example:

```text
65W
20V
3.25A
```

Gaming laptops may require much higher wattage.

---

# ⚡ 32. Charging Port

Connect the charger.

Gently move the cable.

Charging should remain stable.

Warning:

```text
Charging
↓
Not Charging
↓
Charging
```

This may indicate a damaged charging port, cable, or charger.

---

# 🔄 33. Sleep / Restart / Shutdown

Test:

```text
Sleep
Wake
Restart
Shutdown
Power On
```

Check for:

* [ ] Successful sleep
* [ ] Successful wake
* [ ] Fast restart
* [ ] Normal shutdown
* [ ] No random restart
* [ ] No freezing

---

# 👆 34. Fingerprint Reader

If available:

```text
Settings
→ Accounts
→ Sign-in options
```

Check whether the fingerprint reader is detected and working.

---

# 💳 35. Smart Card Reader

Some business laptops have a Smart Card Reader.

Check:

```text
Device Manager
```

Look for the Smart Card Reader device.

A Smart Card Reader is generally used for authentication with compatible smart cards.

---

# 🐧 36. Linux Live USB Test

An advanced method is to boot a Linux Live USB without installing Linux.

Basic process:

```text
Create Linux Live USB
        ↓
Boot from USB
        ↓
Select "Try Linux"
        ↓
Test Hardware
```

Test:

* [ ] Display
* [ ] Keyboard
* [ ] Touchpad
* [ ] Wi-Fi
* [ ] Bluetooth
* [ ] Audio
* [ ] USB
* [ ] Ethernet
* [ ] Webcam

This is useful because it can help identify whether a problem is Windows/driver-related or hardware-related.

---

# 🪛 37. Laptop Internal Inspection

If the seller allows opening the laptop, inspect:

* [ ] Fan
* [ ] Heatsink
* [ ] Dust
* [ ] Battery
* [ ] SSD
* [ ] RAM
* [ ] Wi-Fi card
* [ ] Motherboard
* [ ] Screws
* [ ] Corrosion
* [ ] Liquid damage

### Battery warning

If the battery is:

* Swollen
* Bulging
* Pushing the touchpad upward
* Pushing the keyboard upward

**Do not use or charge it until the battery is safely replaced.**

---

# 🧩 38. Original Parts Check

Used laptops may have replacement parts.

Check whether these are original or replaced:

* [ ] Display
* [ ] Keyboard
* [ ] Battery
* [ ] SSD
* [ ] RAM
* [ ] Wi-Fi card
* [ ] Motherboard
* [ ] Charger

Replacement parts are not automatically bad, but the seller should be transparent about them.

---

# 🚀 39. Performance Test

Open multiple applications:

```text
Chrome
File Explorer
Settings
Task Manager
YouTube
```

Use the laptop for several minutes.

Look for:

* [ ] Lag
* [ ] Freezing
* [ ] Blue Screen
* [ ] Random restart
* [ ] Excessive fan noise
* [ ] Abnormal heat

---

# 🧰 40. Recommended Tools

| Tool            | Purpose               |
| --------------- | --------------------- |
| CPU-Z           | CPU/RAM information   |
| GPU-Z           | GPU information       |
| HWiNFO          | Hardware monitoring   |
| CrystalDiskInfo | SSD/HDD health        |
| CrystalDiskMark | Storage speed         |
| MemTest86       | RAM testing           |
| Cinebench       | CPU performance       |
| OCCT            | CPU/GPU/RAM stability |
| BatteryInfoView | Battery information   |

---

# ✅ 41. Final Checklist

## Physical

* [ ] Body condition
* [ ] Hinges
* [ ] Screws
* [ ] Bottom cover
* [ ] No liquid damage
* [ ] No serious cracks

## Display

* [ ] No dead pixels
* [ ] No lines
* [ ] No flickering
* [ ] Good brightness
* [ ] No major backlight problems

## Keyboard / Touchpad

* [ ] All keys work
* [ ] No double typing
* [ ] Touchpad works
* [ ] Gestures work

## Hardware

* [ ] Correct CPU
* [ ] Correct RAM
* [ ] Correct SSD
* [ ] GPU detected
* [ ] No Device Manager errors

## Storage

* [ ] SSD health good
* [ ] No critical SMART errors
* [ ] Temperature normal

## Battery

* [ ] Battery report checked
* [ ] Full Charge Capacity checked
* [ ] No swelling
* [ ] Charging works

## Ports

* [ ] USB
* [ ] USB-C
* [ ] HDMI
* [ ] Audio
* [ ] Ethernet
* [ ] SD card
* [ ] Charging port

## Connectivity

* [ ] Wi-Fi
* [ ] Bluetooth

## Multimedia

* [ ] Speakers
* [ ] Microphone
* [ ] Webcam

## Security

* [ ] BIOS password checked
* [ ] Computrace/Absolute checked
* [ ] Serial number verified
* [ ] Windows activation checked

## Performance

* [ ] Temperature checked
* [ ] Fan checked
* [ ] CPU test
* [ ] GPU test
* [ ] RAM test
* [ ] SSD test

## Accessories

* [ ] Original charger
* [ ] Correct charger wattage
* [ ] Cable in good condition

---

# 🚨 42. Red Flags

Be very careful if you find:

```text
❌ Unknown BIOS password
❌ Suspicious ownership status
❌ Serious battery swelling
❌ SSD SMART errors
❌ RAM errors
❌ Display lines
❌ Broken hinges
❌ Liquid damage
❌ Random shutdowns
❌ Blue screens
❌ Severe overheating
❌ Charging port problems
❌ Missing important parts
❌ Serial number mismatch
❌ Major hardware specification mismatch
```

If multiple major problems exist, **consider another laptop**.

---

# ⭐ 43. Final Buying Decision

Use this simple rating:

| Category           | Rating |
| ------------------ | ------ |
| Physical condition | ⭐⭐⭐⭐⭐  |
| Display            | ⭐⭐⭐⭐⭐  |
| Keyboard           | ⭐⭐⭐⭐⭐  |
| Battery            | ⭐⭐⭐⭐⭐  |
| SSD                | ⭐⭐⭐⭐⭐  |
| RAM                | ⭐⭐⭐⭐⭐  |
| CPU                | ⭐⭐⭐⭐⭐  |
| GPU                | ⭐⭐⭐⭐⭐  |
| Cooling            | ⭐⭐⭐⭐⭐  |
| Ports              | ⭐⭐⭐⭐⭐  |
| BIOS/Security      | ⭐⭐⭐⭐⭐  |
| Charger            | ⭐⭐⭐⭐⭐  |

### Final decision

```text
🟢 Excellent
Everything works and no major problems.

🟡 Acceptable
Minor problems exist but price is reasonable.

🟠 Needs negotiation
Some repairs/replacements are required.

🔴 Avoid
Major hardware, security, ownership, or reliability problems.
```

---

# 📝 Quick 10-Point Check

If you have very little time with the seller, at minimum check:

```text
1. CPU
2. RAM
3. SSD Health
4. Battery Health
5. Display
6. Keyboard + Touchpad
7. USB/HDMI/Charging Ports
8. BIOS Password
9. Temperature + Fan
10. Serial Number
```

> **Important:** A used laptop should not be judged only by CPU/RAM specifications. Battery condition, SSD health, display, cooling, BIOS/security status, physical condition, and repair history can have a major impact on the real value of the laptop.

---

## 📌 Conclusion

The safest way to buy a used laptop is:

```text
Physical Check
      ↓
Specification Verification
      ↓
BIOS Check
      ↓
Display / Keyboard / Touchpad
      ↓
Ports & Connectivity
      ↓
Battery
      ↓
SSD / RAM
      ↓
Temperature / Fan
      ↓
Stress Tests
      ↓
Serial / Warranty Verification
      ↓
Price Negotiation
      ↓
Final Decision
```

**Never buy a used laptop only because the specifications look good. Test the actual machine before paying.**


# 🖥️ Used Laptop CMD Diagnostic Commands

A practical collection of **CMD and PowerShell commands** for checking a used laptop before buying.

These commands can help inspect:

* Laptop model
* CPU
* RAM
* Motherboard
* BIOS
* Serial number
* SSD/HDD
* Battery
* GPU
* Display
* Wi-Fi
* Bluetooth
* USB devices
* Drivers
* Windows activation
* TPM
* Secure Boot
* System errors
* RAM
* Disk
* Windows health

> ⚠️ Some `WMIC` commands are deprecated or unavailable on newer Windows versions. PowerShell alternatives are included where possible.

---

# 📋 Table of Contents

1. [Requirements](#-requirements)
2. [Run CMD as Administrator](#-run-cmd-as-administrator)
3. [System Information](#-1-system-information)
4. [Laptop Model](#-2-laptop-model)
5. [CPU](#-3-cpu)
6. [RAM](#-4-ram)
7. [Motherboard](#-5-motherboard)
8. [BIOS](#-6-bios)
9. [Serial Number](#-7-serial-number)
10. [SSD/HDD](#-8-ssdhdd)
11. [Disk Health](#-9-disk-health)
12. [Battery](#-10-battery)
13. [Battery Energy Report](#-11-battery-energy-report)
14. [GPU](#-12-gpu)
15. [DirectX Diagnostic](#-13-directx-diagnostic)
16. [Device Manager](#-14-device-manager)
17. [Problem Devices](#-15-problem-devices)
18. [Network](#-16-network)
19. [Wi-Fi](#-17-wi-fi)
20. [Bluetooth](#-18-bluetooth)
21. [USB](#-19-usb)
22. [CPU Usage](#-20-cpu-usage)
23. [Running Processes](#-21-running-processes)
24. [Windows Activation](#-22-windows-activation)
25. [TPM](#-23-tpm)
26. [Secure Boot](#-24-secure-boot)
27. [RAM Test](#-25-ram-test)
28. [Windows System Files](#-26-windows-system-files)
29. [DISM](#-27-dism)
30. [Disk Check](#-28-disk-check)
31. [Event Viewer](#-29-event-viewer)
32. [System Uptime](#-30-system-uptime)
33. [Recommended 15 Commands](#-recommended-15-commands)
34. [Final Checklist](#-final-checklist)

---

# 🧰 Requirements

You need:

* Windows 10/11
* Command Prompt
* PowerShell
* Administrator access

Optional:

* USB Flash Drive
* USB Mouse
* Headphones
* Internet connection

---

# 🔐 Run CMD as Administrator

Press:

```text
Windows Key
```

Type:

```text
cmd
```

Right-click:

```text
Command Prompt
→ Run as administrator
```

Some commands require administrator privileges.

---

# 💻 1. System Information

### Command

```cmd
systeminfo
```

This provides information such as:

* Windows version
* OS build
* Manufacturer
* Model
* BIOS
* RAM
* Network information
* System boot time

### Useful filter

```cmd
systeminfo | find "System Boot Time"
```

---

# 💻 2. Laptop Model

### WMIC

```cmd
wmic computersystem get manufacturer,model
```

### PowerShell alternative

```powershell
Get-CimInstance Win32_ComputerSystem | Select Manufacturer,Model
```

Check that the actual model matches the seller's advertisement.

---

# ⚙️ 3. CPU

### WMIC

```cmd
wmic cpu get name
```

### PowerShell

```powershell
Get-CimInstance Win32_Processor | Select Name,NumberOfCores,NumberOfLogicalProcessors
```

Check:

* CPU model
* Number of cores
* Number of logical processors

Example:

```text
AMD Ryzen 7 4750U
8 Cores
16 Logical Processors
```

---

# 🧠 4. RAM

### WMIC

```cmd
wmic memorychip get capacity,speed,manufacturer,partnumber
```

### PowerShell

```powershell
Get-CimInstance Win32_PhysicalMemory |
Select Manufacturer,PartNumber,Capacity,Speed
```

Check:

* RAM capacity
* RAM speed
* Manufacturer
* Part number

### Total RAM

```cmd
wmic computersystem get TotalPhysicalMemory
```

---

# 🧩 5. Motherboard

```cmd
wmic baseboard get manufacturer,product,serialnumber
```

PowerShell:

```powershell
Get-CimInstance Win32_BaseBoard |
Select Manufacturer,Product,SerialNumber
```

Check:

* Manufacturer
* Model
* Serial number

---

# 🔐 6. BIOS

```cmd
wmic bios get manufacturer,version,serialnumber
```

PowerShell:

```powershell
Get-CimInstance Win32_BIOS |
Select Manufacturer,SMBIOSBIOSVersion,SerialNumber
```

Check:

* BIOS manufacturer
* BIOS version
* BIOS serial number

---

# 🔢 7. Serial Number

```cmd
wmic bios get serialnumber
```

PowerShell:

```powershell
Get-CimInstance Win32_BIOS |
Select SerialNumber
```

Compare the result with the serial number physically printed on the laptop.

> ⚠️ A serial-number mismatch deserves investigation.

---

# 💾 8. SSD/HDD

### WMIC

```cmd
wmic diskdrive get model,size,serialnumber,mediatype
```

### PowerShell

```powershell
Get-PhysicalDisk |
Select FriendlyName,MediaType,Size,HealthStatus
```

Check:

* SSD/HDD model
* Capacity
* Media type
* Health status

---

# ❤️ 9. Disk Health

PowerShell:

```powershell
Get-PhysicalDisk |
Select FriendlyName,HealthStatus,OperationalStatus
```

A healthy drive normally shows:

```text
HealthStatus
------------
Healthy
```

For detailed SMART information, use:

```text
CrystalDiskInfo
```

> ⚠️ PowerShell's `HealthStatus` is only a basic check. It should not replace a detailed SMART inspection.

---

# 🔋 10. Battery

Generate a battery report:

```cmd
powercfg /batteryreport
```

Windows will display the report location.

Usually:

```text
C:\Users\YourName\battery-report.html
```

Open the HTML file.

Check:

* Design Capacity
* Full Charge Capacity
* Battery history
* Recent usage
* Cycle count, if available

### Example

```text
Design Capacity:      50,000 mWh
Full Charge Capacity: 38,000 mWh
```

Approximate health:

```text
38,000 / 50,000 × 100
= 76%
```

---

# ⚡ 11. Battery Energy Report

Run:

```cmd
powercfg /energy
```

Windows creates an energy efficiency report.

It can identify:

* Power problems
* Device power issues
* Driver-related power issues
* Energy efficiency problems

The report location is shown after the command finishes.

---

# 🎮 12. GPU

### WMIC

```cmd
wmic path win32_VideoController get name,driverversion
```

### PowerShell

```powershell
Get-CimInstance Win32_VideoController |
Select Name,DriverVersion
```

Check:

* GPU model
* Driver version

---

# 🖥️ 13. DirectX Diagnostic

Run:

```cmd
dxdiag
```

This opens **DirectX Diagnostic Tool**.

Check:

### System

* CPU
* RAM
* Windows
* DirectX

### Display

* GPU
* VRAM
* Driver
* Display information

### Sound

* Audio devices
* Drivers

### Input

* Input devices

This is one of the most useful built-in Windows diagnostic tools.

---

# 🧩 14. Device Manager

Run:

```cmd
devmgmt.msc
```

Check:

* Display adapters
* Network adapters
* Storage controllers
* USB controllers
* Bluetooth
* Audio devices

Look for:

```text
⚠️ Yellow warning icon
```

---

# 🚨 15. Problem Devices

PowerShell:

```powershell
Get-PnpDevice |
Where-Object {$_.Status -ne 'OK'}
```

This can help identify devices with a non-OK status.

Check particularly for:

```text
Unknown Device
Network Controller
PCI Device
SM Bus Controller
Display Adapter
```

---

# 🌐 16. Network

Run:

```cmd
ipconfig /all
```

Check:

* Ethernet adapter
* Wi-Fi adapter
* MAC address
* IP address
* DHCP
* DNS

---

# 📶 17. Wi-Fi

### Wi-Fi Drivers

```cmd
netsh wlan show drivers
```

This can show:

* Wireless adapter
* Supported radio types
* Driver information
* Supported authentication/capabilities

### Current Wi-Fi connection

```cmd
netsh wlan show interfaces
```

Check:

* SSID
* Signal
* Radio type
* Receive rate
* Transmit rate
* Connection state

### Saved Wi-Fi profiles

```cmd
netsh wlan show profiles
```

---

# 🔵 18. Bluetooth

PowerShell:

```powershell
Get-PnpDevice -Class Bluetooth
```

Check whether the Bluetooth adapter is detected.

---

# 🔌 19. USB

PowerShell:

```powershell
Get-PnpDevice -Class USB
```

This lists USB-related devices detected by Windows.

For actual port testing, physically connect:

* USB mouse
* USB flash drive
* USB keyboard

and test every port.

---

# 📊 20. CPU Usage

### WMIC

```cmd
wmic cpu get loadpercentage
```

### PowerShell

```powershell
Get-Counter '\Processor(_Total)\% Processor Time'
```

Use this to see current CPU utilization.

---

# 📋 21. Running Processes

```cmd
tasklist
```

Open Task Manager:

```cmd
taskmgr
```

Check for:

* High CPU usage
* High RAM usage
* Unknown processes
* Background applications

---

# 🔑 22. Windows Activation

Check activation:

```cmd
slmgr /xpr
```

Detailed information:

```cmd
slmgr /dlv
```

Also check:

```text
Settings
→ System
→ Activation
```

Verify that Windows is properly activated.

---

# 🔐 23. TPM

Run:

```cmd
tpm.msc
```

Check:

* TPM available
* TPM status
* TPM version

This is particularly useful when checking Windows 11 compatibility.

---

# 🛡️ 24. Secure Boot

Run PowerShell:

```powershell
Confirm-SecureBootUEFI
```

Possible result:

```text
True
```

or:

```text
False
```

> Legacy BIOS systems may return an error because Secure Boot requires UEFI.

---

# 🧪 25. RAM Test

Run:

```cmd
mdsched.exe
```

Windows Memory Diagnostic will open.

Select:

```text
Restart now and check for problems
```

For more advanced testing:

```text
MemTest86
```

RAM errors are a serious warning sign.

---

# 🪟 26. Windows System Files

Run:

```cmd
sfc /scannow
```

This checks Windows system files for corruption.

Possible result:

```text
Windows Resource Protection did not find any integrity violations.
```

---

# 🛠️ 27. DISM

### Basic check

```cmd
DISM /Online /Cleanup-Image /CheckHealth
```

### Detailed scan

```cmd
DISM /Online /Cleanup-Image /ScanHealth
```

These commands check the Windows component store for corruption.

---

# 💽 28. Disk Check

Basic:

```cmd
chkdsk
```

For a specific drive:

```cmd
chkdsk C:
```

Repair option:

```cmd
chkdsk C: /f
```

> ⚠️ Do not run repair commands unnecessarily on a seller's machine. Ask permission first, especially if the laptop contains personal data.

---

# 📋 29. Event Viewer

Run:

```cmd
eventvwr.msc
```

Go to:

```text
Windows Logs
→ System
```

Look for repeated:

* Disk errors
* WHEA errors
* Hardware errors
* Kernel-Power errors
* Driver errors

A single event does not automatically mean a hardware failure. Repeated relevant errors are more important.

---

# ⏱️ 30. System Uptime

CMD:

```cmd
systeminfo | find "System Boot Time"
```

PowerShell:

```powershell
(Get-CimInstance Win32_OperatingSystem).LastBootUpTime
```

This shows the last system boot time.

---

# ⭐ Recommended 15 Commands

For a quick used-laptop inspection, save these commands:

### 1. System

```cmd
systeminfo
```

### 2. Model

```cmd
wmic computersystem get manufacturer,model
```

### 3. CPU

```cmd
wmic cpu get name
```

### 4. RAM

```cmd
wmic memorychip get capacity,speed,manufacturer
```

### 5. BIOS

```cmd
wmic bios get manufacturer,version,serialnumber
```

### 6. Storage

```cmd
wmic diskdrive get model,size,serialnumber,mediatype
```

### 7. Battery

```cmd
powercfg /batteryreport
```

### 8. Battery Energy

```cmd
powercfg /energy
```

### 9. GPU

```cmd
wmic path win32_VideoController get name,driverversion
```

### 10. DirectX

```cmd
dxdiag
```

### 11. Devices

```cmd
devmgmt.msc
```

### 12. Network

```cmd
ipconfig /all
```

### 13. Wi-Fi

```cmd
netsh wlan show drivers
```

### 14. Problem Devices

```powershell
Get-PnpDevice | Where-Object {$_.Status -ne 'OK'}
```

### 15. Storage Health

```powershell
Get-PhysicalDisk | Select FriendlyName,MediaType,Size,HealthStatus
```

---

# 📊 Final Checklist

| Test         | Command                    | Status |
| ------------ | -------------------------- | ------ |
| System       | `systeminfo`               | ⬜      |
| Model        | `wmic computersystem`      | ⬜      |
| CPU          | `wmic cpu`                 | ⬜      |
| RAM          | `wmic memorychip`          | ⬜      |
| Motherboard  | `wmic baseboard`           | ⬜      |
| BIOS         | `wmic bios`                | ⬜      |
| Serial       | `wmic bios`                | ⬜      |
| SSD/HDD      | `wmic diskdrive`           | ⬜      |
| Disk Health  | `Get-PhysicalDisk`         | ⬜      |
| Battery      | `powercfg /batteryreport`  | ⬜      |
| Energy       | `powercfg /energy`         | ⬜      |
| GPU          | `dxdiag`                   | ⬜      |
| Drivers      | `devmgmt.msc`              | ⬜      |
| Network      | `ipconfig /all`            | ⬜      |
| Wi-Fi        | `netsh wlan`               | ⬜      |
| Bluetooth    | `Get-PnpDevice`            | ⬜      |
| USB          | `Get-PnpDevice -Class USB` | ⬜      |
| Windows      | `slmgr /xpr`               | ⬜      |
| TPM          | `tpm.msc`                  | ⬜      |
| Secure Boot  | `Confirm-SecureBootUEFI`   | ⬜      |
| RAM Test     | `mdsched.exe`              | ⬜      |
| System Files | `sfc /scannow`             | ⬜      |
| DISM         | `DISM /Online...`          | ⬜      |
| Disk         | `chkdsk`                   | ⬜      |
| Errors       | `eventvwr.msc`             | ⬜      |

---

# 🚨 Important Red Flags

Be careful if you find:

```text
❌ BIOS password you cannot remove
❌ Serial number mismatch
❌ Serious SSD SMART problems
❌ RAM errors
❌ Repeated WHEA hardware errors
❌ Repeated disk errors
❌ Random shutdowns
❌ Blue Screens
❌ Severe overheating
❌ Battery swelling
❌ Charging problems
❌ Unknown critical devices
❌ GPU artifacts
❌ Major specification mismatch
```

---

# 💡 Quick Inspection Workflow

Use this order when you are physically with the seller:

```text
Laptop
  ↓
Physical Inspection
  ↓
systeminfo
  ↓
CPU
  ↓
RAM
  ↓
SSD
  ↓
Battery Report
  ↓
BIOS + Serial
  ↓
GPU / dxdiag
  ↓
Device Manager
  ↓
Wi-Fi / Bluetooth
  ↓
Ports
  ↓
Temperature
  ↓
RAM / SSD Tests
  ↓
Windows Activation
  ↓
Warranty / Ownership
  ↓
Final Price
```

---

# ⚠️ WMIC Note

`WMIC` is deprecated and may not be available on some newer Windows installations.

If this command:

```cmd
wmic cpu get name
```

does not work, use:

```powershell
Get-CimInstance Win32_Processor | Select Name
```

Instead of:

```cmd
wmic memorychip get capacity,speed
```

use:

```powershell
Get-CimInstance Win32_PhysicalMemory |
Select Capacity,Speed
```

Instead of:

```cmd
wmic bios get serialnumber
```

use:

```powershell
Get-CimInstance Win32_BIOS |
Select SerialNumber
```

---

# 🏁 Conclusion

CMD and PowerShell can provide a large amount of information about a used laptop without installing additional software.

However, **software checks alone are not enough**.

A proper used-laptop inspection should combine:

```text
CMD / PowerShell
        +
BIOS / UEFI
        +
Physical Inspection
        +
Battery Test
        +
SSD SMART Test
        +
RAM Test
        +
Temperature Test
        +
Display Test
        +
Keyboard / Port Test
        +
Ownership / Serial Verification
```

This gives a much better picture of the laptop's actual condition before purchasing.
