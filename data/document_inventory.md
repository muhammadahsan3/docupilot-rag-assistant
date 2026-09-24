# DocuPilot — Document Inventory

**Inventory scope:** Initial aviation technical corpus for DocuPilot v1  
**Inventory verified:** 2026-09-24  
**Primary source:** U.S. Federal Aviation Administration (FAA) official Advisory Circular documents and document-information pages.

> **Note on AC 43-12A:** The direct PDF URL supplied for this project is the original 4-page AC 43-12A. The FAA document-information page also lists a separate **Change 1** dated 2007-04-18. This inventory describes the direct PDF supplied in the project; before ingestion, verify whether the local corpus should use the original PDF or the FAA's "AC 43-12A with Change 1" version.

---

## 1. AC 43-9D — Maintenance Records and FAA Form 8130-3 Return to Service

**Document number:** AC 43-9D  
**Date issued:** 2025-09-22  
**FAA status:** Active  
**Number of pages:** 24  
**Direct PDF:** https://www.faa.gov/documentLibrary/media/Advisory_Circular/AC_43-9D.pdf  
**FAA document page:** https://www.faa.gov/regulations_policies/advisory_circulars/index.cfm/go/document.information/documentID/1044416

### Main topics

- Maintenance recordkeeping and record-making requirements under 14 CFR Parts 43 and 91.
- FAA Form 8130-3 and approval for return to service.
- Responsibilities of persons performing and approving maintenance.
- Maintenance record retention and required record contents.
- Records for life-limited parts, inspections, AD compliance, and major alterations.
- Preventive maintenance records.
- Rebuilt-engine maintenance records.
- Maintenance releases and FAA Form 337.
- Tests and inspections for altimeter systems, altitude reporting equipment, and transponders.
- Recordkeeping considerations when purchasing a used aircraft.
- FAA Form 8130-3 block-by-block completion guidance.

### Structure

- Numbered sections and subsections.
- Extensive use of numbered paragraphs.
- Appendices:
  - **Appendix A:** Airworthiness Directive Compliance Record (suggested format).
  - **Appendix B:** Block-by-block instructions for completing FAA Form 8130-3.
  - Feedback form at the end of the AC.
- Contains a structured table in **Table B-1** describing FAA Form 8130-3 Block 11 terms.

### Text searchable

**Yes.** The PDF has machine-readable/searchable text.

### Tables

**Yes.** At least one explicit table is present: **Table B-1**, and Appendix A contains a structured record/form layout.

### Figures

**No formally labeled figures identified.** The document is primarily text plus forms/structured layouts.

### Potential extraction issues

- Appendix A and Appendix B contain form-like layouts that may not extract cleanly into linear text.
- Table B-1 is a structured table and should be tested during PDF extraction to ensure row/column relationships are preserved.
- Page headers/footers and page-number markers may appear in extracted text.
- Cross-references to 14 CFR sections, FAA Orders, forms, and other ACs should be preserved as metadata/content rather than stripped as noise.

---

## 2. AC 20-77B — Use of Manufacturers' Maintenance Manuals

**Document number:** AC 20-77B  
**Date issued:** 2016-01-04  
**FAA status:** Active  
**Number of pages:** 5  
**Direct PDF:** https://www.faa.gov/documentLibrary/media/Advisory_Circular/AC_20-77B.pdf  
**FAA document page:** https://www.faa.gov/regulations_policies/advisory_circulars/index.cfm/go/document.information/documentid/1028757

### Main topics

- Usefulness of manufacturers' maintenance manuals for aircraft, engines, and propellers.
- Background on increasing aircraft complexity and the importance of manufacturer information.
- Maintenance manual structure and organization.
- Typical maintenance-manual subject matter, including:
  - System descriptions.
  - Lubrication instructions and recommended frequencies.
  - Pressures and electrical loads.
  - Tolerances and adjustments.
  - Leveling, raising, and towing.
  - Control-surface balancing.
  - Primary and secondary structures.
  - Inspection frequency and extent.
  - Special repair methods.
  - Special inspection techniques.
  - Special tools.
- Maintenance-manual revision systems.
- Circumstances in which Service Bulletins may become regulatory, including incorporation into an Airworthiness Directive or approved maintenance program.

### Structure

- Short numbered document with sections:
  1. Purpose
  2. Cancellation
  3. Background
  4. Discussion
  5. Recommendations
  6. Comments Invited
- Uses subsections and numbered/bulleted lists.

### Text searchable

**Yes.** The PDF has machine-readable/searchable text.

### Tables

**No formal tables identified.**

### Figures

**No formal figures identified in the AC itself.** The text discusses the use of drawings, charts, and photographs as typical features of manufacturer maintenance manuals, but these are described rather than supplied as figures in this AC.

### Potential extraction issues

