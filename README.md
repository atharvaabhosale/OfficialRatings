# 🇮🇳 Rating App

> **A civic accountability platform for rating the work of elected representatives.**

Rating App is a long-term civic-tech project designed to help citizens discover elected representatives and share structured feedback about their work.

The initial version is intentionally simple:

> **Find a representative → view their profile → rate their work.**

The platform will gradually evolve into a broader accountability system covering promises, delivery, projects, outcomes, citizen issues, evidence, and representative responses.

---

# 🎯 Project Vision

The long-term vision is to create a neutral, evidence-oriented platform where citizens can:

- Discover their elected representatives
- Understand who represents them
- Rate their representative's work
- See how public ratings change over time
- Track promises versus delivery
- Understand projects and outcomes
- Report public issues
- See representative responses
- Explore evidence and official sources
- Eventually use AI to understand public records

The platform should help citizens **understand public representatives and their documented work**, rather than becoming a political campaign platform.

### Core philosophy

> **Know the representative.  
> Understand the work.  
> Track the promises.  
> See the evidence.  
> Have your say.**

---

# ⚠️ IMPORTANT: PROJECT PRINCIPLES

All agents working on this project MUST understand these principles.

## 1. Political neutrality

Rating App must remain politically neutral.

The application must NOT:

- Promote a political party
- Attack a political party
- Recommend who users should vote for
- Declare a politician "good" or "bad"
- Create political propaganda
- Manipulate users toward a political choice
- Automatically rank politicians as "best" or "worst"

The platform provides information and citizen feedback.

It does not make political decisions for users.

---

## 2. Facts and opinions must remain separate

The system should distinguish between:

### VERIFIED FACT

Information supported by an authoritative source.

Example:

> Lok Sabha member for constituency X.

### CLAIM

A statement made by a politician, organization, citizen, or other source.

### CITIZEN OPINION

A user's personal assessment or rating.

Never present a citizen opinion as an established fact.

---

# 🚀 DEVELOPMENT ROADMAP

The project will be developed incrementally.

Agents MUST NOT implement future versions unless explicitly instructed.

---

## V1 — Basic Representative Ratings ⭐

### Goal

Build the simplest useful version of Rating App.

V1 should provide:

- Mobile OTP authentication
- Representative database
- Representative search
- Representative filtering
- Representative profiles
- 1–5 star ratings
- Optional rating comment
- Rating aggregation
- Rating history foundation

### V1 user flow

```text
User
  ↓
Mobile OTP Login
  ↓
Home
  ↓
Search / Browse Representatives
  ↓
Representative Profile
  ↓
Rate Representative
  ↓
Submit Rating
  ↓
Rating reflected in profile
```

### V1 does NOT include

Do NOT implement these unless explicitly requested:

- Aadhaar authentication
- Promise tracking
- Delivery tracking
- Project tracking
- Outcome analysis
- Citizen issue reporting
- AI research assistant
- Complex evidence engine
- Representative response system
- Election prediction
- Political advertising
- Advanced political rankings

Keep V1 focused.

---

# 🔐 V1 AUTHENTICATION

## Mobile OTP

V1 should use:

> **Mobile Number + OTP**

Basic flow:

```text
Enter mobile number
        ↓
Send OTP
        ↓
Verify OTP
        ↓
Create / access account
        ↓
User can rate
```

### Important

A mobile number is NOT equivalent to a uniquely verified Indian citizen.

Therefore the product should NOT claim:

> "One Indian citizen = one vote."

Instead:

> **One verified account can submit one active rating per representative.**

The system should prevent the same account from repeatedly creating multiple active ratings for the same representative.

---

# 🚫 DO NOT USE AADHAAR IN V1

Do not implement:

```text
Aadhaar number
       ↓
Rating App database
```

Do not store Aadhaar numbers.

Do not build custom Aadhaar verification.

If stronger identity verification becomes necessary in a future version, it must be designed with appropriate legal/privacy review and a compliant identity-verification provider.

