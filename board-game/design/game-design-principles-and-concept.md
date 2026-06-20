# Game Design Principles + Concept — "Build an AI" (Naija Edition)

> Purpose of this doc: (1) teach you the **principles of board-game design** in plain language so you can judge and shape the game yourself, and (2) propose **one concrete game** built on those principles, themed on **building an AI system**, for **5–10 players**, with **beginner / intermediate / advanced** modes, and **Nigeria-first** flavour. Read it, scribble on it, push back. Nothing here is fixed.

---

## PART 1 — The principles of game design (plain language)

Every good group game, from Ludo to Monopoly to Whot, is built from the same handful of building blocks. If we get these right, the game is fun. If we teach AI *through* these blocks, players learn without it feeling like school.

1. **The core loop.** The small set of actions a player repeats every turn. In Monopoly: *roll → move → buy or pay → end turn.* A good loop is simple to say and satisfying to repeat. **Our loop:** *get resources → build your AI one step further → deal with what happens.*

2. **The goal (win condition).** One clear sentence for how you win. "First to deploy a working AI" or "most Impact Points." If players can't say how to win in one breath, the design isn't ready.

3. **Resources & scarcity.** Fun comes from *not* being able to do everything. You have limited money, data, and compute, so every turn is a choice. Scarcity creates decisions; decisions create thinking; thinking is where learning hides.

4. **Tension & risk.** The heartbeat of a game — the moment before you flip a card or roll. "Push-your-luck" (do I train more and risk a crash?) and surprise **Event cards** create drama and laughter.

5. **Player interaction.** What players do *to and with each other*: racing, blocking, trading, helping. With 5–10 people this is what keeps everyone awake — nobody should be bored waiting.

6. **Catch-up / balance.** Mechanics so a player who falls behind can still hope. Without it, people quit halfway. (e.g., trailing players get cheaper data, or "open-source breakthrough" helps the last-place lab.)

7. **Progression / difficulty tiers.** The same box should grow with the player: a simple version for beginners, extra rules unlocked for intermediate and advanced. Like levels in a video game.

8. **Theme–mechanic fit (the most important one for us).** The *action* should match the *idea*. This is called **intrinsic integration** or **"stealth learning":** if you must understand AI to win, you learn AI by playing. A trivia game *asks about* AI; a well-designed game *makes you do* AI. **This is the bar we hold every mechanic to.**

9. **Components.** The physical stuff: cards, tokens, a board, dice, money. Cheaper and more flexible = mostly **cards** (easy to print, easy to add new ones later — which suits fast-changing AI).

10. **Replayability.** Reasons to play again: shuffled decks, random events, different strategies, and later **expansion packs** (new data, new techniques, new events).

11. **Teachability.** A group game must be learnable in **5–10 minutes**, or people give up. Rules grow only as players level up.

> **How to read the rest of this doc:** for each part of the game, I'll point back to which principle it's serving.

---

## PART 2 — The game concept

**Working title:** *Build an AI* (Naija Edition). Final name TBD.

**The fantasy:** You and your rivals are **AI startups in Nigeria** racing to build and launch an AI that people actually trust. To do it, you must move your AI through the **real stages of building an AI system** — and survive the real-world wahala (power cuts, bad data, hallucinations, scandals) along the way.

**Players:** 5–10 (see "How 5–10 people play" below).
**Length:** ~30–45 min (beginner), up to ~75 min (advanced).
**Medium:** mostly **cards** + simple tokens + one shared track. Easy to print; easy to expand.

### The spine: the AI-build pipeline = the game's path

This is the heart. Every player advances their **Model** along the same pipeline. **The stages of building an AI *are* the stages of the game** (Principle 8 — theme–mechanic fit):

```
[0] IDEA  →  [1] DATA  →  [2] COMPUTE  →  [3] PRETRAIN  →  [4] FINE-TUNE  →  [5] DEPLOY  →  (LIVE: earn Trust & Impact)
   pick a     collect &     secure a      turn data +      specialise it     launch to       survive hallucinations,
   problem    clean data    data centre   compute into a   for your task     real users      errors, scandals;
                            + power        base model                                          score Impact Points
```

You can't skip steps — just like real life. **To Pretrain you must already hold enough Data + Compute.** That single rule teaches the most important lesson in the game: *AI is built from data + compute, in order.*

### The resources (these are the "elements of building an AI" you asked for)

Each is a **card type** or token. This is where "data, harvesting, pretraining, fine-tuning, data centres, hallucination, errors, strengths/weaknesses" all live:

| Element | In the game | What it teaches |
|---|---|---|
| **Funding** (₦ tokens) | Money to buy everything. You earn it each round / from investors. | Resources are scarce; you choose. (Principle 3) |
| **Data cards** | e.g. *Nollywood subtitles, Hausa/Yoruba/Igbo text, Mile-12 market prices, mobile-money records, clinic records.* Each shows **Quantity**, **Quality**, and sometimes a **⚠ Bias** mark. | Data collection/harvesting; quality vs quantity; where bias enters. |
| **Compute / Data-Centre cards** | *Borrowed GPUs, cloud credits, your own data centre.* Each needs **Power** to run. | You can't train without compute; infrastructure is real. |
| **Technique cards** | *Data Cleaning, Pretraining, Fine-Tuning, Evaluation/Testing, RLHF (advanced).* Played to advance a pipeline stage. | The actual methods of building AI, in the right order. |
| **Event cards** (the drama) | *NEPA power cut — data centre offline; Hallucination! — your AI gave a fake answer; Data breach — privacy fine; Open-source breakthrough — everyone draws; Viral launch — bonus Impact.* | Strengths & weaknesses of AI, errors, real-world risk. (Principle 4) |
| **Trust track** (intermediate+) | A score that rises with good data/testing and **falls** when your AI hallucinates or ships bias. | Why trustworthiness matters as much as accuracy. |
| **Ethics/Society cards** (advanced) | Dilemmas the table votes/debates on. | Societal impact, fairness, responsibility. |

