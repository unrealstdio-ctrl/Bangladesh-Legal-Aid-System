# Bangladesh Legal Aid System (BLAS)

## Complete Requirement Analysis & System Specification

> **Project Type:** Online Legal Aid Service System\
> **Primary Scope:** Legal-aid access, assisted case intake,
> accessibility, mediation support, human-officer escalation, case
> tracking, and secure communication\
> **Design Principle:** AI-assisted, human-controlled,
> accessibility-first, safety-aware, and legally accountable\
> **Primary Users:** Citizens / Applicants, Assisted or Proxy Reporters,
> District Legal Aid Officers (DLAOs), Mediators, Panel Lawyers, System
> Administrators\
> **Core Operational Concept:** A citizen may submit a case manually
> after verification, while users who cannot independently operate the
> conventional interface may use an AI-assisted voice/conversational
> workflow. AI prepares and organizes information and supports triage,
> but legal decisions and final case actions remain under authorized
> human officers.

------------------------------------------------------------------------

# 01. System Objectives

## 01.1 Primary Objectives

-   Build a unified online legal-aid access platform for Bangladesh.
-   Allow verified citizens to initiate and manage legal-aid requests.
-   Allow a person to report a case manually when they can use the
    normal application interface.
-   Provide an accessible AI-assisted pathway for people who cannot
    independently complete conventional digital forms.
-   Support Bangla voice interaction, including regional speech/dialect
    variations where technically supported.
-   Convert spoken information into structured case information.
-   Handle incomplete information without inventing or assuming missing
    facts.
-   Clearly distinguish confirmed information, applicant-provided
    information, proxy-provided information, and system-generated
    summaries.
-   Provide legal-information and awareness assistance without replacing
    a lawyer, mediator, DLAO, court, or other authorized decision-maker.
-   Support pre-case mediation where the matter is suitable and
    authorized for mediation.
-   Support escalation from intake to the nearest/relevant District
    Legal Aid Office for human review.
-   Identify urgent safety situations and provide an appropriate
    emergency escalation workflow subject to authorized policy and
    government-supported communication channels.
-   Provide low-bandwidth and voice-centric access for people with
    limited connectivity or basic phones.
-   Provide accessibility support for people with visual, physical,
    technological, or other relevant access limitations.
-   Prevent incomplete digital forms, lack of digital literacy, or lack
    of immediate NID access from automatically causing a potentially
    eligible request to disappear from the system.
-   Maintain secure case records and strictly restrict sensitive
    communication information.
-   Maintain a complete, traceable case lifecycle from intake through
    resolution or closure.

------------------------------------------------------------------------

# 02. Core System Principles

## 02.1 Human-in-the-Loop

-   AI is a decision-support and assistance layer.
-   AI must not independently determine the legal outcome of a case.
-   AI must not independently issue legal notices.
-   AI must not independently register a court case.
-   AI must not independently reject a citizen's legal-aid request.
-   AI-generated summaries, classifications, risk indicators, and
    suggested next actions must remain reviewable by an authorized human
    officer.
-   Final legal, mediation, escalation, representation, and
    case-management decisions must remain with authorized human
    personnel.

## 02.2 Consent & Verification

-   The system must distinguish:
    -   Identity verification
    -   Case-information confirmation
    -   Consent for legal-aid assistance
    -   Consent for communication
    -   Consent for proxy-assisted reporting
    -   Consent for mediation
    -   Consent for relevant information sharing
-   Information supplied by a third party must not automatically be
    treated as verified victim/applicant information.
-   Unverified information must remain explicitly labeled until
    confirmed through an approved process.
-   The system must support a transition from proxy-reported information
    to directly confirmed applicant information.

## 02.3 Accessibility-First

-   The system must not depend exclusively on visual web forms.
-   The system must support:
    -   Screen-reader compatible interfaces
    -   Keyboard navigation
    -   Large and clear controls
    -   Bangla-first interaction
    -   Voice-first workflows
    -   Audio prompts
    -   Voice responses
    -   Low-bandwidth operation
    -   Basic-phone/IVR-compatible workflows where the required service
        infrastructure is available
-   CAPTCHA, complex PDF forms, small text, and visually dependent
    workflows must not be the only available path for an eligible user.

## 02.4 Safety-First

-   Safety-sensitive cases require special handling.
-   The system must avoid sending communications that could expose a
    victim to additional risk.
-   Sensitive communication windows and routing information must be
    treated as restricted information.
-   Emergency conditions must be separately identified from ordinary
    legal-aid requests.
-   Mediation must have a safety stop condition.
-   If a case becomes unsuitable or unsafe for mediation, the workflow
    must be capable of stopping mediation and transferring the matter to
    the appropriate legal-action workflow.

## 02.5 Data Integrity

-   The system must never fill missing legal facts by guessing.
-   Missing information must be explicitly marked.
-   Every important fact should have a source/provenance indicator where
    applicable.
-   AI-generated content must remain distinguishable from user-provided
    or officer-confirmed information.
-   Changes to critical case information must be traceable.

------------------------------------------------------------------------

# 03. User Roles

## 03.1 Citizen / Applicant

-   Creates or accesses a legal-aid request.
-   Completes identity and required verification.
-   Files a case manually.
-   Uses AI assistance when necessary.
-   Provides case information.
-   Reviews and confirms information where possible.
-   Receives case-status information through an approved safe
    communication channel.
-   Requests legal information or awareness information.
-   Participates in mediation when applicable.
-   Receives assigned officer/lawyer/mediator communication where
    authorized.
-   Reviews case history and documents subject to access permissions.

## 03.2 Proxy Reporter / Assisted User

-   May report information on behalf of another person where permitted.
-   Can provide preliminary case information.
-   Must be clearly identified as a proxy/third-party source.
-   Cannot automatically finalize the victim/applicant's identity or
    consent.
-   Can assist in creating an initial case record.
-   May provide a safe communication route for the applicant where the
    applicant cannot independently communicate.

## 03.3 District Legal Aid Officer (DLAO)

-   Reviews incoming cases.
-   Reviews AI-generated case summaries and risk indicators.
-   Verifies case information.
-   Communicates with applicant/proxy.
-   Determines the appropriate administrative/legal workflow under
    applicable rules.
-   Assigns mediators or panel lawyers where applicable.
-   Handles urgent escalation.
-   Approves, returns, updates, transfers, or closes cases according to
    authorized procedure.
-   Supervises mediation and legal-aid progression.
-   Reviews audit information relevant to their assigned
    responsibilities.

## 03.4 Mediator

-   Receives cases assigned for mediation.
-   Reviews permitted case information.
-   Communicates with parties through approved channels.
-   Records statements and mediation activity.
-   Documents proposed or agreed settlement terms.
-   Uses audio-based confirmation where required for accessibility.
-   Stops or escalates mediation when a safety or legal hard-stop
    condition is identified.

## 03.5 Panel Lawyer / Legal Representative

-   Receives cases assigned for legal representation.
-   Reviews authorized case information and documents.
-   Provides legal assistance.
-   Updates case progress.
-   Records relevant legal actions.
-   Coordinates with DLAO and applicant through authorized channels.

## 03.6 System Administrator

