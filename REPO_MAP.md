# 🗺️ The PersonaPlex City Map

**A non-technical tour of this entire repository — explained like a city, with streets, houses, rooms, workers, and the money it was built to make.**

> 💡 **How to read this:** Every diagram below is drawn with "Mermaid," which GitHub turns into real pictures automatically. Just scroll — the maps render right on this page.

---

## 🏛️ The Big Idea (Before We Enter the City)

Imagine you could hire an employee who:

- **Never sleeps** ☕
- **Answers the phone instantly**, in a friendly human voice 📞
- Can be told *"Today you work for a pizza shop"* or *"Today you're a drone rental clerk"* — and instantly plays that role perfectly 🎭
- Can **talk and listen at the same time**, just like a real person (no awkward walkie-talkie pauses)

That employee is **PersonaPlex**. This repository is the **city where that employee lives, trains, and works**.

---

## 🌎 Level 1: The State → The City

```mermaid
graph TD
    STATE["🌎 THE STATE OF VOICE AI<br/>(The world of talking computers)"]
    CITY["🏙️ PERSONAPLEX CITY<br/>(This repository)"]
    NEIGHBOR1["🏙️ Neighbor City: Moshi<br/>(The original city this one<br/>was modeled after)"]
    NEIGHBOR2["🏙️ Neighbor City: Hugging Face<br/>(The giant warehouse city where<br/>the AI's 'brain' is stored)"]

    STATE --> CITY
    STATE --> NEIGHBOR1
    STATE --> NEIGHBOR2
    NEIGHBOR1 -.->|"blueprints"| CITY
    NEIGHBOR2 -.->|"ships the brain<br/>when the city opens"| CITY
```

**The analogy:** Voice AI is the *state* — a huge territory full of cities trying to make computers talk. **PersonaPlex City** (this repo) is one city in that state. It was built using blueprints from an older city called **Moshi**, and every morning it imports its "brain" (the trained model weights) from a giant warehouse city called **Hugging Face** — like a city that imports its power generator instead of building one from scratch.

---

## 🏙️ Level 2: The City and Its Streets

The city has **two main streets** plus a few service roads.

```mermaid
graph TD
    CITY["🏙️ PERSONAPLEX CITY<br/>(the repository)"]

    STREET1["🏭 FACTORY STREET<br/><code>moshi/</code><br/>Where the AI brain lives and works<br/>(Python — the 'industrial district')"]
    STREET2["🛍️ MAIN STREET<br/><code>client/</code><br/>The storefront customers visit<br/>(the web page you talk into)"]
    ROAD1["🚚 SHIPPING ROAD<br/><code>Dockerfile</code> + <code>docker-compose.yaml</code><br/>Pre-packed moving trucks so the whole<br/>city can be copied anywhere"]
    ROAD2["🪧 WELCOME CENTER<br/><code>README.md</code> + <code>assets/</code><br/>The visitor's guide and city photos"]

    CITY --> STREET1
    CITY --> STREET2
    CITY --> ROAD1
    CITY --> ROAD2

    STREET2 <-->|"customers' voices travel<br/>back and forth in real time"| STREET1
```

**The analogy:**
- **Factory Street (`moshi/`)** is the industrial side of town. No customers come here — this is where the heavy machinery (the AI model) actually *thinks*.
- **Main Street (`client/`)** is the pretty storefront — the web page with a microphone button where real people talk to the AI.
- **Shipping Road (Docker files)** is like a fleet of moving trucks: the entire city, furniture and all, can be boxed up and rebuilt on any computer in minutes.
- The two streets are connected by a **pneumatic tube** (a WebSocket) that whooshes voice audio back and forth about 12 times per second.

---

## 🏭 Level 3: Factory Street — The Houses