### The core loop (one turn)

Serving Principle 1 (simple, repeatable):

1. **Collect** — take Funding; refresh the shared **Market** of Data/Compute/Technique cards.
2. **Build** — spend resources to either *buy a card* into your lab **or** *play a Technique* to advance your Model one pipeline stage (if you meet its prerequisites).
3. **Resolve** — flip the top **Event card**; deal with the wahala.
4. **Score/Check** — if you reached **Deploy**, your AI goes live and starts earning **Impact Points** based on your data **Quality** minus any **Bias/Trust** penalties.

### How you win (Principle 2)

- **Beginner:** *First lab to DEPLOY a working AI wins.* (Teaches the pipeline.)
- **Intermediate / Advanced:** *Most **Impact Points** when the deck runs out.* Impact = usefulness × Trust − bias/hallucination penalties. (Teaches that a fast but biased, untrustworthy AI loses to a slower, trustworthy one.)

### Why this genuinely teaches (not trivia)

This is the test we set earlier, and the design passes it:
- You **physically assemble** data + compute before you can train → you *feel* the pipeline.
- **Cheap, biased data** lets you rush ahead, but later triggers **Hallucination/Bias events** that wreck your Trust and Impact → you *lose because of bias*, you don't read about it.
- **Train too much on narrow data** and an **Overfit** event punishes you on new users → generalization, felt not recited.
- **Power cuts** hitting data centres make compute precious → infrastructure reality, very Naija.

The AI understanding **is the winning strategy** (Principle 8).

---

## How 5–10 people play (the key constraint you set)

Card-engine games usually seat 2–5 with downtime. To make **5–10 fun with no boredom**, two supported modes:

- **Simultaneous mode (recommended for 5–10 players).** Everyone has the same action choices and plays at the **same time** each round: all players secretly pick an action card (Collect / Buy / Build), reveal together, then resolve against a **shared Market**. No waiting for "your turn." This is the standard trick for keeping big groups engaged.
- **Teams mode.** 5–10 people form **3–5 labs of 2**. Teammates discuss decisions (peer teaching), which is great in classrooms and at home.

Both use the same cards and pipeline — only the seating changes.

---

## The three tiers (same box grows with the player) — Principle 7

- **BEGINNER** — *Pipeline race.* Only Funding, Data, Compute, and the three core Techniques (Pretrain, Fine-Tune, Deploy). Simple events. First to Deploy wins. Goal: learn that **AI = data + compute, built in stages.** (~30 min, learn in 5.)
- **INTERMEDIATE** — adds **Data Quality & ⚠ Bias**, the **Trust track**, money management, and Hallucination/Breach events. Now a *fast* AI can still *lose* if it's untrustworthy. Goal: **quality, bias, and trust.**
- **ADVANCED** — adds **Evaluation/RLHF** techniques, **data-centre + power** sub-management, **Ethics dilemma** cards (table debate/vote), and player competition (block the Market, trade data). Best for university + clubs. Goal: **trade-offs and responsible AI.**

---

## Nigeria-first flavour (makes it relatable + funny)

- **NEPA/grid power cuts** knock data centres offline — a recurring, very-local hazard.
- **Local datasets:** Hausa/Yoruba/Igbo/Pidgin text, Nollywood, market prices, mobile-money, agric & clinic data.
- **Local use-cases to "deploy" into:** farming advice, fintech credit scoring, exam tutoring, traffic, health screening.
- **Local dilemmas:** NIN/BVN privacy, lending bias against rural applicants, exam-malpractice detection.

---

## What a card looks like (so you can picture it)

```
┌──────────────────────────────┐        ┌──────────────────────────────┐
│ DATA — Nollywood Subtitles    │        │ EVENT — NEPA Strikes ⚡        │
│ Quantity: ●●●  Quality: ●●    │        │ Your data centre goes dark.   │
│ ⚠ Bias: skews to Lagos slang  │        │ Skip your next BUILD step,    │
│ Cost: ₦2                      │        │ unless you hold a Generator   │
│ "Great for language tasks —   │        │ (Compute) card.               │
│  if your users talk like      │        │                               │
│  Lagos Twitter."              │        │ (Teaches: compute needs power)│
└──────────────────────────────┘        └──────────────────────────────┘
```

---

## A sample mini-turn (to feel the flow)

> **Round 3, beginner mode.** Tunde's lab has 2 Data and 1 Compute. He plays the **Pretrain** technique → his Model advances to stage [3]. He flips an Event: **"Open-source breakthrough — every lab draws 1 free Data."** Nice. Next round he wants to **Fine-Tune** for a farming-advice app, but he only has Lagos market data (⚠ Bias). He can rush to Deploy now and *probably* win the race… but in intermediate mode that bias would come back to bite his Trust. Decision time. *(That decision is the learning.)*

---

## Open questions for you (so we shape it together)

1. **Win feel:** do you prefer a **race** ("first to deploy wins" — fast, punchy) or a **points/empire** feel ("best, most-trusted AI wins" — richer, a bit longer)? We can do race for beginner, points for advanced.
2. **Competition level:** friendly (everyone builds their own AI, light interference) or cut-throat (steal data, block rivals, sabotage)?
3. **Board or no board:** pure cards + a small shared pipeline track (cheapest, most flexible) — or a fuller printed board (more "premium" feel)?
4. **First playable:** want me to turn this into a **print-and-cut prototype** (real cards + track you can photocopy and play this week) so you can test the principles with your own hands?