-   Manages system-level configuration.
-   Manages authorized staff accounts and permissions.
-   Maintains operational settings.
-   Monitors system health and audit events.
-   Cannot bypass case-level privacy controls without authorized
    elevated access and logging.

------------------------------------------------------------------------

# 04. Applicant Entry & Verification

## 04.1 Entry Methods

The system must provide multiple entry routes:

-   Standard web/mobile application.
-   Accessible web interface.
-   AI-assisted conversational interface.
-   Voice/IVR pathway where available.
-   Assisted/proxy intake pathway.
-   Officer-assisted intake.

## 04.2 Account Creation

Required capability:

-   Applicant registration.
-   Secure authentication.
-   Identity verification according to applicable legal/service
    requirements.
-   Contact verification where required.
-   Account recovery.
-   Session management.
-   Device/session visibility where appropriate.
-   Logout from all active sessions.

## 04.3 Identity Verification

The system must support a staged verification process.

### Verification States

-   Unverified
-   Verification Pending
-   Partially Verified
-   Verified
-   Officer Verified
-   Verification Failed
-   Verification Requires Review

### Requirements

-   NID verification where legally/service-required.
-   Support for alternative approved identity information where the
    process permits it.
-   Allow an authorized officer to handle cases where the applicant
    cannot immediately provide the required identifier.
-   Missing NID must not automatically destroy or discard an intake
    record.
-   A case may be marked as:
    -   Pending Identity Verification
    -   Pending NID
    -   Alternative Verification Required
    -   Officer Verification Required
-   The system must clearly show which identity fields are verified and
    which are not.

## 04.4 Verification for Proxy Cases

-   Proxy identity must be separately recorded.
-   Relationship to applicant/victim must be captured.
-   Proxy-provided information must be marked as third-party/unverified
    until confirmation.
-   The applicant must be contacted through an approved safe channel
    when direct confirmation is required.
-   Applicant consent must be separately recorded.
-   Proxy identity must not be substituted for applicant identity.

------------------------------------------------------------------------

# 05. Manual Case Filing

## 05.1 Manual Filing Workflow

The applicant must be able to:

1.  Start a new legal-aid request.
2.  Select or describe the problem.
3.  Provide personal information.
4.  Provide respondent/opposing-party information where known.
5.  Provide location information.
6.  Provide incident/history information.
7.  Provide relevant dates and timeline.
8.  Add supporting documents or evidence where available.
9.  Identify accessibility or communication requirements.
10. Identify immediate safety concerns.
11. Review the generated case summary.
12. Confirm the information.
13. Submit the case.
14. Receive a case reference/acknowledgment.

## 05.2 Case Intake Information

The system should support structured collection of:

-   Applicant identity
-   Applicant contact information
-   Applicant location
-   Applicant accessibility requirements
-   Proxy identity, where applicable
-   Proxy relationship
-   Opposing party/respondent information
-   Nature of complaint
-   Complaint category
-   Incident description
-   Incident timeline
-   Relevant dates
-   Location of incident
-   Current situation
-   Immediate safety status
-   Communication restrictions
-   Preferred/safe communication method
-   Preferred/safe communication time
-   Available documents
-   Missing documents
-   Identity-verification status
-   Previous legal-aid involvement
-   Previous mediation involvement
-   Court/proceeding information where applicable
-   Additional notes

------------------------------------------------------------------------

# 06. AI-Assisted Legal Aid Assistant

## 06.1 Purpose

The AI Assistant is intended to reduce accessibility and information
barriers and assist with case intake.

It must operate as:

-   Information assistant
-   Conversational intake assistant
-   Accessibility assistant
-   Case-structuring assistant
-   Missing-information guide
-   Safety-signal detector
-   Case-summary generator
-   Human-officer handoff assistant

It must not operate as an autonomous legal decision-maker.

## 06.2 Bangla Voice Interaction

Required capability:

-   Spoken Bangla input.
-   Bangla speech-to-text.
-   Support for regional pronunciation/dialect variations where
    supported.
-   Natural conversational questioning.
-   Audio response.
-   Voice-based navigation.
-   Repeat/slow-down option.
-   Confirmation prompts.
-   Ability to correct previously captured information.

## 06.3 Voice-to-Structured-Case

The AI must convert conversation into structured fields such as:

-   Name
-   Relationship
-   Location
-   Complaint type
-   Respondent
-   Timeline
-   Safety information
-   Contact restrictions
-   Available documents
-   Missing information
-   Communication preferences

The user must be able to review/correct information before it becomes
confirmed.

## 06.4 Incomplete Data Handling

If required information is missing:

-   AI must not guess.
-   AI must ask targeted questions.
-   AI may explain acceptable alternative information if such
    alternatives are legally/service-wise supported.
-   Missing fields must be labeled.
-   The case may continue in a pending/review state where permitted.
-   The system must create an officer-review flag when a required
    verification item is unavailable.

Example system behavior:

-   `NID unavailable`
-   `Alternative identity verification required`
-   `Third-party information`
-   `Applicant confirmation pending`
-   `Supporting document unavailable`

## 06.5 Legal Information & Awareness

The assistant may provide:

-   General legal information.
-   Legal-aid eligibility information based on authoritative system
    content.
-   Mediation information.
-   General explanation of legal processes.
-   Rights and awareness information.
-   Explanation of what information/documents may be useful.
-   Guidance on how to contact or reach the appropriate legal-aid
    service.
-   Explanation of case-status terminology.

The assistant must:

-   Distinguish general information from case-specific legal advice.
-   Avoid presenting uncertain information as confirmed law.
-   Use approved/legal-authority-backed content for legal information.
-   Direct the user to a human legal-aid officer/lawyer when human
    review is required.

## 06.6 AI Case Summary

For each AI-assisted case, the system may generate an
`AI Case Insight Brief` containing:

-   Case reference
-   Applicant status
-   Proxy status
-   Complaint summary
-   Timeline summary
-   Safety indicators
-   Accessibility barriers
-   Missing information
-   Verification state
-   Communication constraints
-   Possible mediation relevance
-   Human-review requirements
-   Source/provenance labels

The summary must not replace the underlying case information.

------------------------------------------------------------------------

# 07. Safety & Risk Handling

## 07.1 Safety Classification

The system must identify safety-related signals including:

-   Physical violence
-   Immediate threat to life
-   Threat of serious harm
-   Coercion
-   Domestic violence indicators
-   Threats connected to dowry or other disputes
-   Stalking/surveillance indicators
-   Communication monitoring
-   Unsafe contact conditions
-   Other urgent safety indicators defined by authorized policy

## 07.2 Risk States

The system may use descriptive states such as:

-   `Safety: Unknown`
-   `Safety: Low / No Immediate Threat Identified`
-   `Safety: Review Required`
-   `Safety: High`
-   `Safety: Immediate Threat`

These states are support indicators for authorized human review and must
not independently determine the legal outcome.

## 07.3 Emergency Escalation

Where the system detects or receives information indicating an immediate
life-threatening situation:

-   Trigger the configured emergency-review workflow.
-   Notify the authorized District Legal Aid Officer.
-   Where officially integrated and legally authorized, notify the
    relevant emergency/public-safety authority.