```mermaid
graph TD
    STREET1["🏭 FACTORY STREET — <code>moshi/moshi/</code>"]

    H1["🏠 THE BRAIN HOUSE<br/><code>models/</code><br/>Where thinking happens"]
    H2["🏠 THE WORKSHOP HOUSE<br/><code>modules/</code><br/>The toolboxes and machine parts<br/>the brain is built from"]
    H3["🏠 THE COMPRESSION HOUSE<br/><code>quantization/</code><br/>Squeezes sound into tiny codes<br/>(like vacuum-sealing luggage)"]
    H4["🏠 THE FRONT OFFICE<br/><code>server.py</code><br/>Answers the door when<br/>customers connect"]
    H5["🏠 THE TESTING LAB<br/><code>offline.py</code><br/>Practice conversations with<br/>recorded audio, no customers"]
    H6["🏠 THE UTILITY SHED<br/><code>utils/</code><br/>Wires, plumbing, and spare parts"]

    STREET1 --> H1
    STREET1 --> H2
    STREET1 --> H3
    STREET1 --> H4
    STREET1 --> H5
    STREET1 --> H6
```

### 🚪 Inside the Brain House (`models/`) — The Rooms

```mermaid
graph LR
    H1["🏠 THE BRAIN HOUSE"]

    R1["🚪 The Thinking Room<br/><code>lm.py</code><br/>The actual 7-billion-knob brain that<br/>decides WHAT to say next"]
    R2["🚪 The Ears-and-Mouth Room<br/><code>compression.py</code><br/>(the 'Mimi' machine) Turns your voice<br/>into brain-code, and brain-code<br/>back into a human voice"]
    R3["🚪 The Delivery Dock<br/><code>loaders.py</code><br/>Unpacks the brain when it arrives<br/>from the Hugging Face warehouse"]

    H1 --> R1
    H1 --> R2
    H1 --> R3
```

**The analogy:** Think of the Brain House like a **call-center employee's head**:
- The **Ears-and-Mouth Room** (`compression.py`, a machine called *Mimi*) is the ears and voice box. It converts messy sound waves into neat little numbered tokens — like turning a song into sheet music — and back again.
- The **Thinking Room** (`lm.py`) reads that sheet music and composes the reply *while still listening* — that's the "full duplex" magic. Most voice AIs are walkie-talkies; this one is a real phone call.
- The **Delivery Dock** (`loaders.py`) is the receiving bay where the pre-trained brain (gigabytes of learned knowledge) gets unboxed and installed each time the server starts.

### 🚪 Inside the Workshop House (`modules/`) — The Rooms

```mermaid
graph LR
    H2["🏠 THE WORKSHOP HOUSE"]

    W1["🚪 <code>transformer.py</code><br/>The engine block — the core<br/>machinery of modern AI"]
    W2["🚪 <code>seanet.py</code> & <code>conv.py</code><br/>The audio lathes — shape raw<br/>sound like wood on a lathe"]
    W3["🚪 <code>streaming.py</code><br/>The conveyor belt — keeps audio<br/>flowing piece-by-piece in real time"]
    W4["🚪 <code>rope.py</code> & <code>gating.py</code><br/>Specialty hand tools — help the brain<br/>remember WHEN things were said"]

    H2 --> W1
    H2 --> W2
    H2 --> W3
    H2 --> W4
```

---

## 🛍️ Level 4: Main Street — The Storefront

```mermaid
graph TD
    STREET2["🛍️ MAIN STREET — <code>client/src/</code>"]

    S1["🏠 THE SHOWROOM<br/><code>pages/Conversation/</code><br/>The main room where you<br/>actually talk to the AI"]
    S2["🏠 THE WAITING ROOM<br/><code>pages/Queue/</code><br/>Take a number if the<br/>store is busy"]
    S3["🏠 THE MAILROOM<br/><code>protocol/</code><br/>Packs voice data into envelopes<br/>before sending it down the tube"]
    S4["🏠 THE SOUND BOOTH<br/><code>audio-processor.ts</code> + <code>decoder/</code><br/>Microphone wiring and speakers"]

    STREET2 --> S1
    STREET2 --> S2
    STREET2 --> S3
    STREET2 --> S4

    S1R1["🚪 Microphone corner — <code>UserAudio</code>"]
    S1R2["🚪 Speaker corner — <code>ServerAudio</code>"]
    S1R3["🚪 Dancing lights — <code>AudioVisualizer</code><br/>(shows the sound waves bouncing)"]
    S1R4["🚪 Subtitle screen — <code>TextDisplay</code><br/>(shows the AI's words as text)"]
    S1R5["🚪 Control panel — <code>ModelParams</code><br/>(pick the voice & write the role)"]

    S1 --> S1R1
    S1 --> S1R2
    S1 --> S1R3
    S1 --> S1R4
    S1 --> S1R5
```

