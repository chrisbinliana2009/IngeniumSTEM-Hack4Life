# IngeniumSTEM-Hack4Life
Eco-Alert Torch is a STEM-powered, eco-friendly safety torch designed for forest-fringe communities. It uses high-intensity light patterns and safe alert sounds to prevent dangerous encounters at night—without harming wildlife. Portable, rechargeable, and built to improve safety sustainably.
Eco-Alert Torch: STEM-Based Wildlife Safety Solution
Team Members

Chrisbin Liana

Chrisbin Jaedon

Johan Danieo R

Affiliation

11th, 8th, 7th Standard — Sacred Heart International School, Tamil Nadu, India

📌 Inspiration

Families living near forest borders often face unexpected wildlife encounters, especially at night. Traditional safety methods—like fire, shouting, and crackers—are unsafe, polluting, and can cause forest fires.

We wanted a safe, eco-friendly, STEM-powered solution that protects people without harming wildlife. This inspired the creation of the Eco-Alert Torch, a clean-tech safety tool meant for rural and forest-fringe communities.

🔦 What It Does

The Eco-Alert Torch is a portable night-time safety device that uses:

High-intensity red strobe lights

Artificial flame LED visuals

Safe alert sound patterns

Rechargeable battery system

(Optional) IoT motion detection and basic alerting

It helps users deter approaching wildlife safely, improving visibility and night-time security while ensuring no animal is harmed.

🛠️ How We Built It

Research on wildlife behavior and safe deterrent techniques

Electronic design using high-power LEDs, speaker modules, and microcontrollers

Programming light/sound patterns using Arduino/ESP32

Prototype assembly with rechargeable battery and handheld casing

STEM Extension:

Motion sensors

IoT alerts using ESP32 Wi-Fi

Dashboard for viewing detection events

The device is designed to be safe, sustainable, and easy for anyone to use.

🚧 Challenges We Ran Into

Balancing brightness to be effective but not harmful

Designing a torch that works in rain, fog, and outdoor conditions

Battery consumption management

Making it lightweight, durable, and user-friendly

Ensuring animal-safe sound and light levels

Integrating IoT connectivity reliably in low-signal areas

🏆 Accomplishments That We’re Proud Of

A zero-pollution alternative to harmful fire/crackers

Built entirely by school students using STEM skills

Wildlife-friendly and environmentally safe

Portable, affordable, and replicable for rural communities

Optional IoT alerts for modernizing wildlife safety

A working prototype that can help real communities

📚 What We Learned

How STEM can solve everyday rural safety problems

Designing user-centered, eco-friendly hardware

Coding microcontroller logic for LEDs and audio

Basics of IoT, sensors, and alert systems

Importance of teamwork, testing, and iteration

Using innovation to protect both humans and wildlife

🚀 What’s Next for Eco-Alert Torch

Adding solar charging for off-grid use

Improving weatherproof enclosure

Integrating AI-based animal detection

Community-level alert network

Long-term field testing with forest-fringe villages

Creating a STEM student kit so schools can build it easily
## 🧭 Safety, Ethics, and Wildlife Protection

To ensure complete safety, the **Eco-Alert Torch** system is designed around strict animal-welfare and ethical guidelines:

- Uses only **non-harmful deterrence** — no real fire, no explosives, no traps, and no electric fencing.  
- Light and sound patterns are designed to stay within **wildlife-safe limits**, preventing pain or long-term stress.  
- Planned AI features focus on **reducing false alarms**, helping distinguish normal animal movement from human activity.  
- **Community consent and privacy** are respected through anonymised data and secure storage of any images or alerts.  
- Deployment at scale will be guided by **wildlife experts and forest officials** to ensure responsible, legal, and ethical implementation.

### ✔ Ethical and Safe by Design

This approach is:

- ✔ **Non-harmful and ethically responsible**  
- ✔ **Scientifically aligned** with natural animal behaviour  
- ✔ **Far safer** than crackers, open flames, or electric fencing  
- ✔ **Future-ready**, with full automation possible using AI + IoT  

Today, there is still **no dedicated, humane safety device** designed specifically for people working inside forests, forest-fringe communities, or for tracking people during wildlife-related emergencies.

