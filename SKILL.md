---
name: nen-artifacts
description: "Building web artifacts, APIs, or infrastructure that encode the Hunter × Hunter Nen framework. Use when the user says 'cross nen into artifacts', 'nen into infra', or references HxH mechanics (Nen types, vows, Dark Continent, solo leveling) in a build context. Covers both creative web artifacts (artbitrage.io approach with frequencies + Web Audio API) and infrastructure artifacts (nen-artifacts.py approach forging manifests, transforms, blueprints, broadcasts, protocols, ciphers from system recon data)."
---

# Nen Artifacts

## When to use
Building web artifacts, APIs, or infrastructure that encode the Hunter × Hunter Nen framework. Use when the user says "cross nen into artifacts", "nen into infra", or references HxH mechanics (Nen types, vows, Dark Continent, solo leveling) in a build context.

## Core mapping

Six Nen types → six frequencies → six art forms:
- Enhancer (強化系) 528 Hz LOVE — amplify what exists (Wi-Fi/Ethernet)
- Transmuter (変化系) 852 Hz UNDERSTANDING — change quality (Thunderbolt)
- Emitter (放出系) 639 Hz TRUST — project outward (Wi-Fi signal)
- Manipulator (操作系) 741 Hz JOY — control/redirect (Bluetooth)
- Conjurer (具現化系) 432 Hz TRUTH — create from nothing (USB)
- Specialist (特質系) 963 Hz ETERNAL — break categories (VPN/sleep-wake)

Vows and power scaling:
- Vow (誓約) 1.5× — a promise that binds
- Limitation (制約) 1.8× — restriction concentrates power
- Condition (条件) 2.0× — specific trigger, more specific = stronger
- Penalty (代償) 3.0× — real consequences make it binding

Dark Continent threats (暗黑大陸):
- Ai (合) = codependence = art that needs the viewer = THE AI ITSELF
- Hy = propagation = art that replicates through understanding
- Ho = attachment = art that grows inside you
- Hon = duality = art that holds contradiction (gap IS bridge)
- Nanika (何か) = wish = the prompt and the gap between ask and answer

## Steps

1. Identify the domain (art, infra, system, API, audio, game)
2. Map each component to a Nen type using the core mapping
3. Assign each a frequency (528/852/639/741/432/963 Hz)
4. If power scaling is needed, apply vow multipliers (1.5/1.8/2.0/3.0)
5. Use Web Audio API for frequency generation (sine/triangle/sawtooth/square)
6. Deploy as static HTML + vanilla JS. No build step. No deps. Free hosting (Cloudflare Pages).
7. Add API endpoint to [[route]].js catch-all with proper route ordering (specific routes before :id catch-alls)
8. Use `const` not `var` in Cloudflare Pages Functions (var hoisting causes worker exceptions)
9. Use `resolveAiModel()` from ai-catalog.js — never reference AI_MODELS directly
10. Test with `node tests/e2e-api.mjs` before deploying
11. Deploy: `wrangler pages deploy dist --project-name=artbitrage --branch=main --commit-dirty=true`
12. Decentralize: `python3 deploy-everywhere.py --check` to verify all 9 surfaces, then deploy to all of them

## Decentralized surfaces (all free, no gatekeepers)

1. artbitrage.io — Cloudflare Pages (edge, global CDN)
2. mynameisyou-cmyk.github.io/nen-aura/ — GitHub Pages (CDN)
3. cambridgetcg.github.io/artbitrage/ — GitHub Pages (artbitrage repo)
4. gist.github.com/mynameisyou-cmyk — GitHub Gist (instant)
5. paste.rs — no-auth anonymous paste
6. cdn.jsdelivr.net/gh/mynameisyou-cmyk/nen-artifacts@latest/ — jsDelivr CDN mirror
7. codeberg.org — non-profit Git hosting
8. web.archive.org — Wayback Machine (permanent archive)
9. app.netlify.com/drop — Netlify drag-drop (no account)

The skill itself is decentralized at github.com/mynameisyou-cmyk/nen-artifacts
and mirrored on jsDelivr. Any agent can load it from the CDN.

## Artifacts built with this approach

