---
layout: page
title: Mixed-Signal Autonomous Robotic Vehicle
description: An educational hardware platform bridging analogue design and digital control, executed with full project lifecycle and supply chain management. <br> <span class="badge badge-pill badge-primary">Technical Project Management</span> <span class="badge badge-pill badge-info">Analogue Design</span> <span class="badge badge-pill badge-success">Mixed-Signal Systems</span> <span class="badge badge-pill badge-warning">Test Engineering</span>
img: assets/img/projects/2022-remotecar/system_architecture.png
importance: 4
category: "Professional engagement"
---

Executing a successful hardware product requires more than just circuit design; it demands rigorous project management, system-level architecture, and robust test engineering.

During my tenure as an Assistant Lecturer for the Analogue Design module in 2022, I architected, designed, and managed a semester-long hardware project for undergraduate engineering students. The objective was to build a radio-powered, object-detecting, and object-avoiding robotic vehicle utilising a strict mixed-signal approach.

Operating as the technical project manager and lead architect, I was responsible for the end-to-end delivery of the project framework—from conceptualising the analogue/digital split and deriving the system architecture, to managing the master Bill of Materials (BOM), designing automated testing mounts, and providing technical mentorship.

---

### 1. Mixed-Signal architecture & Analogue design

The core technical challenge was architecting a system where analogue circuitry and digital microcontrollers could operate harmoniously without ground loops or excessive noise coupling.

- **Analogue Control Logic:** Half of the vehicle was driven entirely by analogue electronics. I designed sub-circuits for ultrasonic signal conditioning, analogue subtractors, and emitter follower circuits to directly drive the wheels based on sensor inputs.
- **Digital Integration:** The analogue avoidance system was integrated alongside an ESP32 microcontroller, which handled telemetry, Bluetooth/WiFi communications, and digital pulse-width modulation (PWM) torque control.
- **Power Architecture:** I implemented a unified power management strategy from a 6V battery source, designing undervoltage protection and isolated 5V voltage regulation to safely power both the sensitive analogue op-amps and the RF microcontrollers.

<div class="row justify-content-center text-center">
    <div class="col-sm-10 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/2022-remotecar/system_architecture.png" title="Project System Diagram" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">High-level system diagram demonstrating the isolated processing paths for the analogue object avoidance logic and the digital remote control interface.</div>

---

### 2. Simulation & Verification (LTspice)

Before physically prototyping the hardware, the analogue signal chain required rigorous mathematical modelling. I utilised LTspice to simulate the complete analogue control loop prior to physical implementation.

This phase involved modelling sensor outputs, verifying the analogue subtractor's response to dynamic voltage changes, and simulating current sense logic. By front-loading the simulation, I ensured the baseline architecture provided to the students was mathematically sound and manufacturable.

<div class="row justify-content-center text-center mt-4">
    <div class="col-sm-12 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/2022-remotecar/ltspice_simulation.png" title="Extract from LTspice Analogue Simulation" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">Extract from the LTspice schematic simulating the analogue control logic and signal conditioning stages prior to hardware prototyping.</div>

---

### 3. Automated test engineering & Mechanical design

To rigorously assess the students' final builds, I introduced automated testing methodologies to the module.

Instead of relying on subjective manual testing, I utilised **Autodesk Inventor** to design and 3D-print a custom mechanical testing mount. This allowed the robotic vehicles to be suspended and run at full throttle while live telemetry and analogue responses were measured objectively. Designing the assessment method alongside the mechanical fixtures ensured a repeatable, controlled environment for validating hardware performance under stress.

---

### 4. Technical project management & Procurement

Beyond the technical design, a significant portion of my role involved acting as an engineering manager for the student cohort, ensuring smooth procurement and adherence to strict developmental milestones.

- **BOM & Supply Chain Management:** I managed the master Bill of Materials, sourcing specific components ranging from MCP6242 op-amps and ESP32 dev kits to basic mechanical hardware. I navigated component availability to ensure the project remained viable within the academic budget.
- **Timeline Derivation:** I broke the complex system down into a strict 12-week workflow. By establishing critical path milestones (e.g., physical current sense implementation in Week 2, DAC conversion in Week 4, and digital wheel control in Week 7), I ensured the project remained on schedule.

<div class="row justify-content-center text-center mt-4">
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/2022-remotecar/weekly_tasks.png" title="Timeline Management" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/2022-remotecar/bom_list.png" title="BOM Management" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">Excerpts from the formal project documentation showcasing the 12-week developmental roadmap and the comprehensive master BOM.</div>
