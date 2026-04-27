
- 📐 [Schaltplan (PDF)](hardware/schematic/schematic.pdf)
- 🧭 [PCB-Layout (PDF)](hardware/pcb/layout.pdf)
- 🧾 [Stückliste (BOM)](docs/BOM.xlsx)
- ⚙️ [Firmware Build & Flash](firmware/README.md#build--flash)
- ✅ [Testergebnisse](docs/test-report.md)
## Build & Flash
This schematic shows an AC-to-DC switching mode power supply (SMPS).  
The AC input is first rectified by the bridge rectifier and then smoothed by the bulk capacitor to create a high-voltage DC bus.  
The UC3842 controller generates switching pulses that drive the IRF740 MOSFET.  
The MOSFET rapidly switches the transformer primary, transferring energy in high-frequency pulses instead of using a low-frequency linear conversion method.  
On the secondary side, the output is rectified by a fast diode and filtered by capacitors and an inductor to produce a stable DC voltage.  
A feedback network returns regulation information to the controller so that the output voltage remains controlled under changing load conditions.  
This design improves efficiency, reduces transformer size, and is widely used in
### Build
```bash
pio run
