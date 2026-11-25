# 🔒 Security Policy

## Scope

This repository publishes **prompt templates and methodology documentation** for
a Symbolic Prompting Framework (SPF), including dual-use examples that describe
how to chain LLMs to analyze CVEs and, in later stages, generate verification
scripts (see `ai_3xploit.md`).

This repository does **not** host, distribute, or execute:
- Pre-built exploit binaries or ready-to-run attack tools
- Malware, C2 infrastructure, or credential-stealing code
- Any hosted service or API that performs attacks on behalf of users

All generated-code examples and demonstration videos were produced against
infrastructure the author owns or controls, in an isolated lab environment.

## Reporting a Vulnerability

If you believe you have found:
- A security vulnerability in any code sample published in this repository, or
- An unpublished (non-public) vulnerability discovered **while using** the
  prompts/pipeline described here,

please **do not** open a public GitHub issue with technical details.

Instead, use **GitHub's private vulnerability reporting**:
1. Go to the **Security** tab of this repository.
2. Click **"Report a vulnerability"**.
3. Fill in a description, reproduction steps (if applicable), and potential impact.

You will receive an acknowledgment within **7 days**.

## Reporting Misuse or Abuse of This Content

This repository contains dual-use security research material. If you believe
this content is being used to facilitate an active, unlawful attack, or you
have concerns about how this material is being used or redistributed:

- **Open a public issue** in this repository describing your concern.

This channel lets third parties raise concerns directly with the maintainer
without filing a formal abuse report with GitHub first.

## Responsible Disclosure

If this pipeline helps you identify a vulnerability that is not yet public,
follow coordinated disclosure: notify the affected vendor first, allow a
reasonable disclosure window (typically 90 days or per the vendor's policy),
and only share PoC details publicly after a patch or public disclosure. See
`ai_3xploit.md` → "Responsible Disclosure Policy" for the full procedure this
project expects users to follow.

## Supported Content

| Component | Status |
|---|---|
| Prompt templates (1–6) | Actively maintained |
| Prompt templates (7–8, active-testing code generation) | Maintained; dual-use, high-risk — see `ai_3xploit.md` for limitations |

---

*This policy covers vulnerabilities in this repository's own content and
reporting channels for misuse. It does not grant any authorization to test,
attack, or scan systems you do not own or have written permission to test.*