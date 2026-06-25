---
layout: page
title: Analogue Battery Level Manager
description: An analogue signal conditioning circuit designed to scale and map battery voltage ranges for high-resolution ADC reading. <br> <span class="badge badge-pill badge-info">Analogue Design</span> <span class="badge badge-pill badge-primary">Signal Conditioning</span> <span class="badge badge-pill badge-success">LTspice</span>
img: assets/img/projects/2022-analoguebatterylevelmanager/fullschematic.png
importance: 5
category: "Professional engagement"
---

Monitoring battery health is critical for any untethered hardware device. However, microcontrollers cannot directly read voltages that exceed their internal operating logic, and employing a simple voltage divider often wastes valuable Analog-to-Digital Converter (ADC) resolution.

To address this, I designed a dedicated analogue signal conditioning circuit. By utilizing an operational amplifier to level-shift and scale the battery voltage, the microcontroller can safely and accurately monitor the state of charge across the battery's entire usable discharge curve.

---

### 1. The Analogue design challenge

A standard battery in this system charges to a peak of **3.7V**, but the onboard voltage regulator shuts down when the battery drops to **2.0V**. Meanwhile, the microcontroller's ADC pin only accepts inputs from **0V** to **3.3V**.

If a simple resistive voltage divider is used to step **3.7V** down to **3.3V**, the "empty" battery state (**2.0V**) would read as roughly **1.78V** on the ADC. This wastes more than half of the ADC's measurable range, drastically reducing the dynamic resolution and accuracy of the telemetry.

### 2. Signal conditioning architecture

To maximize the ADC resolution, I designed a differential amplifier circuit in LTspice that applies both a targeted gain and a specific DC offset. This maps the useful battery voltage window directly to the full input spectrum of the microcontroller.

- **Maximum Limit:** When the battery is fully charged (**3.7V**), the operational amplifier scales the output to precisely **3.3V** (the ADC maximum).
- **Minimum Limit:** When the battery hits the regulator's minimum operating voltage (**2.0V**), the analogue circuit applies a negative offset to output **0V** (the ADC minimum).

By mathematically shifting the lower bound to absolute zero, the microcontroller can utilise its entire digital resolution to track the discharge curve of the battery flawlessly.

<div class="row justify-content-center text-center mt-4">
    <div class="col-sm-10 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/2022-analoguebatterylevelmanager/fullschematic.png" title="LTspice Analogue Battery Level Manager" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">LTspice simulation of the differential amplifier circuit, demonstrating the resistor networks used to scale the 2.0V - 3.7V battery curve to a safe 0V - 3.3V ADC input.</div>
