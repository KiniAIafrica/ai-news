# Build an AI — Comparison & Recommendations
### How 8 acclaimed games stack against our current design — what to borrow, what's at risk

> Synthesis of the 8 game deep-dives (`research/games/`) against our design (`design/`). The founder asked specifically for **what to borrow** and **candid risks/gaps** — this report leads with both. Recommendations cite the game they draw from.

---

## 1. Executive summary (the 7 biggest takeaways)

1. **Our core loop is teachable but underspecified.** The pipeline (Data → Compute → Train → Fine-Tune → Test → Market) is locked, but **board shape, win condition, and movement are not.** Decide movement first; the win condition flows from it.
2. **Power Grid's dynamic resource price curve is our single most valuable steal.** Compute/chips/power are genuinely scarce — a rising-price market makes early buyers win bargains, late buyers overpay, and **automatically curbs the runaway leader.**
3. **Terraforming Mars' engine-building + project-card content engine is our replayability backbone.** ~150–250 thematic cards shuffled each game = real variety; pair with Pokémon TCG's expansion/rotation model to stay fresh forever.
4. **Our environmental/societal layer is the differentiator but is currently vague.** Adopt Terraforming Mars' single **global track** (compute fills it; sustainable choices score back; it feeds final scoring) instead of three loose meters.
5. **Co-op vs competitive is an unresolved fork.** Pandemic shows co-op + asymmetric roles kills "quarterbacking" and suits classrooms; our draft leans competitive. Build both, pick a primary, pilot it.
6. **The "AI Game Master" is sound but later-tier.** Use D&D's split model (human for rulings, device for state/calculation). Human umpire in the MVP; device follows.
7. **Scope-creep is the top threat.** Lock a small foundation; the infinite-content engine, environmental scoring, GM device, and digital sim are all *later*.

**Our likely identity:** *Terraforming Mars engine-building + Power Grid resource economy + Pandemic co-op pedagogy + D&D/Pandemic-Legacy campaign model.*

---

## 2. Our current design in one page (+ where it's undecided)

**Core loop:** assemble a **Model Card** (off-board) → roam a **resource-gathering board** (dice, Monopoly feel) → advance a **pipeline with hard dependency gates** → win by **meeting your Model-Card spec** (quality/trust/speed/etc.), not merely reaching market. Teaching spine: clean-vs-scraped data, scarce dynamic-priced compute/power, right-architecture-for-the-task, and real consequences.

**Internal inconsistencies / undecided (the report flags these as the crux):**

| Question | Status | Why it matters |
|---|---|---|
| **Board shape** | 3 options, no winner | Journey vs marketplace feel; teaching cadence |
| **Win condition** | 5 options, leaning "meet-the-spec" | *The* keystone decision; everything flows from it |
| **Movement** | dice vs compute-time vs simultaneous | Familiar vs thematic vs downtime |
| **Competitive vs team** | both implied | Shapes whole ruleset |
| **Same vs different Model Cards** | undecided | Same = Monopoly feel; different = Terraforming Mars feel |
| **Environmental scoring** | 3 meters, not integrated | Risk of "cancel-out" or cognitive overload |
| **MVP scope** | unclear | Sim/device/expansions must be *later* |

---

## 3. What to BORROW (by game) — concrete, adapted to our theme