V1 does not need it.

---

# ⭐ V1 RATING SYSTEM

The initial rating system should remain simple.

## Overall rating

Users give:

```text
1 ⭐
2 ⭐
3 ⭐
4 ⭐
5 ⭐
```

Example:

```text
How would you rate this representative's work?

☆ ☆ ☆ ☆ ☆
```

Optional:

```text
What influenced your rating?
[ Text ]
```

---

# Important Rating Rules

A user can have:

```text
ONE ACTIVE RATING
        ↓
PER REPRESENTATIVE
```

Example:

```text
User A
 ├── Representative X → 4 ⭐
 ├── Representative Y → 2 ⭐
 └── Representative Z → 5 ⭐
```

The same user cannot create:

```text
Representative X
→ 4 ⭐
→ 5 ⭐
→ 3 ⭐
```

as three simultaneous ratings.

Instead, the user can UPDATE their existing rating.

---

# 🔄 RATING HISTORY

The data model should support future rating periods.

Do not design the database as if a rating is permanent.

Future structure:

```text
Representative
       │
       ├── 2026 Rating
       ├── 2027 Rating
       ├── 2028 Rating
       └── ...
```

This allows citizens to update their assessment over time.

V1 may display only the current rating, but the database should not prevent historical ratings.

---

# 👤 REPRESENTATIVE DATABASE

Rating App needs a structured representative database.

The database should NOT simply contain:

```text
name
rating
```

Use a scalable structure.

Example:

```text
Representative
├── id
├── name
├── photo
├── party
├── position
├── level
├── state
├── district
├── constituency
├── term_start
├── term_end
├── status
├── wikidata_id
├── wikipedia_url
├── source
└── last_verified
```

The exact schema can evolve with implementation.

---

# 🏛️ REPRESENTATIVE LEVELS

The long-term system should support multiple levels.

## National

- President
- Vice President
- Prime Minister
- Union Ministers
- Lok Sabha MPs
- Rajya Sabha MPs

## State

- Chief Ministers
- State Ministers
- MLAs
- MLCs

## Local

Future support:

- Municipal representatives
- Municipal councillors
- Zilla Parishad
- Panchayat Samiti
- Gram Panchayat representatives
- Other elected local representatives

---

# 🚦 V1 DATA SCOPE

Do NOT attempt to solve every elected representative in India before launching V1.

Recommended initial coverage:

```text
V1
│
├── President
├── Prime Minister
├── Union Ministers
├── Lok Sabha MPs
└── Rajya Sabha MPs
```

Future expansion:

```text
V1.5
└── State representatives

V2+
└── Local representatives
```

The database architecture must be capable of expanding without major restructuring.

---

# 🔎 REPRESENTATIVE DISCOVERY

Because the platform will eventually contain a large number of representatives, search and filtering are core features.

Users should be able to find representatives using:

### Search

Search by:

- Name
- Constituency
- Party
- Location

Example:

```text
Search:
"Nitin Gadkari"
```

---

# 🎛️ FILTERING

The Representative Explorer should eventually support:

### Level

- National
- State
- Local

### Position

- President
- Vice President
- Prime Minister
- Union Minister
- MP
- Chief Minister
- State Minister
- MLA
- MLC
- Municipal Representative
- Other elected positions

### State

Example:

```text
Maharashtra
```

### District

Example:

```text
Pune
```

### Constituency

Example:

```text
Nagpur
```

### Party

Example:

```text
BJP
INC
NCP
...
```

### Status

- Current
- Former

---

# 📍 FUTURE: "WHO REPRESENTS ME?"

A major future feature should be location-based representative discovery.

Example:

```text
India
  ↓
Maharashtra
  ↓
Pune
  ↓
Constituency
  ↓
Representative
```

Eventually:

> **Who represents me?**

could become one of the primary entry points into the application.

---

# 🗂️ POLITICIAN DATA SOURCES

Do NOT manually enter thousands of politicians.

The system should use structured data sources.

Recommended source hierarchy:

## Tier 1 — Official sources

Prefer:

- Election Commission of India
- Digital Sansad
- State legislative assembly/legislative council websites
- Government departments
- Official election records

These should be preferred for current political office information.

---

## Tier 2 — Wikidata

Wikidata is useful for structured identity and relationships.

Useful fields can include:

- Person identity
- Political position
- Party
- Country
- Constituency
- Dates
- External identifiers

Use stable IDs such as Wikidata IDs wherever possible.

---

## Tier 3 — EveryPolitician

EveryPolitician is a useful source/reference for structured political data.

Important:

The original EveryPolitician project/data should NOT automatically be assumed to contain current information.

Its datasets can be used as an initial/reference dataset, but current information should be verified against more authoritative or current sources.

---

## Tier 4 — Wikipedia

Wikipedia can be useful for:

- Biography
- Photos
- Background information
- Discovering political offices
- External references

However:

> **Wikipedia should not automatically be treated as the authoritative source for current office status.**

Use official sources for important current facts wherever possible.

---

# 🔄 DATA INGESTION ARCHITECTURE

Do not scrape external websites every time a user opens a page.

Use an ingestion pipeline.

```text
External Sources
      │
      ├── ECI
      ├── Digital Sansad
      ├── Wikidata
      ├── EveryPolitician
      └── Wikipedia
             │
             ▼
       Data Importer
             │
             ▼
       Data Normalizer
             │
             ▼
        Validation
             │
             ▼
      Representative DB
             │
             ▼
          FastAPI
             │
             ▼
         Frontend
```

This makes the application faster, more reliable and easier to maintain.

---

# 🧹 DATA NORMALIZATION

Different sources may represent the same person differently.

Example:

```text
N. Modi
Narendra Modi
Shri Narendra Damodardas Modi
```

The system should recognize that these can refer to the same individual.

Use stable identifiers where possible:

```text
wikidata_id
official_id
constituency_id
```

Do not rely only on names for identity matching.

---

# 📅 TERMS MUST BE FIRST-CLASS DATA

Political representatives can change over time.

Do NOT overwrite the previous representative record.

Example:

```text
Constituency X

2024–2029
Representative A

2029–2034
Representative B
```

The platform should preserve historical terms.

This will become essential when V2 introduces delivery and outcomes.

---

# 🏗️ FUTURE ROADMAP

## V1 — Rating ⭐

```text
Mobile OTP
      ↓
Representative discovery
      ↓
Profile
      ↓
Rating
```

---

## V2 — Promises vs Delivery 📋

Track:

```text
Promise
   ↓
Action
   ↓
Delivery
   ↓
Current status
```

Example:

```text
Promise:
Build a hospital

Promised:
2024

Target:
2027

Current status:
In Progress
```

Important:

Do not automatically label an incomplete promise as "failure."

Possible reasons may include:

- Funding
- Legal proceedings
- Land acquisition
- Administrative responsibility
- Environmental clearance
- Change in government
- Other documented circumstances

The platform should present evidence and status rather than automatically deciding intent or blame.

---

# V3 — Work vs Outcome 🏗️

Distinguish:

> Announcement ≠ Delivery ≠ Outcome

Example:

```text
Project announced
       ↓
Budget allocated
       ↓
Tender
       ↓
Construction
       ↓
Completion
       ↓
Actual outcome
```

This will make the platform significantly more useful than a basic rating website.

---

# V4 — Citizen Issues 🚨

Users can report public issues.

Example:

```text
Issue
├── Category
├── Location
├── Description
├── Photo
├── Date
└── Status
```

Possible categories:

- Roads
- Water
- Electricity
- Healthcare
- Education
- Transport
- Sanitation
- Public infrastructure
- Other

This should be introduced only after the basic rating system is stable.

---

# V5 — Representative Response 💬

Representatives can eventually have verified official profiles and respond to issues.

```text
Citizen Issue
      ↓
Representative
      ↓
Official Response
      ↓
Supporting Document
      ↓
Status Update
```