-   Record the escalation event.
-   Preserve the information used to trigger the escalation.
-   Avoid unsafe communication to the applicant.
-   Use only approved communication channels.

No emergency integration should be assumed unless the relevant
government/authorized communication service is actually available.

## 07.4 Unsafe Outbound Communication

The system must not automatically send:

-   SMS
-   Push notification
-   Email
-   Automated call

when the configured communication method or timing could expose the
applicant to danger.

Communication safety settings must be respected before any outbound
communication is initiated.

------------------------------------------------------------------------

# 08. Safe Communication Management

## 08.1 Safe Communication Profile

Each sensitive case may contain:

-   Safe contact method
-   Safe contact number
-   Proxy contact method
-   Safe communication window
-   Unsafe communication methods
-   Communication restrictions
-   Communication instructions
-   Last confirmed safe-contact information

## 08.2 Restricted Communication Data

Sensitive fields such as:

-   Safe communication time
-   Secret contact window
-   Sensitive phone number
-   Proxy-routing information
-   Communication history

must have restricted access.

## 08.3 Communication Workflow

The system must support:

-   Scheduled safe-contact windows.
-   Officer-initiated safe calls.
-   Voice/IVR communication where available.
-   Proxy-assisted communication.
-   Applicant consent confirmation.
-   Communication history.
-   Communication outcome.
-   Follow-up scheduling.

## 08.4 Zero-Trace / Low-Trace Requirement

Where safety requirements demand it, the system should minimize:

-   Exposed notification text.
-   Sensitive message previews.
-   Identifying push notifications.
-   Risky device-level traces.
-   Unnecessary call/message metadata exposure.

The exact implementation must be validated against the actual
communication technology and operating environment.

------------------------------------------------------------------------

# 09. Proxy-to-Applicant Verification Bridge

## 09.1 Initial Proxy Intake

The proxy may provide:

-   Applicant name.
-   Relationship.
-   Complaint information.
-   Location.
-   Timeline.
-   Communication limitations.
-   Known identity information.
-   Safety information.

All such information must initially carry a proxy/third-party provenance
label where applicable.

## 09.2 Applicant Confirmation

The system must provide an authorized process to:

1.  Contact the applicant during a safe communication window.
2.  Explain that a proxy has submitted information.
3.  Ask whether the applicant wants legal-aid assistance.
4.  Record the applicant's consent.
5.  Verify or correct relevant information.
6.  Update provenance labels.
7.  Continue the case workflow.

## 09.3 Consent Result

Possible states:

-   Consent Confirmed
-   Consent Pending
-   Consent Refused
-   Applicant Unreachable
-   Unsafe to Contact
-   Requires Officer Review

------------------------------------------------------------------------

# 10. AI-Assisted Triage & Officer Decision Support

## 10.1 Purpose

The triage system is designed to help DLAOs identify cases requiring
attention without replacing human judgment.

## 10.2 Priority Factors

The system may organize incoming cases using descriptive indicators
including:

### Safety / Immediate Threat

-   Physical violence
-   Life-threatening situation
-   Threat level
-   Escalating harm indicators

### Vulnerability / Access Barrier

-   Disability
-   No smartphone
-   No reliable internet
-   Basic phone only
-   Screen-reader limitation
-   Communication barrier
-   Geographic access difficulty
-   Unsafe home environment
-   Dependence on proxy

### Legal-Aid Relevance

-   Relevant legal-aid category
-   Potential mediation relevance
-   Need for legal representation
-   Verification requirements
-   Required human review

## 10.3 Smart Queue

The DLAO dashboard must provide:

-   Incoming cases
-   Urgent cases
-   Cases awaiting verification
-   Cases awaiting applicant consent
-   Cases awaiting documents
-   Cases awaiting officer review
-   Mediation candidates
-   Cases requiring lawyer assignment
-   Cases with communication constraints
-   Overdue follow-ups

## 10.4 Priority Representation

The system may present descriptive tags such as:

-   `Safety: High`
-   `Digital Access: Limited`
-   `Verification: Pending`
-   `Proxy Report: Yes`
-   `Legal-Aid Review: Required`

The system must not present an AI-generated score as the final legal
decision.

## 10.5 Anti-Deprioritization Safeguard

The system must not automatically deprioritize a case solely because:

-   A form is incomplete.
-   The applicant is digitally illiterate.
-   The applicant cannot upload a document.
-   The applicant lacks a smartphone.
-   The applicant uses a proxy.
-   NID is temporarily unavailable.
-   The applicant uses voice rather than text.
-   The applicant has limited connectivity.

Incomplete information should generate a review/verification state
rather than silent disappearance.

------------------------------------------------------------------------

# 11. District Legal Aid Officer Dashboard

## 11.1 Dashboard Sections

-   Overview
-   New Cases
-   Urgent Cases
-   Verification Queue
-   Proxy Cases
-   Mediation Queue
-   Lawyer Assignment Queue
-   Active Cases
-   Follow-Up Queue
-   Pending Documents
-   Communication Schedule
-   Resolved Cases
-   Closed Cases
-   Reports
-   Audit/Activity History

## 11.2 Case List

Each case entry should show:

-   Case ID
-   Applicant name/reference
-   Case category
-   Location
-   Submission method
-   Verification state
-   Consent state
-   Safety indicator
-   Accessibility indicator
-   Proxy indicator
-   Current stage
-   Assigned officer
-   Assigned mediator/lawyer
-   Last activity
-   Next action
-   Priority/review tags

## 11.3 Case Detail View

The officer must be able to access:

-   Applicant profile
-   Case summary
-   Original applicant/proxy statements
-   AI-generated summary
-   Source/provenance labels
-   Verification information
-   Timeline
-   Documents
-   Communication requirements
-   Safety information subject to role permissions
-   Mediation history
-   Lawyer assignment
-   Officer notes
-   Follow-up tasks
-   Case status history
-   Audit history

## 11.4 Officer Actions

Authorized officers may:

-   Review case.
-   Verify information.
-   Request additional information.
-   Contact applicant/proxy.
-   Approve progression to the next workflow stage.
-   Assign mediator.
-   Assign panel lawyer.
-   Return case for additional information.
-   Transfer case where authorized.
-   Mark case as pending.
-   Escalate urgent matters.
-   Stop mediation under applicable hard-stop conditions.
-   Move a case to legal representation workflow.
-   Close case according to authorized procedure.

------------------------------------------------------------------------

# 12. Nearest / Relevant District Legal Aid Office Routing

## 12.1 Location-Based Routing

The system must determine the relevant District Legal Aid Office using:

-   Applicant location.
-   Case jurisdiction/service area.
-   Administrative area.
-   Configured District Legal Aid Office coverage.
-   Officer/service availability where applicable.

## 12.2 Routing States

-   Office Determined
-   Routing Pending
-   Manual Routing Required
-   Transferred
-   Accepted by DLAO
-   Reassigned

## 12.3 Routing Requirements

-   AI-assisted intake may create a pending case and route it for human
    review.
-   The routing mechanism must not be the final legal decision.
-   If location is uncertain, the case must be flagged for manual
    routing.
-   The applicant must not be rejected solely because the system cannot
    determine the correct office automatically.

