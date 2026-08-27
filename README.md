# Keystone AI Provider Onboarding & Readiness
## Revised Phase 0 and Katherine Proposal

**Prepared by:** Waqar Pathan  
**Packet reviewed:** Keystone AI Provider Onboarding & Readiness — Consolidated Developer Execution Packet v3.0  
**Revision date:** August 27, 2026  
**Document status:** Revised proposal submitted for Keystone review; no implementation is authorized  
**Controlling record:** The accepted Upwork message and funded Upwork milestone. This repository copy is supporting material only.

---

## 1. Scope and authorization boundary

This document responds to Keystone's requested revisions and proposes two independently authorized milestones:

1. **Phase 0 — design and specification**
2. **Katherine — synthetic vertical-slice proof**

Nothing in this document authorizes implementation. Work begins only after the applicable Upwork milestone is expressly approved and funded. A meeting, draft, comment, demonstration, or acceptance of one milestone does not authorize another milestone or expand scope.

All project communication, questions, decisions, deliverables, approvals, scope changes, and payment authorizations will remain in Upwork. After any meeting, I will post written notes in Upwork listing decisions, assumptions, unresolved issues, and proposed scope changes. A meeting note changes scope only when Keystone confirms it in writing and the applicable Upwork milestone is updated and accepted.

### Terminology

| Term | Meaning |
|---|---|
| MUST / MUST NOT | Objective acceptance requirement |
| SHOULD | Proposed default that requires a written deviation if changed |
| TBD | Keystone decision required before dependent implementation |
| EXTERNAL UNKNOWN | Authoritative policy, contract, local-program, or integration evidence is required |
| ASSUMPTION | Estimate basis that Keystone must confirm |
| RESOLVED IN THIS REVISION | Prior inconsistency removed from the proposal |

---

## 2. Revision traceability

| Requested revision | Resolution in this document |
|---|---|
| 1. Correct document status | Header and Section 1 |
| 2. Reconcile G-13, G-13a, and G-14 | Complete register in Section 4 |
| 3. Use one architecture and price it consistently | Sections 5 and 16 |
| 4. Replace Node.js 18+ and state upgrade policy | Section 5.3 |
| 5. Compare Supabase with self-managed AWS RDS | Architecture Decision Record in Section 6 |
| 6. Explain database-level authorization and negative tests | Section 7 |
| 7. Expand the canonical model | Section 8 |
| 8. Keep readiness dimensions separate | Section 9 |
| 9. Separate detection, recalculation, restriction, suspension, review, and release | Section 10 |
| 10. Require affirmative human confirmation of AI classification | Sections 11–13 |
| 11. Clarify restricted-data routing | Section 12 |
| 12. Identify deterministic and AI functions | Section 11 |
| 13. Separate technical administration from release authority | Section 14 |
| 14. Use one identity and session model | Section 15 |
| 15. Remove premature components | Section 5.4 |
| 16. Replace application-local cron | Section 17 |
| 17. Provide three infrastructure cost models | Section 16 |
| 18. Separate design, prototype, production-intent, and hardening estimates | Section 19 |
| 19. Separate Phase 0 and Katherine Upwork milestones | Section 20 |
| 20. Put work products in Keystone-controlled accounts per milestone | Section 21 |

---

## 3. Requirement implementation classification

This classification prevents external unknowns from becoming production rules.

| Classification | Immediately implementable after milestone authorization | Requires additional Keystone detail | Requires authoritative external information |
|---|---|---|---|
| Platform foundation | Client-owned repository, CI, typed schema, audit event pattern, synthetic fixtures, environment configuration | Naming standards, account owners, retention, availability targets | None |
| Identity and access | Google SSO through Supabase Auth, scoped role assignments, RLS, negative authorization tests | User roster, role holders, small-team separation-of-duties decision, session policy | Keystone Google Workspace configuration |
| Provider model | Multi-organization practitioners, locations, relationship types, effective dates, supervisors, disciplines, specialties | Keystone terminology and required fields | County/joinder participation definitions where governed externally |
| Evidence | Versioned evidence, many-to-many requirement links, findings, decisions, human confirmation | Accepted evidence taxonomy, duplicate rules, retention, review responsibilities | Program-specific evidence standards and source policy |
| Readiness | Separate dimensions, deterministic calculation framework, human release records | Ratified dimension rules, reason codes, operator summaries | County, joinder, ChildLink, Elwyn, PROMISe/HCSIS, and policy-controlled rules |
| AI assistance | Typed advisory tools, structured responses, citations, confidence display, human confirmation | Model selection, approved prompts, evaluation set, acceptable use | Data-processing terms and any external model restrictions |
| Integrations | Connector interfaces and mock contracts | Google OAuth mode and reconciliation rules | ChildLink/Elwyn/API contracts, county systems, PROMISe/HCSIS capabilities |

---

## 4. Gap, question, dependency, and assumptions register

No requirement below is silently converted into a production rule.

| ID | Type | Question, assumption, or decision | Needed from | Effect if unresolved |
|---|---|---|---|---|
| G-01 | TBD | Confirm that packet v3.0 is the complete controlling source and identify any superseding policy attachments. | Keystone | Traceability and downstream estimates remain conditional. |
| G-02 | PROPOSED DECISION | Use Supabase/PostgreSQL/Auth/RLS for Phase 0 and Katherine. AWS RDS is evaluated but not selected. | Keystone technical reviewer | Katherine implementation cannot start until the selected architecture is accepted. |
| G-03 | TBD | Keystone must supply or approve Katherine's fully synthetic identity, relationships, requirements, evidence, findings, and expected results. | Keystone operations/compliance | Golden-record implementation and acceptance tests are blocked. |
| G-04 | TBD | Confirm the Keystone-owned GitHub organization, Supabase organization, AWS account, Google Cloud project, and OpenAI project to use. | Keystone IT | Repository and environment work cannot begin in client-controlled accounts. |
| G-05 | TBD | Confirm Google Workspace domain, permitted accounts, SSO provisioning model, and administrator responsible for OAuth consent. | Keystone IT/security | Authentication configuration is blocked. |
| G-06 | FUTURE DEPENDENCY | Decide whether Gmail and Drive use operator OAuth or domain-wide delegation, and provide scopes, retention, and reconciliation rules. | Keystone IT/security | Live integrations are excluded from Katherine and cannot yet be estimated reliably. |
| G-07 | EXTERNAL UNKNOWN | ChildLink API, export, authentication, sandbox, data contract, limits, and contractual permissions. | ChildLink / Keystone | No production rule or integration estimate will be created. |
| G-08 | EXTERNAL UNKNOWN | Elwyn API, export, authentication, sandbox, data contract, limits, and contractual permissions. | Elwyn / Keystone | No production rule or integration estimate will be created. |
| G-09 | EXTERNAL UNKNOWN | PROMISe, HCSIS, and ITF Waiver workflows: API, manual evidence, lookup, reconciliation, or another mechanism. | Keystone / PA program authority | Enrollment and billing rules remain placeholders, not executable policy. |
| G-10 | EXTERNAL UNKNOWN | Counties and joinders in scope, their participation relationships, rule variations, and ratifying authorities. | Keystone / county / joinder | Local-program rules and nine-provider regression coverage cannot be finalized. |
| G-11 | TBD | Identify authoritative policy owners and approved policy/version sources for every readiness rule. | Keystone compliance | Deterministic rules cannot be activated without versioned ratification. |
| G-12 | ASSUMPTION | Phase 0 and Katherine use synthetic data only; no PHI, child/family case data, SSNs, banking data, tax identifiers, or restricted financial data will be supplied. | Keystone confirmation | Any real or restricted data is a scope and security stop condition. |
| G-13 | ASSUMPTION | Phase 0/Katherine uses a Keystone-controlled Supabase project and one Keystone-controlled AWS deployment for the Next.js service. Development remains local; Katherine has one hosted synthetic environment. | Keystone IT | A different hosting decision requires an updated architecture and cost model before authorization. |
| G-13a | RESOLVED IN THIS REVISION | Redis, BullMQ, ElastiCache, and EC2/containerized Redis are not used for Phase 0/Katherine. Durable work uses Postgres-native scheduling and queues. | None | Removes the prior architecture/pricing conflict. |
| G-14 | TBD | Ratify requester/reviewer/releaser separation, the minimum number of independent people, and the break-glass review window for a small team. | Keystone owner/compliance/security | Consequential action workflow cannot be finalized. |
| G-15 | TBD | Confirm operator count, practitioner count, documents per practitioner, request volume, concurrency, storage, and growth assumptions. | Keystone operations | Pilot/production costs remain planning ranges. |
| G-16 | TBD | Approve availability, RPO, RTO, backup retention, audit retention, evidence retention, deletion, and legal-hold requirements. | Keystone security/legal/operations | Production infrastructure and hardening cannot be fixed-price estimated. |
| G-17 | TBD | Approve evidence taxonomy, accepted document types, version rules, duplicate rules, and required human-review evidence. | Keystone compliance | Evidence contracts remain structural rather than policy-complete. |
| G-18 | TBD | Ratify which findings may cause an automatic operational restriction. Default proposal: detection and recalculation do not restrict operations unless an approved policy version explicitly says so. | Keystone compliance/operations | Automated restriction remains disabled. |
| G-19 | TBD | Define employment, contractor, supervisor, capacity, assignment, enrollment, and contract semantics, including effective-date overlap rules. | Keystone operations/legal | Data structures can be built, but business validation rules remain inactive. |
| G-20 | TBD | Select and approve malware scanning and OCR components, deployment boundary, data residency, and contractual terms. | Keystone security/legal | Katherine will use pre-sanitized synthetic fixtures; production file ingestion remains excluded. |
| G-21 | TBD | Define AI evaluation dataset, model/version approval, accuracy measures, thresholds, drift monitoring, and change-approval owner. | Keystone | AI remains advisory with 100% affirmative human confirmation. |
| G-22 | TBD | Confirm the agreed Upwork rate. Dollar illustrations in this proposal use $24/hour; milestone amounts must be written and funded in Upwork. | Keystone / Waqar | Hours remain valid, but dollar totals change if the rate differs. |

