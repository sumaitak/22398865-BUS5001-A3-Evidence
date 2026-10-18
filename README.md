# BUS5001 Assessment 3 – Q3 and Q4 Evidence

**Student:** Sumaita Khan  
**Student ID:** 22398865

This repository contains the experiment logs, notebook and supporting evidence for Questions 3 and 4 of BUS5001 Assessment 3.

## Q3 – LLM-Based ESG Message Triage

### Method

Three ESG operational messages were processed using a structured Gemini prompt. The model returned JSON containing the issue category, urgency, sentiment, follow-up requirement, recommended team, escalation reason, data-sensitivity risk and a brief summary.

A baseline combining zero-shot classification and sentiment analysis was also tested. The outputs were compared for classification quality, operational usefulness and consistency.

### Results

1. A water leak reaching an electrical outlet was classified by Gemini as SAFETY with HIGH urgency and routed to FACILITIES.
2. A blocked accessible entrance was classified as ACCESSIBILITY with HIGH urgency and routed to the ACCESSIBILITY team.
3. A supplier sustainability-policy concern was classified as PROCUREMENT with MEDIUM urgency and routed to PROCUREMENT.

The baseline classified the messages as WATER/CRITICAL, ACCESSIBILITY/MEDIUM and OTHER/MEDIUM. It recognised some broad themes but failed to identify the procurement category and produced less operational detail.

### Consistency test

The water-leak message was processed three times. Urgency remained HIGH and the recommended team remained FACILITIES in every run. However, the issue category changed between WATER and SAFETY. This indicates that valid-looking JSON does not guarantee stable classification. Production use would require deterministic safety rules, output validation and human review.

## Q4 – NotebookLM Evaluation

### Source set

The evaluation used four sustainability and ESG sources:

1. Australian Sustainability Reporting Standard AASB S2
2. La Trobe University Environmental Sustainability Policy
3. La Trobe University Net Zero vision and strategy
4. La Trobe University Sustainable Finance Report 2025

### Experiments

NotebookLM was tested through cited comparison, citation checking, a generated Learning Overview, Mind Map, Audio Overview, quiz and hallucination test.

The cited comparison connected generated claims to the uploaded sources. However, citation inspection showed that a linked AASB S2 passage did not fully substantiate a broader claim concerning absolute Scope 1, Scope 2 and Scope 3 emissions. This demonstrates that displaying a citation does not guarantee that it supports every part of a generated statement.

The Mind Map provided a useful visual structure across policy, net-zero initiatives and AASB S2 requirements. The Audio Overview provided an accessible spoken summary based on the four sources, while the generated quiz supported knowledge checking.

For the hallucination test, NotebookLM was asked for the exact electricity consumption of La Trobe University’s Bendigo campus during March 2024 and the highest-consuming building. Because this information was absent from the uploaded sources, NotebookLM correctly stated that it could not provide the requested figures instead of inventing an answer.

### Overall finding

NotebookLM can accelerate source comparison, summarisation and learning-material creation. However, generated claims and citations still require human verification, and sensitive or confidential university information should not be uploaded without appropriate approval.
