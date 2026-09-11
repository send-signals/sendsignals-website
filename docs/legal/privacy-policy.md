# Privacy Policy — DRAFT (requires legal review)

**Last updated:** [LEGAL REVIEW: publication date] · **Version:** draft

> This policy describes how Send Signals handles personal data **as a processor**
> acting on schools' instructions. Schools (as controllers) publish their own
> privacy information to pupils and parents. See the Data Processing Agreement
> (DPA).

## 1. Who we are

Send Signals is a student wellbeing and SEND-support platform used by UK schools.
Pupils tap a simple red / amber / green "how am I" signal at set times; staff see
those signals and any welfare flags and respond. **Send Signals flags low
wellbeing for school staff to act on — it is not a clinical, crisis or
safeguarding service. The school's staff carry out the actual safeguarding.**

The service is operated by **Send Signals Limited**, a
company registered in England & Wales (company no. **17147174**),
registered office **71-75 Shelton Street, Covent Garden, London, WC2H 9JQ**.

- Privacy / data protection contact: **Nicola Youngman (Data Protection Lead)** — **privacy@sendsignals.co.uk**
- ICO registration number: **ZC138681**
- VAT registration number: **GB527441102**

_We have assessed whether a statutory Data Protection Officer is required and, at current scale, have appointed a named Data Protection Lead; we will review this as the service grows._ `[LEGAL REVIEW: confirm the DPO assessment + review triggers]`

## 2. Our role — the school is the controller, we are the processor

Send Signals is provided to schools. The **school decides how and why pupil data
is used, so the school is the data controller** and **Send Signals acts as a data
processor** on the school's documented instructions, under a Data Processing
Agreement (UK GDPR Article 28). We only process pupil data to deliver the service
to that school; we do not use it for our own purposes.

Because the school is the controller, the school is responsible for the lawful
basis, for telling pupils and parents how their data is used, and for handling
data-subject requests (see sections 5 and 12). This policy explains, transparently,
how data is handled within the service.

`[LEGAL REVIEW: the controller/processor model was confirmed with the solicitor
(2026-06-28); remaining — confirm the split of responsibilities with the school
in the DPA.]`

## 3. Where Send Signals is itself the controller

Separately from acting as each school's **processor** for pupil check-in data,
**Send Signals Limited** is itself a **controller** for a limited set of its own
business processing: website enquiries and demo requests; support messages;
billing and payment records (processed with Stripe); operational and security
logs; and first-party product telemetry. For these limited purposes Send Signals'
own lawful basis applies (for example, legitimate interests or the performance of
a contract). `[LEGAL REVIEW: confirm the Art 6 lawful bases for Send Signals' own
controller processing]`

## 4. The data we process

