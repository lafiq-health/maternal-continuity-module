# Continuity Indicators

## Purpose

This document defines the initial indicators used to measure whether maternal-care journeys progress as planned and where continuity breaks.

The indicators are intended for pilot measurement, operational review and aggregated analysis.

They do not represent clinical outcomes and should not be interpreted as measures of treatment quality or clinical effectiveness.

---

## 1. Planned Care-Step Completion

Measures whether planned care steps were completed.

**Definition**

```text
completed planned care steps
--------------------------------
total planned care steps
```

Possible uses:

- identify stages with low completion;
- compare completion across journey stages;
- monitor whether unresolved steps are accumulating.

---

## 2. Referral Completion

Measures whether referrals resulted in the intended referred care being completed.

**Definition**

```text
completed referrals
-------------------
total referrals created
```

Referral status should be derived from the referral schema rather than inferred from appointment creation alone.

A referral is not considered complete simply because it was issued or scheduled.

---

## 3. Follow-up Completion

Measures whether required follow-up activity was completed.

**Definition**

```text
completed follow-ups
--------------------
follow-ups required
```

Examples may include:

- investigation-result follow-up;
- referral follow-up;
- antenatal follow-up;
- postnatal follow-up;
- unresolved care-step follow-up.

---

## 4. Delayed Care Steps

Measures the number or proportion of planned care steps recorded as delayed.

A care step is considered delayed when the expected progression did not occur within the relevant planned timeframe.

Initial reporting may include:

- total delayed steps;
- delayed steps by journey stage;
- delayed steps by barrier category;
- average duration of delay where timestamps are available.

---

## 5. Unresolved Care Steps

Measures care steps that remain incomplete without a confirmed resolution.

This indicator is important because an unresolved step may represent a point where the patient has effectively dropped out of the intended care pathway.

Possible measures include:

- number of unresolved steps;
- unresolved steps by journey stage;
- proportion of journeys containing at least one unresolved step.

---

## 6. Journey Interruption

Identifies where continuity stopped or was materially interrupted.

A journey interruption may be recorded when:

- a required investigation remains incomplete;
- a referral is not completed;
- a required service is unavailable;
- follow-up does not occur;
- another unresolved step prevents progression.

The interruption should be linked to the relevant journey stage and recorded barrier where known.

---

## 7. Time to Next Care Step

Measures the elapsed time between selected care events.

Examples include:

- antenatal visit to requested investigation;
- investigation request to completion;
- referral creation to completion;
- delivery to postnatal follow-up.

This indicator can help distinguish normal progression from prolonged gaps.

Expected timeframes should be defined during implementation and should not be treated as universal clinical thresholds unless clinically validated.

---

## 8. Barrier Frequency

Measures how often specific barriers are associated with delayed, interrupted or unresolved care.

Initial barrier categories include:

- cost;
- transport;
- distance;
- provider unavailable;
- service unavailable;
- facility capacity;
- scheduling delay;
- incomplete referral;
- unable to attend;
- communication failure;
- other locally identified barrier.

Reporting may include:

```text
number of affected care steps by barrier
----------------------------------------
total delayed or unresolved care steps
```

Multiple barriers may apply to the same care step.

---

## 9. Service Availability

Measures whether the provider, facility or service required for a planned step was available when needed.

Possible measures include:

- proportion of required services recorded as available;
- unavailable services by journey stage;
- unavailable services associated with referral failure or delay.

This indicator is intended to help distinguish patient-level barriers from health-system capacity constraints.

---

## 10. Referral Acceptance

Measures whether the intended destination accepted a referral.

Possible outputs include:

- referral acceptance rate;
- referral decline rate;
- referrals remaining unresolved;
- barriers associated with non-acceptance.

Referral acceptance is separate from referral completion.

A referral may be accepted but still not completed.

---

## 11. Patient Attendance

Measures whether the patient reached or attended the intended referred or scheduled service where attendance is relevant.

This can help separate:

- service availability problems;
- referral-system problems;
- transport or affordability barriers;
- missed attendance.

Attendance alone does not establish that the care step was completed.

---

## 12. Continuity Outcome

Each journey event may carry a high-level continuity outcome:

```text
progressed
pending
interrupted
completed
```

These outcomes are intended to summarize what happened after a care step.

They do not determine the clinical condition of the patient.

---

## Pilot-Level Reporting

The first regional pilot in Enugu is expected to establish baseline evidence on:

- planned-step completion;
- referral completion;
- follow-up completion;
- frequency and duration of delays;
- unresolved care steps;
- stages where journeys are interrupted;
- commonly reported barriers;
- service-availability constraints.

The purpose of the pilot is to establish where continuity breaks and why.

It should not assume in advance that the dominant barrier will be the same across locations.

---

## Regional Comparison

Future regional testing may compare patterns such as:

```text
Region A
Primary barrier: transport

Region B
Primary barrier: facility capacity

Region C
Primary barrier: affordability
```

The continuity framework should remain broadly consistent while allowing locally relevant barrier categories and implementation details to evolve.

---

## Data Interpretation

Indicators should be reported using de-identified or aggregated data.

Care should be taken not to interpret continuity indicators as:

- clinical diagnosis;
- clinical risk scores;
- treatment outcomes;
- provider-quality rankings;
- individual patient performance measures.

They are intended to describe the completion and continuity of the care journey.

---

## Indicator Development

These indicators are initial definitions.

They will be refined through:

- production implementation;
- maternal-health practitioner review;
- pilot testing;
- feedback from participating providers and institutions;
- observed data quality and usefulness.

Changes should be documented as the module develops.
