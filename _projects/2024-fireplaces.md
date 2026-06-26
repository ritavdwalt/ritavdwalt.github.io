---
layout: page
title: Residential IAQ & Fireplace Emissions
description: Modifying generic IoT hardware for a multi-site deployment, encompassing ethical administration, high-frequency data analysis, science communication, and a peer-reviewed publication. <br> <span class="badge badge-pill badge-primary">Hardware Adaptation</span> <span class="badge badge-pill badge-info">Stakeholder Management</span> <span class="badge badge-pill badge-success">Data Analysis</span> <span class="badge badge-pill badge-secondary">Science Comm</span>
img: assets/img/projects/2024-fireplaces/in-enclosure-3d.jpg
importance: 3
category: "Academic research"
---

While my primary LoRaWAN sensor network was designed for educational infrastructure, I modified and deployed my generic Indoor Air Quality (IAQ) sensing device into a residential setting to investigate the impact of amenity indoor fireplaces on household air quality.

This project required more than just hardware engineering; it demanded rigorous stakeholder management, formal research administration, and the coordination of a multi-site deployment across eight private households.

The high-frequency data collected during the five-month winter period was rigorously analysed, resulting in a first-author publication in the peer-reviewed journal _Energy Research & Social Science_ and widespread national media coverage.

---

### 1. Hardware modification & Firmware adaptation

Deploying sensors in affluent, private households requires a different approach than deploying them in public school infrastructure. The hardware had to be unobtrusive, reliable, and aesthetically acceptable for a living room environment.

- **Hardware Adaptation:** I adapted my generic Atmel-based IAQ node, utilizing the Plantower PMS5003 laser-scattering particulate matter sensor. The enclosure was redesigned and tested to ensure ample airflow and ventilation while maintaining a compact footprint that could be powered continuously via a standard electrical outlet.
- **Firmware for Transient Capture:** To accurately capture the rapid spikes in particulate matter (PM1.0, PM2.5, and PM10) associated with lighting a fire, I modified the embedded firmware. The device was programmed to sample and transmit data precisely every 11 minutes (over 130 times daily), ensuring no transient emission events were missed.

<div class="row justify-content-center text-center">
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/2024-fireplaces/in-enclosure-3d.jpg" title="Adapted Sensing Device" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">The modified sensing node deployed in the residential households, adapted from my generic IAQ hardware architecture.</div>

---

### 2. Stakeholder management & Ethical administration

Conducting hardware research inside private homes introduces profound logistical and ethical complexities that go beyond standard engineering tasks.

- **Project Proposals & Ethical Clearance:** I authored the formal project proposal and comprehensive technical reports required by the institutional review board. I successfully navigated the ethics committee, drafting the strict protocols needed to ensure occupant privacy, data anonymization, and informed consent for human-environment research.
- **Multi-Site Deployment & Coordination:** I managed the physical deployment across eight different households in Stellenbosch. This required coordinating installation schedules with homeowners, ensuring proper sensor placement relative to open and enclosed fireplaces, and maintaining continuous communication to manage device uptime throughout the winter season.

---

### 3. Data analysis & Environmental correlation

The devices generated a dense, high-frequency dataset that required complex pre-processing to extract meaningful insights regarding human behavior and indoor air quality.

- **Data Processing Pipeline:** I developed Python scripts to clean the dataset, removing invalid measurements and calculating highly specific 24-hour sliding window averages to benchmark the data against strict WHO and EPA exposure guidelines.
- **Ambient Weather Integration:** To prove that colder weather drove fireplace usage and subsequently worsened indoor air quality, I integrated external meteorological data. By pulling hourly ambient temperature data from the NOAA Environmental Monitoring System, I programmatically correlated outdoor weather patterns with indoor PM2.5 spikes.

<div class="row justify-content-center text-center mt-4">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/2024-fireplaces/ambient-temp.png" title="PM2.5 and Temperature Correlation" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">Data analysis demonstrating the negative linear correlation between outdoor ambient temperatures and indoor PM2.5 spikes during fireplace use.</div>

---

### 4. Science communication & Real-world impact

Data is only valuable if it drives change. During the experiment, my automated data analysis flagged dangerously high PM2.5 levels in one specific household. By presenting these data-driven findings directly to the stakeholders, the occupants immediately ceased indoor fire-making, resulting in a stark, immediate drop in particulate matter.

Beyond the academic publication, the findings of this project garnered significant national media attention. I conducted a comprehensive press tour, featuring live television interviews on **eNCA**, as well as prominent radio segments on **RSG**, **Cape Talk**, and various Johannesburg stations.

This required high-level **Science Communication**—distilling dense statistical data, air quality guidelines, and complex engineering methodologies into accessible, actionable information for the general public.

<div class="row justify-content-center text-center mt-4">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/2024-fireplaces/interview_heading.jpg" title="eNCA Live Television Interview" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">Live television interview on eNCA, discussing the engineering methodology and public health findings of the residential fireplace study.</div>

<div class="row justify-content-center text-center mt-4">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/2024-fireplaces/behaviour_change.png" title="Behavioral Change Data" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">Time-series data proving the immediate, drastic reduction in indoor PM2.5 levels after occupants were informed of the sensor readings.</div>

<br>

### Media press release

The work from this project gained substantial media attention with interviews done with blog posts, live televised interviews on eNCA and numerous radio interviews on local and national radio stations (Cape Talk, RSG, and Johannesburg radio). The video below shows an extract of the soundbites recorded for the Stellenbosch University press release.

<div class="row justify-content-center mt-4">
    <div class="col-sm-10 text-center">
        <div class="embed-responsive embed-responsive-16by9 z-depth-1 rounded">
            <iframe class="embed-responsive-item" src="https://www.youtube.com/embed/g6tGqoeZ2Qk" allowfullscreen></iframe>
        </div>
    </div>
</div>

<br>
