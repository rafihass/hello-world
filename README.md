# Kama · A Game for Two

A single-file card game for couples, built around the classical Kama Sutra with
optional kink. No install, no accounts, no network — open `index.html` in any
browser and play.

## Playing

1. Open `index.html`.
2. Enter both names.
3. Say **where you are** — the deck adapts to your surroundings.
4. Tap **what you have with you** — toys you don't own are filtered out.
5. Choose the ceiling for the evening and which card types are in.
6. Agree a stop word out loud, then draw cards and take turns.

## The deck

| Type | What it does |
|---|---|
| **Ask** | Questions that get you talking honestly about wanting each other |
| **Touch** | Specific, timed physical cards with an on-screen countdown |
| **Position** | 22 classical Kama Sutra positions — Sanskrit name, plain description, difficulty, practical note, and a link out to a full illustrated guide |
| **Dare** | Playful challenges and small games inside the game |
| **Kink** | Ten separate 50-card decks — power play, restraint, impact and more — off by default, each opted into separately |

**Three intensity levels** — Spark, Simmer, Fire. Whatever ceiling you set, the
game always opens at Spark and escalates: first third gentle, last third at your
ceiling.

## Where you are

Location is a real filter, not a label. Each card declares the privacy it needs
and anything that doesn't fit is removed before the game starts:

- **Out in public** — restaurant, bar, party. Nothing visible, nothing removed:
  whispering, hands under a table, discreet instructions. (~20 cards)
- **Half-private** — car, quiet corner outdoors, balcony, locked bathroom.
  Discreet, clothed-ish, could be interrupted.
- **Completely private** — home or hotel. The whole deck. (~120 cards with
  everything switched on)

## What you have

Twenty items — blindfold, cuffs, rope, vibrator, wand, plug, strap-on, lube,
paddle/flogger, crop/cane, collar, clamps, gag, ice, feather, massage oil,
massage candle, pinwheel, mirror, camera. Cards list what they
need and are never dealt unless you've said you have it, so nothing lands that
you can't actually do. Cards that need an item show it on the face of the card.

## Kink — ten decks of fifty

Kink is off until you switch it on. Then each kink is a **full deck of its
own** — 50 cards each, 500 in total:

| Deck | Cards | | Deck | Cards |
|---|---|---|---|---|
| Domination & submission | 50 | | Exhibitionism & risk | 50 |
| Restraint & bondage | 50 | | Sensation & temperature | 50 |
| Impact play / spanking | 50 | | Orgasm control & denial | 50 |
| Degradation & humiliation | 50 | | Roleplay | 50 |
| Pegging & strap-on | 50 | | Worship & service | 50 |

**Every card is something to do.** No question cards, no "tell your partner
about…", no conversation prompts — those live in the Ask deck where they belong.
A kink card is an action, a challenge, a named position or a scene.

**Named cards.** Decks carry named techniques and positions the way the Kama
Sutra deck does: *Single column tie*, *Box tie*, *Hogtie*, *Frogtie*, *Spread
eagle* in bondage; *Kneel*, *Present*, *Tower*, *Inspection*, *Prostration* in
domination; *Spooning*, *Missionary*, *The rider*, *Side saddle*, *The chair* in
pegging; *The interrogation*, *The pull-over*, *The captive*, *The audition* in
roleplay.

**Every deck has its own arc.** The opening cards are the light end — over
clothes, one finger, hold your own wrists, one word said once. The closing cards
are the deep end, and each deck ends on coming back down: untying slowly,
soothing every mark, the collar coming off, holding each other while it settles.

**Tonight's shape.** Select two or more decks and a focus picker appears: mix
them, or give one deck the entire evening. In focus mode the game deals only
from that deck, so its arc becomes the shape of the night. A deck deals all 50
of its cards before any of them repeats.

**Deck primers.** Negotiation and safety live in the deck's primer, not in
cards, so the deck itself is all action. The primer appears once, on the first
card that deck deals: rope's names EMT shears, the two-tap signal, 6mm minimum
and the circulation check; impact's names the safe target areas and the ones to
never touch; degradation's requires the word list and forbids using real
insecurities; pegging's covers lube, pace and hygiene.

You also choose who leads — swap each turn, or one person all night — and kink
cards address the two of you by role.

Other design decisions worth knowing about:

- **Nothing is a surprise.** Turn on only what you've already talked about, and
  read the primer out loud when it appears.
- **Safety is in the card text, not a disclaimer.** The box tie card says
  nothing over the front of the shoulders and ten minutes maximum. The hogtie
  card routes the weight through the chest rather than the wrists and says never
  leave them alone. The wax cards say massage candle, tested on your own wrist.
  The crop cards halve the count and double the pause.
- **Public cards never involve anyone else.** Exhibitionism is about nearly
  being seen, by each other — nobody who hasn't agreed to it ever sees anything.
