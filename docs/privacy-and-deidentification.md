# Privacy and De-identification

## Purpose

The Maternal Continuity Module is designed to support continuity measurement without requiring identifiable patient information to be stored in this repository.

The repository contains schemas, documentation and synthetic examples only.

It must not contain real patient records.

---

## Data principles

Implementations of the module should follow four basic principles:

1. collect only the information required to support continuity measurement;
2. separate patient identity from journey-event data where practical;
3. restrict access to sensitive health information;
4. use de-identified or aggregated data for analysis and reporting whenever possible.

---

## Data allowed in this repository

This repository may contain:

- schema definitions;
- technical documentation;
- synthetic journey examples;
- de-identified example records;
- indicator definitions;
- barrier categories;
- interoperability guidance.

Synthetic examples should be clearly marked as demonstration data.

---

## Data that must not be stored here

Do not commit:

- patient names;
- phone numbers;
- email addresses;
- home addresses;
- national identification numbers;
- insurance identifiers;
- medical-record numbers;
- photographs of patients;
- identifiable clinical notes;
- identifiable laboratory reports;
- identifiable prescriptions;
- authentication credentials;
- API keys;
- access tokens;
- production database exports.

---

## Journey identifiers

The module uses identifiers such as:

```text
journey_id
event_id
referral_id
follow_up_id
```

These identifiers should not directly reveal patient identity.

For public examples and open datasets, identifiers should be synthetic or appropriately transformed so they cannot reasonably be used to identify an individual.

---

## Pseudonymous identifiers

A production implementation may need to associate continuity events with a patient.

Where this is required, the open journey records should use a pseudonymous identifier rather than directly storing identity information in every event.

For example:

```text
Patient identity system
        |
        | controlled internal linkage
        v
Pseudonymous journey identifier
        |
        v
Continuity events
```

The mechanism used to generate and manage production identifiers is implementation-specific and is outside the scope of this repository.

---

## Data minimisation

Implementations should collect only the minimum information required for the intended continuity purpose.

For example, a continuity event may need to record:

- that an investigation was requested;
- whether it was completed;
- whether it was delayed;
- the high-level barrier affecting completion.

It may not need to contain the full clinical report or detailed consultation record.

---

## Barrier data

Barrier information should normally be recorded using structured categories such as:

- cost;
- transport;
- distance;
- service unavailable;
- provider unavailable;
- facility capacity;
- scheduling delay;
- incomplete referral;
- unable to attend;
- communication failure;
- other.

Free-text fields should be used cautiously because they can unintentionally contain identifying or sensitive information.

---

## Location data

The module may support broad implementation geography such as:

```text
state
district
region
```

Precise home addresses or unnecessary fine-grained location data should not be included in open or aggregated journey records.

The appropriate geographic level will depend on the implementation and the risk of re-identification.

---

## Dates and timestamps

Journey events may require dates or timestamps to measure delay and progression.

For public reporting or open datasets, implementations should consider whether exact timestamps create a re-identification risk, particularly where datasets are small.

Where appropriate, reporting may use:

- date ranges;
- aggregated time intervals;
- broader reporting periods;
- calculated duration instead of exact timestamp.

---

## Clinical information

The Maternal Continuity Module is intended to measure continuity, not to act as an open clinical record.

The open specification should avoid requiring detailed clinical information unless it is necessary for the continuity function.

Examples of information generally outside the open continuity layer include:

- detailed diagnosis history;
- full clinical notes;
- detailed laboratory results;
- prescriptions;
- clinician free-text assessments;
- sensitive clinical observations.

These may exist in a production healthcare system but should remain governed separately.

---

## Consent

Production implementations should provide an appropriate consent process for collecting and using patient information.

Consent design should clearly address:

- what information is being collected;
- why it is being collected;
- how it will be used;
- who may access it;
- whether de-identified information may be used for analysis;
- how consent can be withdrawn where applicable.

The exact consent process will depend on the implementation environment and applicable requirements.

---

## Access control

Production systems should restrict access according to role and operational need.

Examples may include separate access for:

- patients;
- Care Navigators;
- healthcare providers;
- authorised operational staff;
- authorised analysts.

Access to continuity data should not automatically provide access to all clinical or identifying information.

---

## Auditability

Production systems should maintain appropriate records of access and significant data changes.

Audit records may include:

- who accessed information;
- when access occurred;
- when a journey status changed;
- when a referral or follow-up status changed;
- when data was corrected.

Detailed production audit architecture remains outside the scope of this repository.

---

## De-identification for analysis

Data used for system-level analysis should be de-identified or aggregated before being shared beyond authorised operational use.

Possible approaches include:

- removing direct identifiers;
- replacing identifiers with pseudonymous values;
- reducing geographic precision;
- reducing timestamp precision;
- suppressing very small groups;
- reporting aggregated indicators instead of individual records.

No single technique guarantees anonymity in every context.

De-identification should therefore be assessed against the actual dataset and intended use.

---

## Public reporting

Public reporting should focus on aggregated continuity measures such as:

- referral completion;
- follow-up completion;
- frequency of delays;
- unresolved care steps;
- barrier frequency;
- service-availability patterns.

Public reports should not expose individual maternal journeys unless the data has been appropriately de-identified and disclosure risk has been reviewed.

---

## Example

A public or demonstration record may contain:

```json
{
  "journey_id": "MJ-DEMO-001",
  "stage": "referral_handoff",
  "status": "delayed",
  "barriers": [
    "transport"
  ],
  "region": "Enugu"
}
```

It should not contain:

```json
{
  "patient_name": "Example Person",
  "phone": "+234...",
  "home_address": "...",
  "medical_record_number": "..."
}
```

---

## Production responsibility

This repository defines a reusable continuity-data layer.

Each implementation remains responsible for establishing appropriate:

- privacy controls;
- consent processes;
- security controls;
- access policies;
- retention rules;
- data-sharing agreements;
- breach-response procedures;
- legal and regulatory compliance.

These requirements should be reviewed before any live deployment involving real patient information.
