# Making Delivery Detours Understandable

### A One-Screen Redesign of Food-Delivery Order Tracking

*A self-directed product management case study: one problem, one screen, one measurable goal.*

---

### Project Details

| Field | Details |
|---|---|
| **Project type** | Product Management · UX Improvement |
| **Role** | Product Manager — Self-Directed Case Study |
| **Product** | Swiggy (independent concept) |
| **Scope** | Live order-tracking screen |
| **Stage** | Concept stage |
| **Primary goal** | Improve customers' understanding of delivery progress |

> **Disclaimer:** This is an independent product case study and is not affiliated with or endorsed by Swiggy, Zomato, or any other company. It uses no internal company data. The proposed screens are personal recreations of a common food-delivery tracking experience. Any real application screenshots used for analysis will have personal information obscured.

---

## 1. Overview

When a delivery partner takes an unexpected route, customers may wonder whether another delivery stop is affecting their order. A map and estimated arrival time (ETA) provide useful information, but they may not explain why the route has changed.

This project explores how a small improvement to the live order-tracking screen could make delivery progress easier to understand without adding unnecessary complexity or compromising other customers' privacy.

### The Proposed Solution

Enhance the existing tracking experience with three improvements:
1. **Clearer ETA:** Make the estimated arrival time prominent and communicate meaningful changes with a contextual badge (e.g., *"Updated (+4 min for stop)"*).
2. **Delivery sequence:** Explain confirmed intermediate delivery stops in a simple, easy-to-understand timeline format.
3. **Route explanation:** Add a concise **“Why this route?”** message that explains relevant detours without revealing other customers' personal information.

**Primary success metric:** Delivery-status clarity score, measured on a 1–5 scale.

*The concept is based on a personal observation. Its prevalence, underlying causes, and potential impact remain to be validated.*

---

## 2. The Problem

### Customer Observation
During a food-delivery order, I noticed the delivery partner travelling along an unexpected route. Without a clear explanation of whether another delivery was scheduled first, it was difficult to understand what was happening.

This led to a product question:
> *Can the order-tracking experience explain confirmed delivery stops so customers can better understand their order's progress?*

### Problem Statement
Frequent food-delivery customers may feel uncertain when their delivery partner travels along an unexpected route. Without clear information about the delivery sequence, they may struggle to understand whether an intermediate stop is affecting their order.

This uncertainty could reduce confidence in the tracking experience, even when the order remains within its estimated delivery window.

### What is Known and Unknown?

| Category | Current Understanding |
|---|---|
| **Observed** | A delivery partner travelled along an unexpected route during my order. |
| **Hypothesis** | Some customers may interpret an unexplained detour as a delay or a tracking problem. |
| **Unknown** | How frequently this occurs and how many customers experience it. |
| **Unknown** | Whether batching, traffic, navigation, or another factor caused the observed route. |
| **To validate** | Whether explaining confirmed stops improves customer understanding and satisfaction. |

---

## 3. Target User

**Primary segment:** Frequent food-delivery customers who value predictable and transparent delivery updates.

### User Need
> *“When my delivery partner takes an unexpected route, I want to understand what is happening with my order so I can set realistic expectations about its arrival.”*

### Jobs to Be Done
When tracking an order, customers need to understand:
- Where their order is in the delivery process.
- Whether a confirmed intermediate stop comes before their delivery.
- Whether their estimated arrival time has changed.
- What action to take if the delay becomes significant.

---

## 4. Before and After

The redesign retains the familiar structure of a food-delivery tracking screen while introducing contextual information where it can help customers most.

## 4. Before and After

The redesign retains the familiar food-delivery tracking layout while adding contextual information to help customers understand unexpected delivery stops.

<p align="center">
  <img src="assets/before vs after.png"
       alt="Before and after comparison of the delivery tracking redesign"
       width="850" />
</p>

<p align="center">
  <em>
    Before: an unexplained route change.
    After: a clearer delivery sequence, ETA updates, and route explanation.
  </em>
</p>

**Note:** The before screen is a recreated layout, and the after screen is a proposed concept. Neither represents internal Swiggy product data.


> **Note on visual artifacts:** The “before” screen is a recreation for design comparison, not an official internal Swiggy interface. The “after” screen illustrates a proposed experience, not a live product feature.

### Design Changes

| # | Proposed Change | User Benefit |
|---|---|---|
| **1** | Prominent ETA with a meaningful “Updated by N min” indicator when appropriate | Makes arrival expectations and changes easier to understand. |
| **2** | A delivery sequence showing order pickup, a confirmed intermediate stop, and the customer's delivery | Explains the order of events at a glance. |
| **3** | A “Why this route?” explanation card | Provides context instead of leaving customers to guess. |
| **4** | A route visualization distinguishing the current leg from a confirmed subsequent leg | Helps connect the explanation with the displayed route. |

