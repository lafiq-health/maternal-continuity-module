
# Lafiq Maternal Continuity Module

A reusable framework for representing and measuring continuity across maternal-care journeys.

The module is being developed within the Lafiq healthcare-continuity platform and is intended to support maternal-care pathways from antenatal care through investigations, referrals, delivery, postnatal follow-up and newborn transition.

It is designed to help health teams understand whether planned care steps were completed, where care was delayed or interrupted, and what barriers prevented the journey from progressing.

---

## Status

**Stage:** Prototype and technical specification 

**First planned regional test:** Enugu, Nigeria  

**Patient data:** No identifiable patient data is stored in this repository

The current work builds on Lafiq's existing Care Journey architecture and interactive prototype. The module will be refined during production development and real-world testing.

---

## What this module covers

The Maternal Continuity Module will provide reusable definitions and schemas for:

- maternal-care journey stages;
- planned and completed care steps;
- tests and investigations;
- referrals and facility handoffs;
- follow-up status;
- delayed and unresolved care;
- reasons care was not completed;
- continuity indicators;
- de-identified journey evidence;
- interoperability guidance.

The module focuses on continuity and coordination. It does not provide diagnosis, treatment or prescribing.

Clinical decisions remain with licensed healthcare professionals.

---

## Reference maternal journey

The initial reference pathway is:

**Antenatal Care → Investigations → Referral / Facility Handoff → Delivery Preparation → Delivery → Postnatal Follow-up → Newborn Transition**

A care step may be recorded as:

```text
planned
initiated
completed
delayed
unresolved
```

This makes it possible to follow whether care actually progresses from one stage to the next.

---

## What we want to measure

The module is designed to support questions such as:

- Was the planned care step completed?
- Was the required test completed?
- Was the referral completed?
- Was follow-up completed?
- Was the required service available?
- Was care delayed?
- Why was a step not completed?
- Where did the care journey break?

Initial barrier categories may include:

- cost;
- transport;
- distance;
- unavailable providers or services;
- facility capacity;
- delays;
- incomplete referrals;
- other locally identified barriers.

These will be refined during regional testing.

---

## Open-source scope

This repository is intended to contain the reusable maternal-continuity layer, including:

- maternal journey data schemas;
- care-step status definitions;
- referral and follow-up event models;
- continuity indicators;
- delay and barrier categories;
- de-identified example journey records;
- implementation documentation;
- interoperability guidance;
- non-proprietary journey-flow documentation.

The aim is to make this component useful independently of the wider Lafiq platform.

---

## What remains part of the Lafiq platform

This repository does not contain the full Lafiq product.

The following remain outside the open-source module:

- Care Journey orchestration logic;
- Care Navigator prioritisation and recovery workflows;
- provider-routing and escalation logic;
- provider-network intelligence;
- Care Companion commercial and operational workflows;
- cross-journey benchmarking;
- broader Health Intelligence models and methodology;
- future machine-learning and AI-assisted navigation;
- production infrastructure and internal platform services.

---

## Interoperability

The module is being designed with future interoperability in mind.

Maternal journey events may later be mapped to relevant healthcare standards, including appropriate HL7 FHIR resources.

FHIR mapping has not yet been implemented and will be evaluated during production development.

---

## Privacy

This repository will not contain identifiable patient records.

The module is intended to work with structured, de-identified journey information.

Production use will require appropriate safeguards for:

- consent;
- access control;
- auditability;
- data minimisation;
- secure handling of health information;
- de-identification and aggregation where required.

---

## Repository structure

```text
docs/
  module-scope.md
  maternal-journey-flow.md
  continuity-indicators.md
  privacy-and-deidentification.md
  interoperability.md

schemas/
  README.md
  maternal-journey.schema.json
  maternal-journey-event.schema.json
  referral-status.schema.json
  follow-up-status.schema.json

examples/
  deidentified-example-journey.json

LICENSE-PROPOSED.md
README.md

---

## Open-source commitment

Lafiq intends to release the Maternal Continuity Module as an independently reusable open-source component.

The final licence will be selected before public release after reviewing the module's technical scope and intellectual-property boundaries.

No open-source licence has yet been granted for material in this repository unless explicitly stated in a future licence file.

---

## About Lafiq

Lafiq is a healthcare-continuity platform built around the patient's complete Care Journey rather than isolated healthcare encounters.

The platform is designed to help patients move through fragmented care while generating structured evidence about where and why care becomes delayed or incomplete.

The first planned maternal-health regional test will take place in Enugu, Nigeria.


# Maternal Continuity Schemas

This directory contains the machine-readable JSON Schemas used by the Lafiq Maternal Continuity Module.

## Schema structure

```text
maternal-journey.schema.json
    |
    ├── maternal-journey-event.schema.json
    ├── referral-status.schema.json
    └── follow-up-status.schema.json
