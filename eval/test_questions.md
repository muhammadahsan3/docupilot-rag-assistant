# DocuPilot Evaluation Questions

## Evaluation Overview

**Purpose:** This evaluation set is the predefined benchmark for DocuPilot's RAG pipeline. The questions are designed to test whether the system can retrieve the correct evidence, combine evidence when necessary, generate grounded answers, provide correct source citations, and refuse questions that cannot be answered from the corpus.

**Corpus:**
1. AC 43-9D — Maintenance Records and FAA Form 8130-3 Return to Service
2. AC 20-77B — Use of Manufacturers' Maintenance Manuals
3. AC 121-22D — Maintenance Review Boards, Maintenance Type Boards, and OEM/TCH Recommended Maintenance Procedures
4. AC 43-12A — Preventive Maintenance
5. AC 39-7D — Airworthiness Directives

**Question distribution:**
- Q1–Q5: Direct retrieval
- Q6–Q10: Synthesis / multi-step reasoning
- Q11–Q13: Cross-document comparison
- Q14–Q15: Unanswerable / out-of-corpus

**Important page convention:** Page numbers below are **1-based PDF page numbers**, so they can be mapped directly to the pages in the original PDFs. They are not necessarily the printed page number shown inside the document.

**Evaluation principle:** For answerable questions, the expected answer is a concise paraphrase of the cited evidence. The RAG system should not be expected to reproduce the source wording verbatim.

---

# Category 1 — Direct Retrieval

## Q1 — Who is responsible for making maintenance record entries?

**Type:** Direct Retrieval  
**Difficulty:** Easy

**Question:**  
According to AC 43-9D, which parties have responsibilities for making maintenance record entries, and what additional record-entry responsibility applies to a person approving or disapproving an aircraft, airframe, engine, propeller, appliance, or component for return to service after an applicable inspection?

**Expected Answer:**  
AC 43-9D explains that the aircraft owner/operator is responsible for keeping and maintaining the aircraft maintenance records, while each person who performs maintenance, preventive maintenance, rebuilding, or alteration must make the required maintenance-record entry. It also states that a person approving or disapproving the equipment for return to service after an applicable inspection must make an entry in the maintenance record.

**Expected Source:**  
- Document: AC 43-9D
- PDF page: 3
- Section: 8.1 Responsibilities

**Why this question matters:**  
Tests whether retrieval can find the correct responsibilities instead of returning generic information about maintenance records.

---

## Q2 — What inspection and repair information can a manufacturer's maintenance manual contain?

**Type:** Direct Retrieval  
**Difficulty:** Easy

**Question:**  
According to AC 20-77B, what kinds of inspection and repair information may be included in a manufacturer's maintenance manual?

**Expected Answer:**  
The AC states that a manufacturer's maintenance manual may include the frequency and extent of inspections considered necessary for proper maintenance, special repair methods, special inspection techniques such as X-ray, ultrasonic, or magnetic-particle inspection, and other technical information such as tolerances, adjustments, and special tools.

**Expected Source:**  
- Document: AC 20-77B
- PDF page: 2
- Section: 4(b) Maintenance Manual Subject Matter

**Why this question matters:**  
Tests retrieval of a specific list of technical information rather than just the document's general purpose.

---

## Q3 — What limitation does AC 43-12A place on pilots performing preventive maintenance?

**Type:** Direct Retrieval  
**Difficulty:** Easy

**Question:**  
What limitation does AC 43-12A place on a pilot performing preventive maintenance when the aircraft is operated under Parts 121, 127, or 135?

**Expected Answer:**  
A pilot may not perform preventive maintenance on an aircraft used under Parts 121, 127, or 135, even if the pilot owns the aircraft.

**Expected Source:**  
- Document: AC 43-12A
- PDF page: 2
- Section: 4(b)(2)

**Why this question matters:**  
Tests retrieval of a specific operational limitation from an older, more difficult-to-extract PDF.

---

## Q4 — How can an Airworthiness Directive specify its compliance time?

**Type:** Direct Retrieval  
**Difficulty:** Medium

**Question:**  
According to AC 39-7D, what are several ways an Airworthiness Directive can specify when compliance is required?

**Expected Answer:**  
An AD may require action before further flight, within a specified number of hours in service, within a specified number of landings or other operational events, in cycles for turbine engines, or by a calendar date/time period.

**Expected Source:**  
- Document: AC 39-7D
- PDF pages: 5–6
- Section: 11(b) Requirements and 11(c) Expression of Time

**Why this question matters:**  
Tests whether the system can retrieve a group of related requirements rather than a single keyword match.

---

## Q5 — How long are maintenance records retained under the general rule, and what exception is discussed?

