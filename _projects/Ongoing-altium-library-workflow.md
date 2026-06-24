---
layout: page
title: Component library & Lifecycle management
description: A standardised, version-controlled ECAD library and BOM management architecture. <br> <span class="badge badge-pill badge-dark">Altium / KiCad</span> <span class="badge badge-pill badge-primary">BOM Management</span> <span class="badge badge-pill badge-secondary">DFM</span>
img: assets/img/placeholder.jpg
importance: 4
category: "Passion projects"
---

### 1. The Engineering Standard

Relying on generic or auto-generated CAD footprints introduces significant risk during manufacturing. To ensure high-yield production and seamless BOM generation, I architected and maintain a personal, standardized component library encompassing schematics, footprints, and supply chain metadata.

### 2. Footprint & ECAD Architecture

Every footprint is designed adhering strictly to IPC standards, ensuring correct solder mask expansion, thermal relief, and precise courtyard clearances for dense component placement.

<div class="row text-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/footprint_showcase.jpg" title="Custom 3D Footprints" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">A selection of bespoke 3D footprints designed for optimal thermal dissipation and high-density routing.</div>

### 3. Schematic Clarity

Complex systems require readable schematics. My schematic symbols are heavily customized to group pins by logical function (e.g., segregating power domains, analog inputs, and digital buses) rather than physical pinout, radically reducing schematic clutter and routing errors.

### 4. Supply Chain & Metadata Management

A footprint is only as good as its manufacturability. I maintain a synchronized master component database that tracks critical metadata for every part.

- **Manufacturer Part Numbers (MPN):** Ensuring precise ordering.
- **Alternate Sourcing:** Tracking drop-in replacements for active components to mitigate supply chain shortages.
- **Parametric Data:** Storing tolerances, voltage ratings, and package sizes directly in the library for automated BOM generation.

<div class="row text-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/bom_schema.jpg" title="Component Metadata Schema" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">The underlying metadata schema ensuring accurate procurement and automated BOM generation.</div>
