---
layout: page
title: Analogue Battery Charging Circuit
description: An educational hardware platform designed for undergraduate engineering students to bridge theoretical analogue design with practical component selection. <br> <span class="badge badge-pill badge-primary">Academic & Teaching</span> <span class="badge badge-pill badge-info">Analogue Design</span> <span class="badge badge-pill badge-success">PCB Layout</span> <span class="badge badge-pill badge-warning">Technical Mentorship</span>
img: assets/img/projects/2022-chargingcircuit/chargingcircuit-3d-isometric.png
importance: 3
category: "Professional engagement"
---

A strong foundation in theoretical electronics is only as valuable as the ability to implement it physically. While serving as an Assistant Lecturer for the Analogue Design module at Stellenbosch University in 2022, I recognized the need for a practical, accessible hardware project to help undergraduate students bridge this gap.

I conceptualised, architected, and routed a custom battery charging circuit designed specifically as an educational platform. The core architecture was provided to the students, who were then tasked with calculating and selecting the critical resistor networks required to achieve specific charging profiles.

---

### 1. Educational hardware design & Constraints

Designing hardware for an educational laboratory environment introduces unique constraints. The system had to be robust enough to survive student handling, yet simple enough to clearly demonstrate core analogue principles.

- **Design for Availability:** The entire schematic was intentionally constrained to utilise only standard, commonly available through-hole and SMD components already stocked in the university laboratories. This eliminated supply chain delays and ensured all students had equal access to replacement parts.
- **Analogue architecture:** The schematic was designed to cleanly separate the power delivery stages from the control logic. I architected the core topology, establishing the framework for constant-current and constant-voltage charging phases.
- **PCB Layout & Routing:** I routed the board to provide clear, logical test points, making it easy for students to probe with oscilloscopes and multimeters to verify their theoretical calculations against real-world physical behavior.

<div class="row justify-content-center text-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/2022-chargingcircuit/chargingcircuit-3d-topview.png" title="3D Top View" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">3D Altium top view of the charging circuit, showcasing the clean layout designed for easy probing and component population by students.</div>

---

### 2. Technical mentorship & Practical application

As an Assistant Lecturer, my goal was to elevate the students' understanding of component tolerances and real-world non-idealities.

- **The Student Task:** With the PCB and base architecture provided, students were required to mathematically model the circuit and select the exact resistor values necessary to set the charging voltage thresholds and current limits.
- **Bridging the Gap:** This project successfully forced students out of idealised textbook simulations and into the realities of standard resistor values (E12/E24 series), power dissipation considerations, and component tolerances.

<div class="row justify-content-center text-center mt-4">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/2022-chargingcircuit/charger_3d_isometric.png" title="3D Isometric View" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">3D isometric render of the battery charger board highlighting the standard, easily accessible components selected for the university laboratory.</div>

---

### Project assets & Documentation

The full documentation package provided to the students, including the core schematic and the physical PCB layout, is available below.

<br>

**Downloadable documentation:**

- [Download Schematic & PCB Layout (PDF)](/assets/pdf/projects/2022-chargingcircuit/Battery-Charger-Schematic-Layout.pdf)
