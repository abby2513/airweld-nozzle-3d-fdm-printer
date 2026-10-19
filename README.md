# airweld-nozzle-3d-fdm-printer
Open-source thermal fusion manifold for FDM printers to achieve isotropic Z-axis strength . This system raises the layer interface temperature above the polymer's glass transition threshold ($T_g$) during deposition, promoting molecular diffusion and polymer reptation.
# Coaxial Hot Air Preheater (FDM Layer Fusion Manifold)

An open-source hardware project and experimental toolhead attachment designed to eliminate anisotropic Z-axis weakness in Fused Deposition Modeling (FDM) 3D printers. 

By delivering localized convective heating directly around the extrusion nozzle, this system raises the layer interface temperature above the polymer's glass transition threshold ($T_g$) during deposition, promoting molecular diffusion and polymer reptation.

---

## 🚀 Core Architecture

* **Annular Plenum Manifold:** A compact 360° toroidal ring surrounding the primary extrusion nozzle, functioning as a pressure-equalizing fluid plenum (inspired by multi-orifice annular gas burners).
* **Multi-Orifice Jet Array:** Features discrete micro-orifices (0.4mm – 0.5mm) drilled along the inner-bottom bevel at a 45° convergent angle to focus thermal energy onto the immediate weld interface without disturbing outer perimeters.
* **Secondary Heat Exchanger:** Repurposes a standard FDM heater block (V6/Volcano style) packed with a porous metal matrix (brass wool or copper mesh) to efficiently heat compressed air supplied by an off-toolhead diaphragm pump.

---

## 🛠️ Bill of Materials & Construction

1. **Air Heater Core:** 1x V6 or Volcano aluminum heater block, 24V 50W/60W heater cartridge, high-temp thermistor, and a titanium all-metal heatbreak (acting as a thermal standoff to prevent PTFE degradation).
2. **Internal Matrix:** Coarse brass wool or copper scrubber mesh packed inside the M6 bore to create a high-surface-area thermal exchange matrix.
3. **Coaxial Ring Nozzle:** 3mm OD soft annealed copper capillary tubing (or a two-piece machined brass ring) bent into a ~12mm inner-diameter loop, with 4 to 6 micro-drilled exit ports.
4. **Air Supply:** 12V/24V micro diaphragm air pump connected via 4mm PTFE tubing along the toolhead umbilical.

---

## ⚙️ Slicer & Firmware Strategies

To prevent part sagging on overhangs while achieving high internal Z-strength, this system utilizes dual-mode control:
* **Inner Perimeters & Infill:** Convective hot air is active ($180^\circ\text{C}$–$220^\circ\text{C}$ air stream) to weld internal layers.
* **Outer Skins, Bridges & Overhangs:** Hot air is cut off (or switched via a 3-way solenoid valve) and standard ambient part-cooling fans are engaged to freeze external geometry.

---

## 📂 Repository Contents
* `cad/` — Blender 3D models (`.blend`, `.stl`) of the dual-hotend toolhead assembly and coaxial manifold ring.
* `firmware/` — Sample Klipper configuration macros for air-heater thermal loops and pump PWM scaling.

## 📄 License
This hardware and documentation are released under the **GNU General Public License v3.0 (GPLv3)**. See the `LICENSE` file for details.