------------------------------------------------------------------------

# 13. Case Lifecycle

## 13.1 Standard Lifecycle

``` text
Entry
  ↓
Identity / Account Verification
  ↓
Case Intake
  ↓
Information Review
  ↓
Consent Confirmation
  ↓
Case Submission
  ↓
DLAO Routing
  ↓
Human Review
  ↓
Eligibility / Service Assessment
  ↓
Workflow Selection
  ├── Information / Guidance
  ├── Pre-Case Mediation
  └── Legal Representation / Other Authorized Action
  ↓
Assignment
  ↓
Active Case Handling
  ↓
Follow-Up
  ↓
Resolution
  ↓
Closure
```

## 13.2 AI-Assisted Lifecycle

``` text
Voice / Conversational Entry
  ↓
Speech Recognition
  ↓
Structured Information Extraction
  ↓
Missing Information Guidance
  ↓
Safety Signal Detection
  ↓
Consent / Verification Workflow
  ↓
AI Case Summary
  ↓
Pending / Human Review
  ↓
DLAO Dashboard
  ↓
Human Decision
```

## 13.3 Case Statuses

Minimum supported statuses:

-   Draft
-   Intake Started
-   Verification Pending
-   Pending NID / Identity Information
-   Proxy Reported
-   Applicant Confirmation Pending
-   Consent Confirmed
-   Submitted
-   Routing Pending
-   DLAO Review
-   Additional Information Required
-   Mediation Pending
-   Mediation Active
-   Mediation Hard Stop
-   Lawyer Assignment Pending
-   Legal Assistance Active
-   Follow-Up Required
-   Resolved
-   Closed
-   Withdrawn
-   Referred / Transferred
-   Emergency Review

------------------------------------------------------------------------

# 14. Mediation Module

## 14.1 Mediation Eligibility Workflow

The system should:

-   Identify matters that may be suitable for pre-case mediation.
-   Present the matter to the authorized officer.
-   Allow human approval before mediation begins.
-   Record the reason/status for mediation selection.
-   Confirm required participant consent.

## 14.2 Voice-Centric Mediation

The system should support:

-   Voice statements.
-   Asynchronous communication.
-   IVR-based participation where available.
-   Officer/mediator-assisted voice communication.
-   Recording of statements subject to applicable consent, law, and
    policy.
-   Transcription into structured records.
-   Human review of important transcriptions.

## 14.3 Voice-Bridge Relay

Where direct video/web participation is impractical:

-   Party A may provide a voice statement.
-   Party B may provide a voice statement during a safe communication
    window.
-   The mediator may relay relevant information between parties.
-   The mediator remains responsible for mediation management.
-   AI may assist with transcription, structuring, and documentation.

## 14.4 Mediation Outcome

The system must support:

-   Proposed terms
-   Negotiated terms
-   Final terms
-   Participant confirmation
-   Mediator confirmation
-   Date/time
-   Follow-up requirements
-   Settlement documentation
-   Audio confirmation where appropriate

## 14.5 Audio-Verified Settlement Summary

For participants who cannot reliably read digital documents:

-   Generate a structured settlement summary.
-   Convert the summary into an audio presentation.
-   Read the relevant terms through an approved voice channel.
-   Record participant confirmation according to the approved procedure.
-   Store the confirmation as part of the case record.
-   Provide human review where required.

------------------------------------------------------------------------

# 15. Mediation Hard Stop & Legal Escalation

## 15.1 Hard Stop Conditions

Mediation must be capable of immediate suspension when information
indicates:

-   Ongoing physical violence.
-   Life-threatening threats.
-   Serious coercion.
-   Mediation being used to facilitate harassment or intimidation.
-   Other conditions defined by applicable legal/service policy.

## 15.2 Hard Stop Workflow

``` text
Risk Identified
  ↓
Mediation Suspended
  ↓
DLAO / Authorized Human Review
  ↓
Safety / Legal Assessment
  ↓
Legal Representation / Appropriate Legal Action Workflow
```

## 15.3 Fallback

When mediation is stopped:

-   Preserve the case history.
-   Preserve relevant statements.
-   Record the reason for the hard stop.
-   Notify the responsible DLAO.
-   Transfer the case to the appropriate legal-aid workflow.
-   Assign a panel lawyer where authorized.
-   Provide appropriate safety-aware communication.

AI must not independently decide that a court case has been filed.

------------------------------------------------------------------------

# 16. Panel Lawyer Management

## 16.1 Lawyer Directory

Authorized officers must be able to:

-   View eligible panel lawyers.
-   Search by relevant criteria.
-   View current assignments.
-   View workload.
-   View case categories/areas where permitted.
-   Assign a lawyer.
-   Reassign a case where authorized.

## 16.2 Assignment

Each assignment should record:

-   Case ID
-   Lawyer
-   Assigning officer
-   Assignment date
-   Reason/status
-   Current assignment state
-   Follow-up date

## 16.3 Lawyer Case Workspace

The lawyer may access authorized:

-   Case information
-   Documents
-   Statements
-   Relevant communication history
-   Officer instructions
-   Mediation history
-   Legal-action status
-   Follow-up requirements

------------------------------------------------------------------------

# 17. Legal Information & Awareness Centre

## 17.1 Information Categories

The system should provide an organized knowledge section for:

-   Legal-aid awareness.
-   Eligibility information.
-   Domestic violence awareness.
-   Family/legal disputes.
-   Maintenance-related information.
-   Mediation information.
-   General legal procedure awareness.
-   Rights and responsibilities.
-   Required/commonly requested documents.
-   Accessibility information.
-   Emergency/safety guidance.
-   Contact information for authorized legal-aid services.

## 17.2 AI Knowledge Assistant

Users may ask:

-   What is legal aid?
-   What is mediation?
-   What information do I need?
-   What should I do next?
-   Where can I seek legal assistance?
-   What does my current case status mean?

The assistant should answer from approved legal-information content and
identify when human assistance is needed.

------------------------------------------------------------------------

# 18. Document & Evidence Management

## 18.1 Document Types

Support:

-   Identity documents
-   Supporting evidence
-   Applications
-   Statements
-   Notices
-   Mediation documents
-   Settlement documents
-   Legal-aid documents
-   Officer-generated documents
-   Lawyer-generated documents
-   Audio records
-   Transcripts

## 18.2 Document States

-   Uploaded
-   Pending Review
-   Verified
-   Rejected
-   Re-upload Required
-   Restricted
-   Archived

## 18.3 Missing Document Handling

-   Mark missing documents explicitly.
-   Allow the case to remain pending where permitted.
-   Provide an explanation/reason.
-   Create an officer follow-up task.
-   Never fabricate or infer missing document information.

------------------------------------------------------------------------

# 19. Accessibility & Inclusive UX

## 19.1 Visual Accessibility

-   Screen-reader compatibility.
-   Semantic labels.
-   High-contrast mode.
-   Adjustable text size.
-   Clear focus states.
-   Large interactive controls.
-   Minimal visual complexity.
-   No critical information conveyed only through color.

## 19.2 Voice Accessibility

-   Bangla voice prompts.
-   Voice command navigation.
-   Spoken form completion.
-   Repeat previous question.
-   Skip optional question.
-   Correct previous answer.
-   Confirm before final submission.
-   Audio case-status access.

