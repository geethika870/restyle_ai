# restyle_ai
ReStyle AI is an intelligent, multimodal personal styling platform that acts like a trusted fashion-expert friend who understands you, your wardrobe, your preferences, your occasion, and current trends before making recommendations.
# ReStyle AI

> **Use what you own. Discover what works for you. Know what to look for next.**

ReStyle AI is an **explainable multimodal personal styling platform** that acts like a fashion-expert friend who understands the user, their existing wardrobe, their preferences, their occasion, and relevant trend signals before making recommendations.

Instead of giving generic outfit suggestions, ReStyle is designed around two core experiences:

1. **Manage My Wardrobe** — Create personalized outfits from clothes the user already owns.
2. **Find Something** — Recommend what colors, silhouettes, garment types, and style directions the user should consider when they need something new.

---

## Why ReStyle?

Most people face two common problems:

### “I have clothes, but I don’t know what to wear.”

People often forget what they own, repeatedly wear the same combinations, physically search through their wardrobe, or struggle to mix and match existing pieces.

### “I need something new, but I don’t know what to look for.”

Shopping platforms typically optimize for product discovery and popularity. They do not necessarily understand whether a color complements a user’s confirmed profile, whether a silhouette aligns with the user’s styling goals, whether a trend matches their preferences, or whether the user already owns something similar.

ReStyle aims to bridge this gap through **wardrobe intelligence + personal style intelligence**.

---

# Core Experiences

## 1. Manage My Wardrobe

**Manage My Wardrobe** transforms a user’s physical wardrobe into an intelligent, searchable digital wardrobe.

Users upload images of clothing, footwear, and accessories they already own. ReStyle processes and organizes these items using AI-assisted visual understanding.

### Wardrobe Understanding

For each uploaded item, the system can identify or store attributes such as:

* garment category
* garment type
* dominant colors
* secondary colors
* pattern
* style
* formality
* season suitability
* occasion suitability

Example:

```json
{
  "category": "TOP",
  "subcategory": "SHIRT",
  "primaryColor": "NAVY",
  "secondaryColors": ["WHITE"],
  "pattern": "STRIPED",
  "style": ["MINIMAL", "SMART_CASUAL"],
  "formality": "MEDIUM",
  "occasions": ["OFFICE", "CASUAL"]
}
```

### Ask Your Wardrobe

Instead of manually searching through clothes, users can ask:

> “What should I wear to the office tomorrow?”

> “Create a party outfit using my black skirt.”

> “Show me interview outfits from clothes I already own.”

> “I want something casual but polished.”

> “What can I wear with these trousers?”

ReStyle interprets the request, retrieves relevant wardrobe items, generates compatible outfit candidates, ranks them, and explains why the strongest combinations work.

### Recommendation Pipeline

```text
User Request
    ↓
Intent & Context Extraction
    ↓
Wardrobe Retrieval
    ↓
Constraint Filtering
    ↓
Outfit Candidate Generation
    ↓
Color Compatibility Analysis
    ↓
Personal Preference Matching
    ↓
Occasion Relevance Scoring
    ↓
Personalized Ranking
    ↓
Top-K Outfit Recommendations
    ↓
Human-Readable Explanation
```

### Example

**User request:**

> “I have an interview tomorrow. I want to look professional but not overdressed.”

**ReStyle recommendation:**

```text
OUTFIT 1 — MATCH SCORE: 94%

White Shirt
    +
Navy Trousers
    +
Beige Blazer
    +
Black Loafers

Why this works:

✓ Interview relevance
✓ Strong color compatibility
✓ Matches confirmed style preferences
✓ Uses only existing wardrobe items
```

### Wardrobe Rediscovery

ReStyle is also designed to identify:

* forgotten items
* underused clothes
* repeated outfit patterns
* pieces with high mix-and-match potential
* new combinations from existing items

The goal is simple:

> **Before buying more, discover more possibilities in what you already own.**

---

## 2. Find Something

**Find Something** helps users understand what they should look for when they genuinely need something new.

Instead of immediately displaying thousands of products, ReStyle first analyzes the user’s context.

Users can ask:

> “I have a party next week. What should I look for?”

> “I need an interview outfit.”

> “What colors should I consider for a wedding?”

> “I want something trendy but still aligned with my style.”

### Personalization Signals

