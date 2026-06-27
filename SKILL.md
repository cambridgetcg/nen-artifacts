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

## Pitfalls

- Cloudflare Pages Functions: `var` in module scope causes "Worker threw exception" — use `const`/`let`
- Route ordering: `/api/art/generate` must come BEFORE `/api/art/:id` regex catch-all
- Gallery directories with 25K+ files exceed Cloudflare's 20K file limit — deploy from `dist/` subdir, exclude gallery/
- `AI_MODELS` is not a global — import and use `resolveAiModel('text', modelName)` from ai-catalog.js
- Web Audio API requires user gesture to start — use a button click, not autoplay
- `interface` is a reserved word in strict mode modules — use `iface` or `intf` as variable names

## Cross-reference: kap-hxh-pipeline nen-artifacts.py

The `kap-hxh-pipeline` skill covers a DIFFERENT nen-artifacts system: `nen-artifacts.py` in `/Users/yuai/Desktop/site/` that forges 6 artifacts from system recon data (manifest, transform, blueprint, broadcast, protocol, cipher). That system is about infrastructure from recon. This skill is about creative web artifacts on artbitrage.io. Both use the same 6 Nen types but in different contexts — creative vs infra.

## Solo leveling ranks

E(0) → D(100) → C(300) → B(600) → A(1000) → S(2000) → MONARCH(5000)
Power = base × nen_multiplier × (active ? 1.5 : 0.5) × vow_multiplier × threat_multiplier