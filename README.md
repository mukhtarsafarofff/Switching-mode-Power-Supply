
- 📐 [Schaltplan (PDF)](hardware/schematic/schematic.pdf)
- 🧭 [PCB-Layout (PDF)](hardware/pcb/layout.pdf)
- 🧾 [Stückliste (BOM)](docs/BOM.xlsx)
- ⚙️ [Firmware Build & Flash](firmware/README.md#build--flash)
- ✅ [Testergebnisse](docs/test-report.md)
## Build & Flash
(ENG)This schematic shows an AC-to-DC switching mode power supply (SMPS).  
The AC input is first rectified by the bridge rectifier and then smoothed by the bulk capacitor to create a high-voltage DC bus.  
The UC3842 controller generates switching pulses that drive the IRF740 MOSFET.  
The MOSFET rapidly switches the transformer primary, transferring energy in high-frequency pulses instead of using a low-frequency linear conversion method.  
On the secondary side, the output is rectified by a fast diode and filtered by capacitors and an inductor to produce a stable DC voltage.  
A feedback network returns regulation information to the controller so that the output voltage remains controlled under changing load conditions.  
This design improves efficiency, reduces transformer size, and is widely used in



(DE)
Diese Schaltung zeigt ein AC-zu-DC-Schaltnetzteil (SMPS).  
Die Wechselspannung am Eingang wird zuerst durch den Brückengleichrichter gleichgerichtet und anschließend durch den Siebkondensator zu einer Hochspannungs-Gleichspannung geglättet.  
Der UC3842-Controller erzeugt Schaltimpulse zur Ansteuerung des IRF740-MOSFETs.  
Der MOSFET schaltet die Primärseite des Transformators mit hoher Frequenz, sodass die Energie in Impulsen übertragen wird und keine verlustreiche lineare Wandlung erforderlich ist.  
Auf der Sekundärseite wird die Ausgangsspannung durch eine schnelle Diode gleichgerichtet und durch Spule sowie Kondensatoren geglättet.  
Ein Rückkopplungsnetzwerk liefert Regelinformationen an den Controller zurück, damit die Ausgangsspannung auch bei Laständerungen stabil bleibt.  
Dieses Design bietet einen hohen Wirkungsgrad, kleinere Bauteilgrößen und wird häufig in kompakten Elektroniknetzteilen eingesetzt.
### Build
```bash
pio run