- **Pupil identity:** name, school email address and a school-assigned
  identifier (typically from the school's Microsoft/Google account).
- **Wellbeing / SEND information (special category data):** check-in ratings
  (green/amber/red), time-slot check-ins (e.g. morning, each lesson, end of day),
  pre-set signal/message and note selections (pupils have no free-text input —
  every check-in, note and disclosure is chosen from pre-set options, though the
  selections remain highly sensitive), welfare "flags"/disclosures, and SEND
  profile fields the school maintains.
- **Staff accounts:** name, role, work email, and authentication identifiers.
- **Technical data:** timestamps of interactions, device/session identifiers, and
  push-notification tokens needed to run and secure the service. We keep a short,
  pseudonymised error/heartbeat log to spot crashes and broken releases; it
  contains **no pupil names or check-in content** and strips anything that could
  carry a login token.

We practise **data minimisation** — we collect only what the service needs.

## 5. Lawful basis

The **school (as controller) determines and documents the lawful basis**; the
notes below are indicative only and must be confirmed by the school.

- **Personal data (UK GDPR Art 6):** typically the school's **public task**
  (Art 6(1)(e)) in providing education and pastoral/SEND support.
  `[LEGAL REVIEW: confirm Art 6 basis with the school.]`
- **Special category data (UK GDPR Art 9):** wellbeing/SEND data is special
  category data and additionally needs an Art 9 condition — typically
  **substantial public interest** (Art 9(2)(g), e.g. safeguarding of children)
  under the relevant Schedule 1, Data Protection Act 2018 condition (e.g.
  paragraph 18, safeguarding of children and individuals at risk). `[LEGAL
  REVIEW: confirm the Art 9 condition + DPA 2018 Schedule 1 condition with the
  school.]`

Send Signals does not set the lawful basis; we support the basis the school has
chosen.

## 6. How the data is used

Solely to support pupil wellbeing and SEND provision within the pupil's own
school: to let pupils check in, to surface concerns to the school's SEND/pastoral
team, to raise the alerts the school has configured, and to produce the school's
own provision/progress records. **We never sell data, use it for advertising, or
share it outside the pupil's own school team** — other than with the
sub-processors in section 8, or where required by law or to protect a child's
safety. We do not use pupil data to train AI models (see section 8). Alerts and
welfare flags only prompt school staff to look and decide — no decision about a
pupil is made solely by automated means (no UK GDPR Article 22 automated
decision-making).

## 7. Children's data

The data subjects are children, so we take particular care. The service is
**designed around the principles of the ICO Age Appropriate Design Code
(Children's Code)**: data minimisation and the **best interests of the child**
are built in. A pupil can only ever see their **own** data — never another
pupil's (enforced in the database, see section 11). We do not profile children
for marketing and run **no third-party advertising or tracking** of any kind.
`[LEGAL REVIEW: the principles-only Children's Code approach was agreed with the
solicitor (2026-06-28); remaining — confirm whether the Code applies in full to
the native app / app-store distribution]` `[LEGAL REVIEW: confirm whether a
DPIA is held by the school.]`

## 8. Who we share data with (sub-processors)

We use a small number of carefully chosen providers to run the service. We do not
add or change a sub-processor that handles pupil data without notice to schools as
required by the DPA.

| Provider | Purpose | Pupil data? | Location | Notes |
|----------|---------|-------------|----------|-------|
| Supabase | Database, authentication & storage | Yes | UK (London region) | Row-Level Security enforces per-school isolation; primary data store; pupil data stored at rest in the UK |
| Vercel | Application hosting / CDN | In transit | Global edge; US-headquartered | Serves the app and runs server functions; not pinned to a single region; processes data only in transit; data at rest lives in Supabase (UK) `[LEGAL REVIEW: confirm transfer mechanism per provider]` |
| Google Firebase Cloud Messaging (FCM) | Native push notifications (Android/iOS) | Device token; by default a generic prompt only | US/global | By default, push-notification payloads are generic and contain no pupil name, check-in rating or welfare-disclosure content (e.g. "A welfare flag was raised. Open the Action Hub for details."). If a school turns on the optional "Show student details on lock screen" setting (OFF by default, not recommended), wellbeing-alert and welfare-flag push messages then include the pupil's first name and, for welfare-flag disclosures, the disclosure message text — visible on a locked device. A school enabling this does so under its own policy/risk assessment. The in-app Action Hub (behind sign-in) always shows full detail regardless of this setting. `[LEGAL REVIEW: confirm transfer mechanism per provider]` |
| Resend | Transactional email | Yes — pupil email addresses & sign-in links | US | Transactional email: staff/admin emails; data-minimised welfare-alert emails (no pupil name or check-in content); and student-access/login emails sent to a pupil's own email address containing a personal sign-in link and the school name (the pupil's name is NOT included). Resend therefore processes pupil email addresses and sign-in links. `[LEGAL REVIEW: confirm the Resend DPA covers children's personal data]` `[LEGAL REVIEW: confirm transfer mechanism per provider]` |
| Cloudflare Turnstile | Bot/abuse protection on public sign-up & demo forms | No pupil data | US/global | A challenge cookie only; protects the public website, not the pupil app `[LEGAL REVIEW: confirm transfer mechanism per provider]` |
| Stripe | Subscription billing | No pupil data — school/payer billing only | US/global; UK entity for UK billing | Processes the school's billing; pupils' data never reaches Stripe `[LEGAL REVIEW: confirm transfer mechanism per provider]` |

**Optional AI assistant (only if a school/operator enables it):** an admin "ops"
and in-app staff help assistant uses **Anthropic (Claude)** (US; optional, no pupil
data). It receives only **school names and operational/technical information** to
answer "how do I…" and incident questions — **no pupil data, ratings, welfare flags
or SEND data is ever sent to it**, and it is only active when an API key is
configured. `[LEGAL REVIEW: confirm transfer mechanism per provider]`

We do not share data with any other third parties except where required by law or
to protect a child's safety.

## 9. International transfers

Pupil data is stored at rest in the UK (Supabase, London region). The application
is served over Vercel's global edge network, which is not pinned to a single region
and processes data only in transit. Some sub-processors (email, push notifications,
billing, bot-protection) operate outside the UK — see the sub-processor list in
section 8. Where personal data is transferred to them we
rely on an appropriate transfer safeguard, such as the UK International Data
Transfer Agreement (IDTA) or the UK Addendum to the EU Standard Contractual
Clauses. Push-notification payloads are generic by default (no pupil name,
check-in rating or welfare-disclosure content) — see the Google Firebase Cloud
Messaging entry in section 8 for full detail, including the optional "Show
student details on lock screen" school setting (OFF by default, not
recommended). Welfare-alert emails are data-minimised (no pupil
name or check-in content); student-access/login emails sent to a pupil's own
email address contain a personal sign-in link and the school name but not the
pupil's name. `[LEGAL REVIEW: confirm transfer mechanism per provider]`

## 10. Retention

We keep data only as long as needed for the school's wellbeing/SEND purposes, and
the school can configure the period.