- Numbered lists and bullet lists should remain grouped with their parent section.
- Apostrophes/typographic characters in "Manufacturers' / Manufacturer’s" terminology should be normalized carefully if used for retrieval.
- References to Service Bulletins (SB), Airworthiness Directives (AD), Airworthiness Limitation Sections (ALS), and approved inspection programs are important technical terminology and should not be removed during cleaning.
- Because the document is short, over-aggressive chunking could create chunks that are too small to retain enough context.

---

## 3. AC 121-22D — Maintenance Review Boards, Maintenance Type Boards, and OEM/TCH Recommended Maintenance Procedures

**Document number:** AC 121-22D  
**Date issued:** 2024-05-31  
**FAA status:** Active  
**Number of pages:** 10  
**Direct PDF:** https://www.faa.gov/documentLibrary/media/Advisory_Circular/AC_121-22D.pdf  
**FAA document page:** https://www.faa.gov/regulations_policies/advisory_circulars/index.cfm/go/document.information/documentID/1042771

### Main topics

- Development and revision of minimum scheduled maintenance tasking/interval requirements.
- Maintenance Review Board Reports (MRBR).
- Maintenance Type Board Reports (MTBR).
- OEM/Type Certificate Holder (TCH) Recommended Maintenance Procedures.
- Regulatory scope and intended use of the AC.
- Roles of FAA personnel, operators/industry, and OEM/TCHs.
- International standards and bilateral validation context.
- Maintenance and inspection requirements for new aircraft.
- General MRB/MTB process.
- Development and approval of operator maintenance programs.
- Deviations from MRB/MTB methods.
- MRBR task validation and verification.
- Instructions for Continued Airworthiness (ICA) validation.
- Candidate Certification Maintenance Requirements (CCMR).
- OEM/TCH recommended maintenance procedures.

### Structure

- Numbered sections and subsections.
- Important sections include:
  - 1 Purpose/Application/Regulatory Scope
  - 2 Audience
  - 3 Where You Can Find This AC
  - 4 What This AC Cancels
  - 5 Related 14 CFR Parts
  - 6 Related Reading Material
  - 7 International Standards
  - 8 Maintenance and Inspection Requirements
  - 9 MRBR Approval
  - 10 Validation and Verification of MRB-Related Maintenance Tasks
  - 11 Candidate Certification Maintenance Requirements
  - 12 Maintenance Review Board Policy Board
  - 14 OEM/TCH Recommended Maintenance Procedures
- Contains extensive numbered lists and technical cross-references.

### Text searchable

**Yes.** The PDF has machine-readable/searchable text.

### Tables

**No formal tables identified in the extracted document.**

### Figures

**No formal figures identified.**

### Potential extraction issues

- Heavy use of acronyms and abbreviations (MRBR, MTBR, MRB, MTB, OEM, TCH, ICA, CCMR, FEC, IMPS, etc.) makes metadata/context preservation important.
- Numbered lists are semantically important and should remain associated with their section heading.
- Cross-references to FAA Orders, ACs, 14 CFR sections, and international documents should be preserved.
- Questions may require combining evidence from separate sections, making this document particularly useful for evaluating multi-hop or synthesis-style retrieval.

---

## 4. AC 43-12A — Preventive Maintenance

**Document number:** AC 43-12A  
**Date issued:** 1983-10-28  
**FAA status:** Active  
**Number of pages in supplied direct PDF:** 4  
**Direct PDF supplied:** https://www.faa.gov/documentLibrary/media/Advisory_Circular/AC43-12A.pdf  
**FAA document page:** https://www.faa.gov/regulations_policies/advisory_circulars/index.cfm/go/document.information/documentID/99859

### Main topics

- Definition and scope of preventive maintenance.
- Who may perform preventive maintenance.
- Limitations on pilot-performed preventive maintenance.
- Applicable performance standards under Part 43.
- Use of manufacturer maintenance manuals and FAA ACs as technical references.
- Required tools, equipment, and test apparatus.
- Recording of preventive maintenance.
- Approval for return to service.
- Specific preventive-maintenance examples and limitations, including:
  - Glider assembly.
  - Balloon basket/burner installation.
  - Oil draining/reservicing.
  - Oil-screen, filter, and strainer servicing.
- Relationship between preventive maintenance and Part 43 Appendix A.

### Structure

- Short numbered advisory circular.
- Main content is concentrated in section 4, "Preventive Maintenance."
- Uses subsections (a)-(g), numbered lists, and references to Part 43 and Appendix A.
- Includes a signature/closing page.

### Text searchable

**Yes, but with an important quality caveat.** The supplied FAA PDF exposes machine-readable text, but the extracted text shows substantial legacy/OCR-style character corruption and encoding errors.

### Tables

**No formal tables identified.**

### Figures

**No formal figures identified.**