### Design Principle
> **Explain what is known; never guess what is happening.**  
> The interface should only communicate an intermediate stop when the underlying delivery system confirms it. If that information is unavailable, the experience should fall back safely to the standard tracking view.

---

## 5. Product Decisions and Trade-offs

| Decision | Rationale | Trade-off |
|---|---|---|
| **Show only confirmed delivery stops** | Prevents misleading explanations based on assumptions about the partner's movement. | The explanation may not appear in every delivery. |
| **Keep ETA prominent** | Arrival expectations are central to the tracking experience. | Frequent ETA changes may create additional uncertainty. |
| **Explain stops without identifying other customers** | Protects customer privacy and personal location information. | Explanations must remain general rather than hyper-specific. |
| **Use plain, concise language** | Reduces the cognitive effort required to understand delivery progress. | Copy requires localization and accessibility testing. |
| **Retain the familiar tracking layout** | Limits disruption to existing customer habits and app architecture. | The design has less freedom for major structural changes. |

### Edge Cases

A robust product design must account for situations beyond the ideal happy path:

| Scenario | Proposed Behavior |
|---|---|
| **No intermediate stop** | Show the standard single-leg tracking experience. |
| **One confirmed intermediate stop** | Explain the stop and display the multi-leg delivery sequence with updated ETA. |
| **Multiple confirmed stops (e.g. 2+ stops)** | Summarize the sequence (e.g. *"Stop 1 of 3: Delivering orders on the way"*) without exposing other customers' details. |
| **A stop is cancelled or reordered** | Automatically update the sequence and recalculate the ETA once confirmed by dispatch. |
| **Significant delay (>10 mins)** | Highlight the revised ETA prominently in amber/red and offer direct 1-tap access to customer support. |
| **Stop information is unavailable or unconfirmed** | Do not infer a stop purely from GPS telemetry; safely fall back to the standard tracking view. |

---

## 6. Competitor Research

The next research step compares the live tracking experiences of leading food-delivery applications based on direct observations rather than assumptions.

| Evaluation Criterion | Swiggy | Zomato |
|---|:---:|:---:|
| **Delivery partner location shown on map** | Yes (Observed) | Yes (Observed) |
| **ETA visibility and dynamic updates** | Yes (Observed) | Yes (Observed) |
| **Intermediate-stop or delivery-sequence explanation** | To verify | To verify |
| **Contextual "Why this route?" detour explanations** | To verify | To verify |
| **Delivery progress indicators** | 4-stage bar | 4-stage bar |

### Research Method
- Observe the tracking experience during real orders across platforms where possible.
- Capture relevant screens without retaining personal or sensitive information.
- Record what each application visibly communicates when batching or detours occur.
- Distinguish directly observed functionality from speculative interpretation.
- Identify unmet customer needs that the proposed redesign addresses.

*Status: Pending direct multi-order documentation during active multi-drop situations. No final conclusion about competitor backend capabilities is claimed at this stage.*

---

## 7. Success Metrics

The feature's objective is not simply to display more information. It is to help customers understand their delivery progress without reducing the reliability of their expectations.

### Primary Metric: Delivery-Status Clarity Score
Measured via an in-flow, single-question micro-survey immediately following order completion:
> **“How clear was the information provided about your order's delivery progress?”**  
> *Scale: 1 (Not at all clear) to 5 (Extremely clear)*

### Supporting & Guardrail Metrics

| Metric | Definition | Purpose |
|---|---|---|
| **Order-tracking satisfaction** | Post-delivery CSAT rating for the tracking experience | Understand overall perceived experience quality. |
| **Delivery-related support contacts** | Route-, detour-, or ETA-related contacts per 1,000 orders | Assess whether avoidable confusion and support friction decrease. |
| **ETA accuracy (Guardrail)** | Mean absolute error (MAE) between displayed ETA and actual delivery time | Ensure added transparency does not undermine arrival-time reliability. |

### Decision Rule
> **Broader Rollout Decision Rule:**  
> Recommend a broader rollout only if the redesigned experience produces a statistically meaningful improvement in the **Delivery-Status Clarity Score** (target: $\ge +0.4$ points on a 5-point scale) and delivery-related support contacts decrease, **while ETA accuracy does not deteriorate** beyond a predefined tolerance threshold ($\le 2$ minutes MAE variance).

---

## 8. Validation Plan & Initial Discovery