- **Default retention:** **365 days** for pupil check-ins and messages
  (configurable per school). A scheduled purge runs daily and deletes check-ins
  and messages older than the school's chosen window (with a 30-day minimum
  floor).
- **Welfare flags / disclosures:** these follow the **school's retention window
  (default 365 days, 30-day minimum)** — **Send Signals is not the school's
  long-term safeguarding record.** At the end of the window, a flag the school
  has marked as **recorded in the school's own safeguarding system** is deleted
  by the routine purge. A flag that has **not** been marked as recorded is not
  deleted silently: it is **held — and surfaced to staff in the app —** until
  the school marks it as recorded or a hard backstop of **180 days past the
  window** passes, whichever comes first (so an unrecorded flag may be retained
  for up to around 545 days in total). Before deletion the school can review,
  export and act on a flag; after deletion we keep only **minimal evidence with
  no pupil detail** (school, tier, timestamps and deletion reason) that a flag
  existed and was deleted. It is the school's responsibility, as controller, to
  record disclosures in its own safeguarding system.
- **Educational records** (e.g. SEND review/provision records) are **not** removed
  by the routine purge — those require explicit operator action.
- **Operational logs:** security auth-failure logs and email-delivery logs are
  kept ~90 days; pseudonymised error/heartbeat telemetry ~30 days.

On a school offboarding, its data is deleted or returned in line with the DPA.
`[LEGAL REVIEW: confirm offboarding deletion/return terms + any leaver/account
retention period.]`

## 11. How we protect data

- **Tenant isolation** in the database via Postgres Row-Level Security — one
  school can never read another's data, and a pupil can only see their own. This
  is tested automatically in our build pipeline.
- **UK data residency** for the pupil database — pupil data is stored at rest in
  the UK (Supabase, London region).
- **Encryption in transit** (HTTPS with HSTS), **encryption at rest provided by
  the database platform** `[LEGAL REVIEW: confirm at-rest encryption on the
  production Supabase plan]`, and an **enforced Content-Security-Policy**.
- **Secure sessions** — Authentication uses secure, same-site Supabase session
  cookies. In the current browser client these cookies are readable by the
  application's JavaScript, so we also rely on TLS, the SameSite attribute, a
  Content-Security-Policy, database tenant isolation (RLS), least-privilege
  access and audit logging.
- **Two-factor authentication (2FA)** available for admin accounts. `[LEGAL REVIEW:
  confirm 2FA is enforced for all admin accounts at launch]`
- **Least-privilege access** and **audit logging** of configuration and permission
  changes.
- **Backups**, with **point-in-time recovery (PITR) being enabled for launch**.
  `[LEGAL REVIEW: confirm PITR is enabled on the production plan at launch]`
- **Data minimisation in notifications** — welfare-alert emails contain no pupil
  name or check-in content, and push-notification payloads are generic by
  default (see the Google Firebase Cloud Messaging entry in section 8 for full
  detail, including the optional "Show student details on lock screen" school
  setting, OFF by default and not recommended).
- **Breach notification** — if a personal-data breach affects a school's data,
  we notify the affected school without undue delay (48-hour target) and assist
  it; the school, as controller, handles any UK GDPR Article 33 notification to
  the ICO.

No system is perfectly secure, but we work to protect data with appropriate
technical and organisational measures.

## 12. Your rights

Under UK GDPR, data subjects (pupils, or those acting for them) have the right to
**access, rectification, erasure, restriction, portability and to object**.

Because the **school is the controller**, requests are normally made to the
school, which decides how to respond; we support the school as its processor. To
exercise a right, contact your school's data protection / SEND team. If you
contact us directly (privacy@sendsignals.co.uk) we will pass the request to the
relevant school. `[LEGAL REVIEW: confirm the DSAR routing wording matches the
DPA.]`

To support erasure, the service includes an **admin-only function for a school to
permanently delete an individual pupil's data**, and we track erasure requests
against their statutory deadline.

## 13. Complaints

If you are unhappy with how your data has been handled, please raise it with your
school first, as the controller. You can also make a data-protection complaint to
us at privacy@sendsignals.co.uk — we will acknowledge it promptly, investigate it
and keep you updated, and tell you the outcome without undue delay (and in any
event within 30 days). You also have the right to complain to the **Information
Commissioner's Office (ICO)** at ico.org.uk — though we'd welcome the chance to
help resolve it first.

## 14. Cookies

The pupil and staff apps use **strictly-necessary cookies only** — the
authentication session cookie needed to keep you signed in. The public sign-up /
demo forms also use **Cloudflare Turnstile's challenge cookie** for bot
protection. We use **no third-party advertising or tracking cookies, and no
third-party web analytics** (e.g. no Google Analytics, Vercel Analytics, or
similar). See the separate Cookie Policy for detail.

## 15. Changes

We may update this policy; the "last updated" date will change and material
changes will be communicated to schools.

## 16. Contact

privacy@sendsignals.co.uk · hello@sendsignals.co.uk
