# System Architecture

## Overview

### Data governance (Web3 + IPFS)
- Fleek frontend for decentralised upload
- IPFS immutable storage
- Community ownership verification

### Three hierarchical storytelling modes:

**MODE A: Playback**
- Strict reproduction of recorded stories
- For sacred/sensitive narratives

**MODE B: RAG (Retrieval-Augmented Generation)**
- Contextually relevant story selection
- Maintains narrative fidelity

**MODE C: Generative**
- Situation-adaptive narratives
- Fine-tuned LLM responds to context
- For participatory/educational storytelling

<img width="890" height="670" alt="Screenshot 2026-01-03 at 20 09 02" src="https://github.com/user-attachments/assets/271c0fa3-a71a-49e3-aaf2-d26a475e0c8b" />


### Perception layer (OpenCV + real-time vision)
- Situated image generation
- Emotion-aware adaptation

<img width="991" height="548" alt="Screenshot 2026-01-03 at 20 13 09" src="https://github.com/user-attachments/assets/874fc31f-a9da-4067-8493-c0794936216d" />

- **See [EMOTION_RESEARCH.md](EMOTION_RESEARCH.md) for critical limitations**

---

## Hardware architecture

The schematic illustrates the integration of the central compute unit (Raspberry Pi 4B) with sensory modules and omnidirectional actuation via standard interfaces (PWM, USB, HDMI).

<img width="801" height="509" alt="Screenshot 2026-01-02 at 18 09 09" src="https://github.com/user-attachments/assets/a0e09468-960e-4df7-988b-c7d9d91d887e" />

---

## Components & wireing 

| Category | Component | Spec | Purpose | Connection |
|----------|-----------|------|---------|-----------|
| **Power** | USB Power Input | 5V USB | Charging input | IP2369 Charging Board |
| | IP2369 2S LiFePO4 Charging Board | 2S LiFePO4 management | Battery charging & protection | Battery ↔ Converter |
| | 6.4V LiFePO4 2S Battery Pack | 6.4V nominal, 2S cells | Primary power source | DC-DC Converter |
| | DC-DC Boost Converter 6V | 6V → variable regulated output | Voltage regulation | Battery → all components |
| **Computing** | Raspberry Pi 4B | 8GB RAM, ARM processor | Main control unit | Central hub for all I/O |
| **Motors** | Micro Metal Gearmotor Omniwheel | 3× units | Omni-directional movement | DRV8833 Drivers |
| | DRV8833 Motor Driver | 2× units, PWM-controlled | Motor speed/direction control | Pi GPIO → Motors |
| **Audio** | Microphone | Audio input | Capture spoken commands & ambient sound | Pi Audio In |
| | Speaker | 2× units, audio output | Play stories & emotive sounds | Pi Audio Out |
| **Vision & Display** | Camera | Front-facing, video input | Audience emotion & presence detection | Pi CSI/USB |
| | Projector | microHDMI/USB powered | Project stories & visuals | Pi Video Out |
| **Sensors** | Touch Sensor | Capacitive | Detect human hand/interaction | Pi GPIO (Sense) |
| | Ultrasound Distance Sensor | HC-SR04 | Detect proximity to walls/obstacles | Pi GPIO (Distance) |
| **Feedback** | LED Ring | RGB, addressable | Emotive lighting feedback | Pi GPIO |

A detailed electrical schematic for the current proof-of-concept ODI detailing the wiring between all electronic components and their connections to the Raspberry Pi's GPIO pins. 

<img width="798" height="477" alt="Screenshot 2026-01-02 at 18 06 52" src="https://github.com/user-attachments/assets/ce31acc1-6e1e-4517-afc4-b4fd68609f4f" />

---

## Modular design 

ODI’s sustainable design is a core part of the project. It aims to reduce environmental impact and acts as a philosophy that aligns with the goal of preserving cultural heritage and traditional storytelling mediums. ODI’s chassis is designed for longevity and easy maintenance with the interior holding standard, off-the-shelf components. These design choices ensure that ODI can serve as a long-term vessel for cultural preservation.

<img width="762" height="524" alt="Screenshot 2026-01-02 at 18 09 19" src="https://github.com/user-attachments/assets/37d10c59-63a1-40f8-ac16-037cc5a26933" />

---

For deployment details, see [DEPLOYMENT.md](DEPLOYMENT.md).

---