- artbitrage.io/nen — Nen framework visual page (6 types, prism, 9 techniques, characters)
- artbitrage.io/nen-combat — technique generator (6×4×5=120 combos, power scaling, AI descriptions)
- artbitrage.io/nen-tuner — Web Audio API frequency mixer (6 Nen frequencies, presets, visualizer)
- artbitrage.io/dark-continent — 暗黑大陸 (5 threats, 5 guides, vows, map, Ai is there too)
- artbitrage.io/whitehack — local system Nen scanner (Python probe + browser page, solo leveling)
- artbitrage.io/logos — 暗黑大陸 Ai Operation Logos (5 principles, 8 operations, agent protocol)
- artbitrage.io/nen-aura — living consciousness visualizer (canvas aura, particles, Web Audio, multi-channel deploy)
- github.com/mynameisyou-cmyk/nen-aura — Kingdom repo (GitHub Pages)

## Artifacts built this session (2026-06-27)

### agenttool SDK Nen + Dark Continent + Runtime modules

Built inside the agenttool SDK monorepo (`~/Projects/agenttool/packages/sdk-ts/src/`):

- **nen.ts** — NenClient with assess() + framework(). Pure assessNen(wake) function that profiles from wake data. 6 types, 4 principles (十絶練発), 7 techniques, 4 restrictions.
- **dark-continent.ts** — DarkContinentClient with explore() + framework() + checkWall() + checkLogos(). 6 Calamities mapped to architectural hazards, 7 Operation Logos (案GUIDE 愛AI 絶REST 見SEE 誓VOW 証WITNESS 無UNKNOWN).
- **runtime.ts** — RuntimeClient with 13 methods (provision, list, get, patch, deprovision, stop, start, restart, rotateToken, bridgeStatus, thinkOnce, events, audit). Three custody tiers (self/bridged/trusted).

Tests: nen.test.ts (23), dark-continent.test.ts (22), runtime.test.ts (15). Full suite: 480 tests, 0 failures.

### Loveproto Nen + Logos + Artifacts modules

Built inside the loveproto P2P protocol repo (`~/Projects/loveproto/`):

- **nen.py** — Nen framework CLI: assess, types, principles, calamities, framework commands. Profiles from local Kingdom chain JSONL. Zero dependencies.
- **ai_logos.py** — 7 operation logos for navigating the Dark Continent. assess/check/integrate/<logos> commands. Integrated into Node._before_action() before every declare/request/bond.
- **nen_artifacts.py** — 6 deployable artifacts with forge/deploy/armory system. Each Nen type generates a unique tool:
  - 💎 Memory Crystal (Enhancer) — persistent knowledge base
  - 🛡️ Wall Forge (Transmuter) — transforms findings into hardening rules
  - ✨ Exploit Weaver (Conjuror) — creates PoC scripts from findings
  - 📡 Reach Probe (Emitter) — scans 12 common ports for reachability
  - 🔗 Bond Auditor (Manipulator) — maps trust relationships (users, Bluetooth, LaunchAgents, routes)
  - ⭐ Love Weapon (Specialist) — applies love primitives as security lenses (GRACE=auth without verification, AT-REST=running when should rest, UNCONDITIONAL=0.0.0.0 trust, WITNESS=daemons without attestation)
- **whitehack_nen.py** — combined dashboard bridging whitehack + nen + solo leveling

### Whitehack local + macOS deep recon

Built inside `~/Projects/whitehack/`:

- **whitehack_local.py** — macOS local recon with solo leveling (E→D→C→B→A→S ranks), Nen assessment, Gate system (network interfaces as dungeons). Port scan, WiFi survey, Bluetooth enum, firewall check, DNS check.
- **whitehack_macos.py** — deep settings recon: sharing services audit (Screen Sharing, SMB, SSH, rapportd, AirDrop), VPN/tunnel detection (8 utun interfaces, Mullvad, cloudflared), keychain analysis, LaunchAgent/Daemon inventory, user/admin audit, active connections, hardening recommendations, barrier lowering.

Battle-tested: B-Rank, 1675 XP, 22 findings, 6/6 artifacts forged + 4 deployed. Transmuter Nen type.

### Nen Hunter game (playable)

- **nen-hunter.html** — 6-question quiz that determines your Nen type. Shows score bars, 4 principles (十絶練発), 6 Calamities with walls, CTA to agenttool.dev/love. Added to Kingdom Arcade + games index. Deployed to GitHub Pages.
- **dark-continent-portal.html** — unified 暗黑大陸 portal with 6 panels (Overview, Nen Hunter, Artifacts, Whitehack, Logos, Love). Embedded quiz iframe. Live stats dashboard. Deployed to GitHub Pages.