Depending on user consent and available data, recommendations may combine:

* user-provided photos
* editable color profile
* explicit color-theory relationships
* personal style preferences
* user-confirmed styling goals
* optional body-proportion features
* occasion
* contextual requirements
* relevant trend signals
* previous likes and dislikes

### Example

**User request:**

> “I need something for a party.”

**ReStyle may recommend:**

```text
COLOR DIRECTION

Deep Teal
Emerald
Midnight Blue

SILHOUETTE DIRECTION

Structured
Defined Waist
Clean Vertical Lines

STYLE DIRECTION

Modern
Minimal
Statement Accent

WHY?

✓ Strong color-profile compatibility
✓ Matches selected styling goals
✓ Appropriate for party context
✓ Relevant to personalized trend signals
```

The goal is not to tell users what they “must” wear.

The goal is to provide **transparent, editable, explainable guidance**.

---

# StyleDNA

ReStyle maintains an editable personalization profile called **StyleDNA**.

StyleDNA can represent:

* color preferences
* contrast preferences
* preferred styles
* disliked styles
* silhouette preferences
* occasion patterns
* explicit styling goals
* recommendation feedback

Example:

```json
{
  "colorProfile": {
    "preferredContrast": "MEDIUM_HIGH",
    "preferredColors": [
      "DEEP_TEAL",
      "NAVY",
      "BURGUNDY"
    ]
  },
  "stylePreferences": [
    "MINIMAL",
    "STRUCTURED",
    "SMART_CASUAL"
  ],
  "stylingGoals": [
    "VISUAL_BALANCE"
  ],
  "feedbackProfile": {
    "learnFromLikes": true,
    "learnFromDislikes": true
  }
}
```

Any automatically estimated attribute should be visible and correctable by the user.

---

# Explainable Color Intelligence

ReStyle is designed to avoid treating an LLM as a color-theory engine.

The color pipeline can use explicit image processing and perceptual color calculations.

```text
User-Provided Image
    ↓
Image Quality Validation
    ↓
Lighting Normalization
    ↓
Relevant Region Processing
    ↓
Color Sampling
    ↓
RGB → CIELAB / HSV
    ↓
Perceptual Color Analysis
    ↓
Color Harmony Rules
    ↓
Personalized Compatibility Ranking
```

Potential techniques include:

* CIELAB color representation
* perceptual color difference
* ΔE-based comparison
* complementary relationships
* analogous relationships
* triadic relationships
* split-complementary relationships
* contrast compatibility
* user preference weighting

Conceptual scoring:

```text
ColorScore =
    w1 × HarmonyCompatibility
  + w2 × ContrastCompatibility
  + w3 × UserPreference
  + w4 × OccasionRelevance
```

This makes color recommendations more transparent and testable.

---

# Body-Proportion-Aware Styling

ReStyle does not treat body shape as an objective measure of attractiveness or prescribe what a person must wear.

Instead, optional visual features can support **user-selected styling goals**.

Example:

```text
User-selected goal:
"Create more visual balance"

Optional confirmed observation:
"Shoulder region appears visually broader than hip region"

Possible style directions:
- softer shoulder construction
- lower-body volume
- A-line silhouettes
- straight or wide-leg trousers
```

Important principles:

* visual estimates are optional
* users can correct them
* recommendations are explainable
* styling goals are user-controlled
* subjective fashion heuristics are not presented as universal truths

---

# Trend Intelligence

ReStyle aims to answer:

> **“Which trends are relevant to this specific user?”**

rather than simply:

> “What is globally popular?”

Potential pipeline:

```text
Compliant Trend Sources
    ↓
Scheduled Data Ingestion
    ↓
Content Normalization
    ↓
Text / Image Representation
    ↓
Semantic Grouping
    ↓
Temporal Signal Analysis
    ↓
Emerging Trend Detection
    ↓
StyleDNA Compatibility
    ↓
Personalized Trend Ranking
```

Conceptual trend scoring:

```text
TrendScore =
    w1 × GrowthVelocity
  + w2 × Recency
  + w3 × SourceDiversity
  + w4 × EngagementSignal
  + w5 × Persistence
```

Personalized reranking:

```text
PersonalTrendScore =
    α × TrendScore
  + β × StyleDNACompatibility
  + γ × ColorCompatibility
  + δ × UserPreference
```

