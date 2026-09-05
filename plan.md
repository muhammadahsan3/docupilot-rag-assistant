# DocuPilot — Project Plan

## 1. Problem Definition

### Target User

The primary users of DocuPilot are aircraft maintenance engineers, aviation technical staff, and maintenance personnel who regularly work with aircraft maintenance, inspection, airworthiness, safety, and technical guidance documents.

### Current Pain Point

Aviation technical teams often need to locate specific information across large collections of technical PDFs. Manually searching documents is time-consuming, and traditional keyword search can fail when the terminology used in a user's question differs from the wording used in the source document. This makes it difficult to quickly locate relevant information and verify the supporting source.

### Proposed Solution

DocuPilot is an AI-powered Retrieval-Augmented Generation (RAG) assistant for technical aviation documents. Users can ask questions in natural language, while the system retrieves relevant passages from the document collection and provides them as evidence to an LLM. The LLM then generates a concise answer grounded in the retrieved content and provides citations identifying the supporting document and page.

### Definition of Success

The initial version of DocuPilot will be considered successful when:

1. A user can ask a technical question in natural language and receive a relevant, grounded answer in under 5 seconds for a single-document lookup under the target deployment conditions.
2. The answer is supported by evidence contained in the retrieved documents.
3. Each citation correctly identifies the document and page containing the supporting information.
4. When the required information is not present in the document collection, the system clearly states that it cannot find sufficient evidence rather than generating an unsupported answer.

### Out of Scope for v1

- Scanned or image-only PDFs requiring OCR.
- Non-English documents.
- Real-time aircraft maintenance decision-making or automated maintenance recommendations.
- Information outside the indexed document collection.