---

## 5. Selected Phase 0/Katherine architecture

### 5.1 Architecture decision

The proposed baseline is **Supabase-first**, preserving the preferred stack and implementing authorization in PostgreSQL rather than simulating RLS in application middleware.

| Layer | Selected component | Phase 0/Katherine use |
|---|---|---|
| Web application and server API | Next.js 16 App Router, TypeScript | One full-stack application; no separate Express API |
| Runtime | Node.js 24.20.0 LTS | Pinned in CI, container, package engines, and developer setup |
| Database | Supabase managed PostgreSQL | Canonical data, policies, audit, deterministic calculations |
| Authentication | Supabase Auth with Google Workspace OAuth/OIDC | One identity/session issuer; mandatory MFA policy |
| Authorization | PostgreSQL grants, RLS, scoped role tables, guarded database functions | Enforced beneath UI and API |
| Evidence storage | Supabase Storage | Synthetic Katherine files only; production ingestion is excluded |
| Scheduling | Supabase Cron / pg_cron | Inserts deterministic scheduled work |
| Durable jobs | Supabase Queues / pgmq plus job execution records | Visibility timeout, idempotency, retries, archive/dead-letter, replay |
| AI | OpenAI structured outputs through server-only typed tools | Advisory proposals only |
| Application hosting | One containerized Next.js service on AWS ECS Fargate | No Vercel deployment and no separate frontend/backend services |
| Secrets | AWS Secrets Manager and Supabase secret settings | No secrets in source, logs, prompts, or documentation |
| CI/CD | GitHub Actions in Keystone's organization | Lint, typecheck, tests, migrations, image build, gated deployment |
| Logs/metrics | Structured application logs and AWS CloudWatch; immutable business audit in PostgreSQL | Operational logs are not substitutes for audit records |

### 5.2 Component flow

~~~mermaid
flowchart TD
    U["Authorized operator"] --> APP["Next.js service on AWS ECS Fargate"]
    APP --> AUTH["Supabase Auth: Google SSO and MFA"]
    APP --> DB["Supabase PostgreSQL: RLS and guarded functions"]
    APP --> STORE["Supabase Storage: synthetic evidence"]
    DB --> JOBS["pg_cron and pgmq durable work"]
    APP --> AI["Typed advisory AI gateway"]
    AI --> MODEL["OpenAI structured output"]
    DB --> AUDIT["Append-only audit events"]
~~~

Only the Next.js server may hold privileged credentials. Browser requests use the user's Supabase session so RLS remains active. A Supabase service-role key is never shipped to the browser and is not used for ordinary user requests.

### 5.3 Runtime baseline and dependency policy

The exact baseline for milestone kickoff is:

- **Node.js 24.20.0 LTS**
- **Next.js 16.x**, pinned to an exact patched version in the lockfile
- **TypeScript 5.x**, pinned to an exact version compatible with the selected Next.js release
- **PostgreSQL version supplied by the approved Supabase project**, captured in the environment manifest

Version enforcement will use the container base-image digest, package-manager lockfile, package engine constraint, and CI version check.

Dependency maintenance policy:

1. Dependabot or Renovate opens routine dependency updates; versions never float in production.
2. Critical exploitable vulnerabilities are triaged within one business day and patched or mitigated through a reviewed change as soon as a compatible fix is available.
3. High-severity vulnerabilities are addressed within seven calendar days when a compatible fix exists.
4. Routine compatible updates are grouped and tested monthly.
5. Major framework/runtime upgrades use a separate branch, automated regression evidence, migration notes, and Keystone approval before production promotion.
6. The Node LTS line is reviewed quarterly and upgraded with a target of at least 90 days before end of support.

### 5.4 Components intentionally removed or deferred

| Component | Phase 0/Katherine decision | Reason |
|---|---|---|
| Express API | Removed | Next.js server routes provide the small vertical-slice API. |
| Firebase Auth/Admin | Removed | Supabase Auth is the only identity/session issuer. |
| Custom access/refresh tokens | Removed | Supabase manages signed sessions and refresh-token rotation. |
| Local passwords and bcrypt | Removed | Google SSO is the proposed login method. |
| Socket.io | Deferred | No accepted Katherine requirement needs live sockets. |
| Redis / ElastiCache / BullMQ | Removed | Postgres-native queueing is sufficient for this scope. |
| node-cron / application-local scheduler | Removed | pg_cron schedules once at the database layer. |
| Twilio / SendGrid | Excluded | No accepted Katherine SMS or outbound-email requirement. |
| CloudFront / S3 evidence architecture | Removed | Supabase Storage is selected for this architecture. |
| nginx | Removed | The managed AWS load-balancing path terminates HTTPS. |
| Separate Vercel frontend | Removed | The Next.js application is one containerized full-stack service. |
| Live Gmail/Drive | Deferred | They are limited evidence streams and follow Katherine. |

---

## 6. Architecture Decision Record: Supabase versus self-managed AWS RDS

**ADR-001 status:** Proposed; Keystone approval required  
**Decision:** Select Supabase for Phase 0/Katherine. Revisit only if Phase 0 identifies a non-negotiable requirement Supabase cannot satisfy.

The compared AWS alternative is one Next.js service on ECS Fargate, AWS RDS PostgreSQL with native RLS, Amazon Cognito federated to Google Workspace, S3, SQS/EventBridge Scheduler, Secrets Manager, and CloudWatch. It does not use homemade passwords or application-issued token families.

