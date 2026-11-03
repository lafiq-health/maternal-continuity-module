# Maternal Continuity Schemas

This directory contains the JSON Schemas used by the Lafiq Maternal Continuity Module.

The schemas define the reusable data structures for maternal-care journey events, referrals, follow-up and the overall continuity journey.

## Schema structure

```text
maternal-journey.schema.json
    |
    ├── maternal-journey-event.schema.json
    ├── referral-status.schema.json
    └── follow-up-status.schema.json
```

## maternal-journey.schema.json

Defines the overall maternal-care continuity journey.

It groups:

- journey events;
- referrals;
- follow-up records;

under a common `journey_id`.

This is the top-level schema for a complete maternal continuity record.

## maternal-journey-event.schema.json

Represents an individual care step or event within the maternal journey.

Examples include:

- antenatal care;
- investigations;
- referral or facility handoff;
- delivery preparation;
- delivery;
- postnatal follow-up;
- newborn transition.

The schema records whether a care step was planned, initiated, completed, delayed or unresolved.

## referral-status.schema.json

Represents the status and outcome of a referral.

It can record whether a referral was:

- created;
- sent;
- accepted;
- scheduled;
- completed;
- delayed;
- declined;
- cancelled;
- unresolved.

The schema records referral continuity without defining how a destination is selected or how routing decisions are made.

## follow-up-status.schema.json

Represents follow-up required after a care event, investigation, referral or unresolved care step.

It can record whether follow-up was:

- required;
- scheduled;
- in progress;
- completed;
- delayed;
- missed;
- unresolved;
- cancelled.

## Example journey

A synthetic example showing how the schemas work together is available at:

`../examples/deidentified-example-journey.json`

The example contains no real patient information.

## Design boundary

These schemas describe:

- what happened in the maternal-care journey;
- whether a planned step was completed;
- whether continuity was delayed or interrupted;
- whether follow-up or referral was completed.

They do not define Lafiq's proprietary:

- Care Journey orchestration;
- Care Navigator prioritisation;
- provider-selection logic;
- routing decisions;
- recovery workflows;
- escalation algorithms;
- Health Intelligence models;
- machine-learning or AI-assisted navigation.

The schemas are intended to remain usable independently of the wider Lafiq platform.
