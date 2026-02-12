🏛 Civic Issue Signal Platform

Citizen complaints → Structured issues → Priority signal → Governance visibility → Authority execution → Transparency tracking

🚀 Purpose

Convert unstructured civic complaints into priority-ranked governance signal using controlled taxonomy, vote-budget enforcement, and threshold-based escalation.

⚙ Core Flow
Issue Created → Citizens Vote → Vote Budget Enforced →
Threshold Hit → Issue Flagged → Authority Creates Project →
Weekly Updates → Transparency Visibility

🧠 Key Design Decisions

Taxonomy-controlled issues (no free text categories)

One vote per issue per user (DB enforced)

Monthly vote budget → 5 votes / user

Threshold triggers visibility, not obligation

Projects created only by authorities

Transparency tracked via weekly updates

🗄 Data Model
Location Hierarchy:
States → Districts → Taluks → Wards/Villages

Core Tables:
Users
Issues
Votes
Projects
Weekly_Updates
Documents (Future)

📌 Issue Lifecycle
OPEN → THRESHOLD_REACHED → PROJECT_CREATED → IN_PROGRESS → RESOLVED

🗳 Vote Governance

Constraints:

UNIQUE(user_id, issue_id)

Ward-based voting

Monthly vote budget enforcement

Purpose:

Prevent spam voting

Prevent herd amplification

Preserve true priority signal

🎯 Threshold Model
Votes ≥ Threshold → Issue Status = THRESHOLD_REACHED


Does NOT:

Create projects

Assign funds

Force authority action

🏗 Authority Layer

Projects represent:

Administrative acknowledgement

Budget expectation

Execution responsibility

📅 Transparency Layer

Tracks:

Weekly progress updates

Document uploads

Update gaps

Delay patterns

Does NOT attempt fraud detection.

🔐 Identity Model (Phase 0)

Phone-based login:

Existing user → return user_id

New user → auto-create

(No OTP / JWT yet — adoption-first design)

🔌 APIs
POST   /login
GET    /issues
GET    /issues/ward/:wardId
POST   /issues
POST   /votes

🛠 Tech Stack
Backend:  Node.js + Express + PostgreSQL
Frontend: React + Vite + Axios

✔ System Guarantees

DB-level vote integrity

Transaction-safe vote + threshold update

Taxonomy-controlled data quality

Governance-aligned workflow modeling

⚖ Ethical Position

Records:

Citizen signal

Administrative response

Process compliance

Avoids:

Corruption claims

Truth verification

Enforcement authority behavior

📈 Evolution Path
Ward Signal → District Signal → State Signal → Policy Analytics