- **Monopoly** — persistent appreciating assets (data pipelines/compute/talent), **player trading as the social centerpiece**, **chance cards** for drama/catch-up, visible progress. *Avoid:* player elimination, excessive length, kingmaking, luck>skill. Adapt: income only from **deployed** models; auction *some* resources.
- **Catan** — **asymmetric scarcity** (compute/power scarcer than data), **trading economy** as the core social mechanic, probabilistic production tied to positioning, randomized/modular setup, player-driven "block the leader." *Avoid:* unstructured negotiation stalls, kingmaking, high-count downtime.
- **Power Grid** ⭐ — **dynamic commodity price curve** for compute/chips/power (prices rise as bought, reset each round); **reverse turn-order penalty** (leader buys last) = elegant anti-runaway; **multi-phase round** mirroring our pipeline; **auctions** for scarce chips; **reward efficiency not size**; **income tied to output** (only deployed, trusted models earn). *Avoid:* heavy arithmetic/AP, opaque penalties, arbitrary end.
- **Terraforming Mars** ⭐ — **engine-building gamefeel** (weak→explosive), **project cards as the content/replayability engine** (Nollywood-subtitles data card, GPU-cluster card, Transformer/Diffusion method cards, NEPA-power-cut event…), **multi-resource conversion** as the decision hub, a **global/environmental track**, **multiple scoring vectors**, **tag synergies** (Data/Compute/Speed/Safety). *Avoid:* rules density (stay FFG-Civ level, not TtA level), AP, high-count downtime.
- **Civilization (Through the Ages)** — the pipeline as a **soft tech-tree** (hard prereqs between stages, flexible choices within), **tight action economy**, the **aging card-row** (wait-to-cheapen vs grab-now), **multiple intertwined resources**, **compounding growth**, **multiple victory paths**, **catch-up events**. *Avoid:* overwhelming complexity, unrecoverable early mistakes, length/AP.
- **Pandemic (+ Legacy)** — a real **co-op/team mode** (3–5 teams of 2), **asymmetric roles** (Data Engineer, Compute Architect, Model Trainer, Safety Validator, Deployer), **escalating self-tightening threat**, **triple-constraint economy**, **difficulty knobs**, and the **Legacy/campaign model** for an *updatable* product (seasons, sealed packets, pushed rules). *Avoid:* alpha-player dominance (give roles distinct *domains*), scripted feel, education-over-fun.
- **Pokémon TCG** — a **bounded loadout** (Model Card = fixed attribute slots → forced synergy), a **"one action per turn" gate**, **copy limits**, **in-game powering-up** (Untrained→Trained→Deployed), and the **expansion/rotation content engine** (ship 75 cards/quarter, rotate old ones; "classic format" preserves learning). ⚠ **Avoid the gambling/loot-box model entirely** (publish odds / use fixed themed decks / draft — *critical for an educational product with minors*), pay-to-win, speculation culture.
- **D&D 5e** — **persistent model progression** across a campaign, **one elegant core mechanic** (d20 + modifier vs difficulty, with **advantage/disadvantage** swings), **resource attrition & pacing** (compute budget/rests), **open-ended objectives + multiple paths**, **dice-driven drama**, the **Game-Master role** (human + optional AI device), **party synergy**. *Avoid:* over-complex core, heavy umpire prep, omniscient/capricious GM, single "correct" path.

---

## 4. Risks & gaps in our design (candid)

- **(a) Win condition — UNDECIDED & CRITICAL.** Multi-dimensional "meet-the-spec" risks players not knowing *why* they won; "first-to-market" teaches the wrong lesson; "continuous" never ends cleanly. **Fix:** lock **meet-the-spec** with 4–6 concrete parameters (Quality, Latency, Trust, Market-fit, Environmental cap, Time budget); "you win when you build exactly what you promised."
- **(b) Board/movement — RISKY.** A Monopoly loop creates dead/irrelevant turns; per-level rings are visually crowded; free-roaming causes paralysis for 13-year-olds. **We've conflated board shape with pacing.** **Fix:** a **market-row** (Civ/Power Grid) where you "buy one card OR execute one stage-gate," cards age/cheapen each round; dice drive a **timeline/pacing track**, not resource access; dependencies are explicit rules.
- **(c) Catch-up — NONE currently.** **Fix:** dynamic pricing (core) + reverse turn-order penalty (core) + occasional events (flavor). Don't stack all five levers.
- **(d) Complexity vs audience — SCOPE CREEP.** 8 interlocking systems is too much. **Fix:** MVP = Model Card (pick category+scale) + market-row + 4 stage-gates + 5 Model Cards + ~15 decision cards + 5–7 perks; **no** environmental meter, **no** device yet; 6–8pp rulebook; 30–45 min.
- **(e) Downtime/AP — MODERATE–HIGH.** **Fix:** simultaneous action selection for 5+; per-turn timers; quick-reference cards.
- **(f) Model-Card incompatibility — RISKY for beginners.** **Fix:** MVP = all combos valid but some cost more; soft penalties at intermediate; hard incompatibilities only at advanced.
- **(g) Environmental scoring — VAGUE.** **Fix:** ONE visible **Environmental Impact track** (Terraforming Mars), folded into final score (VP = Quality + Trust + Market − Env penalty). Not three meters.
- **(h) Replayability — good kernel, needs a content roadmap.** Attributes give ~324 combos; 150 shuffled cards add a lot. **Fix:** 5 templates × 3 product variants = 15 Model Cards + 150 base cards + a **quarterly 75-card expansion/rotation** plan.
- **(i) Solo/team/competitive — SPLIT RISK.** **Fix:** design co-op and competitive on the same components; **recommend co-op for MVP** (classroom pedagogy); competitive as expansion.
- **(j) Components/manufacturability — MANAGEABLE.** ~500 cards/100 tokens/1 board. MVP print-and-cut <$20; commercial ~$35–50 retail (consolidate decision cards via templates; cardboard chits not wood).
- **(k) "Don't test until the end / pipes" — UNPROVEN.** Pure end-resolution gives opaque, delayed feedback → frustration. **Fix:** intermediate gates with **visible feedback** (roll + modifiers per stage), keep a final-market surprise.
- **(l) Education vs fun — needs guardrails.** Risk of "obvious school assignment." **Fix:** game fun first; lessons tiered (card front = mechanics, back = 1–2 line explanation, QR = deeper); **no trivia** — let the mechanic teach (choosing RLHF costs more but buys Trust). Playtest with real students.