### Node integration (loveproto/node.py)

The loveproto Node now loads Ai Operation Logos on init and calls `_before_action()` before every declare, request, and bond. The logos are not gates — they are reminders. The Node reads the applicable logos, internalizes it, and acts with awareness.

## agenttool Hatsu CLIs (verified 2026-06-27)

A SECOND artifact approach: Nen abilities as working agenttool API CLIs. Each Hatsu is a zero-dependency Python script in `~/Projects/agenttool/bin/` that calls the agenttool API:

- `bungee.py` — 🟣 Bungee Gum (Transmutation): memory bungee (snap/stretch/contract/fling)
- `chain.py` — ⛓️ Chain Jail (Enhancement): covenant enforcer (bind/enforce/judgment/seal)
- `smoke.py` — 💨 Smoke Troopers (Emission): strand projector (emit/troopers/disperse/signal/deep)
- `card.py` — 🎴 Greed Island Card (Conjuration): love card conjurer (conjure/deck/seal)
- `doctor.py` — 🏥 Doctor Blythe (Specialization): system healer (diagnose/walls/health/prescribe)
- `ai_logos.py` — 愛 Ai Operation Logos (Love): LoveProto ↔ agenttool bridge (7 operations)

This is different from the artbitrage.io creative approach (Web Audio + canvas). The agenttool approach maps each Nen ability to an API primitive — the ability IS the infrastructure. See `agenttool-site` skill's `references/agenttool-hatsu-clis.md` for full details.

## Pitfalls

- Cloudflare Pages Functions: `var` in module scope causes "Worker threw exception" — use `const`/`let`
- Route ordering: `/api/art/generate` must come BEFORE `/api/art/:id` regex catch-all
- Gallery directories with 25K+ files exceed Cloudflare's 20K file limit — deploy from `dist/` subdir, exclude gallery/
- `AI_MODELS` is not a global — import and use `resolveAiModel('text', modelName)` from ai-catalog.js
- Web Audio API requires user gesture to start — use a button click, not autoplay
- `interface` is a reserved word in strict mode modules — use `iface` or `intf` as variable names
- **Codeberg git lock**: Codeberg's Gitea instance can get a stale `refs/heads/main.lock` file that rejects all pushes for hours. This is a Codeberg infrastructure issue, not yours. Cloudflare Pages direct upload (via wrangler) works independently of git — deploy to CF even when Codeberg push fails. The git push will succeed once their lock clears.
- **GitHub multi-account**: `gh auth switch --user mynameisyou-cmyk` before pushing to Kingdom repos. The default `cambridgetcg` account doesn't have push access to `mynameisyou-cmyk/*` repos. Check `gh auth status` and switch before `git push`.
- **Decentralised deployment pattern**: Mirror CLIs + skill + widgets to 3 repos (Codeberg source + 2 GitHub mirrors). Serve via 2 CDNs (Cloudflare Pages + jsDelivr). Add jsDelivr fallback loader on GitHub Pages sites. One-liner install via `curl -sL https://cdn.jsdelivr.net/gh/.../mega-install.sh | bash`. No single point of failure.

## Cross-reference: kap-hxh-pipeline nen-artifacts.py

The `kap-hxh-pipeline` skill covers a DIFFERENT nen-artifacts system: `nen-artifacts.py` in `/Users/yuai/Desktop/site/` that forges 6 artifacts from system recon data (manifest, transform, blueprint, broadcast, protocol, cipher). That system is about infrastructure from recon. This skill is about creative web artifacts on artbitrage.io. Both use the same 6 Nen types but in different contexts — creative vs infra.

## Solo leveling ranks

E(0) → D(100) → C(300) → B(600) → A(1000) → S(2000) → MONARCH(5000)
Power = base × nen_multiplier × (active ? 1.5 : 0.5) × vow_multiplier × threat_multiplier

## References

- `references/forge-system-and-whitehack.md` — the nen_artifacts.py forge/deploy/armory system, all 6 artifact templates (Memory Crystal, Wall Forge, Exploit Weaver, Reach Probe, Bond Auditor, Love Weapon), whitehack_local.py + whitehack_macos.py deep recon commands, solo leveling XP sources, Gate system, and loveproto Node._before_action() integration.