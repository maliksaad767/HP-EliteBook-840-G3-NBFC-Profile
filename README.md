# HP EliteBook 840 G3 - Notebook FanControl (NBFC) Profile

This repository contains a highly optimized, EC-verified Notebook FanControl (NBFC) configuration file for the **HP EliteBook 840 G3** and related HP EliteBook models. 

If your HP laptop suffers from a loud, whining fan at idle, or if it constantly thermal throttles under heavy load, this custom XML profile safely takes control of the Embedded Controller (EC) to provide a quiet, balanced thermal curve.

## 💻 Supported Models
This configuration was built specifically for the 840 G3, but shares Embedded Controller (EC) logic with the following HP laptops:
* HP EliteBook 840 G3
* HP EliteBook 850 G3 (Untested, but likely compatible)
* HP EliteBook 820 G3 (Untested, but likely compatible)
* HP EliteBook 745 G3 (Untested, but likely compatible)
* HP ZBook 14u G3 (Untested, but likely compatible)

## 🛠️ What This Profile Fixes
* **Loud Fan at Idle:** Keeps the fan completely off at 0% when the CPU is under 44°C.
* **Aggressive BIOS Override:** Tricks the HP BIOS by constantly writing a "fake temperature" to the EC (Register 38), preventing the BIOS from stealing fan control back from NBFC.
* **Thermal Throttling:** Ramps the fan up to 100% at 85°C to prevent the CPU from hitting the 100°C critical throttle limit.

## 🚀 How to Install
1. Download and install [Notebook FanControl (NBFC)](https://github.com/hirschmann/nbfc/releases).
2. Download the `HP_EliteBook_840_G3_Optimized.xml` file from this repository.
3. Move the XML file into your NBFC configs directory (Usually located at `C:\Program Files (x86)\NoteBook FanControl\Configs`).
4. Open the NBFC application.
5. Click the gear icon to open Settings.
6. Select **HP EliteBook 840 G3 Perfect** from the dropdown menu and apply.
7. Ensure the service is "Enabled".

## 📊 Technical Details for Developers
For those looking to tweak this further, here are the verified EC registers used in this build:
* **Fan Read Register:** `0x2E` (46)
* **Fan Write Register:** `0x2F` (47)
* **HP Thermal Zone Select:** `0x22` (34)
* **Fake Temperature Write:** `0x26` (38)

---
*Keywords for Search: HP 840 G3 fan noise fix, HP EliteBook loud fan, Notebook FanControl HP 840 G3, NBFC config HP Elitebook, HP 850 G3 fan control, HP EliteBook overheating fix.*
