# EXHAUSTIVE EXTRACTION: POWER GRID (FUNKENSCHLAG)

> Note: a condensed-but-complete capture of the deep-dive (all 14 sections). Power Grid is the **most thematically on-target** comparable for our compute/energy economy.

## 1. Snapshot
- **Designer:** Friedemann Friese · **Publisher:** Rio Grande Games · **Year:** 2004 (orig. *Funkenschlag*)
- **Players:** 2–6 · **Age:** 13+ · **Time:** 90–120 min (≈50 for experienced 4p) · **Weight:** ~3.5/5 (medium-heavy)
- **Acclaim:** 2004 International Gamers Award (Best Strategy, Multiplayer); long-time BGG top ~30; reference design for economic games. Revered for **minimal luck**, deep auctions, anti-runaway mechanics, dynamic commodity market, tight theme–mechanics fit.

## 2. Core fantasy
Competing **energy-company executives** building electrical networks and supplying cities. You literally buy power plants at auction, buy fuel, expand a grid, and get paid for cities powered. Theme and mechanics are inseparable.

## 3. Goal & win/lose
- **Goal:** power the **most cities** at game end.
- **End trigger:** the round in which any player reaches **17 cities** (after the Building phase).
- **Win:** most cities *actually powered* (you may power fewer than you own). **Tie-breaks:** most money, then most cities.
- **Key:** reaching 17 cities ≠ winning — you need plants + fuel to *power* them. Efficiency can beat raw size.

## 4. Full rules & turn structure — FIVE phases per round
1. **Player order** — recalculated each round: most cities goes **first** (a disadvantage). Order drives auctions (bid first), and reverse order for buying resources and building.
2. **Auction power plants** — market shows 4 "current" + 2 "future" plants (ascending). Active player starts an auction (min bid = plant number) or passes; clockwise bidding; winner takes the plant (max 3 plants, discard if buying a 4th). Market replenishes & re-sorts. (Step 3: no future market.)
3. **Buy resources** — in **reverse** order. Coal/oil/garbage/uranium on an 8-spot **price track** (cheap→expensive). Buying depletes cheap spots → prices rise for later buyers. Storage limited to **2× a plant's consumption**. Resource denial (buying out a fuel) is a core tactic.
4. **Build / expand network** — in reverse order. Connect a new city to your network; pay **connection cost (route number) + city slot cost**. Slots per city grow by Step (10 / 15 / 20).
5. **Bureaucracy** — power cities (spend fuel) → earn income from the **income table** (0 cities = 10 minimum, scaling steeply with network size); replenish resource market; check end trigger.

**Power-plant cards** show: number (min bid/era), fuel type, fuel needed per city, and cities powered. Renewables need no fuel.

## 5. Economic / resource systems
- **Dynamic commodity price curve (the signature):** as resources are bought, cheap spots deplete and prices climb; **replenished each round**, so scarcity is recurring not permanent. First buyer gets cheap fuel; last buyer overpays. Uranium is especially scarce (few spots) → denial is potent.
- **Auctions:** min bid = plant number prevents trivial prices; players sometimes *intentionally lose* to keep a favorable turn order.
- **Self-balancing plant market:** higher-numbered (more efficient) plants enter over time; laggards get access to better plants.
- **Income curve:** modest early, steep late → **catch-up elasticity** (falling behind is recoverable through efficiency + turn-order positioning).