| Criterion | Supabase PostgreSQL/Auth/RLS | AWS RDS PostgreSQL + custom identity/application stack |
|---|---|---|
| Security boundary | Native PostgreSQL RLS, Auth integration, Storage policies, managed patching | Native RLS is available, but identity claims, token lifecycle, policy helpers, storage controls, and operational integration must be built/configured |
| Tenant isolation | Database policies can enforce organization, location, practitioner, scope, and data-class access on every query | Equally possible in PostgreSQL, but more implementation and test responsibility sits with the team |
| Authentication | Managed Google OIDC, MFA, token rotation, session APIs | Requires AWS Cognito or another approved identity provider; a custom JWT/password system is not proposed |
| Operational complexity | Lower for a small team; managed database, auth, storage, backups, queues, and cron | Higher: RDS networking, connection pooling, identity service, object storage, queues, schedulers, IAM, patching, backup validation, and observability |
| Vendor dependency | Supabase APIs/Auth/Storage create moderate platform dependency; core data and RLS remain PostgreSQL | Greater AWS service dependency but more infrastructure control |
| Prototype cost | Selected Katherine infrastructure: approximately $65–$145/month | Directional equivalent AWS-managed stack: approximately $110–$260/month before engineering, depending on network topology and backups |
| Development effort | Faster for the Katherine slice | Estimated 25–40 additional setup/security hours before equivalent Katherine business behavior |
| Long-term maintenance | Smaller platform surface; review limits, plan/SLA, and migration path | Larger DevOps/security burden; more control over topology and vendor selection |
| Exit path | PostgreSQL schema/migrations are portable; Auth/Storage/Edge-specific parts require a migration plan | PostgreSQL remains portable; AWS-specific IAM, queues, storage, and deployment also require migration |
| Best fit | Current preferred stack, small internal team, rapid controlled validation | Future case requiring private networking, a specific AWS compliance agreement, custom regional architecture, or unsupported Supabase capability |

**Why selected:** Supabase satisfies Keystone's stated preference, gives real database-level RLS, removes the conflicting custom-auth design, and reduces the number of services that must be secured before Katherine can prove the domain model. The AWS RDS alternative is not rejected permanently; it is simply not authorized or priced as the selected Phase 0/Katherine build.

---

## 7. Database-level authorization strategy

### 7.1 Enforcement model

Authorization is enforced with four layers:

1. **PostgreSQL grants:** unauthenticated access is revoked; each table receives only the operations required by the authenticated role.
2. **RLS policies:** separate SELECT, INSERT, UPDATE, and DELETE policies enforce row visibility and allowed resulting state.
3. **Guarded database functions:** consequential mutations such as evidence acceptance, policy decisions, restrictions, suspension, release, and reinstatement occur through typed functions that re-check actor, scope, separation of duties, effective dates, and allowed transition.
4. **Constraints and audit:** foreign keys, unique constraints, check constraints, optimistic version columns, and append-only audit events prevent partial or invalid writes.

Application checks improve error messages but are not treated as the security boundary.

### 7.2 Scoped access model

The authorization graph is stored in:

- app_user
- role
- permission
- resource_scope
- user_role_assignment

A user may hold multiple roles, each with an effective-dated scope at platform, organization, location, practitioner, or security/audit level. Database helper functions such as can_read_practitioner, can_review_evidence, and can_release_provider resolve the current user through auth.uid(), verify the account is enabled, evaluate active assignments, and enforce the row's data class.

Key rules:

- Organization-scoped users cannot see another organization's relationship, evidence, finding, or readiness rows.
- Location-scoped users cannot see other locations unless an active broader assignment permits it.
- A practitioner linked to several organizations does not make organization-specific data visible across those organizations.
- Suspected restricted files are visible only to specifically scoped security reviewers.
- Technical system administrators have no business release permission by default.
- Direct writes to consequential tables are revoked from browser roles.
- Views are created with security-invoker behavior or protected equivalent and are included in policy tests.

### 7.3 Required negative authorization tests

Every protected resource must include allowed-path and denied-path tests. The minimum matrix includes:

- anonymous user denied;
- disabled user denied;
- expired role assignment denied;
- correct role but wrong organization denied;
- correct organization but wrong location denied;
- practitioner relationship outside its effective dates denied;
- ordinary evidence reviewer denied access to quarantined data;
- system administrator denied provider release;
- requester denied review/release of the same case where separation applies;
- stale session denied after role change or revocation;
- direct REST/database mutation denied even when the UI hides the action;
- INSERT or UPDATE that changes organization/location scope denied;
- view/function path cannot bypass base-table RLS;
- service-role key absent from browser bundles and ordinary request paths.

Tests will run against local Supabase/PostgreSQL in CI using pgTAP/SQL policy tests plus TypeScript API integration tests.

---

## 8. Canonical data model

### 8.1 Modeling principles

- A **practitioner** is a person, not an employment record and not a single provider status.
- Organization, location, employment/contracting, supervision, discipline, specialty, county/joinder participation, enrollment, and assignments are separate effective-dated relationships.
- Evidence is immutable by version. One evidence version may support several requirement instances through a many-to-many link.
- Requirements point to a versioned policy source and applicability rule.
- Findings, exceptions, waivers, and decisions are separate records with actors and rationale.
- Readiness dimensions are calculated separately; operational restrictions, suspensions, assignments, and human release decisions are not encoded as one status.

### 8.2 Entity catalog

| Domain | Canonical entities |
|---|---|
| Organization and place | organization, location, county, joinder, local_program, program_participation |
| Practitioner relationships | practitioner, organization_practitioner_relationship, relationship_location, practitioner_supervision |
| Professional attributes | discipline, specialty, practitioner_discipline, practitioner_specialty |
| Operational dimensions | enrollment, contract_record, clearance, training_completion, billing_configuration, capacity_record, assignment, local_program_approval |
| Policy and requirements | policy_source, policy_version, requirement_definition, requirement_version, applicability_rule, practitioner_requirement |
| Evidence | evidence_item, evidence_version, evidence_requirement_link, evidence_source_reference, evidence_review |
| Control records | finding, exception_request, waiver, decision, operational_restriction, suspension, release_decision |
| Readiness | readiness_dimension, readiness_assessment, readiness_recalculation |
| Access and audit | app_user, role, permission, resource_scope, user_role_assignment, audit_event |
| AI advisory records | ai_run, ai_proposal, human_confirmation |

### 8.3 Practitioner and organizational relationships

