# Demo Guide

## Recommended 3–5 minute walkthrough

### 1. Start at Home

Open the live demo and briefly explain:

> RoG-उपाttam helps a patient prepare a structured clinical history before meeting a doctor.

Show the large patient-facing controls and bilingual toggle.

### 2. Start the assessment

Select **Start Health Assessment**.

Explain that the flow begins with the patient's main health concern rather than a long generic form.

### 3. Select a concern

Choose one of the predefined concerns, such as fever, headache, abdominal pain, chest pain, or cough/breathing difficulty.

Point out that the next questions are driven by the selected concern.

### 4. Demonstrate multiple input modes

Use one multiple-choice answer, one text answer, and voice input where browser support is available.

The goal is to demonstrate that a patient does not have to rely on typing alone.

### 5. Add a sample medical document

Open document upload and show the supported file flow.

Explain that the current prototype handles the client-side interaction; production OCR and secure storage are future components.

### 6. Show safety screening

Use a supported test scenario that triggers the application's deterministic red-flag logic.

Explain that the prototype surfaces urgent guidance rather than claiming to diagnose the patient.

### 7. Open Clinical Summary

Show the structured summary.

Point out how symptoms, history, answers and relevant information are organized for a clinician.

### 8. Show Physician Review

Open the physician review stage and explain:

> The system prepares information. The clinician remains responsible for verification and clinical decisions.

---

## Good technical talking points

If asked "Is this AI?":

> The current prototype contains lightweight rule-based NLP and deterministic safety logic. A production version can add validated ASR, OCR, clinical NLP and AI-assisted summarization behind secured backend services.

If asked "Where is the backend?":

> This submission is the frontend workflow prototype. The repository documents a planned FastAPI backend, secure data layer and hospital integration architecture separately from the current implementation.

If asked "Does it diagnose diseases?":

> No. It organizes patient-reported information and surfaces predefined safety guidance. Diagnosis and treatment stay with the physician.

If asked "What happens after deployment?":

> The next stage is authenticated backend services, secure document storage, clinical NLP/OCR, physician dashboarding and standards-based HIS/EMR/ABDM/FHIR integration.
