# Gordon Anderson — GAA Custom Electronics 🔬

Welcome! I design and build high-performance scientific instrumentation, specialized embedded controllers, and custom hardware modules tailored for mass spectrometry, ion mobility separation, and ion processing applications. 

This profile serves as a structured dashboard to navigate active production firmware, next-generation architectures, standalone instrument platforms, and core infrastructure libraries.

---

## ⚡ MIPS Modular Power Supply Ecosystem
The Modular Intelligent Power Sources (MIPS) platform is a highly flexible, multi-channel instrumentation control architecture deployed globally across academic and industrial mass spectrometry research labs.

### 🎛️ Active Production Firmware
*   **[MIPS](https://github.com/GordonAnderson/MIPS)** — High-performance core firmware running the production MIPS instrument ecosystem on the Arduino Due (SAM3X8E ARM Cortex-M3 @ 84MHz), managed via PlatformIO.
*   **[MIPS-Isolated-Controller](https://github.com/GordonAnderson/MIPS-Isolated-Controller)** — Firmware for a standalone or system-integrated module that provides up to 5kV of electrical isolation for all downstream connected MIPS modules.

### 🧠 Smart Hardware Modules (Embedded Processors)
While managed by the central MIPS controller, several auxiliary hardware modules within the MIPS ecosystem utilize localized on-board processors to handle high-speed tasks, real-time calculations, and complex internal signaling:

*   **[FAIMSfb](https://github.com/GordonAnderson/FAIMSfb)** — Dedicated module firmware for managing High-Field Asymmetric Waveform Ion Mobility Spectrometry, utilizing flyback transformer technology to generate high-voltage RF waveforms.
*   **[RFdriver](https://github.com/GordonAnderson/RFdriver)** — Enables a MIPS system to drive two high-Q RF heads. Up to four modules can be combined in a single chassis to support 8 high-Q RF heads simultaneously.
*   **[ARB](https://github.com/GordonAnderson/ARB)** / **[ARB2](https://github.com/GordonAnderson/ARB2)** — Arbitrary Waveform Generator module firmware driving 8 separate output channels. Specialized variants feature dedicated TWave generation algorithms with advanced control profiles.
*   **[DualElec](https://github.com/GordonAnderson/DualElec)** — Firmware targeting the dual-channel electrometer input module interfaces.
*   **[IsolatedElectrometer](https://github.com/GordonAnderson/IsolatedElectrometer)** — Specialized floating electrometer module leveraging on-board DSP to significantly optimize signal-to-noise ratios.
*   **[HVpowerSupplyInterface](https://github.com/GordonAnderson/HVpowerSupplyInterface)** — Interface module allowing MIPS to seamlessly command, adjust, and monitor output parameters across a wide range of external high-voltage modules.
*   **[DCBswitch](https://github.com/GordonAnderson/DCBswitch)** — Integrates four $\pm250\text{V}$ programmable power supplies and two high-speed FET switches, enabling MIPS to generate sub-microsecond high-voltage pulses.
*   **[LevelDet](https://github.com/GordonAnderson/LevelDet)** — High input impedance, high-voltage monitor designed to instantly notify the MIPS controller of threshold level changes for real-time reactive event handling.
*   **[PowerCtrl](https://github.com/GordonAnderson/PowerCtrl)** — Power control utility for MIPS motherboard configurations, allowing users to script customized hardware power-on sequences.
*   **[MIPSnet](https://github.com/GordonAnderson/MIPSnet)** — Firmware enabling wireless hardware modules to interface with MIPS, establishing wireless data transmission pipelines to the host software.

### 🔳 Next-Generation Architecture
*   **[MIPS_STM](https://github.com/GordonAnderson/MIPS_STM32)** *(In Development)* — Ground-up architecture migration to the **STM32H743** (Cortex-M7 running at 440 MHz). Built natively using **STM32Cube (HAL/LL)**, decoupling entirely from the legacy Arduino framework to unlock unparalleled processing overhead and ultra-precise hardware timing.

---

## 🔬 Standalone Instruments (Embedded Microcontrollers)
Dedicated standalone scientific instruments engineered with integrated processors to drive localized control, waveform generation, and analytical workflows independently of a larger MIPS base chassis:

*   **[SLIMrev](https://github.com/GordonAnderson/SLIMrev)** *(Twave Reverser)* — Standalone module providing polarity/direction reversal for sets of TWave signals in any traveling-wave device, supporting voltage levels up to $100\text{V}_{pp}$. (Repository name retained; the product is now the Twave Reverser.)
*   **[FETpulser](https://github.com/GordonAnderson/FETpulser)** — Dual-output, high-speed FET pulser featuring a wireless configuration interface and user-programmable gate pulse generators.
*   **[RFgenerator](https://github.com/GordonAnderson/RFgenerator)** — Control firmware for dedicated standalone RF generators, engineered to drive ion funnels, TWave modules, ion guides, and related ion optics.
*   **[RFmega](https://github.com/GordonAnderson/RFmega)** — Specialized firmware for the RF Mega Generator, optimized to stable-drive highly capacitive and lossy experimental loads.
*   **[RemoteElectrometer](https://github.com/GordonAnderson/RemoteElectrometer)** — Multi-stage electrometer featuring a floatable remote measurement head that safely transmits low-current telemetry back to a base module for host system processing.
*   **[Astraea](https://github.com/GordonAnderson/Astraea)** — Next-generation waveform generation platform engineered explicitly for digital quadrupole and ion trap structures.
*   **[QUADdriver250V](https://github.com/GordonAnderson/QUADdriver250V)** — Embedded driver firmware managing high-voltage, FET-based rod driver networks for the Astraea system, supporting pulse waveforms up to $\pm250\text{V}$.
*   **[PulseValve](https://github.com/GordonAnderson/PulseValve)** — Fast-acting valve controller firmware optimized for gas pulsed valve timing injections within vacuum chambers.
*   **[MFT](https://github.com/GordonAnderson/MFT)** — Multi-Function TWave standalone system, providing a full-featured framework for independent TWave generation.
*   **[FAIMSrec](https://github.com/GordonAnderson/FAIMSrec)** — Dedicated standalone system optimized for generating precise rectangular FAIMS waveforms.

---

## 💻 Host Applications & Tooling
Desktop client interfaces and scripts designed to map, command, and monitor active instrument hardware across automated testing profiles.

*   **[MIPS_QT6](https://github.com/GordonAnderson/MIPS_QT6)** — Flagship cross-platform desktop control framework built using C++ and multi-threaded Qt6 event environments.
*   **[MIPS-Python-Host-app](https://github.com/GordonAnderson/MIPS-Python-Host-app)** — Python-centric variant of the MIPS host software, opening fast scriptable access and high-level cross-platform diagnostic integration.

---

## 🚀 Core Frameworks & Libraries
The modular infrastructure layer underlying my firmware repositories, prioritizing portable and abstract code reuse.

*   **[GAACE_Core](https://github.com/GordonAnderson/GAACE_Core)** — Reusable, architecture-agnostic C++ core libraries forming the foundation of firmwares across multiple hardware platforms (SAMD21, SAMD51, SAM3X8, ESP32, Teensy, and STM32).
*   **[GAACE_Template](https://github.com/GordonAnderson/GAACE_Template)** — A standardized PlatformIO starter template used to rapidly bootstrap new modules communicating with the MIPS host over USB serial or optional TCP/IP protocols.

---

## 📡 Specialized Hardware Projects
Targeted software wrappers and interface controllers managing auxiliary radio and custom communication equipment.

*   **[RemoteKeyer](https://github.com/GordonAnderson/RemoteKeyer)** — System layouts and firmware automating local/remote transmission keying parameters.
*   **[ICOM.py](https://github.com/GordonAnderson/ICOM.py)** — Python-based CAT control utility handling passthrough instructions for external HF transceivers.

---

## 📄 Licensing

I believe research instruments should outlive their documentation and their vendor. My firmware and host software have been public here since the beginning, and hardware designs are being published progressively. Each repository carries its own `LICENSE` file, which governs. **Unless a repository states otherwise,** the defaults for the instrumentation projects above are:

| Asset type | License | SPDX identifier |
|---|---|---|
| Hardware design files (schematics, PCB, Gerbers, BOM) | CERN Open Hardware Licence v2 — Weakly Reciprocal | `CERN-OHL-W-2.0` |
| Firmware (runs on GAACE hardware) | MIT License | `MIT` |
| Host applications / portable software | GNU General Public License v3.0 or later | `GPL-3.0-or-later` |
| Documentation and manuals | Creative Commons Attribution 4.0 | `CC-BY-4.0` |

You may study, modify, manufacture, and distribute these designs — including commercially — subject to the terms of the applicable license. For hardware, that means publishing your modified **design files** under the same license if you distribute a product based on them; changes to the surrounding instrument do not have to be published.

**Trademarks are not licensed.** "GAA Custom Electronics," "GAACE," "MIPS," and "Astraea" are marks of GAA Custom Electronics, LLC. You may accurately state that your work is based on one of these designs; you may not use these names or the GAACE logo to identify your own product or to imply endorsement.

**A request, not a requirement:** if you're manufacturing these designs commercially, I'd appreciate hearing from you first.

If a design you need isn't published yet, or your institution requires a specific license identifier for procurement, get in touch — I'd rather have that conversation than have you go without. More on the approach at [gaacustom.com/open-source.html](https://www.gaacustom.com/open-source.html).

> **Note:** the amateur-radio projects (`RemoteKeyer`, `ICOM.py`) are personal work outside the GAACE product line; check each repository for its own terms.

---

📬 **Connect & Collaborative Engineering:** Explore custom configurations, design pipelines, and complete open-source instrumentation platforms at [GAAcustom.com](https://www.gaacustom.com).
