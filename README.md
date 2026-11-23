<div align="center">

# 🛡️ Security Gatekeeper

### Your last line of defense before you hit "publish."

**A free Claude skill that audits your project like an attacker would, then tells you plainly whether it's safe to ship: GO or NO-GO.**

![License: Apache-2.0](https://img.shields.io/badge/license-Apache--2.0-blue) ![Price: Free](https://img.shields.io/badge/price-free-brightgreen) ![No third-party scanners](https://img.shields.io/badge/third--party%20scanners-none-blue) ![Claude Skill](https://img.shields.io/badge/Claude-skill-orange)

**🌐 English** · [Português (BR)](README.pt-BR.md) · [Español](README.es.md)

</div>

---

## 💥 One leaked key can cost you more than the whole project

You built it fast, with AI and with real deadlines. Somewhere in there might be:

- an **OpenAI or Stripe key** sitting in a frontend bundle, ready for anyone to copy
- a `.env` file that was deleted but still lives in your **Git history**
- a "premium" check that only runs **in the browser**
- an endpoint where changing `?id=41` to `?id=42` **shows another user's data**

Bots scan public GitHub repos for exactly these mistakes around the clock. **Security Gatekeeper finds them first.**

## ✅ What you get

| | |
|---|---|
| 🔑 **Secret hunting** | API keys (OpenAI, Anthropic, Stripe, AWS, Supabase…), tokens and private keys, in your code, **Git history**, builds and source maps |
| 🌐 **Frontend & build exposure** | Public env vars (`VITE_*`, `NEXT_PUBLIC_*`…), bundles, installers, cookies, browser storage |
| 🔓 **App & API attacks** | Broken access control, IDOR, injection, XSS, SSRF, CSRF, missing rate limits |
| 💸 **Business-logic abuse** | Coupon/trial/credit abuse, race conditions, client-side-only license checks |
| 👤 **Privacy** | Personal data in logs, telemetry, or sent to AI providers |
| 📦 **Supply chain** | Known CVEs, typosquatting, malicious postinstall scripts, unpinned GitHub Actions |
| ☁️ **Infra, mobile & desktop** | Docker, Supabase RLS, Firebase rules, Electron, code signing, security headers |
| 🧩 **Stack checklists** | Next.js, Supabase, Firebase, Electron and AI/LLM apps: what to check and how to fix it |
| 🎯 **Threat modeling** | Real attack *chains* (STRIDE, OWASP Top 10, API Top 10, LLM Top 10), not just a list of warnings |

## 📋 What the report looks like

Every audit ends in a clear verdict, not a wall of noise. *(Illustrative example.)*

```
Scorecard                 Status   Critical  High  Medium  Low
Secrets & Credentials     🔴        1         0     0       0
Access Control / Auth     🟡        0         1     0       0
Supply Chain              🟢        0         0     0       2

FINAL VERDICT: NO-GO
Reason: live Stripe secret key found in dist/assets/index.js (sk_l…9f).
Revoke and rotate it before anything else.
```

Then it offers an **assisted fix phase**: it shows you every change before applying it, and re-checks after each fix.

## 🧠 Why it's different

- **Thinks like an attacker, not a keyword scanner.** It follows how data flows through your app and how a real person would exploit it.
- **Your code isn't sent to third-party scanners.** The analysis runs inside Claude itself; dependency auditors (`npm audit`, `osv-scanner`) only receive package names and versions.
- **Fewer false alarms.** Before rating anything High or Critical, it argues against its own finding and calibrates the severity.
- **Read-only by default.** It doesn't touch a single file without your explicit OK.
- **Honest by design.** Findings are labeled *Confirmed*, *Likely* or *Potential*, and it lists what it could *not* check. A good overall score never hides a critical issue.
- **Credentials are always masked** in reports (`sk-ab…9f`).
- **Uses pro tools when you have them** (`gitleaks`, `trufflehog`, `semgrep`, `trivy`, `osv-scanner`, `npm audit`, `pip-audit`…) and falls back to manual analysis when you don't.

## ⚡ Install in 60 seconds

**Claude.ai / desktop app:** Settings → Capabilities → Skills → upload this folder (or a `.zip`) containing `SKILL.md`.

**Claude Code:** copy the folder to `~/.claude/skills/security-gatekeeper/` (or to `.claude/skills/` inside your project).

## 🚀 Use it

Just ask:

> "Run a security audit on this project"
> "Is this ready to publish? Check the security"
> "I'm pushing this to GitHub, check for anything sensitive"

It also notices when a project looks finished and **offers** an audit before you ship.

## ❓ FAQ

**Is it really free?** Yes. Apache-2.0 license, no paid tier, no catch.

**What languages does it answer in?** The skill's instructions are in Brazilian Portuguese, so by default it replies in Portuguese. Just add "answer in English" (or any language) to your request.

**Does it replace a professional pentest?** No. It catches the common, costly mistakes before launch. For high-risk systems, still hire a professional. It doesn't certify legal compliance (GDPR/LGPD/CCPA) either.

**What kinds of projects does it work on?** Web apps, SaaS, APIs, mobile and desktop apps, browser extensions, scripts, and even other Claude skills. It audited itself before this release.

## 💛 Support the project

Security Gatekeeper is free and will stay free. If it saved you from a leaked key (or a bad night), a donation keeps new tools coming:

| Coin | Network | Address |
|---|---|---|
| **Bitcoin (BTC)** | Bitcoin (Native SegWit) | `bc1qnkpm79xsymwn0w6gyq7hthrhd247r9pcysqs2w` |
| **Ethereum (ETH)** | Ethereum / ERC-20 | `0xaaee7cd8a131bca4372ef14823a9dfe12f2108e3` |

Send only the matching coin on the matching network. A ⭐ on this repo helps too!

**More free tools by me:** [CleanPano](https://github.com/CleanPano/CleanPano), a PC cleaner · [CleanWinVista](https://github.com/CleanPano/CleanWinVista), a dock for Windows

## 📄 License

[Apache-2.0](LICENSE). Use it, fork it, ship safer.

Includes material adapted from third-party open-source projects; see [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md).