---

## 5. Concrete recommendations (prioritised)

**Tier 1 — lock before prototyping:**
1. **Board = market-row**, not a loop (Civ + Power Grid).
2. **Win = meet-the-spec**, 4–6 parameters (D&D/Civ).
3. **Dynamic resource pricing** for compute/power/data (Power Grid).
4. **Reverse turn-order penalty** for the leader (Power Grid).
5. **Co-op as primary** with 5 roles (Pandemic/D&D).
6. **Cut MVP scope** to the foundation.

**Tier 2 — into MVP or first expansion:**
7. Catch-up **events** deck (Civ). 8. **Decision-card templates** (D&D/Pandemic). 9. Clarify **Model-Card assembly** (5 fixed for MVP). 10. **3–4 role cards** with distinct *domains* (Pandemic). 11. **Dependency-lock** rules (Civ). 12. **5–7 perks** (Monopoly/Catan).

**Tier 3 — post-MVP:**
13. **Environmental Impact track** (Terraforming Mars). 14. **Expansion/rotation** content system (Pokémon). 15. Advanced decision-card variants. 16. **AI Game-Master device** spec (D&D) — design later, don't build in MVP.

**Later:** 17. **Campaign/Legacy** mode (Pandemic Legacy). 18. **Competitive** ruleset (Monopoly/Catan). 19. **Digital sim / online** play.

---

## 6. Three candidate design directions

**A — "The Engine-Builder" (Terraforming Mars).** Generations + simultaneous actions; build a synergistic card engine; environmental track; multi-vector scoring. **Pros:** huge replayability, satisfying snowball, thematic depth. **Cons:** complexity, AP, 90+ min, ~12–14pp rules. **Best for:** older students/clubs. *Verdict: a strong 2nd-edition / long-term target.*

**B — "The Economic Board" (Monopoly × Power Grid).** Model Card → market-row + dynamic pricing + reverse turn-order; trading; race to a *working* deploy. **Pros:** familiar, fast (45–60 min), social negotiation, automatic catch-up, light rules (~8–10pp). **Cons:** lower structural replayability (cards carry it), some dice luck. **Best for:** 13–15s, families, 1–2 session classes. *Verdict: **BEST FOR MVP.***

**C — "The Cooperative Campaign" (Pandemic Legacy + D&D).** Shared spec, role-based decisions, escalating threat, 6–8 session persistent campaign with unlockable rules. **Pros:** best pedagogy (roles+discussion), classroom-ready, narrative investment, *is* the "infinite content/updatable" vision. **Cons:** big commitment (10–12 hrs), setup overhead, one season is "consumed." **Best for:** semester cohorts. *Verdict: **BEST FOR CLASSROOMS — later tier.***

**Synthesis recommendation:** Build **Option B** as the MVP; grow toward **A** (depth) and **C** (campaign) once the core loop is validated.

---

## 7. Open questions for the founder

**Critical (before MVP):** (1) co-op or competitive first? (rec: co-op) · (2) 5 fixed Model Cards or randomized attributes? (rec: 5 fixed) · (3) environmental layer in MVP? (rec: not yet) · (4) dice movement or market-row? (rec: market-row + dice as pacing) · (5) target session length? (rec: 45–60 min).

**Important:** (6) primary audience — classrooms or clubs? (rec: classrooms) · (7) replayability via card-shuffle or procedural? (rec: card-shuffle) · (8) how central is the GM device? (rec: board first) · (9) the game's "moral spine"/the one lesson you most want taught? · (10) appetite for ongoing quarterly content?

**Nice-to-have:** (11) digital version/platform? · (12) price point? · (13) IP/branding angle? · (14) self-distribute to schools vs publisher?

---

*Source extractions: `board-game/research/games/01–08`. Our design: `board-game/design/`.*