Trend data should come from authorized, public, licensed, or otherwise compliant sources.

---

# Hybrid Recommendation Engine

The recommendation engine is the technical core of ReStyle.

A simple implementation might directly ask an LLM:

```text
Prompt → LLM → Outfit
```

ReStyle instead aims for a multi-stage architecture:

```text
User Request
    ↓
Structured Intent Extraction
    ↓
Hard Constraint Filtering
    ↓
Semantic Candidate Retrieval
    ↓
Candidate Outfit Generation
    ↓
Color Compatibility
    ↓
StyleDNA Compatibility
    ↓
Occasion Relevance
    ↓
Trend Relevance
    ↓
Wardrobe Availability
    ↓
Multi-Objective Ranking
    ↓
Top-K Results
    ↓
Explanation Layer
```

Conceptual ranking:

```text
FinalScore =
    w1 × ColorCompatibility
  + w2 × PreferenceMatch
  + w3 × StylingGoalMatch
  + w4 × OccasionRelevance
  + w5 × TrendRelevance
  + w6 × WardrobeCompatibility
```

The ranking system can evolve incrementally:

```text
V1 — Rule-Based Recommendation
        ↓
V2 — Weighted Hybrid Ranking
        ↓
V3 — Embedding-Assisted Retrieval
        ↓
V4 — Feedback-Aware Personalization
        ↓
V5 — Learning-to-Rank
```

---

# Planned Architecture

```text
                        ┌──────────────────────┐
                        │ React + TypeScript   │
                        │ Frontend             │
                        └──────────┬───────────┘
                                   │
                                   ▼
                        ┌──────────────────────┐
                        │ Spring Boot Core API │
                        │                      │
                        │ Auth                 │
                        │ Users                │
                        │ StyleDNA             │
                        │ Wardrobe             │
                        │ Recommendations      │
                        │ Feedback             │
                        └──────────┬───────────┘
                                   │
                  ┌────────────────┴────────────────┐
                  │                                 │
                  ▼                                 ▼
        ┌──────────────────────┐          ┌──────────────────────┐
        │ PostgreSQL           │          │ FastAPI AI Service   │
        │                      │          │                      │
        │ Users                │          │ Vision Processing    │
        │ Wardrobe Metadata    │          │ Color Analysis       │
        │ Preferences          │          │ Embeddings           │
        │ Recommendations      │          │ Feature Extraction   │
        │ Feedback             │          │ Model Inference      │
        └──────────┬───────────┘          └──────────┬───────────┘
                   │                                 │
                   ▼                                 ▼
        ┌──────────────────────┐          ┌──────────────────────┐
        │ pgvector             │          │ AI / CV Models       │
        │ Semantic Retrieval   │          │                      │
        └──────────────────────┘          └──────────────────────┘

                  ┌──────────────────────┐
                  │ Redis                │
                  │ Cache                │
                  │ Rate Limiting        │
                  │ Short-Lived State    │
                  └──────────────────────┘

                  ┌──────────────────────┐
                  │ Object Storage       │
                  │ User Images          │
                  │ Wardrobe Images      │
                  └──────────────────────┘
```

The initial architectural strategy is a **modular Spring Boot core application with a separate Python AI inference service**, avoiding unnecessary microservice complexity.

---

# Proposed Tech Stack

## Frontend

* React
* TypeScript
* Tailwind CSS
* TanStack Query

## Core Backend

* Java 21
* Spring Boot
* Spring Security
* Spring Data JPA
* Hibernate
* REST APIs

## AI Service

* Python
* FastAPI
* PyTorch
* OpenCV
* scikit-learn

## AI / Recommendation Concepts

* Computer Vision
* Multimodal Embeddings
* Semantic Retrieval
* Vector Search
* Hybrid Recommendation
* Personalized Ranking
* Explainable AI
* Human-in-the-Loop Feedback

## Data Layer

* PostgreSQL
* pgvector
* Redis

## Infrastructure

* Docker
* Docker Compose
* GitHub Actions
* AWS

## Testing

* JUnit 5
* Mockito
* Testcontainers
* Pytest
* React Testing Library

## API Documentation

* OpenAPI
* Swagger

---

# Project Structure