The **Eco-Alert Torch** aims to fill this long-standing gap in safety technology — delivering a practical, STEM-powered solution that protects **both humans and wildlife**.
UN Sustainable Development Goals (SDG) Alignment
Our project aligns strongly with 6 major SDGs, and partially with several others.
Here is a clear, judge-friendly SDG mapping:

SDG 3 — Good Health & Well-Being
How your project aligns:
•	Protects people in forest-fringe areas from dangerous wildlife encounters.
•	Reduces night-time fear, stress, and accidents.
•	Eliminates unsafe traditional methods like fire, crackers, or makeshift traps.
•	Provides a safe, non-harmful way to increase community safety.
✔ Promotes mental and physical safety
✔ Reduces injuries and harmful practices
 SDG 11 — Sustainable Cities & Communities
How your project aligns:
•	Supports rural and forest-edge communities with smart safety technology.
•	Strengthens community resilience during wildlife emergencies.
•	Encourages safer coexistence between humans and nature.
✔ Builds safer, more resilient villages
✔ Enhances local disaster risk reduction
 SDG 13 — Climate Action
How your project aligns:
•	Replaces fire-based deterrence methods—reducing smoke, forest fire risk, and carbon emissions.
•	Uses rechargeable batteries, low power consumption, and can integrate solar charging.
•	Reduces need for crackers that cause heavy CO₂ release.
✔ Prevents forest fires
✔ Environmentally low-impact safety tool
 SDG 14 — Life Below Water (Indirect)
While not directly related, reducing forest fires and pollution prevents ash and toxins from reaching water bodies and aquatic ecosystems.
✔ Supports healthier ecosystems indirectly

 SDG 15 — Life on Land (Strongest Match)
How your project aligns:
•	Protects wildlife by using 100% non-harmful deterrence methods.
•	Reduces animal stress, injury, and retaliation from humans.
•	Helps avoid conflict behaviors that can harm elephants, deer, wild boars, and community animals.
•	Introduces AI-based detection to prevent unnecessary disturbance.
✔ Prevents harm to wildlife
✔ Supports biodiversity
✔ Enables peaceful coexistence
 SDG 9 — Industry, Innovation & Infrastructure
How your project aligns:
•	Built using STEM principles (electronics, sensors, logic, mechanical design).
•	Uses innovation (LED flame simulation + blower + safe sound patterns).
•	Offers a replicable, scalable model for community-level safety tech.
✔ Promotes student-led innovation
✔ Demonstrates affordable engineering solutions
 Additional SDG Connections
SDG 1 — No Poverty (Indirect)
•	Prevents crop damage and financial loss caused by wildlife.
•	Protects livestock and avoids economic loss for low-income families.
SDG 4 — Quality Education
•	Created by school students using STEM learning.
•	Can be turned into a STEM learning kit for other students.
SDG 7 — Affordable & Clean Energy
•	Uses rechargeable battery and can integrate solar charging.



Try it out Video https://youtu.be/yz2kcooeCaM
Demo Video https://youtu.be/ReLTamfFB6Q

// Eco-Alert Torch v0.1 (ESP32)
// Features: red strobe, artificial flame, safe alert tones, simple motion trigger
// Hardware: ESP32, WS2812/Neopixel strip (flame), high-power red LED via MOSFET, piezo/buzzer, PIR sensor

#include <Arduino.h>
#include <Adafruit_NeoPixel.h>

// ---------------- Hardware pins ----------------
#define PIN_FLAME        5    // Neopixel data pin
#define NUM_PIXELS       24   // adjust to your strip
#define PIN_STROBE_LED   18   // MOSFET gate driving high-power red LED
#define PIN_BUZZER       19   // piezo/buzzer
#define PIN_PIR          23   // motion sensor

// ---------------- Safety/limits ----------------
// Keep duty cycles conservative to avoid wildlife stress.
#define STROBE_ON_MS     60
#define STROBE_OFF_MS    140
#define STROBE_BURST_CT  5    // short bursts only

#define ALERT_TONE_FREQ1 1200 // Hz
#define ALERT_TONE_FREQ2 900
#define ALERT_TONE_MS    120
#define ALERT_PAUSE_MS   180
#define ALERT_REPEAT     6

