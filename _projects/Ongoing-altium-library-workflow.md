---
layout: page
title: IN PROGRESS - Component library & Lifecycle management
description: A standardised, version-controlled ECAD library and BOM management architecture. <br> <span class="badge badge-pill badge-dark">Altium Designer</span> <span class="badge badge-pill badge-primary">BOM Management</span> <span class="badge badge-pill badge-secondary">DFM</span>
img: assets/img/placeholder.jpg
importance: 4
category: "Passion projects"
---

### 1. The Engineering Standard

Relying on generic or auto-generated CAD footprints introduces manufacturing risk. To ensure high-yield production and seamless BOM generation, I created and maintain a personal, standardised component library encompassing schematics, footprints, and supply chain metadata. This library was created in 2021 and has been maintained and updated since. <!-- TODO also add info about design rules, manufacturing standards, BOM management, etc -->

### 2. Footprint & ECAD Architecture

Every footprint is designed adhering strictly to IPC standards, ensuring correct solder mask expansion, thermal relief, and precise courtyard clearances for dense component placement.

<div class="row text-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/Ongoing-altium-library-workflow/library-schem.png" title="Custom component library selection" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">A selection of representative components from my custom library.</div>

<div class="row text-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/Ongoing-altium-library-workflow/library-pcb-3d.png" title="Custom 3D footprints selection" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">A selection of representative 3D footprints designed for optimal thermal dissipation and high-density routing.</div>

Library exerpt breakdown:

- **U1** (RF/MCU): Custom ESP32 footprint featuring accurate 3D step models for mechanical clearance and optimised thermal pad expansion for reflow.
- **U3** (Galvanic isolation): Digital isolator symbol explicitly denotes the internal isolation barrier, ensuring safe separation of digital and high-voltage ground planes during layout.
- **JP1** (Interconnect): 16-pin USB-C receptacle capturing complex mechanical mounting pegs and precise CC/SBU pin definitions for power delivery (PD) negotiation.
- **L1** (Power): High-current SMD inductor footprint tailored for custom switch-mode power supply (SMPS) layouts.
- **H1** (External connector): Connector for external components or power supply.

### 3. Design for Manufacturing (DFM) & Rules Constraints

A beautiful layout is useless if the fabrication house rejects it. To eliminate production delays and guarantee high-yield manufacturing, I maintain a strictly version-controlled set of DRC (Design Rule Check) and ERC (Electrical Rule Check) profiles.

Rather than relying on default parameters, my rule sets are tailored to specific fab capabilities (e.g., standard vs. advanced HDI manufacturing) and employ custom queries to automate complex constraints.

- **Clearance Matrices:** Pre-defined isolation rules for high-voltage and high-current nets.
- **Impedance Control:** Automated trace width and gap constraints for RF and differential pairs.
- **Polygon Pours:** Custom thermal relief rules tailored to specific component package sizes to prevent tombstoning during reflow.

<div class="row text-center">
    <div class="col-sm mt-3 mt-md-0">
        <!-- Insert a cropped, zoomed-in screenshot of a complex Altium custom query or a clean snippet of a rule definition -->
        {% include figure.liquid loading="eager" path="assets/img/projects/Ongoing-altium-library-workflow/designrules_antennawidth.png" title="Custom DRC query for antenna and RF tracks on FR4 four-layer board" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">Custom DRC query for antenna and RF tracks on FR4 four-layer board ensuring physical constraints are automatically enforced during layout.</div>

<div class="row text-center">
    <div class="col-sm mt-3 mt-md-0">
        <!-- Insert a cropped, zoomed-in screenshot of a complex Altium custom query or a clean snippet of a rule definition -->
        {% include figure.liquid loading="eager" path="assets/img/projects/Ongoing-altium-library-workflow/designrules_polygonconnect.png" title="Custom DRC query for power planes and polygons connect style" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">Custom DRC query for power planes and polygons connect style ensuring physical constraints are automatically enforced during layout.</div>

### 4. Schematic Clarity

Complex systems require readable schematics. My schematic symbols are heavily customised to group pins by logical function (e.g., separating power domains, analog inputs, and digital buses) rather than physical pinout, reducing schematic clutter and routing errors risk.

### 5. Supply Chain & Metadata Management

A footprint is only as good as its manufacturability. I maintain a synchronised master component database that tracks critical metadata for every part.

- **Manufacturer part numbers (MPN):** Ensuring precise and efficient ordering.
- **Alternate Sourcing:** Tracking drop-in replacements for active components to mitigate supply chain shortages.
- **Parametric Data:** Storing tolerances, voltage ratings, and package sizes directly in the library for automated BOM generation.

<div class="row text-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/Ongoing-altium-library-workflow/bommanage-resistors.png" title="Extract from resistors common lumped components sheet" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">Extract from resistors sheet underlying metadata schema ensuring accurate procurement and automated BOM generation.</div>

<div class="row text-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/Ongoing-altium-library-workflow/bommanage-dropdowns.png" title="Extract from common lumped components sheet dropdown information" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">Extract from common components sheet metadata and considerations ensuring accurate procurement.</div>