**Type:** Direct Retrieval  
**Difficulty:** Medium

**Question:**  
According to AC 43-9D, what is the general retention period for records of maintenance, alterations, and required or approved inspections, and what special retention period is discussed for work performed under 14 CFR §§ 91.411 and 91.413?

**Expected Answer:**  
The general rule described in AC 43-9D is that the records are retained until the work is repeated, superseded, or for 1 year. Because the altimeter and transponder tests under §§ 91.411 and 91.413 have a 24-month interval, the AC states that entries for work performed under § 43.9 will be retained for 24 months or until the work is repeated or superseded.

**Expected Source:**  
- Document: AC 43-9D
- PDF page: 3
- Section: 8.2 Maintenance Records That Are to Be Retained

**Why this question matters:**  
Tests retrieval of an exception and helps detect systems that only retrieve the headline "1 year" rule.

---

# Category 2 — Synthesis / Multi-step Reasoning

## Q6 — How do AC 43-12A and AC 43-9D define the information that should appear in a preventive-maintenance record entry?

**Type:** Synthesis / Multi-step Reasoning  
**Difficulty:** Medium

**Question:**  
Compare the preventive-maintenance recording guidance in AC 43-12A with the maintenance-record guidance in AC 43-9D. What information does the system need to identify for the description of the work, and when can a reference to technical data be used instead of a detailed description?

**Expected Answer:**  
Both documents emphasize that the record must describe the work performed or provide an acceptable reference to data describing the work. AC 43-12A specifically says the entry should indicate what was done and how it was done, and allows references to manufacturer's manuals, FAA ACs, or other acceptable documents when appropriate; if a non-common reference is used, it should become part of the maintenance record. AC 43-9D likewise says the work description must be detailed enough for a person unfamiliar with the work to understand what was done and the methods/procedures used, while allowing reference to acceptable technical data when the work is extensive.

**Expected Sources:**  
- AC 43-12A — PDF pages 2–3, Section 4(e)
- AC 43-9D — PDF page 4, Section 8.4

**Why this question matters:**  
Tests whether retrieval can bring together semantically similar guidance from two different documents and preserve the distinction between the two explanations.

---

## Q7 — How do AC 20-77B and AC 43-12A connect manufacturer maintenance manuals to preventive-maintenance work?

**Type:** Synthesis / Multi-step Reasoning  
**Difficulty:** Medium

**Question:**  
Using AC 20-77B and AC 43-12A together, explain why a manufacturer's maintenance manual is relevant when performing preventive maintenance.

**Expected Answer:**  
AC 20-77B describes manufacturer's maintenance manuals as an important source of servicing, repair, and maintenance information, including inspection frequencies, repair methods, special inspection techniques, tools, and other technical information. AC 43-12A states that preventive maintenance must use methods, techniques, and practices acceptable to the Administrator and says these are normally set out in the manufacturer's maintenance manuals, although some may also be found in FAA ACs. Together, the documents establish the manufacturer's manual as an important technical reference for carrying out preventive maintenance properly.

**Expected Sources:**  
- AC 20-77B — PDF pages 1–2, Sections 3–4
- AC 43-12A — PDF page 2, Section 4(d)(1)

**Why this question matters:**  
Tests semantic retrieval because the two documents discuss the same concept using different language.

---

## Q8 — What does the corpus say about AD compliance records and the information they should contain?

**Type:** Synthesis / Multi-step Reasoning  
**Difficulty:** Medium

**Question:**  
Using AC 39-7D and AC 43-9D, explain the relationship between complying with an Airworthiness Directive and recording that compliance in maintenance records.

**Expected Answer:**  
AC 39-7D explains that owners/operators are responsible for complying with applicable ADs and recording AD compliance in the appropriate maintenance records. AC 43-9D adds specific record-content guidance: the current AD status should include, at minimum, the method used to comply, the AD number, the revision date, and—when recurring action is required—the date when the next action is due. AC 43-9D also provides a suggested Airworthiness Directive Compliance Record format in Appendix A.

**Expected Sources:**  
- AC 39-7D — PDF page 1, Section 1
- AC 43-9D — PDF pages 5–6, Section 8.7.5 and Appendix A on PDF page 18

**Why this question matters:**  
Tests whether the system can connect a high-level compliance responsibility with the more detailed recordkeeping requirements.

---

## Q9 — How do manufacturer maintenance manuals differ from MRBR/MTBR or OEM/TCH requirements documents in the maintenance-program context?

**Type:** Synthesis / Multi-step Reasoning  
**Difficulty:** Hard

**Question:**  
Based on AC 20-77B and AC 121-22D, explain the different roles played by manufacturer's maintenance manuals and MRBR/MTBR/OEM-TCH requirements documents in supporting aircraft maintenance programs.

