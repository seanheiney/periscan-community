# Periscan open-core model

**This file is not a license change.** Root [`LICENSE`](./LICENSE) stays
proprietary until founder and counsel explicitly flip it. Community edition is
the open-core **validation slice**, not “we are open source now.”

Settled axiom: [`docs/SETTLED.md`](./docs/SETTLED.md). Plan (not a flip):
[`docs/OPEN_SOURCE_PROJECT_PLAN.md`](./docs/OPEN_SOURCE_PROJECT_PLAN.md).
Package tags (scaffold): [`docs/OPEN_SOURCE_LICENSE_MATRIX.md`](./docs/OPEN_SOURCE_LICENSE_MATRIX.md).
Offering: [`COMMUNITY.md`](./COMMUNITY.md). Contribution law: [`GOVERNANCE.md`](./GOVERNANCE.md).

---

## Option A (recommended) — Apache-2.0 core later + commercial edge

| Layer | Intended license | Status today |
| --- | --- | --- |
| Core control plane (API, policy, evidence graph, runner protocol) | Apache-2.0 **later** | Proprietary product LICENSE |
| Lab, safe/passive modules, connector *interfaces* | Same as core **later** | Proprietary product LICENSE; engines keep **upstream SPDX** |
| Hosted multi-tenant SaaS, SSO/SCIM polish, MSSP portfolio, premium compliance catalogs, support SLAs | Commercial | Commercial / not Community-supported |
| Live Atomic / Caldera / SharpHound / sqlmap / Metasploit | **Never default** | Catalog theater; not installable as validation |

Option A is the **recommended future split**, not a completed split. There are no
per-package Apache-2.0 `LICENSE` files. Do not add them in a coding session.

Other models from the plan (full MIT/Apache, BSL/SSPL source-available, dual
license) stay on the table for counsel. They are not the working assumption.

---

## What Community edition is TODAY

A **product contract**, encoded in `packages/shared/src/community-edition.ts`:

- Verified customer-authorized scope
- Policy decision on every start (denied work never queues)
- Default engine pack: **permissive SPDX only** (MIT / Apache-2.0 / BSD-3-Clause /
  NPSL) plus first-party checks
- Evidence ledger; findings for a mission are evidence-intersected, not theater
- Remediations from that mission; **Fixed** only after a verification event

That is the open-core *validation* offering. Third-party engines keep their own
SPDX. Node dependencies are inventoried in
[`licenses/THIRD_PARTY_NOTICES.md`](./licenses/THIRD_PARTY_NOTICES.md).

It is **not**:

- A public LICENSE flip or OSI-open product
- Full multi-vector BAS, automated pentest, or a CNAPP/RBVM replacement
- GPL / LGPL / AGPL in the default Validate start (Engine Lab + license accept)
- Live Atomic, Caldera, SharpHound, sqlmap, or Metasploit

---

## What is commercial

Stay commercial even after a future Option A split:

| Surface | Why it is not Community core |
| --- | --- |
| Hosted multi-tenant SaaS operations | Cloud ops, tenancy at scale, support SLAs |
| Enterprise identity polish (SSO/SCIM as a managed product) | Funded edge, not the validation loop |
| MSSP portfolio / multi-client operations | Commercial services |
| Premium / complete compliance catalogs as a product | Evidence support is core; certification theater is refused |
| Payments, AWS Marketplace, Production connector certification | Partner keys and counsel; out of Community GA |
| Design-partner onboarding and support SLAs | Services |

The monorepo still contains commercial-adjacent routes (MSSP, billing meters).
Presence in the tree does **not** make those Apache-licensed or Community-supported.

---

## Explicit “not a LICENSE flip”

| Do | Do not |
| --- | --- |
| Keep root [`LICENSE`](./LICENSE) proprietary | Rewrite `LICENSE` or publish “we are open source now” |
| Call this Community / open-core **validation** | Call the repository MIT or Apache-2.0 today |
| Attribute upstream engines by name + SPDX | Present Trivy/Nuclei/Gitleaks as Periscan-authored |
| Fail CI on `pnpm licenses:check` | Launder AGPL / SSPL / BSL / Commons Clause / PolyForm into the default image |
| Point strangers at [`COMMUNITY.md`](./COMMUNITY.md) | Equate Engine Lab catalog size with Community start |

When founder + counsel flip the product license, this file and the matrix get a
dated amendment. Until then, every PR that changes `LICENSE` is a **STOP**.
