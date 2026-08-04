# Examity (examity)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Examity is an online exam proctoring and test-integrity platform used by universities, certification bodies, and enterprises to authenticate test-takers and monitor online assessments. It offers automated (AI/ML) proctoring, live proctoring, audit-based (record-and-review) proctoring, and ID verification, and integrates with major learning management systems including Canvas, Blackboard, D2L Brightspace, Moodle, Sakai, and Schoology.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/examity/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/examity/refs/heads/main/apis.yml)

## Access Model — please read

Examity does **not** publish a public, self-service developer API. There is no developer portal, no public API reference, and no published OpenAPI. Its programmatic surface is a **partner / LMS integration**:

- **Single sign-on via IMS LTI** — provisioned with a **consumer key** and a **shared secret**, used to launch Examity from within an LMS.
- **A partner integration REST API** — used by platform vendors to register exams, schedule proctoring appointments, launch monitored sessions, and retrieve completion status and integrity flags.

Both are **gated behind an institutional/partner agreement**. Integration keys and the integration manual are issued on request via **developers@examity.com**.

Because no endpoints, paths, or base URLs are publicly documented, the APIs listed below are **modeled** (`endpointsModeled: true`) from Examity's well-known integration flow with LMS partners — they are an honest map of the capability surface, **not** a transcription of a published reference. No OpenAPI, endpoint list, base URL, or rate-limit/FinOps document is asserted, because none is public.

## Tags

- Proctoring
- Exam Integrity
- Online Assessment
- EdTech
- LMS Integration
- Identity Verification
- Test Security

## Timestamps

- **Created:** 2026-07-05
- **Modified:** 2026-07-05

## APIs (modeled)

### Examity Exams API
Register and manage the exams to be proctored — name, proctoring type (automated / live / audit), duration, allowed resources, rules, and the launch URL handed back to the LMS.

### Examity Appointments (Scheduling) API
Create, reschedule, and cancel proctoring appointments for a test-taker against a registered exam, and query available proctor slots for live proctoring.

### Examity Sessions API
Launch and track a proctoring session — authenticate the test-taker, start the monitored exam session, and check live session status.

### Examity Results & Flags API
Retrieve session outcomes after a proctored exam — completion status, integrity/violation flags, proctor notes, review verdicts, and links to recorded session evidence, for posting results back to the LMS gradebook.

### Examity Users API
Provision and manage test-takers, instructors, and administrators, including profile details used for identity verification. In practice most user context arrives through the LTI SSO handshake.

## Pricing

Examity does not publish a price list. Pricing is a **custom quote** scoped to an institution's exam volume and proctoring mix, arranged through sales. Publicly reported reference points (indicative only, not an Examity price list) put per-exam cost in the ~$4–$30+ range depending on proctoring type. See [`plans/examity-plans-pricing.yml`](plans/examity-plans-pricing.yml).

## WebSocket / Real-time

**No.** Examity publishes no documented public WebSocket (or any server-push / SSE) API. See [`review.yml`](review.yml).

## Common Properties

- [Website](https://www.examity.com)
- [LinkedIn](https://www.linkedin.com/company/examity)
- [Plans](plans/examity-plans-pricing.yml)
- [Integration contact](mailto:developers@examity.com)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