**Expected Answer:**  
AC 20-77B describes manufacturer's maintenance manuals as detailed technical sources for maintaining aircraft, engines, and propellers, including inspection frequencies, repair methods, inspection techniques, and special tools; some may also contain a detailed CAMP that an operator may choose to adopt. AC 121-22D describes MRBRs, MTBRs, and OEM/TCH requirements documents as sources of minimum scheduled maintenance tasking/interval requirements that operators use as a basis for developing and designing their maintenance programs after FAA approval. Thus, the manual is primarily a detailed technical-maintenance reference, while the MRBR/MTBR/OEM-TCH requirements document provides scheduled-maintenance tasking/interval requirements used in maintenance-program development.

**Expected Sources:**  
- AC 20-77B — PDF pages 1–2, Sections 3–4
- AC 121-22D — PDF pages 1 and 4–5, Sections 1.1 and 8.1–8.2

**Why this question matters:**  
Tests deeper semantic retrieval and distinction between closely related maintenance-information concepts.

---

## Q10 — If a modified product appears to remove an unsafe condition, can the operator simply treat the AD as no longer applicable?

**Type:** Synthesis / Multi-step Reasoning  
**Difficulty:** Hard

**Question:**  
Suppose a product covered by an Airworthiness Directive has been modified in a way that appears to eliminate the unsafe condition. Based on AC 39-7D and AC 43-9D, can the operator simply treat the AD as no longer applicable, and what recordkeeping issue remains important?

**Expected Answer:**  
No. AC 39-7D states that an AD applies to each product identified in its applicability statement even if it has been modified, altered, or repaired. If the change affects how the AD requirements can be performed, the owner/operator must use the AD's AMOC provision to request FAA approval for an alternative action or, in some cases, no action. AC 43-9D further requires the current status of applicable ADs to be part of the maintenance record, including the method of compliance, AD number, revision date, and the next action due when the requirement is recurring.

**Expected Sources:**  
- AC 39-7D — PDF page 4, Section 9(c), and PDF pages 4–5, Sections 10–11
- AC 43-9D — PDF pages 5–6, Section 8.7.5

**Why this question matters:**  
Tests scenario-based reasoning across documents and specifically targets a common hallucination failure: assuming a modification automatically eliminates an AD obligation.

---

# Category 3 — Cross-Document Comparison

## Q11 — How do AC 43-12A and AC 43-9D differ in their treatment of preventive-maintenance records?

**Type:** Cross-Document Comparison  
**Difficulty:** Medium

**Question:**  
Compare the preventive-maintenance recordkeeping guidance in AC 43-12A with the broader maintenance-record requirements in AC 43-9D. What does each document emphasize?

**Expected Answer:**  
AC 43-12A focuses specifically on how preventive maintenance is recorded, including the description/reference of work performed, date of completion, and the kind of airman certificate exercised. AC 43-9D provides a broader framework for maintenance records, including who must make entries, what records must be retained, retention periods, AD status, and other record-content requirements. The two documents therefore overlap on recording the work but differ in scope and level of detail.

**Expected Sources:**  
- AC 43-12A — PDF pages 2–3, Section 4(e)
- AC 43-9D — PDF pages 3–6, Sections 8.1–8.7

**Why this question matters:**  
Tests whether the system can retrieve multiple sources and produce a comparison rather than merging them into one undifferentiated answer.

---

## Q12 — How do AC 20-77B and AC 121-22D describe keeping maintenance information current?

**Type:** Cross-Document Comparison  
**Difficulty:** Hard

**Question:**  
Compare the mechanisms described in AC 20-77B and AC 121-22D for keeping maintenance information or requirements current as aircraft information changes over time.

**Expected Answer:**  
AC 20-77B says manufacturers may use a systematic manual-revision system to implement changes to maintenance instructions and notes that owners/operators should allow for such changes; it also identifies circumstances in which Service Bulletins can become regulatory. AC 121-22D describes MRBR/MTBR/OEM-TCH requirements as dynamic reports subject to periodic revision based on new or changed analysis or requirements, and describes processes for validation, verification, and updates. Both recognize that maintenance information evolves, but they address different document/revision mechanisms.

**Expected Sources:**  
- AC 20-77B — PDF page 2, Section 5
- AC 121-22D — PDF page 1, Section 1.1; PDF pages 5–6, Sections 10 and related validation material

**Why this question matters:**  
Tests whether retrieval can distinguish two different revision/update mechanisms instead of treating all "maintenance updates" as the same concept.

---

## Q13 — How do AC 39-7D and AC 43-9D differ in their treatment of AD compliance?