// ---------------- Flame effect ----------------
Adafruit_NeoPixel strip(NUM_PIXELS, PIN_FLAME, NEO_GRB + NEO_KHZ800);

// Simple noise for flame flicker
uint8_t rand8() { return (uint8_t)random(0, 255); }

void flameFrame(uint8_t baseRed = 255, uint8_t baseGreen = 60, uint8_t baseBlue = 0) {
  // Per-pixel warm flicker with subtle variability
  for (int i = 0; i < NUM_PIXELS; i++) {
    int heat = 180 + (rand8() % 60);          // 180–239
    int flicker = (rand8() % 50) - 25;        // -25..24
    int r = constrain(baseRed   + flicker, 120, 255);
    int g = constrain(baseGreen + flicker/2,  20, 140);
    int b = constrain(baseBlue  + flicker/3,   0,  60);

    // “breathing” brightness along the strip
    int brightness = constrain(heat, 160, 255);
    strip.setPixelColor(i, strip.Color((r * brightness) / 255,
                                       (g * brightness) / 255,
                                       (b * brightness) / 255));
  }
  strip.show();
}

// ---------------- Alert tones ----------------
void playTone(uint16_t freq, uint16_t durMs) {
  // ESP32: use LEDC for tone generation on PIN_BUZZER
  ledcAttachPin(PIN_BUZZER, 0);
  ledcSetup(0, freq, 10); // channel 0, frequency, 10-bit resolution
  ledcWrite(0, 512);      // ~50% duty
  delay(durMs);
  ledcWrite(0, 0);
}

void safeAlertPattern() {
  for (int i = 0; i < ALERT_REPEAT; i++) {
    playTone(ALERT_TONE_FREQ1, ALERT_TONE_MS);
    delay(ALERT_PAUSE_MS);
    playTone(ALERT_TONE_FREQ2, ALERT_TONE_MS);
    delay(ALERT_PAUSE_MS);
  }
}

// ---------------- Red strobe ----------------
void redStrobeBurst() {
  for (int i = 0; i < STROBE_BURST_CT; i++) {
    digitalWrite(PIN_STROBE_LED, HIGH);
    delay(STROBE_ON_MS);
    digitalWrite(PIN_STROBE_LED, LOW);
    delay(STROBE_OFF_MS);
  }
}

// ---------------- Setup ----------------
void setup() {
  randomSeed(esp_random());
  pinMode(PIN_STROBE_LED, OUTPUT);
  pinMode(PIN_PIR, INPUT);
  strip.begin();
  strip.setBrightness(200); // keep below max to reduce glare/stress
  strip.show();

  // Initial warm-up flame
  for (int i = 0; i < 60; i++) {
    flameFrame();
    delay(50);
  }
}

// ---------------- Loop ----------------
unsigned long lastFlameUpdate = 0;
const uint16_t flameIntervalMs = 40;

