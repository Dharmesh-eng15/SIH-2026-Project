# Technical Architecture

## Current repository

RoG-उपाttam is currently implemented as a static frontend prototype.

```text
index.html
   │
   ├── style.css
   │
   └── script.js
          │
          ├── UI rendering
          ├── application state
          ├── question bank
          ├── voice interaction
          ├── document handling
          ├── lightweight NLP
          ├── red-flag rules
          ├── summary generation
          ├── AYUSH flow
          └── physician review
```

## Main data flow

```text
Patient details
      ↓
Concern selection
      ↓
Question / answer state
      ↓
Optional voice or text analysis
      ↓
Medical document metadata
      ↓
Safety rules
      ↓
Summary object
      ↓
Physician review
```

## State model

The application maintains an in-memory state object containing areas such as:

- patient details
- selected health concern
- current question
- patient answers
- uploaded document metadata
- generated summary
- urgent flag
- AYUSH answers
- physician verification/review state
- accessibility preferences

Because state is in memory, refreshing the page resets the prototype. A production system would move persistence into authenticated backend services and a secure database/document store.

## Voice

The browser `SpeechRecognition` / `webkitSpeechRecognition` interfaces are used when available. The application uses language-specific settings such as English and Hindi variants and provides text/touch fallback when voice is unavailable.

## NLP

The current text analyzer is a transparent rule-based extractor. It normalizes text and searches predefined terminology for:

- symptoms
- severity
- approximate duration
- simple symptom relationships

It is deliberately documented as a prototype rather than as a medical-grade NLP model.

## Safety rules

Red-flag handling is deterministic. Patient responses are evaluated against predefined high-risk combinations. A match routes the interface to urgent guidance rather than attempting an autonomous diagnosis.

## Production architecture

A future implementation can separate concerns into:

```text
Web / Mobile Frontend
        ↓
API Gateway / FastAPI
        ↓
Authentication + Authorization
        ↓
Clinical Workflow Service
   ├── Question Service
   ├── Document Service
   ├── NLP / AI Service
   ├── Safety Rule Service
   └── Summary Service
        ↓
Secure Data Layer
   ├── Relational database
   ├── Document/object storage
   └── Audit logs
        ↓
Hospital integration layer
   ├── HIS
   ├── EMR
   ├── ABDM
   └── FHIR
```