## 19.3 Basic Phone Accessibility

Where telephony/IVR infrastructure is available:

-   No smartphone requirement.
-   No browser requirement.
-   No visual CAPTCHA requirement.
-   DTMF/keypad support.
-   Voice prompt support.
-   Voice response support.
-   Safe communication window support.

## 19.4 Low-Bandwidth Design

-   Minimal media transfer.
-   Lightweight pages.
-   Asynchronous submission.
-   Retry failed requests.
-   Resume incomplete intake.
-   Avoid unnecessary video.
-   Prefer voice/audio or text alternatives where appropriate.

------------------------------------------------------------------------

# 20. Voice / IVR Service

## 20.1 IVR Entry

The system should support:

-   Incoming voice call.
-   Language selection.
-   Bangla voice guidance.
-   Identity/account lookup where appropriate.
-   New case intake.
-   Existing case status.
-   Add information to case.
-   Request human contact.
-   Safe communication setup.
-   Follow-up.

## 20.2 Voice Interaction States

-   Welcome
-   Authentication/verification
-   Case selection
-   New case
-   Existing case
-   Information collection
-   Confirmation
-   Submission
-   Human handoff
-   Emergency handling
-   Exit

## 20.3 Human Handoff

The user must be able to request or be routed to human assistance where:

-   AI cannot understand the request.
-   The matter is legally complex.
-   The user requests a human.
-   Consent requires human handling.
-   Verification cannot be completed.
-   Safety concerns require human review.
-   Mediation/legal action requires authorized personnel.

------------------------------------------------------------------------

# 21. Communication & Notification Centre

## 21.1 Applicant Notifications

Where safe and permitted:

-   Case received.
-   Verification required.
-   Additional information required.
-   DLAO review started.
-   Appointment/contact reminder.
-   Mediation update.
-   Lawyer assignment.
-   Case status change.
-   Resolution/closure notice.

## 21.2 Safety-Aware Notifications

Sensitive notifications must:

-   Use minimal identifying information.
-   Respect communication restrictions.
-   Respect safe contact windows.
-   Avoid revealing case details through lock-screen previews where
    applicable.
-   Support voice-based notification where appropriate.

## 21.3 Officer Notifications

-   New case.
-   Urgent case.
-   Verification pending.
-   Applicant confirmation pending.
-   Safe-contact window approaching.
-   Mediation appointment.
-   Hard-stop event.
-   Follow-up overdue.
-   Case transfer.
-   Lawyer assignment update.

------------------------------------------------------------------------

# 22. Case Follow-Up & Reminder System

The system must support:

-   Follow-up date.
-   Responsible officer.
-   Responsible mediator/lawyer.
-   Follow-up reason.
-   Reminder status.
-   Completed follow-up.
-   Missed follow-up.
-   Rescheduling.
-   Communication result.

For applicable cases, the system may support recurring reminders related
to agreed obligations or scheduled follow-up.

------------------------------------------------------------------------

# 23. Search & Case Discovery

Authorized staff must be able to search cases using permitted fields:

-   Case ID
-   Applicant reference
-   Name
-   Location
-   Case category
-   Current status
-   Verification state
-   Safety state
-   Assigned officer
-   Mediator
-   Lawyer
-   Submission date
-   Last activity
-   Follow-up date

Sensitive fields must not become searchable to roles that are not
authorized to access them.

------------------------------------------------------------------------

# 24. Case History & Timeline

Every case should have a chronological timeline containing:

-   Intake started
-   Information submitted
-   Verification events
-   Consent events
-   Officer review
-   Status changes
-   Assignment events
-   Communication events
-   Document events
-   Mediation events
-   Hard-stop events
-   Legal assistance events
-   Follow-ups
-   Resolution
-   Closure

Each event should preserve:

-   Timestamp
-   Actor/system source
-   Event type
-   Relevant status
-   Change summary
-   Authorization context where applicable

------------------------------------------------------------------------

# 25. Audit & Accountability

The system must maintain an auditable record of important actions.

Audit events should include:

-   Login/security events.
-   Case creation.
-   Case access.
-   Sensitive-field access.
-   Case modification.
-   Verification.
-   Consent recording.
-   Assignment.
-   Status changes.
-   Communication scheduling.
-   Restricted-data access.
-   Document access.
-   Mediation action.
-   Hard-stop action.
-   Case closure.
-   Administrative changes.

Audit records must be protected from unauthorized alteration.

------------------------------------------------------------------------

# 26. Privacy & Sensitive Information Controls

## 26.1 Sensitive Data Categories

Special protection should apply to:

-   Identity information.
-   Applicant contact information.
-   Proxy information.
-   Safe communication numbers.
-   Safe communication windows.
-   Domestic violence information.
-   Threat information.
-   Audio recordings.
-   Voice data.
-   Case statements.
-   Legal documents.
-   Lawyer/mediator communications.
-   Any other information classified as sensitive by applicable policy.

## 26.2 Role-Based Access

Access must be based on:

-   User role.
-   Case assignment.
-   Organizational responsibility.
-   Need-to-know.
-   Sensitivity of the field.

## 26.3 Restricted Fields

Some sensitive fields should remain hidden/masked unless the user's role
and current task require access.

Example:

``` text
Restricted Contact Information
[RESTRICTED]
Access: Authorized DLAO / Assigned Mediator / Assigned Lawyer
```

## 26.4 Sensitive Access Verification

For especially sensitive operations, the system should support:

-   Strong authentication.
-   Multi-factor authentication.
-   Additional verification for restricted data.
-   Access logging.
-   Session timeout.
-   Re-authentication for critical actions.

------------------------------------------------------------------------

# 27. Applicant Profile

The applicant profile should contain:

-   Applicant reference.
-   Verified identity status.
-   Contact methods.
-   Location.
-   Accessibility requirements.
-   Communication preferences.
-   Safe communication settings where applicable.
-   Active cases.
-   Previous cases subject to authorization.
-   Documents subject to authorization.
-   Notifications.
-   Consent records.

Applicants should be able to update permitted profile information while
protected/verified fields require appropriate verification.

------------------------------------------------------------------------

# 28. Applicant Case Portal

## 28.1 Main Sections

-   Home
-   My Cases
-   New Case
-   AI Legal Aid Assistant
-   Legal Information
-   Mediation
-   Documents
-   Notifications
-   Communication
-   Profile
-   Accessibility Settings
-   Security Settings

## 28.2 Case View

The applicant should be able to see permitted:

-   Case ID
-   Current status
-   Current stage
-   Assigned office
-   Next required action
-   Requested documents
-   Appointment/contact information
-   Mediation status
-   Lawyer assignment status where appropriate
-   Resolution information

------------------------------------------------------------------------

# 29. Proxy / Assisted Access Portal

The proxy workflow should support:

-   Proxy registration/identification.
-   Applicant relationship.
-   New case initiation.
-   Voice intake.
-   Case reference.
-   Pending applicant confirmation.
-   Safe communication details.
-   Officer contact.
-   Case updates limited to authorized information.

The proxy must not automatically gain access to all applicant
information.

------------------------------------------------------------------------