## 6. Decision dynamics
- **Auction bidding** ripples through the whole economy (plant → fuel demand → network size).
- **Resource hoarding/denial** vs **storage limits** (can't hoard infinitely).
- **Turn-order meta:** avoid 1st (penalised); a stable mid position is often optimal.
- **Expansion vs efficiency:** 15 well-powered cities can beat 17 poorly-powered ones.
- **No dice / zero randomness in resolution** — pure optimisation with hidden budgets and a randomized plant deck for uncertainty. Source of analysis paralysis but deep satisfaction.

## 7. Progression / growth — three Steps
- **Step 1:** 1 slot/city (10); lowest-tier plants.
- **Step 2 (triggers at someone's 7th city):** 2 slots/city (15); lowest plant removed; mid-tier plants.
- **Step 3 (triggers on the Step-3 card):** 3 slots/city (20); future market removed; only the most efficient plants; game ends at 17 cities.
- Steps are triggered by **player action**, not a round counter → organic pacing.

## 8. Tension, drama & fun
Auction bidding wars ("just one more bid"); the **resource squeeze** (can I afford fuel AND building?); leader-penalisation schadenfreude; the optimisation-puzzle payoff; the suspense of **when Step 3 triggers**.

## 9. Replayability engine
- **Many maps** (US/Germany base; France=nuclear, Italy=garbage, etc.) each with distinct economies/restrictions.
- **Randomized plant deck** + random Step-3 position → different pacing every game.
- **Player-count scaling** (2p uses a dummy "Trust"); expansions (robots, alternate decks).

## 10. Components & physical design
Double-sided map, ~132 wooden houses, ~84 resource tokens, 36+ plant cards, resource-market board, income/order tracks, Elektro currency (start 50), reference cards, ~16-page rulebook. **Minimalist, functional, wooden, "serious."** Teach ~15–20 min; **math-heavy**; counterintuitive "going last is better." Recharged Edition (2018) improved art/components.

## 11. Accessibility & scaling
3p optimal; 4–5 recommended; 6 drags (150+ min, heavy AP). Age 13+. Requires comfort with arithmetic. **AP risk is real**, especially in the resource phase — mitigate with timers/aids.

## 12. Criticisms & weaknesses
Analysis paralysis; fiddly bookkeeping; dry/abstract theme to some; "leader punished" feels unthematic to some; bland components; slow at high counts; heavy math; arbitrary-feeling "17 cities" end.

## 13. Transferable design principles for our AI-building game

**Emulate**
1. **Dynamic commodity price curve for COMPUTE/CHIPS/POWER** — early buyers get cheap compute; prices rise as it's bought; replenish each round so scarcity is ever-present but not permanent. *This is the single most valuable mechanic to steal for our compute/energy theme.*
2. **Anti-runaway via turn order** — the leader (best model) bids first / buys power last / deploys into a saturated market first. Self-balancing, thematic, no arbitrary handicap.
3. **Multi-phase round** — order → acquire compute (auction) → buy power/fuel → train → deploy/income. Mirrors the real pipeline.
4. **Auctions for scarce resources** (chips, exclusive data) — competition sets price, no artificial caps.
5. **Reward efficiency, not just size** — a smaller, well-trained, well-deployed model beats a bloated, poorly-powered one.
6. **Asymmetric info + randomized discovery** (hidden budgets, random tech/architecture availability) keeps games fresh.
7. **Income tied to OUTPUT** — only *deployed, working* models earn; a trained-but-undeployed model earns nothing.
8. **Finite resources + storage limits** — can't hoard infinite cheap compute/power; forces real trade-offs.
9. **Stages triggered by player action** — "first to X triggers a new era of more-efficient models."

**Avoid**
1. **Severe analysis paralysis** — keep arithmetic simple; provide decision aids.
2. **Opaque turn-order penalty** — explain clearly; offer a fixed-order beginner mode.
3. **Dry theme** — invest in evocative flavor/art (we're educational + mass-market).
4. **Unwieldy component count** — color-code, clear iconography, good player mats.
5. **Slow play at high counts** — use simultaneous action selection for 5+.
6. **Arbitrary end condition** — tie end to a thematic milestone (e.g., a model hits a benchmark / N quarters).

## 14. Sources
- Wikipedia: Power Grid — https://en.wikipedia.org/wiki/Power_Grid
- BoardGameGeek: Power Grid — https://boardgamegeek.com/boardgame/2651/power-grid
- Power Grid FAQ (BGG wiki) — https://boardgamegeek.com/wiki/page/Power_Grid_FAQ
- The Opinionated Gamers: Funkenschlag at Fifteen — https://opinionatedgamers.com/2016/07/11/funkenschlag-at-fifteen-the-story-of-power-grid/
- UltraBoardGames: Power Grid — https://www.ultraboardgames.com/power-grid/
- Rio Grande: Power Grid Recharged Rules (PDF) — https://www.riograndegames.com/wp-content/uploads/2018/12/Power-Grid-Recharged-Rules.pdf
- Meeple Mountain review — https://www.meeplemountain.com/reviews/power-grid/
- The Thoughtful Gamer: Catch-Up Mechanisms — https://thethoughtfulgamer.com/2017/03/28/catch-up-mechanisms/
- Friedemann Friese (Wikipedia) — https://en.wikipedia.org/wiki/Friedemann_Friese