~~~mermaid
erDiagram
    ORGANIZATION ||--o{ LOCATION : contains
    PRACTITIONER ||--o{ ORG_PRACTITIONER_RELATIONSHIP : works_through
    ORGANIZATION ||--o{ ORG_PRACTITIONER_RELATIONSHIP : engages
    ORG_PRACTITIONER_RELATIONSHIP ||--o{ RELATIONSHIP_LOCATION : operates_at
    LOCATION ||--o{ RELATIONSHIP_LOCATION : scopes
    ORG_PRACTITIONER_RELATIONSHIP ||--o{ PRACTITIONER_SUPERVISION : supervisee
    PRACTITIONER ||--o{ PRACTITIONER_SUPERVISION : supervisor
    PRACTITIONER ||--o{ PRACTITIONER_DISCIPLINE : has
    DISCIPLINE ||--o{ PRACTITIONER_DISCIPLINE : classifies
    PRACTITIONER ||--o{ PRACTITIONER_SPECIALTY : has
    SPECIALTY ||--o{ PRACTITIONER_SPECIALTY : classifies
    COUNTY ||--o{ PROGRAM_PARTICIPATION : governs
    JOINDER ||--o{ PROGRAM_PARTICIPATION : governs
    ORG_PRACTITIONER_RELATIONSHIP ||--o{ PROGRAM_PARTICIPATION : participates
~~~

Every relationship above includes valid_from, valid_to, source, recorded_by, and version fields. organization_practitioner_relationship includes relationship_type values such as employee or contractor; the allowed values and overlap rules require Keystone ratification under G-19.

### 8.4 Requirements, evidence, and policy

~~~mermaid
erDiagram
    POLICY_SOURCE ||--o{ POLICY_VERSION : versions
    POLICY_VERSION ||--o{ REQUIREMENT_VERSION : authorizes
    REQUIREMENT_DEFINITION ||--o{ REQUIREMENT_VERSION : versions
    REQUIREMENT_VERSION ||--o{ APPLICABILITY_RULE : determines
    PRACTITIONER ||--o{ PRACTITIONER_REQUIREMENT : receives
    REQUIREMENT_VERSION ||--o{ PRACTITIONER_REQUIREMENT : instantiates
    EVIDENCE_ITEM ||--o{ EVIDENCE_VERSION : versions
    EVIDENCE_VERSION ||--o{ EVIDENCE_REQUIREMENT_LINK : supports
    PRACTITIONER_REQUIREMENT ||--o{ EVIDENCE_REQUIREMENT_LINK : supported_by
    EVIDENCE_VERSION ||--o{ EVIDENCE_REVIEW : reviewed
    PRACTITIONER_REQUIREMENT ||--o{ FINDING : produces
    FINDING ||--o{ EXCEPTION_REQUEST : may_request
    EXCEPTION_REQUEST ||--o| WAIVER : may_grant
    FINDING ||--o{ DECISION : resolved_by
~~~

An evidence link does not equal acceptance. A human evidence_review must affirm an AI-proposed classification before that evidence can satisfy a V1 release prerequisite.

### 8.5 Readiness and operational control

~~~mermaid
erDiagram
    PRACTITIONER ||--o{ READINESS_ASSESSMENT : has
    READINESS_DIMENSION ||--o{ READINESS_ASSESSMENT : separates
    READINESS_ASSESSMENT ||--o{ READINESS_RECALCULATION : computed_by
    PRACTITIONER ||--o{ ENROLLMENT : has
    PRACTITIONER ||--o{ CONTRACT_RECORD : has
    PRACTITIONER ||--o{ CLEARANCE : has
    PRACTITIONER ||--o{ TRAINING_COMPLETION : has
    PRACTITIONER ||--o{ BILLING_CONFIGURATION : has
    PRACTITIONER ||--o{ CAPACITY_RECORD : has
    PRACTITIONER ||--o{ ASSIGNMENT : receives
    PRACTITIONER ||--o{ LOCAL_PROGRAM_APPROVAL : has
    PRACTITIONER ||--o{ OPERATIONAL_RESTRICTION : may_receive
    PRACTITIONER ||--o{ SUSPENSION : may_receive
    PRACTITIONER ||--o{ RELEASE_DECISION : human_controls
~~~

---

## 9. Readiness dimensions

There is no single global provider status column. The operator summary is a deterministic projection over separate records.

| Dimension | Example deterministic inputs | Example states | Human-controlled element |
|---|---|---|---|
| Qualification | discipline, specialty, education/credential requirements | unknown, incomplete, in_review, satisfied, not_applicable | acceptance of contested evidence or exception |
| Clearance | clearance requirements, issue/expiration dates | unknown, incomplete, in_review, satisfied, expired | exception/waiver decision |
| Training | required training and completion dates | unknown, incomplete, in_review, satisfied, expired | evidence acceptance |
| Enrollment | program enrollment records and effective dates | unknown, pending, active, lapsed, not_applicable | external/manual confirmation where no authoritative integration exists |
| Contracting | organization relationship and contract record | unknown, pending, active, ended | contract approval outside AI |
| Billing configuration | approved deterministic configuration checks | unknown, incomplete, configured, blocked | business confirmation |
| Local-program approval | county/joinder/program records | unknown, pending, approved, denied, not_applicable | authoritative local decision |
| Capacity | capacity record, effective dates, limits | unknown, available, limited, unavailable | operator-entered approved capacity |
| Assignment readiness | all assignment-specific requirements | unknown, incomplete, ready, restricted | assignment authorization |
| Human release authority | signed release/reinstatement decision | not_requested, pending, released, denied, revoked | always human |

The summary response returns each dimension, reason codes, open finding IDs, policy version, calculation time, and active operational controls. It may display “blocked” to an operator, but that label is a summary—not an editable master status and not a substitute for the underlying dimension and human decision records.

---

## 10. Detection, calculation, restriction, review, and release

| Stage | Trigger | System action | May AI control it? | Human/policy gate |
|---|---|---|---|---|
| 1. Detection | Expiration, missing evidence, conflict, failed reconciliation | Create or update a finding with stable reason code and evidence references | No; deterministic detection. AI may summarize. | None |
| 2. Recalculation | Relevant data or policy version changes | Recompute only affected readiness dimensions and store inputs/version | No | None |
| 3. Operational restriction evaluation | A finding matches a ratified restriction rule | Create a proposed or automatic restriction according to the exact approved policy version | No | Automatic only if Keystone has expressly ratified that rule |
| 4. Suspension | Authorized suspension request/decision | Record suspension with scope, reason, effective period, and audit event | No | Authorized human decision |
| 5. Human review | Finding, exception, evidence proposal, release request | Queue review; record reviewer evidence and decision | AI may provide advisory summary only | Affirmative human action |
| 6. Release or reinstatement | All deterministic prerequisites satisfied and an authorized request exists | Guarded database function records release/reinstatement | No | Distinct authorized human releaser with recent MFA |

Example: an expired document automatically creates a finding and recalculates the relevant dimension. It does **not** automatically restrict operations unless Keystone has approved a versioned policy that explicitly requires that restriction. Otherwise it enters human review.

Invalid transitions return a stable reason code, write no partial business state, and create a denied-attempt audit event where appropriate.

---

## 11. Deterministic, AI-advisory, and human-controlled functions

| Function | Deterministic code | AI advisory | Affirmative human control |
|---|---:|---:|---:|
| Requirement applicability | Yes | May explain result | Ratifies policy/rule version |
| Missing-requirement detection | Yes | May draft follow-up | May resolve exception |
| Expiration and effective-date calculation | Yes | May summarize impact | Approves exception/waiver |
| Duplicate/idempotency detection | Yes | No | Reviews unresolved conflict |
| Readiness-dimension calculation | Yes | May explain reason codes | Ratifies rules |
| Permissions and resource scopes | Yes, database enforced | No | Assigns approved roles |
| Transition guards | Yes | No | Executes consequential transition where required |
| Candidate document classification | No | Yes | Must confirm before evidence can satisfy V1 prerequisite |
| Candidate metadata extraction | Deterministic validation of types/ranges | Yes | Confirms controlling values |
| Evidence-conflict summary | No | Yes | Resolves conflict |
| Follow-up draft | Deterministic recipient/request deduplication | Yes | Reviews and sends |
| Restriction, suspension, release, reinstatement | Guarded deterministic execution | Cannot request or execute independently | Authorized decision required except a separately ratified automatic restriction rule |

AI output is never a source of authorization. Confidence is display/evaluation metadata, not an approval threshold.

Any future reduction from 100% affirmative human confirmation is outside V1. It would require measured performance on a Keystone-approved labeled dataset, per-document and per-field thresholds, false-positive/false-negative analysis, drift monitoring, rollback criteria, versioned evaluation evidence, and a separate written Keystone decision and milestone.

---

## 12. Restricted-data pipeline

The pre-model screen and post-model confidence are separate controls.

| Step | Processing and control | Result on failure |
|---:|---|---|
| 1 | Receive file into a non-AI intake/quarantine area; assign correlation ID and content hash | Reject malformed upload; log without sensitive content |
| 2 | Malware scan with an approved component | Quarantine; no extraction or AI call |
| 3 | Extract text/OCR within the approved processing boundary | Quarantine on failure or unsupported type |
| 4 | Run deterministic restricted-data screening over filename, metadata, extracted text, and detector results | Quarantine on match, ambiguity, or incomplete scan |
| 5 | Security reviewer handles quarantine under restricted scope | No model access |
| 6 | Construct an allowlisted prompt from permitted fields only; exclude raw unrestricted records and unnecessary identifiers | Fail closed if allowlist contract is not satisfied |
| 7 | Call the approved AI model through one typed server-side tool | No direct database state transition |
| 8 | Validate response against strict JSON Schema, enums, date/range rules, and cited source spans | Reject invalid response; retain diagnostic metadata only |
| 9 | Store confidence as advisory model output after the call | Confidence never overrides screening or human review |
| 10 | Human reviewer affirmatively confirms, edits, or rejects the proposal | Unconfirmed proposal cannot satisfy a prerequisite |
| 11 | Guarded evidence-acceptance function links the confirmed evidence version to requirements and triggers deterministic recalculation | Deny if role, scope, SoD, version, or policy guard fails |

For Katherine, all files are synthetic and pre-sanitized. A synthetic restricted-data canary will test that the pipeline quarantines before the model call. Production malware/OCR tooling is excluded until G-20 is resolved.

---

## 13. Proposed API, AI-tool, and structured-response contracts

All contracts are versioned, server-validated, and documented through OpenAPI and JSON Schema. Mutating operations require an authenticated actor, explicit authorization, a correlation ID, and an Idempotency-Key. Consequential mutations also require a current entity version and recent AAL2 authentication.

### 13.1 API surface for the Katherine slice

| Method and route | Purpose | Authorization and control |
|---|---|---|
| POST /api/v1/practitioners | Create synthetic practitioner | Onboarding role; organization scope; idempotent |
| GET /api/v1/practitioners/:id | Read practitioner and scoped relationships | RLS-filtered; no cross-organization data |
| POST /api/v1/practitioners/:id/relationships | Add effective-dated organization/location relationship | Onboarding role; overlap validation; optimistic version |
| GET /api/v1/practitioners/:id/requirements | Return deterministic requirement instances | RLS-filtered; includes policy/reason codes |
| POST /api/v1/practitioners/:id/readiness/recalculate | Recalculate affected dimensions | Deterministic function; never releases or restricts by itself |
| POST /api/v1/evidence | Register a synthetic evidence item/version | Onboarding/evidence role; content hash deduplication |
| POST /api/v1/evidence/:versionId/ai-proposals | Request advisory classification | Approved evidence role; restricted-data gate must have passed |
| POST /api/v1/evidence/:versionId/confirm | Affirm, edit, or reject AI proposal | Independent evidence reviewer; human action and rationale required |
| POST /api/v1/findings/:id/decisions | Record finding/exception decision | Compliance decision role; typed decision and policy version |
| POST /api/v1/release-requests | Request release/reinstatement review | Scoped requester; cannot self-release |
| POST /api/v1/release-decisions | Release, deny, revoke, or reinstate | Release authority; SoD, current policy, no blocking prerequisites, recent AAL2 |
| GET /api/v1/practitioners/:id/readiness | Return multi-dimensional summary | Deterministic read; RLS-filtered |
| GET /api/v1/practitioners/:id/audit-events | Return scoped business audit history | Auditor or appropriately scoped business role |

Stable errors use HTTP status plus a machine-readable code such as CROSS_SCOPE_DENIED, STALE_VERSION, POLICY_NOT_RATIFIED, SOD_VIOLATION, MFA_REAUTH_REQUIRED, BLOCKING_FINDING_OPEN, RESTRICTED_DATA_QUARANTINED, or IDEMPOTENT_REPLAY.

### 13.2 AI-agent tool contracts

| Tool | Allowlisted input | Structured output | Permitted effect |
|---|---|---|---|
| propose_evidence_classification | evidence_version_id, sanitized text blocks, page/span coordinates, approved taxonomy version | candidate type, candidate fields, source spans, confidence, warnings | Create ai_proposal only |
| propose_evidence_metadata | confirmed candidate type, sanitized spans, allowed field schema | proposed dates/identifiers with source spans and confidence | Append proposal fields only |
| summarize_evidence_conflict | conflict reason codes and allowlisted evidence summaries | neutral summary, cited inputs, unresolved questions | Append advisory summary |
| draft_consolidated_followup | deterministic missing-item list, approved recipient context, prior-request keys | subject/body draft, referenced requirement IDs | Save draft only; cannot send |
| explain_readiness | deterministic readiness response and reason-code glossary | plain-language explanation with dimension references | Read-only explanation |
| get_readiness_summary | practitioner ID and actor scope | deterministic structured readiness response | Read-only database function; no model reasoning |

There is deliberately no AI tool for deciding applicability, finding missing requirements, calculating expiration, changing readiness, granting a waiver, applying a restriction, suspending, releasing, or reinstating.

### 13.3 Structured AI proposal

~~~json
{
  "schemaVersion": "1.0",
  "proposalId": "uuid",
  "evidenceVersionId": "uuid",
  "taxonomyVersion": "2026-08-approved",
  "candidateDocumentType": "clearance",
  "candidateFields": [
    {
      "name": "expires_on",
      "value": "2027-01-31",
      "sourceSpans": [
        {
          "page": 1,
          "start": 104,
          "end": 114
        }
      ],
      "confidence": 0.91
    }
  ],
  "warnings": [],
  "humanConfirmationRequired": true
}
~~~

The server rejects unknown properties, invalid enums, impossible dates, missing source spans, unapproved taxonomy versions, and outputs that exceed the allowlisted schema. humanConfirmationRequired is fixed to true for any V1 classification used toward a release prerequisite.

### 13.4 Deterministic readiness response

~~~json
{
  "schemaVersion": "1.0",
  "practitionerId": "uuid",
  "calculatedAt": "2026-08-27T12:00:00Z",
  "engineVersion": "readiness-engine-1.0.0",
  "policyVersion": "keystone-policy-pending-ratification",
  "dimensions": [
    {
      "name": "clearance",
      "state": "incomplete",
      "reasonCodes": ["CLEARANCE_EXPIRED"],
      "findingIds": ["uuid"]
    },
    {
      "name": "training",
      "state": "satisfied",
      "reasonCodes": [],
      "findingIds": []
    }
  ],
  "activeRestrictions": [],
  "suspension": null,
  "release": {
    "state": "not_released",
    "decisionId": null
  }
}
~~~

The summary cannot be used as a write payload. Release is derived only from a separate signed human release_decision record.

### 13.5 Error response

~~~json
{
  "error": {
    "code": "SOD_VIOLATION",
    "message": "A different authorized releaser is required.",
    "retryable": false
  },
  "correlationId": "uuid"
}
~~~

Raw document text, secrets, tokens, and restricted values never appear in errors or operational logs.

---

## 14. Roles, permissions, and separation of duties

### 14.1 Operation-level matrix

| Operation | System administrator | Onboarding worker | Evidence reviewer | Compliance decision maker | Release authority | Security reviewer | Auditor | Emergency custodian | AI service |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| Configure infrastructure/connectors | Yes | No | No | No | No | Security approval | Read | Break-glass only | No |
| Provision/disable users | Yes | No | No | No | No | Review | Read | Break-glass only | No |
| Assign business roles | Request only | No | No | Approve if scoped | No | Review | Read | Break-glass only | No |
| Create/edit practitioner and relationships | No by default | Yes | Read | Read | Read | No | Read | No | No |
| Upload/link candidate evidence | No by default | Yes | Yes | Read | Read | Quarantine only | Read | No | Proposal only |
| Confirm AI classification | No | No | Yes | Yes if separately scoped | No | For quarantine only | Read | No | Never |
| Create release request | No | Yes | Yes | Yes | No | No | Read | No | Never |
| Decide exception/waiver/compliance finding | No | No | No | Yes | Read | Security findings only | Read | No | Never |
| Apply operational restriction | No | No | No | Yes when policy permits | No | Security restriction only | Read | Break-glass only | Never |
| Suspend | No | No | No | Request/approve per policy | Yes if scoped | Security request only | Read | Break-glass only | Never |
| Release/reinstate practitioner | No | No | No | Request only | Yes | No | Read | Break-glass only | Never |
| View ordinary audit history | Technical events only | Own actions | Scoped | Scoped | Scoped | Security events | Yes | Emergency events | No |
| View quarantined content | No by default | No | No | No | No | Yes | Metadata only unless separately authorized | Break-glass only | Never |
| Modify policy version | No | No | No | Draft | Ratify only if designated | Security review | Read | No | Never |

### 14.2 Small-team proposal

The default is three distinct actors on a consequential case:

1. requester/onboarding worker;
2. evidence or compliance reviewer;
3. release authority.

A person may hold several roles organizationally but cannot perform incompatible steps on the same request. If Keystone cannot staff three independent actors, the system will not silently relax the rule. Keystone must approve a compensating-control design, such as an external/owner releaser or dual confirmation by two independent people with no self-approval.

Break-glass access is disabled by default, time-limited, requires a reason, creates immediate alerts, cannot be used by the AI service, and requires retrospective review within a Keystone-approved window under G-14.

---

## 15. Coherent authentication and session model

Supabase Auth is the only identity and session authority.

1. **SSO:** users sign in with Keystone-approved Google Workspace accounts through Supabase Auth's Google OIDC provider.
2. **Provisioning:** an account must be pre-provisioned/invited and linked to an active app_user record; domain membership alone grants no application access.
3. **MFA:** TOTP MFA is mandatory for privileged application access. Consequential actions require AAL2.
4. **Tokens:** Supabase issues and rotates access/refresh tokens. The application does not issue a second JWT family.
5. **Role evaluation:** roles and scopes are database records evaluated on every protected operation, not long-lived custom claims.
6. **Disabled accounts:** disabled_at and membership state are checked by RLS helpers and guarded functions. Active sessions are revoked through the Auth administration path.
7. **Role changes:** take effect immediately for database authorization because current role assignments are queried at action time.
8. **Proposed session policy:** 15-minute access-token lifetime, eight-hour maximum working session, 30-minute inactivity lock, subject to Keystone approval.
9. **Reauthentication:** release, reinstatement, suspension, role grant, connector change, and break-glass actions require AAL2 and authentication no older than 15 minutes.
10. **No local passwords:** Firebase, local password hashes, and application-created refresh tokens are removed from the design.

Exact session durations remain a Keystone security decision, but the implementation mechanism is coherent regardless of the selected values.

---

## 16. Infrastructure cost models

All amounts are planning estimates in USD as of August 2026, before tax. They price the selected Supabase + one AWS Next.js deployment architecture. They exclude engineering fees, Keystone's existing Google Workspace, legal/compliance reviews, and unapproved integrations. Actual AWS, model, OCR, scanning, egress, and log costs are usage-based.

### 16.1 Assumptions

| Model | Users / practitioners | Traffic and jobs | Database / evidence | Availability | Retention assumed for estimate |
|---|---|---|---|---|---|
| Katherine prototype | 2–5 users / 1 synthetic practitioner | Under 5,000 requests and 500 job runs/month | Under 1 GB DB and 1 GB synthetic files | Best effort; one app task; no production SLA | 7-day operational logs; Supabase Pro daily backups; synthetic data disposable after acceptance |
| Internal pilot | 10–25 users / up to 500 practitioners | Up to 150,000 requests and 25,000 jobs/month | Up to 8 GB DB and 50 GB evidence | Two app tasks proposed; no contractual SLA until approved | 30-day operational logs; 7-day managed backup; evidence retention assumed 1 year for costing only |
| Production target | 25–75 users / up to 5,000 practitioners | Up to 1.5M requests and 250,000 jobs/month | Up to 50 GB DB and 500 GB evidence | Multi-instance app; formal SLA/RPO/RTO require G-16 | 90-day hot operational logs; 7-day PITR assumption; evidence/audit archive term remains TBD |

### 16.2 Monthly cost ranges

| Material service | Katherine | Internal pilot | Production target | Basis |
|---|---:|---:|---:|---|
| Supabase plan/compute/storage/backups | $25–$40 | $75–$175 | $700–$1,050 | Pro for prototype/pilot; production assumes Team, larger compute, storage, and PITR allowance |
| AWS ECS Fargate, load balancer, registry | $30–$55 | $70–$140 | $180–$400 | One prototype task; two pilot tasks; multi-instance production |
| AWS logs, metrics, secrets, alerts | $5–$15 | $20–$75 | $100–$350 | Driven by ingestion and retention |
| OpenAI API | $5–$25 | $25–$150 | $100–$750 | Advisory calls only; depends on document/token volume and selected model |
| Malware scanning/OCR | $0 in Katherine | $25–$150 | $100–$600 | Production component is TBD under G-20 |
| GitHub Actions / security scanning | $0–$10 | $0–$50 | $25–$150 | Depends on plan, seats, and CI minutes |
| **Estimated total** | **$65–$145/month** | **$215–$740/month** | **$1,205–$3,300/month** | Directional until G-15, G-16, and G-20 are resolved |

These are not vendor quotes or a production commitment. A production cost ceiling cannot be reliable until data volume, retention, availability, OCR/scanning, model selection, and integration frequency are approved.

---

## 17. Multi-instance-safe background work

Application-local cron is not used.

1. Supabase Cron/pg_cron creates scheduled work at the database layer.
2. Supabase Queues/pgmq stores durable messages with a visibility timeout.
3. Every job has a unique idempotency key based on job type, source system, source record, and payload version.
4. A job_execution row records claim time, worker, attempt, correlation ID, input hash, result, and next retry time.
5. Workers may run concurrently; queue visibility and an atomic idempotency claim prevent duplicate business effects.
6. Retries are bounded. The proposed default is five attempts with capped exponential backoff, subject to connector-specific limits.
7. Exhausted or non-retryable work enters a dead-letter/archive state with a stable reason code and operator alert.
8. Replay requires an authorized operator, preserves the original job, and creates a linked execution using the same business idempotency key.
9. Reconciliation jobs compare source cursors/counts/identifiers with accepted local records and create findings for gaps.
10. A retry never directly creates a second evidence, request, email draft, decision, or release event.

Live Gmail, Drive, ChildLink, and Elwyn jobs are not part of Katherine; the queue contract is established so later connectors do not require a new reliability model.

---

## 18. Katherine synthetic golden-record plan

### 18.1 Fixture contents

Keystone supplies or approves a wholly synthetic manifest containing:

- a fictional practitioner identity;
- at least one organization relationship, two locations, and effective dates;
- discipline and specialty assignments;
- a supervisor relationship;
- versioned requirement and policy fixtures;
- valid, expiring, expired, missing, conflicting, and duplicate-candidate evidence;
- one evidence version that supports more than one requirement;
- enrollment, contract, clearance, training, billing, local-program, capacity, and assignment examples;
- a synthetic restricted-data canary that must never reach the model;
- named synthetic requester, reviewer, releaser, auditor, and security-review users;
- expected findings, readiness dimensions, denied actions, and final human decision sequence.

No real person, provider, child, family, patient, bank, or taxpayer data is permitted.

### 18.2 Versioned implementation

The fixture will live under fixtures/katherine with:

- manifest.json for identity and relationships;
- policies.json and requirements.json for ratified synthetic rules;
- evidence metadata plus synthetic files;
- expected-readiness.json;
- expected-audit-sequence.json;
- a fixture version, content hashes, and change history.

Database seeding uses deterministic fixture identifiers. An accepted fixture is immutable; a change creates a new version and requires updated expected outputs.

### 18.3 Proof sequence

1. Start from a clean local/test database.
2. Seed Katherine and the synthetic role accounts.
3. Calculate requirement applicability through deterministic code.
4. Register candidate evidence and prove content-hash deduplication.
5. Quarantine the restricted-data canary before any model call.
6. Generate an AI classification proposal for an allowed synthetic document.
7. Prove that the unconfirmed proposal satisfies no prerequisite.
8. Affirmatively confirm it as the independent evidence reviewer.
9. Recalculate each affected readiness dimension and open findings.
10. Demonstrate that expiration changes the dimension but does not silently restrict operations.
11. Resolve the synthetic finding through an authorized human decision.
12. Prove the requester cannot self-release and the system administrator cannot release.
13. Complete release through the distinct authorized releaser with recent AAL2.
14. Verify the append-only audit sequence.
15. Reset and rerun to prove semantically equivalent deterministic results.

### 18.4 Katherine acceptance artifact

The generated golden-record report includes fixture hash/version, application commit, database migration version, policy version, engine version, AI model/schema version, test results, expected-versus-actual dimensions, denied-path evidence, audit-event sequence, known limitations, and unresolved decisions. Katherine proves the vertical slice only; it does not prove production scale, live integration behavior, or readiness for real data.

---

## 19. Bottom-up estimates by maturity level

Dollar illustrations use the G-22 assumption of $24/hour. The Phase 0 and Katherine figures are proposed milestone estimates. Production-intent and hardening ranges apply only to maturing the same Katherine vertical slice—not the complete platform, integrations, nine-provider suite, internal application, or provider portal.

### 19.1 Design/specification — Phase 0

| Work category | Hours | Keystone receives |
|---|---:|---|
| Packet traceability and gap/dependency register | 6 | Requirement map, complete register, implementability classification |
| Architecture and ADR | 6 | Selected architecture, ADR, component boundaries, version policy |
| Canonical data model | 9 | Data dictionary, relationship rules, ERDs, migration sequence |
| Readiness and transition design | 7 | Separate dimension definitions, calculation inputs, state/transition tables |
| Authorization, auth, and separation-of-duties design | 7 | RLS strategy, role matrix, identity/session design, negative-test matrix |
| API, AI, restricted-data, and job contracts | 6 | Endpoint/tool schemas, structured responses, pipeline and idempotency design |
| Cost, delivery, acceptance, and repository documentation | 4 | Three cost models, milestone SOWs, test/deployment/monitoring plan |
| **Total** | **45 hours / $1,080** | Complete Phase 0 design package |

### 19.2 Prototype implementation — Katherine

| Work category | Hours | Keystone receives |
|---|---:|---|
| Keystone-owned repo, environment, and CI scaffold | 7 | Repository, protected workflow, local setup, build/test pipeline |
| Schema, migrations, Supabase Auth, RLS, and scoped roles | 14 | Executable schema and policy tests |
| Practitioner record and requirements-checklist UI/API | 9 | Working login-to-checklist flow |
| Deterministic findings, readiness, guarded transitions, and audit | 14 | Versioned engine and append-only decision/audit path |
| Synthetic evidence, AI proposal, human confirmation, Katherine fixture | 10 | Advisory classification flow and repeatable golden record |
| Automated unit, integration, RLS-negative, and restricted-routing tests | 9 | CI test report and acceptance evidence |
| Demonstration, runbook, risks, and handoff | 5 | Recorded/live demo, setup/runbook, known limitations |
| **Total** | **68 hours / $1,632** | Katherine synthetic prototype; not a production system |

### 19.3 Production-intent implementation of the same vertical slice

| Work category | Range | Keystone receives |
|---|---:|---|
| Production file intake, scanning/OCR boundary, storage lifecycle | 18–26h | Approved ingestion implementation and failure paths |
| Durable workers, reconciliation, dead-letter/replay tooling | 14–20h | Multi-instance-safe operational job flow |
| Production-intent identity lifecycle and access administration | 12–18h | Provisioning, revocation, reviews, role-change controls |
| Data migration, policy-version operations, operator queues | 14–20h | Operational workflows replacing prototype shortcuts |
| Expanded tests and documentation | 14–20h | Production-intent regression and operations package |
| **ROM total** | **72–104h / $1,728–$2,496** | Same slice implemented with production intent; separately authorized |

### 19.4 Production hardening of the same vertical slice

| Work category | Range | Keystone receives |
|---|---:|---|
| Threat model, security review, dependency/container hardening | 12–18h | Resolved findings and security evidence |
| Load, failure, concurrency, and recovery testing | 12–18h | Test reports and remediation |
| Backups, restore drill, monitoring, alerting, runbooks | 12–18h | Recovery evidence and operator runbooks |
| Accessibility, browser, privacy, release checklist, final defect pass | 12–18h | Release-readiness evidence |
| **ROM total** | **48–72h / $1,152–$1,728** | Hardened vertical slice; full production authorization remains separate |

---

## 20. Independently authorized Upwork milestones

### Milestone 0 — Phase 0 design and specification

**Proposed amount:** $1,080 based on 45 hours at $24/hour. Hours explain the estimate; payment is tied to accepted deliverables and evidence.

**Exact deliverables**

- Final gap/question/dependency/assumption/decision register
- Requirement traceability and implementability matrix
- Approved architecture and ADR
- Canonical data dictionary and ERDs
- Readiness dimensions and formal transition tables
- RLS, RBAC, authentication, restricted-data, job, API, and AI-tool contracts
- Katherine fixture specification and expected-output manifest
- Three cost models
- Repository, testing, deployment, logging, monitoring, backup, and recovery plan
- Katherine milestone SOW and acceptance-test specification

**Explicit exclusions**

- Product implementation or deployable application
- Production migrations, live accounts, or real data
- Gmail/Drive, ChildLink, Elwyn, PROMISe/HCSIS, county, or joinder integration
- Production security certification, legal opinion, or policy authorship

**Dependencies and Keystone inputs**

- Complete controlling packet and source materials
- Written answers/owners for G-01 through G-22 as applicable
- Approval of selected architecture and Katherine synthetic-data owner
- Availability of Keystone technical, operations, compliance, and security reviewers

**Demonstration**

- Upwork technical-review meeting and repository walk-through
- Written meeting notes posted afterward in Upwork

**Automated tests**

- No application code is delivered, so product behavior tests are explicitly not applicable.
- Documentation CI will validate Markdown, internal links, Mermaid syntax/renderability, JSON Schema syntax, and table/identifier consistency.

**Acceptance evidence**

- Every requested Phase 0 artifact exists in the Keystone-controlled repository.
- Every unresolved item has an owner, type, impact, and required decision/source.
- No dangling register IDs or conflicting architecture/cost assumptions.
- Architecture, model, transitions, tools, and permissions are cross-referenced and internally consistent.

**Defect-resolution period**

- Five business days after consolidated Keystone acceptance feedback for in-scope corrections.

**Payment gate**

- Milestone is funded before work.
- Submission includes an acceptance checklist.
- Keystone approves payment when the checklist evidence satisfies the written milestone; elapsed hours alone do not trigger payment.

**Go/no-go for Katherine**

- Phase 0 accepted.
- G-02 architecture approved.
- G-03 Katherine fixture and expected results approved.
- Required Keystone-controlled accounts available.
- RLS/role/SoD model approved.
- No unresolved security or policy question blocks the synthetic flow.

### Milestone 1 — Katherine synthetic vertical-slice proof

**Proposed amount:** $1,632 based on 68 hours at $24/hour. Hours explain the estimate; payment is tied to accepted evidence.

**Exact deliverables**

- Keystone-owned repository, CI, environment manifest, and deployment assets
- Google SSO through Supabase Auth, MFA enforcement, scoped roles, and disabled-account flow
- Practitioner record with multi-organization-ready relationship structure
- Requirements checklist and deterministic applicability/expiration/missing-item logic
- Separate readiness-dimension calculations and findings
- Guarded review/release flow with audit history and separation-of-duties enforcement
- Synthetic evidence versions, AI classification proposal, and affirmative human confirmation
- Katherine seed/fixture, expected-output manifest, and repeatable demonstration
- Automated test suite and generated test report
- Setup, operations, risk, and limitation documentation

**Explicit exclusions**

- Real provider or production data
- PHI, child/family case information, SSNs, banking, tax, or direct-deposit data
- Live Gmail/Drive, ChildLink, Elwyn, county/joinder, PROMISe, HCSIS, or payer integration
- Nine-provider regression suite
- Provider portal
- Production ingestion/OCR/malware service
- Production HA/SLA, load certification, disaster-recovery certification, or full production hardening
- Autonomous AI acceptance, compliance decision, restriction, suspension, release, or reinstatement

**Dependencies and Keystone inputs**

- Milestone 0 accepted and Milestone 1 funded
- Keystone-owned GitHub, Supabase, AWS, Google, and OpenAI access
- Approved Katherine fixture, requirements, expected results, and policy version
- Named requester, reviewer, releaser, and security-test accounts
- Approved evidence taxonomy and restricted-data canary

**Demonstration requirements**

- Login → practitioner → requirements checklist → evidence proposal → human confirmation → deterministic readiness → review → human release decision → audit history
- Re-run from a clean database using the versioned Katherine fixture
- Demonstrate denied cross-organization and unauthorized-release attempts

**Automated tests and acceptance evidence**

| Acceptance behavior | Required evidence |
|---|---|
| Unauthorized and cross-scope users cannot read or mutate records | Passing RLS and API negative-test report |
| Expired evidence creates a finding and recalculates a dimension without silently restricting operations | Deterministic unit/integration test |
| Missing requirements are detected by code, not AI | Unit test with stable reason codes |
| AI response cannot satisfy a prerequisite before affirmative human confirmation | Integration test and audit sequence |
| AI cannot call release/restriction/suspension functions | Tool-contract and database-permission negative tests |
| Release requires authorized distinct human, current policy, and recent AAL2 | Guarded-function test and demo |
| Restricted-data canary is quarantined before any model call | Spy/mock assertion and security event |
| Duplicate/retried command produces one business effect | Idempotency and concurrency test |
| Katherine produces semantically equivalent deterministic results on repeat | Golden-record regression report |
| Every consequential action is attributable and immutable | Audit-catalog assertions |

**Defect-resolution period**

- Ten business days after consolidated acceptance feedback for reproducible in-scope defects.

**Payment gate**

- Milestone is funded before implementation.
- Submission includes the repository commit, deployment link, test report, demonstration, and acceptance checklist.
- Keystone approves payment after the written acceptance evidence passes; hours worked alone do not trigger payment.

**Go/no-go for the next milestone**

- Katherine acceptance suite passes with no open critical/high security defect.
- Keystone accepts the actual architecture and operating-cost findings.
- Nine-provider fixtures and authoritative rules are available.
- Any next scope is separately written, priced, funded, and authorized in Upwork.

---

## 21. Repository, ownership, deployment, and work-product control

At the start of each paid milestone, work will be created directly in Keystone-controlled accounts wherever the relevant resource exists:

- GitHub repositories, branches, issues, Actions workflows, and release artifacts
- Supabase organizations/projects, schemas, migrations, policies, Auth settings, Storage policies, Cron/Queue configuration, and backups
- AWS account resources, container registry, task definitions, secrets, logs, alarms, and deployment configuration
- Google Cloud/OAuth projects and approved scopes
- OpenAI project, approved model configuration, prompts, tool schemas, and evaluation fixtures
- Documentation, ADRs, data dictionaries, test fixtures, runbooks, diagrams, cost models, and acceptance evidence

Credentials are not transferred through source code or documentation. Keystone grants least-privilege access in its accounts and can revoke it. If an unavoidable temporary development artifact is created outside a Keystone account, it is listed in the milestone register and transferred before that milestone can be accepted. No milestone depends on waiting until the end of the entire project for handoff.

Repository proposal:

~~~
keystone-provider-readiness/
├── apps/web/                    # Next.js UI and server routes
├── packages/domain/             # deterministic rules and reason codes
├── packages/contracts/          # API, event, AI-tool, JSON Schemas
├── supabase/migrations/         # schema, grants, RLS, guarded functions
├── supabase/tests/              # pgTAP/RLS negative tests
├── fixtures/katherine/          # synthetic golden record and expectations
├── tests/                       # unit, integration, security, golden record
├── docs/                        # ADRs, ERDs, registers, runbooks, decisions
└── .github/workflows/           # validated CI and gated deployment
~~~

Production and non-production resources will be separated before real data is authorized. Phase 0 defines the separation; Katherine uses synthetic data only.

---

## 22. Logging, monitoring, backup, and recovery assumptions

- **Business audit:** append-only PostgreSQL events record actor, effective role/scope, action, entity/version, reason, policy version, correlation ID, and before/after hashes where appropriate.
- **Operational logs:** structured, redacted logs contain correlation IDs and stable error codes, not raw evidence or secrets.
- **Monitoring:** health, error rate, queue age/depth, dead-letter count, failed login/authorization attempts, model/schema failures, and reconciliation findings.
- **Alerts:** security-sensitive and exhausted-job events route to named Keystone responders; channels are decided in Phase 0.
- **Backups:** managed database backups and storage versioning are configured to the approved environment. Restore tests are part of production hardening, not Katherine.
- **Recovery:** production RPO/RTO, regional design, archive retention, and legal hold are not assumed; they require G-16.
- **Environment separation:** synthetic development/Katherine data remains separate from future pilot/production data and credentials.
- **Restricted categories:** V1 does not intentionally model or expose PHI, child/family case details, SSNs, banking, tax identifiers, or direct-deposit data to AI. Suspected content fails closed into quarantine.

---

## 23. Items not yet reliably estimable

The following cannot be fixed-price estimated from the current information:

- ChildLink and Elwyn integrations
- PROMISe, HCSIS, ITF Waiver, payer, or enrollment integrations
- County and joinder rule implementation
- Live Gmail and Drive ingestion/reconciliation
- Nine-provider regression suite content and coverage
- Production document malware scanning/OCR until G-20 is resolved
- Production availability, retention, backup, disaster recovery, and support obligations until G-16 is resolved
- Full internal application beyond the Katherine slice
- Provider portal
- Legal, contractual, and policy-ratification work

These are explicit exclusions, not assumptions hidden in the Phase 0 or Katherine prices.

---

## 24. Proposed next step

1. Keystone reviews this revision in Upwork.
2. Remaining questions are resolved in an Upwork technical-review meeting.
3. I post written meeting notes in Upwork.
4. Keystone and I finalize the Phase 0 deliverables, amount, acceptance evidence, and exclusions in an independently funded Upwork milestone.
5. Only after Phase 0 acceptance may Keystone choose whether to authorize Katherine through a separate funded milestone.

No later milestone, integration, production activity, or scope expansion is authorized by this proposal.

---

## 25. Technical reference baseline

- Node.js releases: https://nodejs.org/en/about/previous-releases
- Next.js 16 upgrade/runtime requirements: https://nextjs.org/docs/app/guides/upgrading/version-16
- Supabase Row Level Security: https://supabase.com/docs/guides/database/postgres/row-level-security
- Supabase MFA: https://supabase.com/docs/guides/auth/auth-mfa
- Supabase Cron: https://supabase.com/docs/guides/cron
- Supabase Queues/pgmq: https://supabase.com/docs/guides/queues
- Supabase pricing: https://supabase.com/pricing
- AWS Fargate pricing: https://aws.amazon.com/fargate/pricing/
