# AssetTrace Node

**AssetTrace Node** is a local maintenance intelligence node designed for machine park management, fault memory, technical event tracking and lightweight pattern analysis.

It is a practical development mode of a broader mother architecture, focused on technical memory, maintenance-oriented decision support and progressive system evolution.

AssetTrace Node is not an autonomous agent.
It does not take final decisions, does not act directly on the physical world and does not replace human responsibility.

---

## Purpose

AssetTrace Node was created to support the management of technical assets such as:

* 3D printers;
* Raspberry Pi nodes;
* local servers;
* PCs;
* sensors;
* automation devices;
* maintenance-critical machines;
* technical infrastructure components.

The system stores machines, faults, events, observations and recurring patterns in order to help the user understand the state of a machine park over time.

Its goal is not to automate decisions blindly, but to provide a structured decision-support layer for technical maintenance.

---

## Core Concepts

AssetTrace Node is based on a modular architecture composed of:

* **Machine Park Management**
  Registration and tracking of machines, status, criticality, location, technical notes and events.

* **Fault Memory**
  Structured storage of faults, symptoms, hypotheses, tests, risks and minimal reversible actions.

* **Technical Events**
  Manual logging of maintenance events, status changes, inspections, faults and observations.

* **Web Observations**
  Governed web search used as an external perception layer. Web results are treated as signals, not as automatic truth.

* **Pattern Analysis**
  Lightweight detection of recurring faults, fragile machines, repeated terms and maintenance signals.

* **Health Index**
  Synthetic indicator from 0 to 100 used to estimate the current fragility of each machine.

* **Local AI Reasoning**
  Integration with Ollama for local language-model reasoning.

---

## Project Structure

```text
AssetTrace_Node/
│
├── app.py
├── config.py
│
├── core/
│   ├── governance.py
│   ├── ollama_client.py
│   └── prompt_builder.py
│
├── tools/
│   ├── docs_loader.py
│   └── web_search.py
│
├── memory/
│   ├── store.py
│   ├── guasti.py
│   ├── parco_macchine.py
│   └── patterns.py
│
├── docs/
│   ├── Parte 1.md
│   ├── Parte 2.md
│   ├── Parte 3.md
│   ├── Parte 4.md
│   ├── Parte 5.md
│   └── Parte 6.md
│
├── guasti/
├── dati/
├── ricerche_web/
├── README.md
└── .gitignore
```

---

## Main Features

### Machine Park

AssetTrace Node allows the user to register and manage machines with:

* machine ID;
* name;
* category;
* status;
* location;
* criticality;
* IP address or local URL;
* notes;
* technical history.

Example command:

```text
/macchine
```

---

### Machine Status

Each machine can have a status such as:

```text
operativa
manutenzione
guasto
ferma
osservazione
dismessa
```

Example:

```text
/stato MAC-001 manutenzione
```

---

### Machine Events

Events can be attached to a machine to build its technical history.

Example:

```text
/eventomacchina MAC-001
```

Events may include:

* maintenance;
* inspection;
* fault;
* status change;
* observation;
* technical note.

---

### Fault Memory

Faults can be stored as structured markdown documents.

Each fault may include:

* category;
* title;
* involved system;
* connected machine;
* observed signals;
* hypotheses;
* active doubts;
* minimal reversible tests;
* risks;
* next action.

Example:

```text
/addguasto
```

---

### Pattern Analysis

AssetTrace Node can analyze stored events and faults to detect recurring maintenance patterns.

Example:

```text
/patterns
```

For a specific machine:

```text
/patterns MAC-001
```

The pattern module can identify:

* fragile machines;
* recurring event types;
* recurring technical terms;
* linked fault files;
* maintenance signals;
* suggested next minimal action.

---

### Health Index

AssetTrace Node computes a lightweight health index for each machine.

Example:

```text
/health
```

The health index is not a diagnosis.
It is a maintenance signal used to support prioritization.

---

### Web Search

AssetTrace Node includes a governed web search module.

Example:

```text
/web OctoPrint non si avvia automaticamente Raspberry Pi
```

Web results are treated as external observations, not as automatic truth.

The system should always distinguish:

* internal memory;
* external sources;
* uncertainty;
* risk;
* actions requiring human confirmation.

---

### Ollama Integration

AssetTrace Node uses Ollama as a local language-model engine.

Check Ollama status:

```text
/ollama
```

Recommended model:

```text
llama3.2:3b
```

Install or run it with:

```powershell
ollama pull llama3.2:3b
ollama run llama3.2:3b
```

---

## Installation

### Requirements

* Python 3.10+
* Ollama installed locally
* A compatible local model, for example `llama3.2:3b`

---

### Start Ollama

Open PowerShell and run:

```powershell
ollama serve
```

In another PowerShell window, check installed models:

```powershell
ollama list
```

If needed:

```powershell
ollama pull llama3.2:3b
```

---

### Start AssetTrace Node

Move into the project folder:

```powershell
cd AssetTrace_Node
```

Run:

```powershell
py .\app.py
```

Or:

```powershell
python .\app.py
```

---

## Available Commands

```text
/docs
  Show loaded foundational documents.

/mem
  Show recent memory.

/macchine
  Show registered machines.

/macchina MAC-001
  Show details and events of a specific machine.

/stato MAC-001 manutenzione
  Update the status of a machine.

/eventomacchina MAC-001
  Add an event to a machine.

/addmacchina
  Add a new machine.

/addguasto
  Add a new fault.

/health
  Show machine health index.

/patterns
  Show global pattern analysis.

/patterns MAC-001
  Show pattern analysis for a specific machine.

/web <query>
  Run governed web search.

/ollama
  Check Ollama connection and model availability.

/help
  Show help.

/exit
  Close AssetTrace Node.
```

---

## Data and Privacy

AssetTrace Node is designed to run locally.

Runtime data may include:

* machine records;
* local events;
* fault history;
* web observations;
* local memory;
* SQLite database files.

Before publishing the project publicly, avoid uploading local runtime data such as:

```text
dati/
*.db
memory.jsonl
ricerche_web/
logs/
```

A `.gitignore` file is included to help prevent accidental upload of local data.

---

## Suggested Repository Name

```text
assettrace-node
```

---

## Short Description

```text
Local maintenance intelligence node for machine park management, fault memory and lightweight pattern analysis.
```

---

## Project Status

AssetTrace Node is an experimental local system.

Current focus:

* local machine park management;
* structured fault storage;
* event tracking;
* governed web observations;
* lightweight pattern analysis;
* health index generation;
* support for maintenance-oriented reasoning.

Future developments may include:

* web dashboard;
* advanced database interface;
* semantic memory;
* vector search over faults and events;
* automated report generation;
* integration with OctoPrint or other machine APIs;
* predictive maintenance indicators.
