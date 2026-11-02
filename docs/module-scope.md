# Maternal Continuity Module — Scope

## Purpose

The Maternal Continuity Module provides a reusable way to represent and measure continuity across a maternal-care journey.

The module focuses on whether planned care steps happen, whether referrals and follow-up are completed, where delays occur, and what prevents the patient from progressing through care.

It is intended to support implementation, measurement and future interoperability without defining how a particular healthcare platform must operate internally.

---

## Initial maternal pathway

The first reference pathway covers:

**Antenatal Care → Investigations → Referral / Facility Handoff → Delivery Preparation → Delivery → Postnatal Follow-up → Newborn Transition**

Not every patient journey will require every step.

The structure should support variation while maintaining a common way to record progress and continuity.

---

## Included in this module

The open module is expected to include:

### Journey stages

Common definitions for maternal-care stages and care steps.

### Care-step status

A simple status model for recording whether a planned step is:

- `planned`
- `initiated`
- `completed`
- `delayed`
- `unresolved`

Additional statuses may be introduced where testing shows a clear need.

### Investigations

Structures for recording:

- requested investigations;
- whether they were completed;
- whether results are pending or available;
- whether an incomplete investigation is preventing the journey from progressing.

### Referrals

Structures for recording:

- referral creation;
- destination or service type;
- referral status;
- completion or non-completion;
- follow-up status.

### Continuity indicators

Definitions for measuring areas such as:

- care-step completion;
- referral completion;
- follow-up completion;
- delays between planned care steps;
- unresolved care steps;
- journey interruption.

### Barrier categories

High-level categories for recording why a planned care step was not completed.

Initial categories may include:

- cost;
- transport;
- distance;
- provider or service unavailable;
- facility capacity;
- delay;
- incomplete referral;
- patient unable to attend;
- other locally identified barrier.

These categories are expected to evolve through real-world testing.

### De-identified example data

Example records may be provided to demonstrate how the schemas work.

Examples must not contain real patient-identifying information.

### Documentation

Documentation may include:

- maternal journey flow;
- schema definitions;
- continuity indicators;
- privacy considerations;
- implementation guidance;
- interoperability guidance.

---

## Outside the scope of this module

The Maternal Continuity Module does not include the complete Lafiq platform or the internal mechanisms used to operate it.

The following remain outside this repository:

- Lafiq Care Journey orchestration logic;
- Care Navigator work allocation and prioritisation;
- internal recovery workflows for stalled journeys;
- proprietary provider-routing logic;
- escalation algorithms and internal business rules;
- provider-network intelligence;
- Care Companion commercial operations;
- pricing and revenue logic;
- cross-journey benchmarking methodology;
- broader Lafiq Health Intelligence architecture;
- proprietary analytical models;
- future machine-learning models;
- future AI-assisted navigation;
- production infrastructure;
- internal APIs and platform services not required for the reusable module.

---

## Clinical boundary

The module records care-continuity events and outcomes.

It does not:

- diagnose a patient;
- recommend treatment;
- prescribe medication;
- replace clinical judgement;
- independently manage clinical emergencies.

Clinical decisions remain with appropriately licensed healthcare professionals.

The module may record that escalation or clinical attention is required without determining the clinical decision itself.

---

## Data boundary

The repository is intended for schemas, specifications, documentation and de-identified examples.

It should not contain:

- names;
- phone numbers;
- addresses;
- government identification numbers;
- identifiable medical records;
- real patient histories;
- authentication credentials;
- production secrets or keys.

Testing examples should use synthetic or appropriately de-identified data.

---

## Interoperability

The module should remain implementation-neutral where practical.

Future versions may include mappings to relevant interoperability standards, including appropriate HL7 FHIR resources.

FHIR mappings are not currently implemented and should only be added after the relevant journey events and data requirements have been validated.

---

## Regional testing

The first planned regional test is in Enugu, Nigeria.

Testing will be used to validate:

- whether the journey structure reflects real maternal-care pathways;
- whether care-step status can be captured reliably;
- where referrals and follow-up fail;
- which barriers most often prevent care completion;
- which indicators are useful to providers and health institutions.

The core framework should remain reusable across regions, while local barrier categories and implementation details may differ.

---

## Design principle

The open module should describe **what happened in the maternal-care journey and whether continuity was achieved**.

It should not prescribe or expose the proprietary mechanisms used by Lafiq to decide **how to route, prioritise, recover or coordinate each individual case**.