The platform should allow the representative to explain or dispute claims.

---

# V6 — Evidence Layer 📚

Every important factual claim should eventually be traceable.

Example:

```text
CLAIM

₹20 crore project announced

Source:
Government document

Published:
12 June 2026

Status:
Verified
```

The system should distinguish:

```text
FACT
CLAIM
OPINION
```

---

# V7 — AI Civic Assistant 🤖

AI should help users understand information.

Example:

> "What work has this representative done regarding education?"

The AI should retrieve documented information and provide sources.

It should NOT answer:

> "Is this politician good?"

with an independent political judgment.

The AI's job is:

> **Explain the available evidence.**

Not:

> **Tell citizens what political conclusion to reach.**

---

# 🛡️ MODERATION & SAFETY

Political platforms require strong moderation.

Users must not be allowed to freely publish unsupported allegations such as:

> "Politician X stole ₹500 crore."

without evidence.

The platform should eventually distinguish:

```text
Opinion
    ↓
Can generally be expressed as opinion

Factual allegation
    ↓
May require evidence/moderation

Threat / abuse / harassment
    ↓
Reject
```

Do not allow the rating system to become a political abuse platform.

---

# ⚖️ LEGAL / PRIVACY PRINCIPLES

This project is intended as a civic-information and public-feedback platform.

Before production launch, obtain appropriate Indian legal/privacy review for:

- Data protection
- User-generated content
- Defamation
- Identity verification
- Political advertising
- Election-period rules
- Privacy
- Data retention
- User rights
- Content moderation

### Important

Do not implement Aadhaar authentication simply because it seems like a convenient way to enforce uniqueness.

V1 uses:

> **Mobile OTP**

and stores only the information necessary for the application.

---

# 🏛️ POLITICAL NEUTRALITY

The platform must never:

- Tell users who to vote for
- Predict election winners
- Promote a political party
- Attack a political party
- Manipulate rating results
- Hide ratings because of political preference
- Artificially boost ratings
- Create "best politician" recommendations

The system should present data transparently.

Example:

```text
Representative A
4.2 ⭐
12,421 ratings
```

is acceptable.

But:

```text
BEST POLITICIAN IN INDIA
🏆 Representative A
```

should NOT be generated by the platform as an independent political judgment.

---

# 🧱 RECOMMENDED V1 ARCHITECTURE

The initial architecture should remain simple.

```text
                  RATING APP V1

                     Frontend
                        │
              HTML / Tailwind / JS
                        │
                        ▼
                     FastAPI
                        │
            ┌───────────┼───────────┐
            │           │           │
            ▼           ▼           ▼
          Users    Representatives Ratings
            │           │           │
            └───────────┼───────────┘
                        │
                        ▼
                     MongoDB
```

Data ingestion:

```text
Official / Open Sources
          │
          ▼
     Data Importer
          │
          ▼
   Representative DB
```

---

# 🗃️ CORE V1 ENTITIES

## User

```text
User
├── id
├── mobile
├── mobile_verified
└── created_at
```

Avoid unnecessary personal data.

---

## Representative

```text
Representative
├── id
├── name
├── photo
├── party
├── position
├── level
├── state
├── district
├── constituency
├── status
├── term_start
├── term_end
├── wikidata_id
├── wikipedia_url
├── source
└── last_verified
```

---

## Rating

```text
Rating
├── id
├── user_id
├── representative_id
├── rating
├── comment
├── created_at
└── updated_at
```

A unique constraint should ensure:

```text
user_id + representative_id
```

cannot create multiple active ratings.

---

# 🎨 DESIGN DIRECTION

The application should NOT look like:

- A government portal
- A generic college project
- An old political website
- A news website
- A social-media clone

The UI should feel like a modern technology product.

### Desired characteristics

- Clean
- Modern
- Trustworthy
- Minimal
- Fast
- Responsive
- Data-oriented
- Accessible
- Neutral

Possible visual inspiration:

- Linear
- Vercel
- Notion
- Modern civic-tech platforms
- Premium SaaS dashboards

Political neutrality should also be reflected visually.

Avoid making the entire application look like a political party campaign.

---

# 🧠 AGENT DEVELOPMENT RULES

Any coding agent working on this project MUST follow these rules.

## Rule 1

**Do not expand the scope without instruction.**

If the task is V1 ratings, do not build:

- AI
- Promise tracking
- Issue reporting
- Evidence engine
- Election analytics

---

## Rule 2

**Do not rewrite the entire application unnecessarily.**

Preserve existing:

- Architecture
- API contracts
- Database structure
- Components
- Working functionality

unless a change is explicitly required.

---

## Rule 3

**Build reusable components.**

Examples:

```text
RepresentativeCard
RepresentativeFilters
RatingStars
RatingDialog
SearchBar
Navbar
Pagination
EmptyState
LoadingState
```

Do not duplicate the same UI logic across pages.

---

## Rule 4

**Separate frontend and backend responsibilities.**

Frontend:

```text
UI
State
Interactions
API calls
```

Backend:

```text
Authentication
Validation
Business logic
Rating rules
Database
Aggregation
```

---

## Rule 5

**Do not trust client-side rating validation.**

The backend must enforce:

```text
One active rating
per user
per representative
```

Client-side validation is only for UX.

---

## Rule 6

**Never store sensitive identity information unnecessarily.**

Especially:

- Aadhaar numbers
- Aadhaar documents
- OTP values after verification
- Unnecessary personal information

Follow data minimization.

---

## Rule 7

**Do not invent representative information.**

If data is missing:

```text
Unknown
Not available
Needs verification
```

is better than fabricated data.

---

## Rule 8

**Source important political data.**

Representative information should eventually have:

```text
source
source_url
last_verified
```

where applicable.

---

# 📌 WHAT V1 SHOULD FEEL LIKE

The user should be able to open the application and immediately understand:

> **"I can find a representative and rate their work."**

The core experience should be:

```text
                    HOME

        🔍 Search Representative

                   OR

       Browse Representatives

                   ↓

             Representative

          Name
          Position
          Party
          Constituency

          ⭐ 4.2 / 5

       12,421 ratings

       [ Rate Representative ]

                   ↓

             Submit Rating
```

That's V1.

Simple.

Fast.

Useful.

---

# 🗺️ LONG-TERM PRODUCT MAP

```text
                       RATING APP
                           │
                           ▼
                    V1 — RATINGS ⭐
                           │
                           ▼
              V2 — PROMISES vs DELIVERY 📋
                           │
                           ▼
                 V3 — WORK vs OUTCOME 🏗️
                           │
                           ▼
                  V4 — CITIZEN ISSUES 🚨
                           │
                           ▼
              V5 — REPRESENTATIVE RESPONSE 💬
                           │
                           ▼
                 V6 — EVIDENCE LAYER 📚
                           │
                           ▼
                 V7 — AI ASSISTANT 🤖
                           │
                           ▼
              V8 — ADVANCED IDENTITY 🔐
```

Each version should provide value independently.

---

# 🌱 FINAL PRODUCT PHILOSOPHY

Rating App should not try to tell citizens:

> **"Who is the best politician?"**

It should help citizens answer:

> **"Who represents me?"**

> **"What is this representative responsible for?"**

> **"What have they said they would do?"**

> **"What has actually happened?"**

> **"What evidence exists?"**

> **"What do other citizens think?"**

And ultimately:

> **"I can make my own informed judgment."**

---

## V1 SUCCESS CRITERIA

V1 is successful if a new user can:

1. Register using mobile OTP
2. Search for a representative
3. Filter representatives
4. Open a representative profile
5. Understand basic representative information
6. Submit a 1–5 star rating
7. Optionally provide a comment
8. Update their rating later
9. See the aggregated rating
10. See the number of ratings

Nothing more is required for V1.

**Build the foundation correctly. Expand only when the previous version is stable.**