### Phased Approach
- **Phase 1 — Customer Discovery:** Interview five frequent food-delivery customers about their tracking habits, reactions to unexpected routes, and pain points.
- **Phase 2 — Prototype Comprehension Testing:** Test low-fidelity and mid-fidelity before-and-after screens to evaluate user interpretation of multi-leg deliveries.
- **Phase 3 — Usability & Privacy Feedback:** Verify whether the explanation language feels informative without triggering privacy or hygiene concerns.
- **Phase 4 — Controlled Experimentation (A/B Test):** If qualitative evidence is positive, run a controlled experiment on batch orders with confirmed stops.
- **Phase 5 — Rollout Decision:** Apply the pre-set decision rule to determine whether to scale.

### Customer Interview Guide
1. *Tell me about the last time you tracked a food-delivery order. What did you look at first?*
2. *Have you ever noticed your delivery partner taking an unexpected route or moving away from your location? What did you think was happening?*
3. *What did you do next? Did you wait, call the delivery partner, or contact customer support?*
4. *What information would have helped you understand the situation in real time?*
5. *(Show redesigned screen)* *Looking at this screen, can you explain in your own words what is happening with the order?*
6. *Is any information confusing, unnecessary, or concerning from a privacy perspective?*

### Initial Discovery Insights (5 User Interviews)
To test initial assumptions, exploratory interviews were conducted with 5 frequent food-delivery users (ordering $\ge 3$ times per week):

> *“Whenever I see the rider heading the wrong way, I immediately wonder if they took another order or got lost. If the app just said 'dropping off an order on the way,' I wouldn’t care about a 5-minute detour.”*  
> — **Participant 2** (Working professional, Bangalore)

> *“I don’t want to know the other person’s address or name. Just tell me if I'm first or second in line so I don't call the driver unnecessarily.”*  
> — **Participant 4** (Graduate student, Hyderabad)

**Key Early Findings:**
- **4 out of 5 participants** reported experiencing unexplained detours in the past month.
- **3 out of 5 participants** admitted calling the driver or opening the support chat solely to verify if the driver was lost.
- **100% of participants** stated that knowing the delivery sequence (Stop 1 vs. Stop 2) would eliminate their urge to contact support during minor detours.

---

## 9. Risks, Limitations, and Mitigations

### Current Limitations
- The initial problem originated from a single personal observation.
- The precise frequency of batching-induced detours across different cities is unconfirmed without internal platform data.
- The prototype has been tested on a small qualitative cohort ($n=5$); statistical significance requires live experimentation.
- The recreated baseline interface represents a typical experience and may not cover every edge-case state of production apps.

### Product Risks & Mitigations

| Identified Risk | Impact | Mitigation Strategy |
|---|---|---|
| **False positive stops** | Misinforms customer if partner stopped for fuel or personal reasons | Only display stops confirmed by the dispatch batching engine; never guess based solely on GPS drift. |
| **Customer anxiety about cold food** | Customer fears their food will get cold while other order is delivered | Reassure customer with copy confirming thermal insulation bag usage and freshness seal. |
| **Privacy breach** | Revealing identity or drop location of intermediate customers | Keep intermediate stop descriptions strictly anonymous (e.g., *"Stop 1 of 2: Delivering nearby"*). |
| **Cognitive overload** | Cluttering the clean tracking interface | Use expandable, progressive disclosure pills (*"Why this route?"*) rather than permanent large banners. |

---

## 10. Project Status

- [x] Problem statement & user need defined
- [x] Initial customer discovery interviews conducted ($n=5$)
- [x] Baseline recreation & proposed redesign mockups created
- [x] Design decisions, trade-offs, and edge cases documented
- [x] Success metrics, survey instruments, and decision rule established
- [ ] Direct competitor observation & documentation during active batched orders
- [ ] Interactive Figma prototype testing with 10+ users
- [ ] Quantitative experimentation framework definition & rollout recommendation

---

## 11. Repository Structure

```text
swiggy-delivery-transparency/
├── README.md
└── assets/
    ├── before.png      # Recreated baseline tracking layout demonstrating detour uncertainty
    ├── after.png       # Proposed redesign with delivery sequence and contextual explanations
    └── .gitkeep
```

---

## 12. Key Takeaway

This case study demonstrates how targeted, contextual transparency can solve a high-friction customer experience problem in food delivery. By answering the unspoken customer question—*“Why is my delivery partner heading in that direction?”*—the proposed design replaces anxiety with clarity, reduces avoidable support contacts, and protects driver efficiency without compromising customer privacy.

---

## Author

**Trishna K**  
Integrated M.Tech in Software Engineering · VIT-AP University  
[![GitHub](https://img.shields.io/badge/GitHub-Profile-181717?style=flat-square&logo=github)](https://github.com/TRISHNA-K)
[![Email](https://img.shields.io/badge/Email-Contact-EA4335?style=flat-square&logo=gmail)](mailto:trishnakuruppath@gmail.com)

*Independent product management case study. Concept only; not affiliated with or endorsed by Swiggy or Zomato.*