# 30. Officer Case Assignment

Cases must support assignment to:

-   DLAO
-   Supporting officer
-   Mediator
-   Panel lawyer

Assignment must include:

-   Assigned person.
-   Assignment role.
-   Assignment date.
-   Current status.
-   Reassignment history.
-   Next action.

------------------------------------------------------------------------

# 31. Administrative Management

## 31.1 System Administration

Administrative functions should include:

-   Staff account management.
-   Role management.
-   District/office directory.
-   Mediator directory.
-   Panel lawyer directory.
-   Case category management.
-   Legal-information content management.
-   Communication-channel configuration.
-   Notification templates.
-   Accessibility configuration.
-   AI knowledge/content management.
-   Audit review.
-   System status monitoring.

## 31.2 Administrative Restrictions

Administrators must not automatically receive unrestricted access to
every sensitive case field.

Administrative access must remain role- and permission-controlled.

------------------------------------------------------------------------

# 32. AI Governance

## 32.1 AI Output Types

The system must clearly distinguish:

-   User statement
-   Proxy statement
-   Officer-confirmed fact
-   AI transcription
-   AI-generated summary
-   AI-generated suggestion
-   System-generated status
-   Human decision

## 32.2 AI Confidence / Review

Where technically available, the system may provide:

-   Speech recognition confidence.
-   Extraction confidence.
-   Missing-field indicators.
-   Ambiguity indicators.

Low-confidence information should trigger confirmation rather than being
silently accepted.

## 32.3 AI Hallucination Protection

For legal-information responses:

-   Use approved source content.
-   Avoid unsupported legal claims.
-   Identify uncertainty.
-   Escalate complex legal questions.
-   Preserve source references where possible.
-   Do not invent laws, sections, procedures, government services, or
    legal outcomes.

------------------------------------------------------------------------

# 33. Legal Knowledge Management

The legal-information knowledge base should be managed by authorized
personnel.

Each knowledge item should support:

-   Title
-   Category
-   Content
-   Source/reference
-   Effective date
-   Review date
-   Version
-   Status
-   Reviewer
-   Language
-   Accessibility version

The AI assistant should use the approved version of legal-information
content.

------------------------------------------------------------------------

# 34. Reporting & Analytics

## 34.1 Operational Metrics

Authorized management users may view:

-   Total cases.
-   New cases.
-   Active cases.
-   Pending cases.
-   Resolved cases.
-   Closed cases.
-   Cases by district.
-   Cases by category.
-   Cases by intake method.
-   Cases requiring verification.
-   Proxy-assisted cases.
-   Accessibility-assisted cases.
-   Mediation cases.
-   Mediation outcomes.
-   Legal-representation cases.
-   Emergency/urgent cases.
-   Average processing time.
-   Pending follow-ups.
-   Case backlog.
-   Case transfer count.

## 34.2 Accessibility Metrics

-   Voice-assisted cases.
-   Screen-reader/accessibility-assisted cases.
-   Basic-phone/IVR cases.
-   Cases with digital-access barriers.
-   Cases pending because of missing information.
-   Cases where alternative verification was required.

## 34.3 Safety Metrics

Sensitive reporting must be access-controlled.

Possible aggregate indicators:

-   Safety-review cases.
-   High-risk review cases.
-   Emergency escalations.
-   Mediation hard stops.
-   Safety-related transfers.

------------------------------------------------------------------------

# 35. Case Export & Documentation

Authorized personnel should be able to generate case documents such as:

-   Case intake summary.
-   Officer review summary.
-   Mediation summary.
-   Settlement summary.
-   Legal-assistance case summary.
-   Follow-up report.
-   Case closure summary.

Documents should distinguish:

-   Original statements.
-   Verified facts.
-   AI-generated summaries.
-   Human-confirmed information.

------------------------------------------------------------------------

# 36. Security Requirements

The system must include:

-   Strong authentication.
-   Role-based authorization.
-   Multi-factor authentication for privileged roles.
-   Encryption for sensitive information.
-   Secure session management.
-   Secure file handling.
-   Secure API communication.
-   Protection against unauthorized case access.
-   Audit logging.
-   Sensitive-field masking.
-   Rate limiting.
-   Abuse detection.
-   Account lock/recovery controls.
-   Secure password handling.
-   Secure secret/key management.
-   Data backup and recovery procedures.
-   Security monitoring.

Highly sensitive communication information should receive stronger
protection than ordinary case metadata.

------------------------------------------------------------------------

# 37. Data Classification

Minimum classification model:

``` text
PUBLIC
  ↓
INTERNAL
  ↓
CONFIDENTIAL
  ↓
SENSITIVE
  ↓
HIGHLY RESTRICTED
```

Examples of highly restricted information:

-   Safe communication window.
-   Sensitive contact number.
-   Proxy-routing information.
-   Domestic-violence safety information.
-   Certain audio/voice records.
-   Restricted legal communications.

------------------------------------------------------------------------

# 38. Case Provenance Model

Every important information item should be capable of carrying
provenance such as:

``` text
SOURCE:
- Applicant
- Proxy
- Officer
- Mediator
- Lawyer
- Uploaded Document
- AI Transcription
- AI Extraction
- System
```

And verification state:

``` text
VERIFICATION:
- Unverified
- Pending
- Applicant Confirmed
- Officer Verified
- Document Verified
- Rejected / Corrected
```

This allows officers to understand what is known, what is reported, and
what still requires confirmation.

------------------------------------------------------------------------

# 39. Error & Recovery Handling

The system must support:

-   Interrupted voice calls.
-   Network failure.
-   Partial form completion.
-   Reconnecting an interrupted intake.
-   Duplicate submission detection.
-   Incorrect speech transcription correction.
-   Invalid document upload.
-   Failed notification delivery.
-   Failed communication attempt.
-   Incorrect office routing.
-   Officer reassignment.
-   Lost/incomplete verification.
-   User-requested correction.

A failed technical process must not silently delete an active legal-aid
request.

------------------------------------------------------------------------

# 40. Duplicate & Fraud Prevention

The system should identify possible duplicates using permitted
information.

Possible indicators:

-   Similar applicant identity.
-   Similar contact information.
-   Same incident.
-   Same case reference.
-   Existing active case.

Possible duplicate detection must create a review state rather than
automatically deleting or rejecting a case.

Suspicious activity should be routed to authorized staff for review.

------------------------------------------------------------------------

# 41. Consent Management

The system must maintain separate consent records where applicable:

-   Account/service consent.
-   AI interaction consent.
-   Voice recording consent.
-   Data processing consent.
-   Proxy-assisted intake consent.
-   Applicant confirmation.
-   Mediation participation consent.
-   Audio settlement confirmation.
-   Communication consent.

Consent records should include:

-   Person giving consent.
-   Date/time.
-   Method.
-   Scope.
-   Current state.
-   Withdrawal/change state where applicable.

------------------------------------------------------------------------

# 42. Communication Channel Model

Supported channel types may include:

``` text
WEB
MOBILE WEB
VOICE
IVR
PHONE
OFFICER-ASSISTED CALL
PROXY
IN-PERSON
```

The case should identify the currently approved communication channel.

------------------------------------------------------------------------