- **Aftercare is guaranteed.** Play any kink card and the game ends with an
  aftercare screen.

### Where the material comes from

The decks were built against published guidance rather than invented whole —
rope safety (single and double column ties, 6mm minimum, EMT shears,
circulation checks, hogtie weight distribution), impact play (implement
characteristics, warm-up, safe target areas, flogger wrap), orgasm control
(edging, denial, ruined orgasms, permission), sensation play (temperature,
pinwheel, wax, sensory deprivation), D/s protocol postures (present, tower,
inspection, prostration), pegging technique, negotiated degradation, and the
consent line on exhibitionism. Sources are listed at the bottom of this file.

## Consent is in the mechanics

- **Pass** sits next to every card, costs nothing, needs no reason, and is
  counted separately from playing — never as a forfeit.
- **End the game** is on every screen.
- Card types and kink categories are opt-in at setup, so anything either partner
  doesn't want never enters the deck.
- A stop word is chosen before the first card and stays on screen all game.

## Sharing a setup

**Copy a link with these settings** puts your whole configuration — names,
location, toys, card types, kink decks, focus — into the URL and copies it, so
your partner can open the same deck on their own phone. The settings live in the
part of the URL after `#`, which browsers never send to a server. It is still an
ordinary link, so send it the way you'd send anything else you'd rather not have
sitting in a group chat.

## Outbound links

Each position card links to [Bad Girls Bible](https://badgirlsbible.com) for a
fuller illustrated guide. Links go to their site search for the position's
mainstream English name (the site uses common names, not Sanskrit ones), which
always lands on something real rather than risking a dead deep link. To
deep-link instead, drop the page slug into that position's `bgb` field:

```js
{n:"The Lotus-Like", common:"lotus", bgb:"lotus-sex-position", …}
// -> https://badgirlsbible.com/lotus-sex-position
```

The base URL, search URL and link text are all in the `BGB` object at the top of
the script.

## Adding your own cards

Card content lives in the `ASK`, `TOUCH`, `DARE` and `POSE` arrays and the
`KINK_DECKS` list at the top of the `<script>` block. A new kink deck is an
entry in `KINK_DECKS` with an `id`, a name, a `primer` and its cards — the
setup screen, the focus picker and the counts all pick it up automatically.

Card fields:

- `l` — heat level, 1–3
- `p` — privacy needed, 1–3 (public / half-private / private)
- `s` — optional countdown, in seconds
- `toys` — array of required item ids, e.g. `["cuffs","blindfold"]`
- kink cards live inside their deck's `cards` array in `KINK_DECKS`; the deck
  stamps its own id onto them, so a new card only needs `l`, `p` and `t`
- `d` — difficulty 1–4 (positions only)
- `{you}`, `{them}`, `{dom}`, `{sub}` are replaced with the players' names

## Privacy

Everything runs in the browser. Nothing is stored, sent or logged. Closing the
tab erases the session.

## Sources

Guidance the kink decks were built against:

- [Kink Checklist](https://kinkchecklist.com) — sensation play, impact, humiliation, voyeurism/exhibitionism
- [Impact Play Implements](https://bdsmpact.com/activities/impact-implements) — flogger, paddle, crop and cane characteristics
- [Healthline — Impact Play](https://www.healthline.com/health/healthy-sex/impact-play) — safe zones and aftercare
- [Le Wand — Rope Bondage for Beginners](https://www.lewandmassager.com/pleasure-guide/rope-bondage/) — column ties, rope diameter, circulation checks
- [Autostraddle — Shibari 101: Hogtie](https://www.autostraddle.com/shibari-bondage-101-hogtie-404857/) — chest-loaded hogtie
- [Kneel — Submissive Positions Guide](https://getkneel.com/blog/submissive-positions-guide) — present, tower, inspection, prostration
- [Consent Culture — Degradation Play](https://consentculture.community/glossary/degradation-play/) and [Exhibitionism](https://consentculture.community/glossary/exhibitionism/) — negotiation registers and the bystander line
- [Strawberry Patch — Orgasm Control](https://strawberrypatch.love/posts/sexual-wellness/orgasm-control-guide/) — edging, denial, ruined orgasms
- [Future Method — Pegging for Beginners](https://education.futuremethod.com/what-is-pegging-a-beginners-guide/) — positions, warm-up, lube
- [Sei Mio — Wartenberg Pinwheel](https://www.sei-mio.com/blogs/news/understanding-the-wartenberg-pinwheel-a-bdsm-classic) — pinwheel use
- [YourTango — Role Play Ideas](https://www.yourtango.com/2014207426/sex-love-valentines-day-30-role-playing-ideas-couples) and [Kink Weekly](https://www.kinkweekly.com/article-dexx/bdsm-scene-idea-first-bdsm-session-with-a-new-play-partner/) — scenario framing
