---
layout: page
title: Automated Transfer Switch (Relay Board)
description: A custom-designed, 16A automated transfer switch deployed across Western Cape schools to seamlessly manage Eskom and inverter power during load shedding. <br> <span class="badge badge-pill badge-primary">Professional Engagement</span> <span class="badge badge-pill badge-info">Hardware Architecture</span> <span class="badge badge-pill badge-success">PCB Design</span> <span class="badge badge-pill badge-warning">Component Sourcing</span>
img: assets/img/projects/2023-schools-relays/school-relay-3d-isometric.png
importance: 2
category: "Professional engagement"
---

Frequent load shedding and municipal power outages pose a significant disruption to education in South Africa. For schools equipped with solar installations and backup inverters, seamless automation between grid power and backup power is essential.

To solve this, I engineered a custom Automated Transfer Switch (ATS) relay board. I managed the complete hardware delivery lifecycle: from initial component sourcing and schematic design to final PCB layout and manufacturing preparation.

This system was successfully manufactured and rolled out to multiple schools across the Western Cape, ensuring uninterrupted power for classrooms and administrative infrastructure.

---

### 1. Hardware engineering & Component sourcing

Designing for a school environment meant that safety, reliability, and manufacturability were the highest priorities. The system required robust switching capabilities to handle sudden grid state changes without faulting or dropping the load.

- **Version iterations:** I developed two primary variations of the board: a 12A rated version and a robust 16A rated version to cater to different school infrastructure loads. The details below highlight the 16A model (Version 4).
- **Supply chain management:** Navigating global supply chain constraints, I performed all component selection and sourcing. I prioritized robust, high-availability components to ensure the boards could be manufactured continuously and cost-effectively at scale.
- **Schematic capture:** Designed a streamlined, highly reliable schematic focused on fault-tolerant relay switching logic, ensuring the backup inverter immediately takes over upon Eskom grid failure, and safely hands back over once municipal stability is restored.

---

### 2. High-Voltage PCB design & Safety

While the schematic logic of a relay board is relatively straightforward, the PCB layout requires strict adherence to high-voltage and high-current design rules.

- **Creepage & Clearance:** Because the board switches 230V AC mains power, the PCB was routed with strict isolation barriers, adhering to standard creepage and clearance rules to prevent high-voltage arcing and ensure absolute safety for the end-users.
- **High-Current routing:** The 16A continuous current rating required precise calculation of copper trace widths and polygon pours to manage thermal dissipation and prevent localized heating on the board.
- **Design for Manufacturing (DFM):** The board was optimized for straightforward assembly and installation, utilizing reliable screw terminals and clear silkscreen labelling to assist the electricians installing the units in the field.

<div class="row justify-content-center text-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/2023-schools-relays/school-relay-top-view-pcb.png" title="2D PCB Layout" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">2D PCB layout highlighting the high-current polygon pours and high-voltage isolation routing.</div>

<div class="row justify-content-center text-center mt-4">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/2023-schools-relays/school-relay-3d-isometric.png" title="3D PCB Render" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">3D Altium render of the Version 4 (16A) relay board, showcasing the physical footprint and terminal placements.</div>

---

### Real-World impact

This project bridges the gap between theoretical electronic design and tangible, commercial hardware delivery. Seeing these boards actively deployed in electrical distribution boards across the Western Cape—keeping lights and computers on for students during load shedding—stands as a strong testament to the real-world utility of robust engineering.