void loop() {
  // Continuous flame effect
  unsigned long now = millis();
  if (now - lastFlameUpdate >= flameIntervalMs) {
    flameFrame();
    lastFlameUpdate = now;
  }

  // Motion-triggered deterrence
  static bool active = false;
  int motion = digitalRead(PIN_PIR);

  if (motion && !active) {
    active = true;
    // Sequence: short strobe -> safe alert tones -> resume flame
    redStrobeBurst();
    safeAlertPattern();
  }

  // Cool-down period to avoid over-stimulation
  if (active) {
    delay(1500);
    active = false;
  }
}
<?xml version="1.0" encoding="UTF-8" standalone="no"?>
<svg width="1200" height="900" viewBox="0 0 1200 900" xmlns="http://www.w3.org/2000/svg">
  <style>
    .box { fill:#f9f9f9; stroke:#333; stroke-width:2; }
    .label { font-family:Arial, sans-serif; font-size:18px; fill:#111; }
    .small { font-size:14px; fill:#333; }
    .power { stroke:#d33; stroke-width:3; fill:none; marker-end:url(#arrow); }
    .signal { stroke:#337; stroke-width:2; fill:none; marker-end:url(#arrow); stroke-dasharray:6 4; }
    .ground { stroke:#555; stroke-width:2; fill:none; marker-end:url(#arrow); stroke-dasharray:3 3; }
    .note { font-size:12px; fill:#555; }
  </style>
  <defs>
    <marker id="arrow" markerWidth="10" markerHeight="10" refX="7" refY="3" orient="auto">
      <path d="M0,0 L8,3 L0,6 Z" fill="#333"/>
    </marker>
  </defs>

  <!-- Title -->
  <text x="600" y="40" text-anchor="middle" class="label" font-weight="bold">
    Eco-Alert Torch / Ingenium STEM Hack4Life – System Schematic (12 V + 5 V)
  </text>
  <text x="600" y="65" text-anchor="middle" class="small">
    AC adapter + 12 V battery input, regulators, LED/laser drivers, blower, speaker amp, USB control
  </text>

  <!-- Reflector section -->
  <rect x="800" y="120" width="320" height="280" class="box"/>
  <text x="960" y="145" text-anchor="middle" class="label" font-weight="bold">Reflector assembly</text>
  <text x="960" y="170" text-anchor="middle" class="small">Silk cloth diffuser above reflector</text>

  <!-- Laser module -->
  <rect x="820" y="190" width="130" height="60" class="box"/>
  <text x="885" y="220" text-anchor="middle" class="small">Laser module</text>

  <!-- LED module -->
  <rect x="970" y="190" width="130" height="60" class="box"/>
  <text x="1035" y="220" text-anchor="middle" class="small">High-power LED</text>

  <!-- Blower -->
  <rect x="895" y="270" width="130" height="60" class="box"/>
  <text x="960" y="300" text-anchor="middle" class="small">Blower / fan</text>

  <!-- Power area -->
  <rect x="60" y="120" width="360" height="260" class="box"/>
  <text x="240" y="145" text-anchor="middle" class="label" font-weight="bold">Power inputs</text>

  <!-- AC Adapter -->
  <rect x="80" y="180" width="150" height="60" class="box"/>
  <text x="155" y="210" text-anchor="middle" class="small">AC adapter 12 V DC</text>

  <!-- 12V Battery -->
  <rect x="250" y="180" width="150" height="60" class="box"/>
  <text x="325" y="210" text-anchor="middle" class="small">12 V battery</text>

  <!-- OR selector note -->
  <text x="240" y="260" text-anchor="middle" class="note">Use DC jack + battery OR’ing (ideal diode)</text>

  <!-- Protection & distribution -->
  <rect x="60" y="420" width="360" height="160" class="box"/>
  <text x="240" y="445" text-anchor="middle" class="label" font-weight="bold">Protection & regulation</text>

  <!-- Fuse -->
  <rect x="80" y="480" width="90" height="40" class="box"/>
  <text x="125" y="505" text-anchor="middle" class="small">Fuse</text>

  <!-- Reverse protection -->
  <rect x="180" y="480" width="90" height="40" class="box"/>
  <text x="225" y="505" text-anchor="middle" class="small">Ideal diode</text>

  <!-- 12V rail -->
  <rect x="280" y="460" width="120" height="40" class="box"/>
  <text x="340" y="485" text-anchor="middle" class="small">12 V rail</text>

  <!-- 5V buck regulator -->
  <rect x="280" y="510" width="120" height="40" class="box"/>
  <text x="340" y="535" text-anchor="middle" class="small">5 V buck</text>

  <!-- Control section -->
  <rect x="460" y="120" width="320" height="320" class="box"/>
  <text x="620" y="145" text-anchor="middle" class="label" font-weight="bold">USB device & control</text>

  <!-- USB/microcontroller -->
  <rect x="480" y="180" width="150" height="60" class="box"/>
  <text x="555" y="210" text-anchor="middle" class="small">USB device (ESP32/MCU)</text>

  <!-- PIR sensor -->
  <rect x="630" y="180" width="130" height="60" class="box"/>
  <text x="695" y="210" text-anchor="middle" class="small">PIR / radar sensor</text>

  <!-- Audio amp -->
  <rect x="480" y="260" width="150" height="60" class="box"/>
  <text x="555" y="290" text-anchor="middle" class="small">Audio amplifier</text>

  <!-- MOSFET drivers -->
  <rect x="630" y="260" width="130" height="60" class="box"/>
  <text x="695" y="290" text-anchor="middle" class="small">MOSFET drivers (LED / laser)</text>

  <!-- Speaker -->
  <rect x="480" y="340" width="150" height="60" class="box"/>
  <text x="555" y="370" text-anchor="middle" class="small">Speaker</text>

  <!-- Notes block -->
  <rect x="60" y="620" width="1060" height="200" class="box"/>
  <text x="80" y="650" class="small">Notes:</text>
  <text x="80" y="675" class="note">• Power input: combine AC adapter and 12 V battery via ideal-diode OR (e.g., LTC4412 or dual Schottky) with a fuse.</text>
  <text x="80" y="695" class="note">• 12 V rail feeds blower and high-power LED driver if needed; 5 V buck feeds MCU/USB, sensors, and low-power modules.</text>
  <text x="80" y="715" class="note">• Use logic-level N-MOSFETs (e.g., IRLZ44N) for LED/laser switching with gate resistors and flyback diode if inductive loads are present.</text>
  <text x="80" y="735" class="note">• Audio path: MCU PWM or DAC -> low-power audio amp (e.g., PAM8403) -> speaker. Include series RC for click suppression.</text>
  <text x="80" y="755" class="note">• Ground: star-grounds at power entry; separate high-current LED/blower returns from sensitive USB/MCU ground where possible.</text>
  <text x="80" y="775" class="note">• Safety: keep laser low-power, add current limiting; never point at eyes. Use fusing and proper wire gauge.</text>

  <!-- Connections -->

  <!-- AC adapter to protection -->
  <line x1="230" y1="210" x2="230" y2="460" class="power"/>
  <text x="235" y="340" class="note">12 V</text>

  <!-- Battery to protection -->
  <line x1="325" y1="240" x2="325" y2="460" class="power"/>

  <!-- Protection path -->
  <line x1="170" y1="500" x2="180" y2="500" class="power"/>
  <line x1="270" y1="500" x2="280" y2="480" class="power"/>
  <line x1="280" y1="530" x2="400" y2="530" class="power"/>
  <text x="405" y="535" class="note">5 V</text>

  <!-- 12 V rail distribution -->
  <line x1="400" y1="480" x2="840" y2="480" class="power"/>
  <text x="845" y="485" class="note">12 V rail to blower & LED driver</text>

  <!-- 5 V rail to control -->
  <line x1="400" y1="530" x2="540" y2="530" class="power"/>
  <line x1="540" y1="530" x2="540" y2="240" class="power"/>
  <text x="545" y="245" class="note">5 V to MCU/USB</text>

  <!-- MCU signals -->
  <line x1="555" y1="240" x2="690" y2="240" class="signal"/>
  <text x="622" y="230" class="note">GPIO to MOSFET drivers</text>

  <line x1="555" y1="240" x2="555" y2="320" class="signal"/>
  <line x1="555" y1="320" x2="555" y2="340" class="signal"/>
  <text x="560" y="330" class="note">Audio out to amp</text>

  <line x1="695" y1="240" x2="885" y2="220" class="signal"/>
  <text x="790" y="212" class="note">Laser control</text>

  <line x1="695" y1="240" x2="1035" y2="220" class="signal"/>
  <text x="900" y="235" class="note">LED control</text>

  <!-- Blower 12 V -->
  <line x1="960" y1="330" x2="960" y2="480" class="power"/>
  <text x="965" y="410" class="note">12 V</text>

  <!-- Ground bus -->
  <line x1="60" y1="590" x2="1120" y2="590" class="ground"/>
  <text x="1080" y="585" class="note">GND</text>

  <!-- Ground drops -->
  <line x1="155" y1="240" x2="155" y2="590" class="ground"/>
  <line x1="325" y1="240" x2="325" y2="590" class="ground"/>
  <line x1="540" y1="320" x2="540" y2="590" class="ground"/>
  <line x1="960" y1="330" x2="960" y2="590" class="ground"/>

  <!-- Labels: silk cloth -->
  <text x="960" y="105" text-anchor="middle" class="small">Silk cloth (diffuser above reflector)</text>
</svg>