# 43. Offline / Intermittent Connectivity Support

Where technically feasible:

-   Save partially completed intake.
-   Resume later.
-   Queue non-sensitive requests for synchronization.
-   Provide clear connection status.
-   Prevent duplicate submission.
-   Support asynchronous communication.
-   Keep voice workflows usable under low-bandwidth conditions.

Sensitive information must not be stored insecurely on an untrusted
device merely to provide offline support.

------------------------------------------------------------------------

# 44. Mobile-First Design Requirements

The citizen-facing application must prioritize:

-   Small screens.
-   Touch interaction.
-   One-hand usability where possible.
-   Large buttons.
-   Short forms.
-   Progressive disclosure.
-   Voice interaction.
-   Low-bandwidth loading.
-   Clear status indicators.
-   Accessible navigation.

Officer dashboards should remain responsive but may use a richer
desktop-oriented layout.

------------------------------------------------------------------------

# 45. Main Application Navigation

## Citizen Application

``` text
Home
Cases
AI Assistant
Legal Information
Mediation
Documents
Notifications
Profile
Accessibility
Security
```

## Officer Application

``` text
Dashboard
Cases
Urgent
Verification
Mediation
Lawyers
Follow-Ups
Reports
Audit
Profile
```

## Administrator Application

``` text
Dashboard
Users & Staff
Offices
Case Configuration
Legal Knowledge
AI Configuration
Communication
Reports
Security
Audit
System Settings
```

------------------------------------------------------------------------

# 46. End-to-End Functional Workflow

## 46.1 Normal Applicant

``` text
Register / Login
  ↓
Verify Identity
  ↓
Start Case
  ↓
Complete Form
  ↓
Upload Available Documents
  ↓
Review Information
  ↓
Confirm & Submit
  ↓
Case ID
  ↓
Relevant DLAO Routing
  ↓
Human Review
  ↓
Appropriate Legal-Aid Workflow
```

## 46.2 AI-Assisted Applicant

``` text
Open AI Assistant / Voice Service
  ↓
Language & Accessibility Setup
  ↓
Identity / Verification Check
  ↓
Conversational Intake
  ↓
Speech-to-Text
  ↓
Structured Case Extraction
  ↓
Missing Information Questions
  ↓
Safety Check
  ↓
Applicant Confirmation
  ↓
Case Summary
  ↓
DLAO Review
```

## 46.3 Proxy-Assisted Case

``` text
Proxy Entry
  ↓
Proxy Identity / Relationship
  ↓
Voice or Manual Intake
  ↓
Third-Party / Unverified Labels
  ↓
Initial Case Created
  ↓
Safe Contact Window
  ↓
Applicant Contact
  ↓
Applicant Consent
  ↓
Applicant Confirmation
  ↓
DLAO Review
```

## 46.4 Urgent Safety Case

``` text
Case Intake
  ↓
Safety Signal
  ↓
Immediate Human/Emergency Review
  ↓
Authorized Emergency Escalation
  ↓
DLAO Review
  ↓
Safety-Aware Legal-Aid Action
```

## 46.5 Mediation Case

``` text
DLAO Review
  ↓
Mediation Suitability Review
  ↓
Participant Consent
  ↓
Mediator Assignment
  ↓
Voice / Asynchronous Mediation
  ↓
Settlement / No Settlement
  ↓
Documentation
  ↓
Follow-Up / Closure
```

## 46.6 Mediation Hard Stop

``` text
Mediation Active
  ↓
Safety / Coercion / Serious Risk Detected
  ↓
Hard Stop
  ↓
Human Review
  ↓
Legal Assistance / Appropriate Legal Action
  ↓
Panel Lawyer Assignment Where Applicable
```

------------------------------------------------------------------------

# 47. Minimum Viable Product (MVP)

The first production-ready release should prioritize:

## Citizen

-   Account creation/login.
-   Identity verification workflow.
-   Manual case filing.
-   Case ID.
-   Case status.
-   Document upload.
-   Legal information.
-   Basic AI assistant.
-   Bangla voice intake.
-   Accessibility mode.
-   Safe communication preferences.

## DLAO

-   Secure login.
-   Dashboard.
-   Case queue.
-   Case detail.
-   Verification review.
-   AI case summary.
-   Case assignment.
-   Status management.
-   Follow-up management.
-   Safe communication information.
-   Audit trail.

## AI

-   Bangla speech-to-text.
-   Structured intake.
-   Missing-information guidance.
-   Legal-information retrieval from approved content.
-   Safety signal flagging.
-   Case summary generation.
-   Human handoff.

## Mediation

-   Case assignment.
-   Voice/asynchronous workflow.
-   Statements.
-   Settlement documentation.
-   Confirmation.
-   Hard-stop mechanism.

------------------------------------------------------------------------

# 48. Phase-Based Development Plan

## Phase 01 --- Requirements & Legal/Operational Validation

-   Finalize stakeholder requirements.
-   Validate legal-aid workflows with authorized/legal stakeholders.
-   Define official user roles.
-   Define verification requirements.
-   Define case categories.
-   Define mediation eligibility rules.
-   Define emergency escalation rules.
-   Define communication safety requirements.
-   Define applicable data-protection requirements.
-   Define official district-office directory.

## Phase 02 --- Core Citizen System

-   Registration/login.
-   Identity verification.
-   Citizen profile.
-   Manual case filing.
-   Case ID.
-   Case status.
-   Document handling.
-   Notification framework.

## Phase 03 --- DLAO Case Management

-   Officer authentication.
-   Dashboard.
-   Case queue.
-   Case detail.
-   Verification workflow.
-   Assignment.
-   Follow-up.
-   Case history.
-   Audit.

## Phase 04 --- AI Assistant

-   Bangla conversational layer.
-   Speech recognition.
-   Structured extraction.
-   Missing-data handling.
-   Case summary.
-   Legal-information assistant.
-   Human handoff.

## Phase 05 --- Accessibility & Voice/IVR

-   Screen-reader optimization.
-   Voice-first interface.
-   IVR integration.
-   Basic-phone workflow.
-   Safe communication window.
-   Proxy-assisted workflow.

## Phase 06 --- Mediation

-   Mediator dashboard.
-   Voice relay.
-   Asynchronous mediation.
-   Statements.
-   Settlement documentation.
-   Audio confirmation.
-   Hard-stop workflow.

## Phase 07 --- Legal Representation

-   Panel lawyer directory.
-   Assignment.
-   Lawyer workspace.
-   Case progression.
-   Follow-up.

## Phase 08 --- Security & Privacy Hardening

-   RBAC.
-   MFA.
-   Sensitive-field masking.
-   Encryption.
-   Audit controls.
-   Secure communication.
-   Threat monitoring.
-   Data retention controls.
-   Security testing.

## Phase 09 --- Analytics & Administration

-   Management reports.
-   District-level reporting.
-   Service-performance analytics.
-   Accessibility analytics.
-   Case-flow analytics.
-   Legal-information management.
-   Administrative controls.

## Phase 10 --- Testing & Deployment

