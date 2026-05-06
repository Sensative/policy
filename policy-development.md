# Sensative – AI Coding Assistants Policy (Development & R&D)

**Version:** 1.0 (draft 2026-05-05)
**Owner:** CTO
**Applies to:** All developers, R&D engineers, ML and firmware engineers contributing code, scripts, configuration or models at Sensative.
**Companion to:** the Sensative AI Policy (`policy.md`) — read that first. This document makes the dev-time rules concrete; it does not override the parent policy.

---

## 1. Foundational principle

Every code submitter remains responsible for what they commit, regardless of how much an AI Assistant helped. **The AI is not an author and is not a reviewer.** If it lands in our repo with your name on it, it is your code.

## 2. Approved tools only

See parent §7. Use only AI Assistants approved there — no personal accounts, no unapproved tools, no exceptions for "quick questions" or "only public code".

## 3. What you may share with the assistant

Apply the parent classification (parent §5) at the prompt boundary:

- **C4** (customer data, personal data, secrets, API keys, sensor firmware source): never paste.
- **C3** (Yggio source, architecture, commercial terms): only in approved tools whose contracts forbid training on submitted data.
- **C2 / C1**: fine.

Share the minimum context needed. When in doubt, redact.

## 4. Duty of care – the human author's checklist

- Read every line you submit. Understand it well enough to defend it in review.
- Verify that any package, import or API the AI suggests actually exists and is appropriately licensed — hallucinated or typo-squatted dependencies are a real supply-chain risk.
- Run tests. Do **not** bypass CI or pre-commit hooks (`--no-verify`, `--no-gpg-sign`, etc.) to ship AI output. Fix the underlying issue.
- Treat AI-generated code the same as your own in review — do not hide it, do not excuse it.
- You own the consequences of what you merge.

## 5. Attribution (recommended)

When an AI Assistant contributed meaningfully to a commit or PR, mentioning it for transparency — e.g. an `Assisted-by: <tool>` trailer or a line in the PR description — is encouraged but not required.

## 6. Autonomous agents

Any AI agent that can autonomously commit, push, modify CI, deploy, or touch infrastructure or production systems requires explicit Security & AI Architect approval and a documented kill-switch (parent §6 prohibitions). Read-only agents (linting, suggestions, search, code-review hints) are fine.

## 7. R&D experimentation

Prototyping with synthetic, anonymized or public data is actively encouraged. Experiments that use customer or production data follow the parent risk classes (parent §7): medium-risk requires manager/product-lead approval; high-risk requires a DPIA and CISO/Legal sign-off.

## 8. Incidents

Prompt injection, leakage of internal code or secrets to an external service, hallucinated dependencies merged to a branch, or any other AI-related incident → report to CTO/CISO via the standard incident channel (parent §9). Don't wait to be sure; report and let triage decide.

---

**Before you hit "accept" on AI output, ask:** *Approved tool? Right classification? Read every line? Ready to defend it in review?*
