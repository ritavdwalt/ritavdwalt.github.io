---
layout: page
title: Component library & Lifecycle management
description: A standardised, version-controlled ECAD library and BOM management architecture. <br> <span class="badge badge-pill badge-dark">Altium Designer</span> <span class="badge badge-pill badge-primary">BOM Management</span> <span class="badge badge-pill badge-secondary">DFM</span>
img: assets/img/projects/Ongoing-altium-library-workflow/library-pcb-3d.png
importance: 4
category: "Passion projects"
---

To engineer hardware reliably at scale requires moving beyond default software settings. To minimise error risk, eliminate fabrication delays, and accelerate the transition from design to mass production, I have architected and maintained a comprehensive ECAD infrastructure in Altium Designer.

This workflow is built upon three core pillars:

1. **Custom PCB/SCH library:** Over 90 meticulously designed, IPC-compliant footprints with embedded 3D models and parametric metadata.
2. **Manufacturing rule sets (DFM):** Custom DRC/ERC profiles that automate complex constraints.
3. **Component selection strategy:** A maintained database of common lumped components prioritising supply chain resilience, and time-and-cost-efficiency.

---

### 1. Footprint and ECAD architecture

My schematic symbols are customised to group pins by logical function (e.g., separating power domains, analogue inputs, and digital buses) rather than physical pinout, drastically enhancing readability while reducing schematic clutter and routing errors. Every footprint is designed adhering strictly to IPC standards, ensuring correct solder mask expansion, thermal relief, and precise courtyard clearances for dense component placement.

<div class="row">
  <div class="col-sm mt-3 mt-md-0">
    {% include figure.liquid loading="eager" path="assets/img/projects/Ongoing-altium-library-workflow/library-schem.png" title="Custom component library selection" class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm mt-3 mt-md-0">
    {% include figure.liquid loading="eager" path="assets/img/projects/Ongoing-altium-library-workflow/library-pcb-3d.png" title="Custom 3D footprints selection" class="img-fluid rounded z-depth-1" %}
  </div>
</div>
<div class="caption">
  <strong>Left:</strong> A selection of representative components prioritising logical pin grouping. <strong>Right:</strong> 3D footprints designed for optimal thermal dissipation and accurate mechanical collision checking.
</div>

**Library excerpt breakdown:**

- **U1 (RF/MCU):** Custom ESP32 footprint featuring accurate 3D step models for mechanical clearance and optimised thermal pad expansion for reflow.
- **U2 (Opto-isolation):** Phototransistor optocoupler for basic signal isolation and level shifting.
- **U3 (Galvanic isolation):** Digital isolator symbol explicitly denoting the internal isolation barrier, ensuring safe separation of digital and high-voltage ground planes during layout.
- **JP1 (Interconnect):** 16-pin USB-C receptacle capturing complex mechanical mounting pegs and precise CC/SBU pin definitions for power delivery (PD) negotiation.
- **L1 (Power):** High-current SMD inductor footprint tailored for custom switch-mode power supply (SMPS) layouts.
- **H1 (External connector):** Standardised header connector for external peripherals.

---

### 2. Design for manufacturing (DFM) & Rules constraints

To eliminate production delays and guarantee high-yield manufacturing, I maintain a strictly version-controlled set of DRC (Design Rule Check) profiles.

Rather than relying on default parameters, my rule sets are tailored to specific fabrication capabilities (e.g., standard vs. advanced HDI manufacturing) and employ custom queries to automate complex constraints.

<div class="row">
  <div class="col-sm mt-3 mt-md-0">
    {% include figure.liquid loading="eager" path="assets/img/projects/Ongoing-altium-library-workflow/designrules_antennawidth.png" title="Custom DRC query for antenna and RF tracks on FR4 four-layer board" class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm mt-3 mt-md-0">
    {% include figure.liquid loading="eager" path="assets/img/projects/Ongoing-altium-library-workflow/designrules_polygonconnect.png" title="Custom DRC query for power planes and polygons connect style" class="img-fluid rounded z-depth-1" %}
  </div>
</div>
<div class="caption">
  <strong>Left:</strong> Custom DRC query enforcing a calculated 0.35mm trace width for 50-ohm impedance matching on RF nets. <strong>Right:</strong> Prioritised polygon connect styles applying precise thermal reliefs to SMD pads to prevent tombstoning.
</div>

---

### 3. Supply chain & Metadata management

I maintain a synchronised master component database that tracks critical metadata for every part to save time during the design process and optimise manufacturability and component availability.

- **Manufacturer part numbers (MPN):** Parametric data also stored directly in the Altium library for automated, error-free BOM generation.
- **Alternate sourcing:** Tracking drop-in replacements for active components to mitigate supply chain shortages.
- **Standardised inventory:** Maintaining a curated list of preferred passives (e.g., specific X7R capacitors or thick-film resistors) to streamline purchasing and assembly.

<div class="row justify-content-center text-center">
    <div class="col-sm-9 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/Ongoing-altium-library-workflow/bommanage-resistors.png" title="Extract from resistors common lumped components sheet" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">The underlying metadata schema enforcing standardised selection for passive components.</div>

<div class="row justify-content-center text-center">
    <div class="col-sm-9 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/Ongoing-altium-library-workflow/bommanage-dropdowns.png" title="Extract from common lumped components sheet dropdown information" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">Parametric categories driving the component selection strategy, ensuring the correct dielectric, tolerance, and package size are used for the application.</div>