-   Functional testing.
-   Accessibility testing.
-   Voice recognition testing.
-   Bangla/dialect testing.
-   Low-bandwidth testing.
-   Security testing.
-   Privacy testing.
-   Case workflow testing.
-   Mediation testing.
-   Emergency workflow testing.
-   Human-officer acceptance testing.
-   Pilot deployment.
-   Feedback collection.
-   Production rollout.

------------------------------------------------------------------------

# 49. Testing Requirements

## Functional Testing

-   Registration.
-   Verification.
-   Case submission.
-   Case routing.
-   Officer review.
-   Assignment.
-   Mediation.
-   Legal representation.
-   Case closure.
-   Notifications.

## AI Testing

-   Bangla speech.
-   Regional speech variations.
-   Noisy environments.
-   Incorrect transcription.
-   Ambiguous statements.
-   Missing data.
-   Contradictory information.
-   Safety-related statements.
-   Legal-information responses.
-   Hallucination prevention.
-   Human handoff.

## Accessibility Testing

-   Screen readers.
-   Keyboard-only operation.
-   Low vision.
-   Color/contrast.
-   Large text.
-   Voice-only navigation.
-   Basic-phone/IVR.
-   Low-bandwidth conditions.

## Security Testing

-   Authentication.
-   Authorization.
-   Restricted fields.
-   Case isolation.
-   Session security.
-   API security.
-   File security.
-   Audit integrity.
-   Data leakage.
-   Privilege escalation.

## Safety Testing

-   Unsafe notification prevention.
-   Safe-window enforcement.
-   Emergency escalation.
-   Mediation hard stop.
-   Proxy/applicant separation.
-   Restricted communication access.

------------------------------------------------------------------------

# 50. Non-Functional Requirements

## Performance

-   Fast initial loading on mobile.
-   Low-bandwidth compatibility.
-   Responsive case dashboard.
-   Efficient case search.
-   Scalable voice processing.
-   Reliable asynchronous processing.

## Availability

-   High availability for citizen entry.
-   Reliable case submission.
-   Recovery from temporary service failure.
-   Monitoring of critical services.

## Reliability

-   No silent case loss.
-   Idempotent case submission.
-   Recoverable interrupted workflows.
-   Consistent case status.

## Scalability

The system should be capable of expansion across:

-   Districts.
-   Legal-aid offices.
-   Officers.
-   Mediators.
-   Lawyers.
-   Citizens.
-   Voice/IVR traffic.
-   Case volume.

## Maintainability

-   Modular feature development.
-   Versioned legal-information content.
-   Configurable case categories.
-   Configurable roles.
-   Configurable workflows.
-   Traceable changes.
-   Documented operational procedures.

------------------------------------------------------------------------

# 51. Core System Rules

``` text
RULE-01:
AI assists; authorized humans decide.

RULE-02:
No missing information may be invented.

RULE-03:
Proxy information must be labeled as proxy/third-party information until confirmed.

RULE-04:
Lack of immediate NID information must not silently discard an intake.

RULE-05:
Accessibility limitations must not automatically deprioritize or reject a case.

RULE-06:
Sensitive communication information is restricted.

RULE-07:
Safe communication windows must be respected.

RULE-08:
Emergency conditions require the configured human/emergency escalation workflow.

RULE-09:
Mediation must have a hard-stop mechanism for serious safety/coercion conditions.

RULE-10:
AI must not independently file a court case or issue a legal notice.

RULE-11:
Final legal-aid decisions remain under authorized human control.

RULE-12:
Every critical case action must be traceable.

RULE-13:
Users must be able to correct incorrect AI transcription/extraction.

RULE-14:
The system must distinguish AI-generated content from verified human information.

RULE-15:
The system must support low-bandwidth and accessibility-first entry routes.

RULE-16:
Sensitive outbound communication must require communication-safety validation.

RULE-17:
Case routing must support human correction when automated location routing is uncertain.

RULE-18:
A failed technical operation must not cause silent loss of a legal-aid request.

RULE-19:
Duplicate detection must lead to review, not automatic deletion.

RULE-20:
Legal-information content used by AI must be maintained through an authorized knowledge-management process.
```

------------------------------------------------------------------------

# 52. Final BLAS System Definition

``` text
BANGLADESH LEGAL AID SYSTEM (BLAS)

                    ┌─────────────────────────┐
                    │       CITIZEN           │
                    │ Manual / Voice / Web    │
                    └────────────┬────────────┘
                                 │
                    ┌────────────▼────────────┐
                    │ ID & CONSENT WORKFLOW   │
                    └────────────┬────────────┘
                                 │
                ┌────────────────▼────────────────┐
                │      AI ASSISTED INTAKE         │
                │ Voice • Bangla • Structuring    │
                │ Missing Data • Safety Signals   │
                └────────────────┬────────────────┘
                                 │
                    ┌────────────▼────────────┐
                    │    CASE CREATION        │
                    │ Provenance + Verification│
                    └────────────┬────────────┘
                                 │
                    ┌────────────▼────────────┐
                    │  DLAO ROUTING / QUEUE   │
                    └────────────┬────────────┘
                                 │
                    ┌────────────▼────────────┐
                    │ HUMAN REVIEW & DECISION │
                    └────────────┬────────────┘
                                 │
              ┌──────────────────┼──────────────────┐
              │                  │                  │
              ▼                  ▼                  ▼
       INFORMATION          MEDIATION       LEGAL ASSISTANCE
       / GUIDANCE          WORKFLOW          / LAWYER
              │                  │                  │
              │           ┌──────▼──────┐           │
              │           │ HARD STOP   │           │
              │           │ IF REQUIRED │           │
              │           └──────┬──────┘           │
              │                  │                  │
              └──────────────────┼──────────────────┘
                                 │
                    ┌────────────▼────────────┐
                    │ FOLLOW-UP & RESOLUTION  │
                    └────────────┬────────────┘
                                 │
                    ┌────────────▼────────────┐
                    │       CASE CLOSURE      │
                    └─────────────────────────┘
```

## Core BLAS Outcome

BLAS is to be designed as an **accessible, AI-assisted, human-controlled
digital legal-aid service system** in which:

-   a citizen can enter through a conventional verified digital
    workflow;
-   a person facing disability, digital-access, connectivity, or device
    limitations can use a voice/conversational workflow;
-   a proxy can initiate a case without the proxy's information being
    incorrectly treated as the applicant's confirmed information;
-   AI can listen, structure, summarize, identify missing information,
    provide approved legal awareness, and flag safety-related
    conditions;
-   a case can remain pending for human verification when required
    information is unavailable;
-   cases can be routed to the relevant District Legal Aid Office for
    authorized human review;
-   DLAOs, mediators, and panel lawyers can manage the appropriate
    stages of the case;
-   mediation can operate through low-bandwidth, asynchronous,
    voice-centric communication where appropriate;
-   serious safety conditions can trigger a hard stop and transition
    toward the appropriate human-controlled legal-aid workflow;
-   sensitive communication information remains restricted;
-   the complete case lifecycle is traceable;
-   accessibility and lack of digital literacy are treated as
    service-design requirements rather than automatic grounds for
    exclusion.

**The system is therefore designed around the principle: AI assists the
legal-aid process; authorized human officers, mediators, lawyers, and
institutions remain responsible for legal decisions and final case
actions.**