**The analogy:** Main Street is like an **Apple Store for talking to AI**. You walk into the Showroom, the Control Panel lets you choose which employee you want (a friendly female voice? a calm male voice? — 18 voices total, named things like `NATF2` and `NATM1`), you hand them a job description, and you just… start talking. The dancing lights show your voice and the AI's voice as moving waves, and subtitles scroll by so you can read along.

---

## 🤖 Level 5: The Agents — Who Works in This City?

Here's the fun part. The city employs **one shape-shifting actor** who can play any role you write on a sticky note (the "text prompt"):

```mermaid
graph TD
    ACTOR["🎭 THE SHAPE-SHIFTING EMPLOYEE<br/>(the PersonaPlex model)"]

    A1["🧑‍🏫 THE TEACHER<br/>'You are a wise and friendly teacher.'<br/>Answers questions, gives advice"]
    A2["☎️ THE CUSTOMER SERVICE REP<br/>'You work for CitySan Waste Management,<br/>your name is Ayelen…'<br/>Checks schedules, takes orders, books rentals"]
    A3["💬 THE FRIENDLY CHATTER<br/>'You enjoy having a good conversation.'<br/>Casual talk — food, family, careers"]
    A4["🧑‍🚀 THE ASTRONAUT (demo)<br/>'You are Alex, fixing a reactor<br/>on a Mars mission…'<br/>Shows it can improvise ANY role"]

    ACTOR --> A1
    ACTOR --> A2
    ACTOR --> A3
    ACTOR --> A4

    V["🗣️ 18 VOICE COSTUMES<br/>8 'Natural' voices + 10 'Variety' voices<br/>(NATF0-3, NATM0-3, VARF0-4, VARM0-4)"]
    V -.->|"any role can wear<br/>any voice"| ACTOR
```

**The analogy:** It's like one brilliant improv actor with a **closet of 18 voice costumes**. You slide a script under the door — *"You work at Jerusalem Shakshuka, a restaurant. Classic shakshuka is $9.50…"* — and seconds later that actor IS the restaurant employee, in whichever voice you picked, taking orders without missing a beat.

---

## 🧰 Level 6: The Tools — The City's Utilities

```mermaid
graph TD
    subgraph POWER["⚡ Power Plant"]
        T1["PyTorch + NVIDIA GPU<br/>The electricity that makes<br/>the brain run fast"]
    end
    subgraph WATER["🚰 Water Supply"]
        T2["Hugging Face Hub<br/>Pipes in the pre-trained<br/>brain (model weights)"]
    end
    subgraph PHONE["📞 Phone Lines"]
        T3["WebSockets + Opus codec<br/>The pneumatic tubes carrying<br/>compressed voice both ways"]
    end
    subgraph PAINT["🎨 Paint & Glass"]
        T4["React + TypeScript +<br/>Vite + Tailwind<br/>What makes the storefront<br/>pretty and snappy"]
    end
    subgraph TRUCKS["🚚 Moving Trucks"]
        T5["Docker<br/>Boxes up the whole city for<br/>delivery to any computer"]
    end

    CITY2["🏙️ PERSONAPLEX CITY"]
    POWER --> CITY2
    WATER --> CITY2
    PHONE --> CITY2
    PAINT --> CITY2
    TRUCKS --> CITY2
```