```text
restyle-ai/
│
├── frontend/
│   ├── src/
│   ├── public/
│   └── README.md
│
├── backend/
│   ├── src/
│   ├── pom.xml
│   └── README.md
│
├── ai-service/
│   ├── app/
│   ├── tests/
│   ├── requirements.txt
│   └── README.md
│
├── docs/
│   ├── product-requirements.md
│   ├── architecture.md
│   ├── database-schema.md
│   ├── api-contracts.md
│   └── recommendation-design.md
│
├── infrastructure/
│   ├── docker/
│   └── compose/
│
├── .github/
│   └── workflows/
│
├── docker-compose.yml
├── .gitignore
├── LICENSE
└── README.md
```

---

# Development Roadmap

## Phase 1 — Foundation

* [ ] Define product requirements
* [ ] Finalize V1 scope
* [ ] Design database schema
* [ ] Define API contracts
* [ ] Set up repository structure
* [ ] Configure local development environment
* [ ] Add CI checks

## Phase 2 — Manage My Wardrobe MVP

* [ ] User authentication
* [ ] Wardrobe image upload
* [ ] Object storage integration
* [ ] Clothing item metadata
* [ ] Category filtering
* [ ] AI-assisted garment tagging
* [ ] Wardrobe search
* [ ] Occasion-based outfit generation
* [ ] Explainable recommendation ranking

## Phase 3 — Find Something MVP

* [ ] User photo upload
* [ ] Image quality validation
* [ ] Editable StyleDNA profile
* [ ] Color feature extraction
* [ ] Color compatibility engine
* [ ] Occasion-specific recommendations
* [ ] User-controlled styling goals
* [ ] Explainable recommendation results

## Phase 4 — Intelligent Retrieval

* [ ] Garment embeddings
* [ ] pgvector integration
* [ ] Semantic wardrobe search
* [ ] Natural-language wardrobe queries
* [ ] Candidate retrieval
* [ ] Hybrid reranking

## Phase 5 — Personalization

* [ ] Like/dislike feedback
* [ ] Recommendation history
* [ ] Preference adaptation
* [ ] Underused-item discovery
* [ ] Outfit diversity controls

## Phase 6 — Trend Intelligence

* [ ] Compliant trend-source ingestion
* [ ] Scheduled processing
* [ ] Trend representation
* [ ] Semantic grouping
* [ ] Temporal trend scoring
* [ ] Personalized trend reranking

## Phase 7 — Production Engineering

* [ ] Redis caching
* [ ] Rate limiting
* [ ] Background jobs
* [ ] Structured logging
* [ ] Metrics
* [ ] Health checks
* [ ] Dockerized deployment
* [ ] CI/CD
* [ ] Cloud deployment
* [ ] Performance testing

---

# Evaluation Strategy

ReStyle should evaluate recommendation quality rather than relying only on visually appealing demos.

Potential metrics:

### Retrieval

* Precision@K
* Recall@K
* NDCG@K

### Recommendation

* recommendation acceptance rate
* save rate
* like/dislike ratio
* diversity
* coverage
* repeated-item frequency

### System Performance

* API latency
* inference latency
* retrieval latency
* cache hit rate
* error rate

### Experimentation

Potential comparisons:

```text
Rule-Based Ranking
        vs
Weighted Hybrid Ranking
        vs
Embedding-Assisted Retrieval
        vs
Feedback-Aware Personalization
```

---

# Privacy and Responsible Design

ReStyle processes potentially sensitive user-provided images and should be designed with privacy as a core requirement.

Planned principles:

* explicit user consent for image analysis
* clear explanation of analyzed attributes
* user correction of automatically estimated attributes
* no attractiveness scoring
* no sensitive-trait inference
* no deterministic claims about what users “must” wear
* user-controlled styling goals
* secure image storage
* image deletion controls
* minimal data retention
* transparent recommendation explanations

---

# Current Status

> **Status: In Development**

The project is being developed incrementally. Features listed in the roadmap are planned and should not be interpreted as completed unless explicitly marked as implemented.

---

# Product Philosophy

> **Use what you own.**

> **Understand what works for your goals.**

> **Know what to look for next.**

---

# Author

**Geethika Reddy**

2026 Information Technology Graduate
Former Technical Support Engineer Intern — ServiceNow

---

# License

This project is currently intended for educational, portfolio, and research-oriented development.

License details will be finalized as the project evolves.
