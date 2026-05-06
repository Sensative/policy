# Sensative – AI Policy

**Version:** {{VERSION}} ({{DATE}})
**Owner:** CISO/CTO
**Applies to:** All employees, consultants and partners who use or integrate AI, GPT models or agents in Sensative's operations.

**Use only AI services approved by Sensative under company license — never personal accounts. The currently approved services and the approval process for additions are listed in §7.**

---

## 1. Purpose

Enable rapid innovation, productivity and technical development with AI, GPT models and agents without compromising security, privacy, compliance or customer trust. The policy provides employees with clear guidance on what is permitted, what requires approval, and what is prohibited – so that everyone can use AI safely and effectively in their daily work.

## 2. Scope and Sensative's position on AI

Sensative is committed to using AI to accelerate our work and our products, while keeping customer trust and data protection non-negotiable. We adopt AI through enterprise vendors under approved contracts, treat external models as a managed dependency rather than infrastructure we control, and keep humans accountable for everything we publish or ship.

This policy applies to both the use of external AI services and the integration of AI-based functionality into our products, in all environments: product development (Yggio and embedded), support, sales, marketing, operations, HR and internal administration.

### Definitions

- **Agent:** An AI system that can take actions across multiple steps (write files, call APIs, execute code, send messages, modify systems) without per-step human approval. A chat assistant that only generates text in response to prompts is not an agent.
- **Approved tool:** An AI service, model or library on the current approved list maintained by the Security and AI Architect (see §7).
- **AI feature:** AI-driven functionality embedded in another product (e.g., Notion AI, GitHub Copilot Chat, Slack AI, meeting summarization in Zoom/Teams). AI features are in scope and require the same approval as standalone AI tools.

## 3. Principles

- **Security first:** No innovation may compromise data protection or compliance.
- **Human in the loop:** AI assists; humans are accountable for decisions, quality and delivery.
- **Minimum necessary data:** Never share more data than required for the task.
- **Traceability:** Every use and integration of AI must be explainable and auditable.
- **Innovation:** Experimentation is encouraged in controlled environments.
- **Regulatory alignment:** Use of AI complies with the EU AI Act, GDPR and other applicable regulations. Practices prohibited under EU AI Act Art. 5 are off-limits regardless of any other approval.
- **Vendor reliance is a risk we manage:** Since we rely on third-party models, we actively manage vendor, contract and continuity risk.

## 4. Roles and responsibilities

- **Board/CEO:** Sets risk appetite and approves the policy.
- **CTO/CISO:** Owns the policy, risk-classifies use cases and handles incidents.
- **Security and AI Architect:** Approves AI tools, models, agents and integrations; maintains the list of approved tools and vendors.
- **CEO/Legal:** Ensures GDPR, contractual and IP compliance; supports customer agreements concerning AI; reviews vendor contracts and DPAs.
- **Product and engineering leads:** Ensure that AI use within product teams complies with the policy; approve medium-risk use cases.
- **All users:** Comply with the policy, document use where required, and report deviations and incidents.

## 5. Data classification

- **C4 – Strictly confidential:** Customer data, personal data of customers or other external data subjects (in particular GDPR Art. 9 categories), security keys, API keys and authentication tokens, IoT telemetry attributable to an end customer, and sensor firmware source code. Must never be shared with, or used for training by, an external provider. *Internal personal data (employee names, work email, calendar entries, internal HR communications) is handled under normal confidentiality practice; it does not automatically fall into C4 but must not be used outside approved tools or shared with parties that lack an appropriate basis under GDPR.*
- **C3 – Confidential:** Internal business information, unpublished product code, architecture descriptions, commercial terms. Permitted only in approved tools under contracts that guarantee data is not used for training.
- **C2 – Internal:** General internal information, documentation, generic code and configuration without secrets. May be used in approved tools.
- **C1 – Public:** Material intended for publication. Free to use.

## 6. Permitted and prohibited uses

### Permitted (examples)

- Code assistance, refactoring and test generation at C2–C3 level in approved environments.
- Summarization and analysis of public or C2 documents.
- Research and prototyping using synthetic or anonymized data.
- Reviewing public documentation and standards (e.g. LwM2M, MQTT, BLE, NB-IoT).
- Generating example code and debugging assistance for embedded toolchains, provided that internal firmware code is not shared.
- Building RAG and prompt-based features on top of approved vendor models, where the vendor model itself is not modified.

### Prohibited

- Uploading C4 data or customer data to external AI services or training environments.
- Publishing AI-generated content without human review.
- Developing agents with autonomous access to production systems without approval.
- Using non-approved AI tools for work tasks.

### Decisions about individuals

AI must not be the deciding factor in decisions about identified individuals — recruitment, salary, performance, role assignment, account offboarding, or support escalation involving named end users. This is the EU AI Act high-risk category for employment AI; we apply the same line more broadly to anyone we make decisions about.

AI-assisted *analysis* is permitted when all of the following hold:

- A named human makes the final decision and is accountable for it.
- The reviewer evaluates the underlying facts, not only the AI's summary or recommendation.
- The use is documented: which tool, what the AI was asked, what the human concluded.
- Affected individuals are informed where GDPR, the EU AI Act or a contract requires it.

*Permitted, for example:* summarising a CV that a recruiter then reads in full; clustering support tickets to spot patterns; drafting written feedback that a manager edits and signs.

*Prohibited, for example:* ranking candidates by an AI score that drives the shortlist; flagging customer accounts for offboarding from an AI signal alone; generating performance ratings.

## 7. Tools, models and providers

All models used by Sensative are operated by external providers. Vendor selection and contract terms are therefore a primary control.

### Approved services

The following AI services are currently approved for use under company license:

- **Claude** — Anthropic Team License (Sensative AB subscription). General-purpose AI assistant; permitted for C1–C3 data subject to §5–§6.
- **Microsoft 365** — Sensative AB tenant, including Copilot features where the user is licensed. Permitted for C1–C3 data within the tenant; outputs that leave the tenant follow the same rules as any external AI service.
- **GitHub Copilot** — Sensative AB organisation on GitHub Enterprise Cloud, including Copilot features (code completion, chat, PR review) where the user is licensed. Permitted for C1–C3 data subject to §5–§6; engineers using Copilot for source-code work additionally follow `policy-development.md`.

This list is a snapshot. The authoritative, up-to-date list will be maintained by the Security and AI Architect on the internal AI Tools register as that register is established; until then, the snapshot above and direct approval by the Security and AI Architect are authoritative. Additional tools must be approved before use (see below).

### General rules

- Only approved AI services, models and libraries may be used (see *Approved services* above). Additional tools require Security and AI Architect approval before use.
- **AI features in third-party tools** (e.g., Notion AI, GitHub Copilot Chat, Slack AI, meeting summarization in Zoom/Teams) are in scope and follow the same approval process. Disable by default until reviewed.
- **Provider requirements:** data residency in the EU or an approved jurisdiction, encryption at rest and in transit, opt-out from training on customer data, clear logging and deletion procedures, and a DPA where personal data may be processed.
- **Enterprise licenses:** Always use the company license rather than personal accounts for work purposes.
- Personal accounts in AI services may not be used.
- **Vendor continuity:** For AI capabilities embedded in Yggio or embedded products, evaluate model portability and have a documented fallback in case a provider becomes unavailable or changes terms.
- **Logging and retention:** Where approved tools provide audit logs of prompts and outputs, those logs are retained according to the standard incident-and-audit retention schedule. Prompts inherit the classification of the data they contain (see §5).

### Risk classes

Each AI use case is classified by the likely impact if it fails (data exposure, incorrect output reaching customers, regulatory issue, operational disruption):

- **Low:** Internal productivity use of approved tools on C1–C2 data (drafting, summarization, code search). No customer impact if the output is wrong; reversible.
- **Medium:** Use of C3 data in approved tools, AI features integrated into internal workflows, or prototypes on synthetic or anonymized customer-shaped data. Errors could cause limited internal impact or require rework.
- **High:** AI in customer-facing products, agents acting on production systems, processing of C4 data (only via documented exception), or use cases falling under EU AI Act high-risk categories. Errors could cause customer harm, regulatory exposure or material business impact.

### Requirements per class

- **Low:** briefly documented, peer reviewed.
- **Medium:** risk analysis, sandbox testing, approval by manager or product lead.
- **High:** DPIA, CTO/CISO and Legal approval, controlled pilot, documented sunset plan.

## 8. Intellectual property and licenses

- **AI-generated content in products:** Before AI-generated code, text or images are incorporated into a product or public material, copyright, license terms and any third-party contributions must be reviewed.
- **Customer data and IP:** Customer data belongs to the customer. AI use must not result in customer data being mixed with data from other customers or trained into shared models.
- **Open-source contributions:** AI-generated code intended to be contributed to open-source projects is reviewed with particular attention to licensing and provenance.
- **Customer-facing transparency:** When customers or end users interact with AI we operate, or see AI-generated content as part of our products or communications, this is disclosed in line with EU AI Act Art. 50 and any contractual commitments. Sales, support and product teams are responsible for ensuring this disclosure where applicable.

## 9. Incidents, training and awareness

### Incident handling

- Suspected data leakage, prompt injection, hallucinations leading to incorrect decisions, or any other AI-related incident must be reported promptly to the CTO/CISO via the regular incident channel.
- Incidents are triaged according to the existing incident process; AI incidents are logged separately for follow-up and learning.

### Training and awareness

- All employees will be given a brief introduction to the AI policy and safe AI use as part of onboarding and after major policy revisions; this is being rolled out and will become a standing part of onboarding.
- Domain specific governing document (e.g software development) guidelines must be followed if such a document exists for your domain.
- Manager of each team is responsible for making sure that the team has the relevant information and training.
- Development teams receive deeper training in AI-assisted code development, prompt injection and the safe use of agents.
- The Security and AI Architect publishes ongoing examples, lessons learned and updates to the approved tool list.

## 10. Review and follow-up

- The policy is reviewed quarterly.
- **Key metrics:** usage per approved tool, incidents (including hallucination and prompt-injection incidents), customer-impacting errors, share of AI-generated code passing through code review, accuracy/model quality of integrated vendor models, and tracked benefits (cycle time, deploy frequency).
- High-risk use cases, agents and any exception-approved fine-tuning are audited every six months; the approved tool list and logs are subject to ongoing light supervision.

## 11. Exceptions

- Exceptions are granted by the CTO/CISO in consultation with Legal. They are time-limited and documented.
- Exceptions are recorded in an exceptions register (maintained by the Security and AI Architect) including justification, time period, risk assessment and compensating controls.
- **In particular:** any proposal to train or fine-tune a model on Sensative or customer data is treated as a high-risk exception, requires a DPIA, written CTO/CISO and Legal approval, and is reported to the CEO.

---

## Appendix A – Quick guide for employees

Before pasting anything into an AI service, ask yourself:

1. Is this tool approved for what I am doing?
2. What classification (C1–C4) does the information I am sharing have?
3. Would I be comfortable if a customer saw this exchange?
4. Have I reviewed what I intend to use from the AI?
5. Who is accountable for the final result? (Answer: I am.)

When in doubt, ask your manager or the Security and AI Architect.