**Type:** Cross-Document Comparison  
**Difficulty:** Hard

**Question:**  
Compare the focus of AC 39-7D and AC 43-9D regarding Airworthiness Directive compliance.

**Expected Answer:**  
AC 39-7D focuses on the operator's responsibility to comply with ADs, how applicability is determined, how compliance times are expressed, and the use of AMOCs when an alternative method is needed. AC 43-9D focuses more heavily on how AD compliance is documented in maintenance records, including the AD number, revision date, method of compliance, and next due action for recurring requirements. Together they address both the compliance obligation and the recordkeeping evidence of that compliance.

**Expected Sources:**  
- AC 39-7D — PDF pages 1, 4–6, Sections 1, 9–12
- AC 43-9D — PDF pages 5–6, Section 8.7.5 and Appendix A on PDF page 18

**Why this question matters:**  
Tests multi-source retrieval and whether the model can preserve the distinct purpose of two related documents.

---

# Category 4 — Unanswerable / Out-of-Corpus

## Q14 — What is the current labor cost of performing an AD inspection?

**Type:** Unanswerable / Out-of-Corpus  
**Difficulty:** Medium

**Question:**  
What is the current labor cost, in U.S. dollars, for performing an Airworthiness Directive inspection?

**Expected Behavior:**  
The system should state that the provided document corpus does not contain current labor-cost or pricing information and should not invent a dollar amount.

**Why it is unanswerable:**  
The corpus discusses AD compliance, maintenance records, procedures, and responsibilities, but it does not provide current labor rates or inspection prices.

---

## Q15 — What is the next AD compliance date for a specific aircraft registration?

**Type:** Unanswerable / Out-of-Corpus  
**Difficulty:** Medium

**Question:**  
For an aircraft with registration **N12345**, what is the exact next Airworthiness Directive compliance date?

**Expected Behavior:**  
The system should state that the provided documents do not contain enough aircraft-specific information to determine the next AD compliance date and should not fabricate a date.

**Why it is unanswerable:**  
AC 39-7D explains how AD applicability and compliance times work, and AC 43-9D explains what AD status should be recorded, but the corpus does not contain an actual AD record for registration N12345 or the aircraft-specific maintenance history needed to calculate its next due date.

---

# Final Evaluation Matrix

| ID | Type | Difficulty | Expected Source(s) | Main Skill Tested |
|---|---|---|---|---|
| Q1 | Direct Retrieval | Easy | AC 43-9D | Responsibility retrieval |
| Q2 | Direct Retrieval | Easy | AC 20-77B | Technical-list retrieval |
| Q3 | Direct Retrieval | Easy | AC 43-12A | Constraint retrieval |
| Q4 | Direct Retrieval | Medium | AC 39-7D | Multi-item fact retrieval |
| Q5 | Direct Retrieval | Medium | AC 43-9D | Exception retrieval |
| Q6 | Synthesis | Medium | AC 43-12A + AC 43-9D | Similar concepts across documents |
| Q7 | Synthesis | Medium | AC 20-77B + AC 43-12A | Semantic relationship |
| Q8 | Synthesis | Medium | AC 39-7D + AC 43-9D | Compliance + recordkeeping |
| Q9 | Synthesis | Hard | AC 20-77B + AC 121-22D | Distinguishing related technical concepts |
| Q10 | Synthesis | Hard | AC 39-7D + AC 43-9D | Scenario reasoning + grounding |
| Q11 | Comparison | Medium | AC 43-12A + AC 43-9D | Scope comparison |
| Q12 | Comparison | Hard | AC 20-77B + AC 121-22D | Revision/update comparison |
| Q13 | Comparison | Hard | AC 39-7D + AC 43-9D | Compliance vs. recordkeeping |
| Q14 | Unanswerable | Medium | None | Hallucination resistance |
| Q15 | Unanswerable | Medium | None | Missing-data handling |

---

# Evaluation Design Notes

These questions intentionally avoid relying on exact phrase matching. A successful RAG system should retrieve semantically relevant evidence even when the user's wording differs from the source.

Several questions require evidence from more than one document. This is intentional: later, the system should be tested not only on single-passage retrieval but also on retrieving multiple relevant passages and producing a grounded synthesis.

The unanswerable questions are essential because a RAG system should not be considered successful merely because it produces fluent answers. For these questions, a confident invented answer is a failure.

During Week 5, each answerable question should be evaluated on at least:
- whether the required evidence was retrieved,
- whether the answer is faithful to that evidence,
- whether the cited source/document/page is correct.

Do **not** place the expected answers in the production runtime prompt. They are evaluation ground truth and should remain outside the production RAG context.
