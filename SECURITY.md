# Security policy

## Product boundaries

Periscan only validates **customer-authorized, verified scope**. See
[`SECURITY_BOUNDARIES.md`](./SECURITY_BOUNDARIES.md) and
[`docs/SETTLED.md`](./docs/SETTLED.md) for the full floor:

- No destructive tests, real data exfiltration, credential theft, or persistence
- Denied tasks must never be queued
- **Fixed** requires a verification event
- Live Atomic / Caldera / SharpHound and similar offensive live packs stay off
  unless a separate legal/safety program is approved

A vulnerability report does not waive those rules.

## Reporting a vulnerability

**Inbox:** [GitHub private vulnerability reporting](https://github.com/seanheiney/periscan/security/advisories/new)

Until a public domain exists, **GitHub security advisories are the published
reporting channel.** This file does **not** invent a `security@` mailbox. Do
not guess `security@` plus any domain.

The report form works when the repository owner enables private vulnerability
reporting. Maintainers with repository access can also open a draft advisory
at the same URL.

If you believe you have found a security issue in Periscan (control plane, web,
runner, policy gates, or dependency supply chain):

1. **Do not** open a public GitHub issue with exploit details.
2. Submit a **private** advisory at the URL above (Security → Advisories →
   Report a vulnerability).
3. Include: affected component/version, reproduction steps against **your own**
   lab or written-authorized systems only, impact assessment, and any suggested
   fix.
4. **Do not** attach live exploit PoCs, ransomware, credential dumps, or
   weaponized payloads. Describe the defect; do not ship an exploit.

**Coordinated disclosure:** we aim to acknowledge a submitted advisory within
**72 hours** and to ship a fix or disclose within **90 days**, unless we agree
a longer embargo (for example a coordinated CVE).

## Scope of reports we accept

| In scope | Out of scope |
|----------|--------------|
| Authn/z bypass, tenant isolation breaks | Scanning third-party hosts without authorization |
| Policy/audit bypass (denied tasks queued) | Social engineering of customers |
| Runner task signing / result provenance flaws | DoS against public infra you do not operate |
| Fixed-without-verify paths | Purely theoretical issues without repro |
| Dependency CVEs in shipped default images | Issues only in Blocked/legal-review opt-in tools |

## Safe research

Use the local lab (`pnpm lab:up`, `pnpm lab:dev`) and verified lab scopes only.
Do not use Periscan to probe systems you do not own or lack written
authorization to test. Do not ask maintainers to enable live Atomic, Caldera,
SharpHound, or other SETTLED-off capabilities as part of a disclosure.