| Tool | Plain-English job |
|---|---|
| **PyTorch** | The math engine — the power plant that runs the brain's billions of calculations |
| **NVIDIA GPU** | The turbocharger — without it, the AI would think too slowly to hold a live call |
| **Hugging Face** | The warehouse that ships the already-trained brain (you don't train it yourself) |
| **Opus codec** | A sound shrink-ray — squeezes voice tiny so it travels the internet fast |
| **WebSockets** | An always-open phone line between storefront and factory (no redialing) |
| **React / Vite / Tailwind** | The interior decorators of the storefront web page |
| **Docker** | "City-in-a-box" — clone the whole operation onto any machine with one command |

---

## 💰 Level 7: The Objective — How Does This City Make Money?

This is **why the city was built**. The complete pipeline, from your voice to value:

```mermaid
flowchart TD
    C["🗣️ A customer speaks<br/>(into the storefront mic)"]
    E["👂 Ears-and-Mouth machine<br/>compresses voice into brain-code"]
    B["🧠 The Brain thinks WHILE listening<br/>(no awkward pauses — it can even<br/>handle interruptions, like a human)"]
    M["🗣️ Brain-code becomes a natural<br/>human voice reply, instantly"]
    OUT["✅ OUTCOMES"]
    O1["📞 24/7 phone agents that never<br/>sleep, quit, or take breaks"]
    O2["🍕 Order-taking: restaurants,<br/>rentals, pickups, scheduling"]
    O3["🎓 Tutors & companions that<br/>actually converse naturally"]
    REV["💰 THE REVENUE ENGINE"]
    R1["💵 SAVE money:<br/>one server replaces a<br/>roomful of call-center seats"]
    R2["💵 MAKE money:<br/>answer every call instantly =<br/>no missed orders, no hang-ups,<br/>more sales captured"]
    R3["💵 SELL it as a service:<br/>charge businesses monthly for<br/>their own custom voice employee<br/>(any role, any voice, written<br/>in one paragraph)"]

    C --> E --> B --> M --> OUT
    OUT --> O1 --> REV
    OUT --> O2 --> REV
    OUT --> O3 --> REV
    REV --> R1
    REV --> R2
    REV --> R3
```

**The analogy:** Every small business loses money two ways on the phone: paying someone to answer it, and *not* answering it (a missed call at a pizza shop is a lost $30 order). PersonaPlex City exists to fix both at once. Because the "employee" learns a new job from **a single paragraph of instructions** — no retraining, no onboarding — one copy of this city can serve a waste-management company at 9 AM, a shakshuka restaurant at noon, and a drone rental shop at 5 PM. **That's the business: rentable, instantly-retrainable voice employees.**

> ⚖️ **Honest fine print:** The code in this repo is free to use (MIT license), but the brain itself (the model weights from NVIDIA) ships under the *NVIDIA Open Model License* — so check that license before charging customers. This repo is the engine; the business plan is what you bolt onto it.

---

## 🧭 The Whole City on One Page

```mermaid
graph TD
    STATE["🌎 STATE: Voice AI"]
    CITY["🏙️ CITY: personaplex repo"]

    ST1["🏭 Street: moshi/ (factory)"]
    ST2["🛍️ Street: client/ (storefront)"]
    ST3["🚚 Road: Docker (shipping)"]

    HB["🏠 Brain House (models/)"]
    HW["🏠 Workshop (modules/)"]
    HC["🏠 Compression House (quantization/)"]
    HF["🏠 Front Office (server.py)"]
    HL["🏠 Testing Lab (offline.py)"]

    SS["🏠 Showroom (Conversation/)"]
    SQ["🏠 Waiting Room (Queue/)"]
    SM["🏠 Mailroom (protocol/)"]

    RT["🚪 Thinking Room (lm.py)"]
    RE["🚪 Ears & Mouth (compression.py)"]
    RD["🚪 Delivery Dock (loaders.py)"]

    AG["🎭 Agents: Teacher · Service Rep ·<br/>Chatter · Astronaut — in 18 voices"]
    TO["🧰 Tools: PyTorch · GPU · Hugging Face ·<br/>Opus · WebSockets · React · Docker"]
    MONEY["💰 OBJECTIVE: rentable 24/7 voice<br/>employees → saved labor + captured<br/>sales + sellable service"]

    STATE --> CITY
    CITY --> ST1
    CITY --> ST2
    CITY --> ST3
    ST1 --> HB
    ST1 --> HW
    ST1 --> HC
    ST1 --> HF
    ST1 --> HL
    ST2 --> SS
    ST2 --> SQ
    ST2 --> SM
    HB --> RT
    HB --> RE
    HB --> RD
    HF --> AG
    TO -.-> CITY
    AG --> MONEY
```

---

*Map drawn from the actual contents of this repository: the `moshi/` Python package (server, offline runner, models, modules, quantization, utils), the `client/` React app (Conversation, Queue, protocol, audio workers), the Docker packaging, and the README's voices, roles, and prompting guide.*
