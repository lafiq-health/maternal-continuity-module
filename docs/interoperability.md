# Interoperability

## Purpose

The Maternal Continuity Module is intended to remain usable across different digital-health environments.

The module defines a simple continuity layer for maternal-care events, referrals, follow-up and journey status.

It does not depend on one specific electronic medical record, provider system or software platform.

---

## Current position

The current repository uses implementation-neutral JSON schemas.

FHIR mappings have not yet been implemented.

Interoperability work will be developed as the module moves from technical specification into production and pilot testing.

---

## Interoperability goals

The module should support:

- exchange of maternal continuity events between systems;
- referral-status sharing;
- follow-up-status sharing;
- import and export of structured journey data;
- mapping to relevant healthcare standards where useful;
- reuse across different provider and public-health environments.

The aim is to make continuity data portable without requiring external systems to adopt Lafiq's internal platform architecture.

---

## Core data objects

The first version of the module uses three main data objects:

### Maternal Journey Event

Represents a care step within the maternal journey.

Examples include:

- antenatal visit;
- investigation;
- referral handoff;
- delivery preparation;
- delivery;
- postnatal follow-up;
- newborn transition.

Schema:

```text
schemas/maternal-journey-event.schema.json
```

### Referral Status

Represents the progress and outcome of a referral.

Schema:

```text
schemas/referral-status.schema.json
```

### Follow-up Status

Represents follow-up required after a care event, investigation, referral or unresolved step.

Schema:

```text
schemas/follow-up-status.schema.json
```

---

## JSON as the initial exchange format

JSON is used as the initial representation because it is:

- widely supported;
- easy to validate;
- suitable for API exchange;
- readable by both developers and machines;
- independent of a specific technology stack.

The schemas are intended to provide a stable starting point for implementation and future standards mapping.

---

## Future HL7 FHIR mapping

Relevant module fields may later be mapped to appropriate HL7 FHIR resources.

Possible areas for evaluation include:

- referral and service requests;
- appointments and scheduled care;
- observations or investigation status;
- encounters;
- care plans;
- tasks;
- patient-linked care events.

The exact mappings have not yet been finalised.

FHIR resource selection should be based on validated implementation needs rather than forcing the continuity model into a standard before the pilot requirements are understood.

---

## Mapping principle

The open module should describe:

**what happened, whether it was completed, and whether continuity was maintained.**

A standards mapping should preserve that meaning.

For example:

```text
Maternal Continuity Module
        |
        | mapping layer
        v
External clinical or health-information standard
```

The mapping layer should not require external systems to understand Lafiq's proprietary orchestration logic.

---

## Referral interoperability

Referral exchange may need to represent:

- referral identifier;
- referral type;
- status;
- destination category;
- acceptance;
- scheduled time;
- completion;
- barriers affecting completion;
- follow-up requirement.

The open schema records the continuity state.

It does not define how a referral destination is selected.

---

## Follow-up interoperability

Follow-up exchange may need to represent:

- reason for follow-up;
- status;
- scheduled time;
- completion;
- whether the original care step was resolved;
- whether further follow-up remains necessary.

External systems should be able to receive or provide this information without needing access to internal Care Navigator workflows.

---

## Journey-event interoperability

Journey events should be exchangeable using stable identifiers and standard timestamps.

A basic event may include:

```json
{
  "event_id": "EVT-001",
  "journey_id": "MJ-DEMO-001",
  "stage": "investigation",
  "care_step": "antenatal_blood_test",
  "status": "completed",
  "event_time": "2026-09-08T08:30:00Z"
}
```

Additional fields can be included where required by the relevant implementation.

---

## Identifiers

Identifiers used for interoperability should support linkage without unnecessarily exposing patient identity.

Examples include:

- `journey_id`
- `event_id`
- `referral_id`
- `follow_up_id`

Production systems may maintain their own internal identifiers and map them to the continuity module where needed.

---

## Versioning

Schemas should be versioned as the module develops.

Breaking changes should be documented clearly.

Future versions may introduce:

- additional journey stages;
- revised barrier categories;
- expanded referral states;
- additional continuity indicators;
- standards mappings.

Changes should avoid breaking existing implementations where practical.

---

## API use

The schemas may later be used through APIs.

A future implementation could support functions such as:

```text
create journey event
update care-step status
create referral
update referral status
create follow-up
update follow-up outcome
retrieve journey continuity status
```

API design is not part of the current repository scope.

Production API architecture, authentication and internal service design remain implementation-specific.

---

## Platform independence

The open module should not require:

- a specific programming language;
- a specific database;
- a specific cloud provider;
- Lafiq's internal infrastructure;
- access to proprietary Lafiq services.

Implementers should be able to use the schemas and documentation independently.

---

## Data protection

Interoperability should not result in unnecessary sharing of identifiable health information.

Implementations should apply:

- data minimisation;
- appropriate access control;
- secure transport;
- appropriate identifiers;
- de-identification or aggregation where applicable.

See:

```text
docs/privacy-and-deidentification.md
```

for the module's privacy principles.

---

## Planned development

Interoperability work will progress in stages:

1. validate the maternal continuity data model;
2. test the schemas during implementation;
3. identify the external systems most relevant to the pilot;
4. define required exchange points;
5. assess appropriate FHIR mappings;
6. document validated mappings and integration guidance.

The first priority is to ensure that the continuity model reflects real maternal-care journeys before expanding the interoperability layer.