### Potential extraction issues

- **This is the highest-risk document in the current corpus for text extraction quality.**
- Extracted text contains OCR/encoding artifacts such as incorrect characters, broken words, and distorted text.
- This document should be used in Week 2 to test whether the ingestion pipeline can reliably extract and normalize older PDF text.
- Because the project initially assumes English, machine-readable technical PDFs, this document is still usable, but the extraction quality should be explicitly benchmarked.

### Version note

The FAA document-information page lists **Change 1 dated 2007-04-18** in addition to the original AC. Before finalizing the corpus, verify whether the project should ingest the original four-page PDF, the "AC 43-12A with Change 1" PDF, or both.

---

## 5. AC 39-7D — Airworthiness Directives

**Document number:** AC 39-7D  
**Date issued:** 2012-03-02  
**FAA status:** Active  
**Number of pages:** 7  
**Direct PDF:** https://www.faa.gov/documentlibrary/media/advisory_circular/ac%2039-7d.pdf  
**FAA document page:** https://www.faa.gov/regulations_policies/advisory_circulars/index.cfm/go/document.information/documentID/1019839

### Main topics

- Owner/operator responsibility for Airworthiness Directive (AD) compliance.
- Recording AD compliance in maintenance records.
- Relationship between ADs and 14 CFR Parts 39, 43, and 91.
- Background and authority for FAA-issued ADs.
- AD categories and issuance processes.
- Applicability statements for products and aircraft.
- Treatment of modified, altered, or repaired products.
- Compliance requirements and compliance times.
- Electronic distribution of ADs.
- Alternative Methods of Compliance (AMOCs).
- Responsibility for AD compliance and recordation.
- Special flight permits related to AD compliance.
- Examples explaining applicability and compliance concepts.

### Structure

- Numbered sections with subsections.
- Uses multiple numbered examples and explanatory paragraphs.
- Contains extensive regulatory references.

### Text searchable

**Yes.** The PDF has machine-readable/searchable text.

### Tables

**No formal tables identified.**

### Figures

**No formal figures identified.**

### Potential extraction issues

- Long regulatory references and section citations should be kept intact.
- Numbered examples and applicability statements should remain associated with their headings.
- Technical abbreviations such as AD, AMOC, PI, ACO, TC, STC, and FRC are important retrieval terms.
- Examples of applicability statements contain aircraft/product names and model identifiers; chunking should preserve enough surrounding context so the applicability relationship is not separated from the example.

---

# Corpus-Level Observations

## Corpus size

| Document | Pages | Primary topic |
|---|---:|---|
| AC 43-9D | 24 | Maintenance records / FAA Form 8130-3 |
| AC 20-77B | 5 | Manufacturers' maintenance manuals |
| AC 121-22D | 10 | Maintenance review boards / scheduled maintenance |
| AC 43-12A | 4 | Preventive maintenance |
| AC 39-7D | 7 | Airworthiness Directives |
| **Total** | **50** | Aviation maintenance / technical guidance |

## Why this corpus is useful for DocuPilot

The five documents have meaningful topical overlap:

- **AC 43-9D** connects maintenance records with preventive maintenance, AD compliance, and manufacturer technical data.
- **AC 20-77B** explains the role and contents of manufacturer maintenance manuals.
- **AC 121-22D** covers development of scheduled maintenance requirements and OEM/TCH procedures.
- **AC 43-12A** focuses specifically on preventive maintenance and recording requirements.
- **AC 39-7D** addresses Airworthiness Directives and their compliance/recordation.

This overlap should allow the evaluation set to include direct retrieval, cross-document comparison, and synthesis questions rather than only simple fact lookup.

## Corpus-level extraction considerations

1. Preserve **document name, AC number, page number, section/subsection, and paragraph number** as metadata where possible.
2. Do not strip regulatory references such as **14 CFR § 43.9**, **14 CFR § 91.417**, etc. They are meaningful retrieval terms.
3. Preserve section headings and numbered/bulleted lists.
4. Treat tables/forms separately from ordinary paragraphs where possible.
5. Test **AC 43-12A** especially carefully because of its OCR/encoding quality.
6. For **AC 43-9D**, test table/form extraction separately because Appendix A, Appendix B, and Table B-1 contain structured information.
7. Keep the original PDFs unchanged in `data/raw/`; perform cleaned text/chunking on derived data in later pipeline stages.

## Recommended document metadata fields for Week 2

Each extracted document/chunk should eventually retain at least:

- `document_id`
- `document_number`
- `document_title`
- `source_url`
- `date_issued`
- `page_number`
- `section`
- `paragraph`
- `chunk_id`
- `text`

## Source Verification

All five source documents and FAA status/date information were checked against FAA sources on 2026-09-24. The direct PDF links and FAA document-information pages are recorded above.
