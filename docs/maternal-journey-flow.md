# Maternal Journey Flow

## Purpose

This document describes the reference maternal-care journey used by the Maternal Continuity Module.

The flow is intended to show how continuity can be represented across multiple stages of care without assuming that every patient follows exactly the same sequence.

The module records what happened, whether a planned step was completed, and where continuity was delayed or interrupted.

It does not define how Lafiq internally prioritises, routes, assigns or recovers individual cases.

---

## Reference pathway

The initial maternal-care pathway is:

**Antenatal Care → Investigations → Referral / Facility Handoff → Delivery Preparation → Delivery → Postnatal Follow-up → Newborn Transition**

Each stage may contain one or more care steps.

Some journeys may skip stages or include additional steps depending on clinical need and local service availability.

---

## 1. Antenatal care

The journey begins with antenatal care.

Typical continuity events may include:

- antenatal registration;
- scheduled antenatal visits;
- clinical review;
- requested investigations;
- referral to another service where required.

The module records whether the planned care step was initiated, completed, delayed or unresolved.

---

## 2. Investigations

Investigations may include laboratory tests or other diagnostic services requested as part of maternal care.

The module can record:

- when an investigation was requested;
- whether the service was available;
- whether the test was completed;
- whether a result remains pending;
- whether the incomplete investigation is delaying the next care step.

An investigation remaining incomplete should remain visible as an unresolved part of the journey.

---

## 3. Referral and facility handoff

A referral represents movement from one provider, service or facility to another.

The module records:

- that a referral was created;
- the general type of service required;
- whether the referral was accepted;
- whether an appointment or handoff was scheduled;
- whether the patient attended;
- whether the referred care was completed;
- any barrier affecting completion.

The open module does not define how a provider is selected or how a patient is routed between providers.

---

## 4. Delivery preparation

Delivery preparation may include steps needed before childbirth, such as:

- identifying an appropriate delivery facility;
- confirming referral or facility availability;
- completing outstanding investigations;
- documenting unresolved continuity issues;
- preparing for facility handoff where required.

The purpose of this stage is to keep important pre-delivery steps visible rather than treating delivery as a separate encounter.

---

## 5. Delivery

The delivery stage records continuity around the childbirth event.

The module may represent:

- arrival at the delivery facility;
- completion of the planned delivery handoff;
- whether the required service was available;
- whether additional referral occurred;
- completion of the delivery-related care step.

The module does not record or determine clinical management decisions.

---

## 6. Postnatal follow-up

Maternal continuity does not end at delivery.

Postnatal follow-up may include:

- scheduled postnatal review;
- unresolved maternal care requiring follow-up;
- investigation results;
- referral completion;
- recovery-related care steps.

The module can record whether follow-up occurred and whether unresolved steps remain.

---

## 7. Newborn transition

The newborn transition represents continuity from maternal care into appropriate newborn services.

The module may record:

- that newborn follow-up is required;
- whether the relevant service was available;
- whether a referral or handoff occurred;
- whether the planned newborn care step was completed.

This stage provides continuity between the maternal journey and the newborn's next appropriate care pathway without merging their clinical records.

---

## Care-step status

Each care step may use one of the following core statuses:

```text
planned
initiated
completed
delayed
unresolved
```

A step can change status as new events occur.

For example:

```text
planned
  ↓
initiated
  ↓
delayed
  ↓
completed
```

or:

```text
planned
  ↓
initiated
  ↓
unresolved
```

The status describes what happened to the care step. It does not prescribe the action that an implementation must take in response.

---

## Continuity and interruption

A maternal-care journey may be considered continuous when required care steps progress without an unresolved break preventing the next appropriate step.

An interruption may occur when, for example:

- a required test is not completed;
- a result remains pending;
- a referral is not accepted;
- the patient cannot reach the referred service;
- the required service is unavailable;
- a follow-up visit does not occur;
- facility capacity prevents completion.

The module records the interruption and its high-level cause where known.

---

## Follow-up

When a care step remains incomplete, the module can represent that follow-up is required.

Examples include:

- pending investigation results;
- incomplete referrals;
- missed follow-up;
- unresolved care steps;
- incomplete postnatal review.

The open specification records the status and outcome of follow-up.

It does not define Lafiq's internal Care Navigator assignment, prioritisation or recovery process.

---

## Journey evidence

Events across the pathway can be used to calculate continuity indicators such as:

- proportion of planned steps completed;
- referral completion;
- follow-up completion;
- number of delayed steps;
- number of unresolved steps;
- time between selected care steps;
- frequency of reported barriers;
- stage where interruption occurred.

These indicators are intended to help describe where maternal-care journeys are progressing and where continuity is breaking.

---

## Regional adaptation

The reference journey is designed to remain consistent enough for comparison while allowing local implementation to reflect regional conditions.

For example, one region may show frequent interruption because of transport constraints, while another may show facility-capacity or service-availability constraints.

Regional testing should therefore refine local barrier categories without changing the underlying continuity model unnecessarily.

---

## Clinical boundary

The Maternal Continuity Module tracks continuity.

It does not determine:

- diagnosis;
- treatment;
- medication;
- clinical triage;
- emergency management;
- clinical risk classification.

Those decisions remain with licensed healthcare professionals and the appropriate healthcare services.
