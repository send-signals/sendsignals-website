# Terms & Conditions — DRAFT (requires legal review)

**Last updated:** `[LEGAL REVIEW: publication date]` · **Version:** draft

These terms govern access to and use of the Send Signals platform by schools and
their staff and pupils. They sit alongside the **service agreement / order form**
and the **Data Processing Agreement (DPA)** between
**Send Signals Limited** (company no. 17147174) and the school.
`[LEGAL REVIEW: confirm the contractual structure — these terms + order form + DPA]`

Send Signals is a UK school wellbeing **check-in** platform. Pupils tap a simple
red / amber / green "how am I" signal at set times of day, can raise a short
welfare "flag", and may attach a brief note chosen from pre-set options (pupils
have no free-text input). Staff see those signals and
flags and decide what to do. **Send Signals flags low wellbeing for school staff
to act on — it is not a clinical, crisis or safeguarding service. The school's
staff carry out the actual safeguarding.**

## 1. The service

Send Signals provides a pupil wellbeing check-in platform for schools, accessed
via the web app and (where applicable) native mobile apps. Access is provided
through school-managed accounts (e.g. Microsoft/Google sign-in) or credentials
issued by the school. The data subjects are **children**, so the service is built
to UK GDPR and is **designed around the principles of the ICO Age Appropriate
Design Code (Children's Code)**: data minimisation, the best interests of the
child, and no profiling of children for marketing. `[LEGAL REVIEW: confirm
whether the Children's Code applies in full given Send Signals' processor role,
or only its principles — ICO edtech guidance is role-dependent]`

## 2. Accounts & access

- Schools are responsible for who they invite and for managing their users.
- Staff and pupils must keep their access credentials secure and use the service
  only for its intended educational/wellbeing purpose.
- Pupils are added by their school; pupils do not self-register.
- Permission tiers limit what staff can see and do (e.g. an "admin" account owner
  manages invites, authentication and billing; a "full access" pastoral account
  can view and act on pupil wellbeing data; a "hub access" account is view-only
  by default).

## 3. Acceptable use

The platform must be used in line with the school's policies and UK law. Users
must not attempt to access another school's or another pupil's data, disrupt the
service, or use it for any unlawful purpose. The platform enforces strict
**tenant isolation** in the database (see section 11) — one school cannot read
another's data, and a pupil can only ever see their own.

## 4. Data protection — roles

The **school is the data controller** for pupil and staff personal data; it
decides the purposes and means of processing.
`[LEGAL REVIEW: confirm the school is the controller for all in-scope data]`

Where Send Signals processes personal data on the school's behalf, it acts as a
**data processor** on the school's documented instructions under the **Data
Processing Agreement** (UK GDPR Article 28). The DPA governs the detail of
security, sub-processing, international transfers, breach notification, assistance
with data-subject requests, and deletion/return of data on termination. See also
the **Privacy Policy**.

## 5. Lawful basis & special-category data

Pupil wellbeing, welfare-flag and any SEND/health information is **special
category data** under UK GDPR Article 9. The **school, as controller, determines
and documents the lawful basis** — both the Article 6 basis (typically the
school's **public task**) and the additional Article 9 condition for special
category data (e.g. **Article 9(2)(g) substantial public interest** in connection
with safeguarding / education, together with the relevant Schedule 1, Data
Protection Act 2018 condition, or another condition the school identifies).
`[LEGAL REVIEW: confirm the Art 6 basis + Art 9 condition wording — this is the
school's to set; do not assert one on the school's behalf]`

Send Signals does not decide the lawful basis; it provides tools to support the
school in meeting it. The school is responsible for providing privacy information
to pupils and parents/carers and for obtaining any consent it relies on.

## 6. School responsibilities

The school, as controller, is responsible for:

- establishing and documenting the lawful basis for processing pupil data;
- providing privacy information to pupils and parents/carers;
- obtaining any consent it chooses to rely on;
- handling data-subject requests it receives (Send Signals assists as processor —
  see section 9); and
- making appropriate **safeguarding and welfare decisions**.

Send Signals provides tools that surface wellbeing signals and welfare flags for
staff to act on, but **does not replace professional judgement or the school's
safeguarding duties.**

## 7. Retention

By default, pupil check-ins and messages are retained for **365 days**, after
which a scheduled purge deletes them. This window is **configurable per school**
(subject to a minimum of 30 days). Welfare-flag disclosure messages follow the
**same school retention window (default 365 days, 30-day minimum)** — **Send
Signals is not the school's long-term safeguarding record.** At the end of the
window, a flag the school has marked as **recorded in its own safeguarding
system** is deleted by the routine purge; a flag not yet marked as recorded is
**held — and surfaced to staff in the app —** until it is marked recorded or a
hard backstop of **180 days past the window** passes, whichever comes first (so
an unrecorded flag may be retained for up to around 545 days in total). Before
deletion the school can review, export and action a flag; after deletion only
minimal, no-pupil-detail evidence of the flag and its deletion (school, tier,
timestamps, deletion reason) is kept. Educational records that the school maintains (e.g. provision/review
records and accounts) are not auto-deleted and require an explicit operator action
to remove.

On a school offboarding, its data is deleted or returned in line with the DPA.
`[LEGAL REVIEW: confirm retention periods + offboarding deletion/return terms
match the DPA and the school's records-retention policy]`

## 8. Children's data

The data subjects are children, so Send Signals is **designed around the
principles of the ICO Age Appropriate Design Code (Children's Code)**: data
minimisation, the best interests of the child, no behavioural advertising, and no
third-party tracking or profiling of pupils. `[LEGAL REVIEW: confirm whether the
Children's Code applies in full given Send Signals' processor role, or only its
principles — ICO edtech guidance is role-dependent]` Pupils can only ever see
their **own** data. Welfare-alert emails are data-minimised (no pupil name or
check-in content), and push-notification payloads are generic by default — see
the Google Firebase Cloud Messaging entry in section 10 for full detail,
including the optional "Show student details on lock screen" school setting
(OFF by default, not recommended).

## 9. Data-subject rights

Under UK GDPR, data subjects have the right to access, rectification, erasure,
restriction, portability and to object. Because the **school is the controller**,
these requests are made to (and decided by) the school; Send Signals supports the
school as processor.

The platform provides an **admin-only pupil erasure** function that permanently
deletes a pupil's full data footprint when the school instructs it (a typed
confirmation is required, and the action itself is logged with no pupil
identifying detail). `[LEGAL REVIEW: confirm how subject-access requests are routed
and the school↔Send Signals responsibility split for responding within statutory
deadlines]`

## 10. Sub-processors

Send Signals uses a small number of vetted sub-processors to run the service.
Pupil data is stored at rest in the UK (Supabase, London region). The
authoritative, maintained list (with locations and any transfer safeguards) lives
in the **Data Processing Agreement**; the providers in use are:

| Provider | Purpose | Location / notes |
|----------|---------|------------------|
| Supabase | Database, authentication & file storage | UK (London region) — pupil data stored at rest in the UK |
| Vercel | Application hosting / CDN | Global edge; US-headquartered — not pinned to a single region; processes data only in transit. `[LEGAL REVIEW: confirm transfer mechanism per provider]` |
| Google Firebase Cloud Messaging | Native mobile push notifications | US/global — by default, push payloads are generic (no pupil name, check-in rating or welfare-disclosure content; e.g. "A welfare flag was raised. Open the Action Hub for details."). If a school turns on the optional "Show student details on lock screen" setting (OFF by default, not recommended), wellbeing-alert and welfare-flag push messages then include the pupil's first name and, for welfare-flag disclosures, the disclosure message text — visible on a locked device. A school enabling this does so under its own policy/risk assessment. The in-app Action Hub (behind sign-in) always shows full detail regardless of this setting. `[LEGAL REVIEW: confirm transfer mechanism per provider]` |
| Resend | Transactional email | US — Transactional email: staff/admin emails; data-minimised welfare-alert emails (no pupil name or check-in content); and student-access/login emails sent to a pupil's own email address containing a personal sign-in link and the school name (the pupil's name is NOT included). Resend therefore processes pupil email addresses and sign-in links. `[LEGAL REVIEW: confirm the Resend DPA covers children's personal data]` `[LEGAL REVIEW: confirm transfer mechanism per provider]` |
| Stripe | Billing / payments (school-facing) | US/global; UK entity for UK billing — processes the **school's** payer/billing details only, **no pupil data**. `[LEGAL REVIEW: confirm transfer mechanism per provider]` |
| Cloudflare Turnstile | Bot / abuse protection on the public demo and sign-up forms | US/global — no pupil data; used to protect public forms from automated abuse. `[LEGAL REVIEW: confirm transfer mechanism per provider]` |

An **optional** AI help/operations assistant (Anthropic (Claude); US; optional,
no pupil data) is available when configured. It receives **only** a staff member's
typed how-to question (and, for operational alerts, school names + operational
metadata) — **never pupil records, ratings, welfare flags or SEND data** — and is
hard-walled from special-category data. `[LEGAL REVIEW: confirm transfer mechanism
per provider]`

Send Signals does not sell data, use it for advertising, or share it outside the
pupil's school team, except where required by law or to protect a child's safety.
`[LEGAL REVIEW: confirm the final sub-processor list, locations and transfer
mechanisms in the DPA]`

## 11. Security

Send Signals applies, among other measures:

- **Tenant isolation** via Postgres Row-Level Security — one school can never read
  another's data, and a pupil can only see their own; this is tested
  automatically in the build pipeline.
- **Secure session cookies.** Authentication uses secure, same-site Supabase
  session cookies. In the current browser client these cookies are readable by
  the application's JavaScript, so we also rely on TLS, the SameSite attribute, a
  Content-Security-Policy, database tenant isolation (RLS), least-privilege
  access and audit logging.
- **Two-factor authentication (2FA)** available for admin accounts. `[LEGAL REVIEW:
  confirm 2FA is enforced for all admin accounts at launch]`
- **Audit logging** of configuration and permission changes.
- **Encryption in transit** (TLS/HTTPS).
- **Database backups**, with **point-in-time recovery (PITR) being enabled for
  launch**. `[LEGAL REVIEW: confirm PITR is enabled on the production plan at
  launch]`
- **Least-privilege** access and audited use of privileged keys.

`[LEGAL REVIEW: confirm encryption-at-rest and backup/PITR commitments are stated
to match the DPA's security schedule and are not over-stated]`

## 12. International transfers

Pupil data is stored at rest in the UK (Supabase, London region). The application
is served over Vercel's global edge network, which is not pinned to a single region
and processes data only in transit. Some sub-processors (email, push notifications,
billing, bot-protection) operate outside the UK — see the sub-processor list in
section 10. Where personal data is transferred to them, an
appropriate transfer safeguard is relied on (e.g. the UK International Data Transfer
Agreement / Addendum to the EU SCCs). `[LEGAL REVIEW: confirm transfer mechanism
per provider]`

## 13. Cookies & similar technologies

The app uses **strictly-necessary cookies only** (the authentication session),
plus the **Cloudflare Turnstile** challenge cookie on public forms. There is
**no third-party advertising, analytics or cross-site tracking** — no Google
Analytics, no Vercel Analytics, no advertising pixels. (Only first-party,
PII-stripped operational error/telemetry is collected to keep the service
healthy.) See the **Cookie Policy**.

## 14. Availability & support

We aim to provide a reliable, continuously-deployed service but do not guarantee
uninterrupted availability. Planned changes and material incidents will be
communicated to schools. `[LEGAL REVIEW: confirm any service-level / uptime
commitment in the service agreement, or state explicitly that none is given]`

## 15. Intellectual property

All content, design and code is the property of
**Send Signals Limited**. The Send Signals name and logo are the subject of
trademark applications filed April 2026 `[LEGAL REVIEW: confirm registration
status]`. Schools retain ownership of their own data.

## 16. Liability

Nothing in these terms excludes liability that cannot be excluded by law. Subject
to that, liability is limited as set out in the service agreement.
`[LEGAL REVIEW: liability cap, carve-outs and exclusions — to be set by the
solicitor]` Send Signals is a wellbeing-flagging support tool and does **not**
replace the school's professional and statutory responsibilities, including its
safeguarding duties.

## 17. Termination

Either party may end the service as set out in the service agreement. On
termination, pupil/school data is deleted or returned in line with the Data
Processing Agreement.

## 18. Complaints & the ICO

If a data subject is unhappy with how their data has been handled, they should
raise it with their **school** (the controller) in the first instance. They also
have the right to complain to the **Information Commissioner's Office (ICO)**,
ico.org.uk, though we'd welcome the chance to help resolve it first.

## 19. Changes to these terms

We may update these terms from time to time. Material changes will be notified
to schools in advance, and the "last updated" date will be revised; continued
use of the service after a change takes effect constitutes acceptance of the
updated terms. `[LEGAL REVIEW: confirm the variation mechanism — notice period,
and whether school consent (rather than notice) is required for material
changes]`

## 20. Governing law

These terms are governed by the law of England & Wales and subject to the
exclusive jurisdiction of its courts.

## 21. Contact

- General: hello@sendsignals.co.uk
- Data protection / privacy: privacy@sendsignals.co.uk
- **Send Signals Limited**, a company registered in England & Wales (company no. **17147174**), registered office **71-75 Shelton Street, Covent Garden, London, WC2H 9JQ**. ICO registration number **ZC138681**. VAT registration number **GB527441102**.
