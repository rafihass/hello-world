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
| **Kink** | Power play and fetish cards, off by default, each kind opted into separately |

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

Sixteen items — blindfold, cuffs, rope, vibrator, wand, plug, strap-on, lube,
paddle, collar, clamps, gag, ice, feather, oil, camera. Cards list what they
need and are never dealt unless you've said you have it, so nothing lands that
you can't actually do. Cards that need an item show it on the face of the card.

## Kink

Off until you switch it on, then each category is opted into separately:
domination & submission, restraint & bondage, impact play, degradation &
humiliation, pegging & strap-on, exhibitionism & risk, sensation & temperature,
orgasm control & denial, roleplay, worship & service.

You also choose who leads — swap each turn, or one person all night — and kink
cards address the two of you by role.

Design decisions worth knowing about:

- **Nothing is a surprise.** The panel tells you to switch on only what you have
  already talked about. Degradation cards start by having the receiving partner
  name the words that are allowed and the ones that aren't.
- **Safety is in the card text, not a disclaimer.** Rope cards say two fingers
  under every wrap and scissors within reach. Gag cards make you agree a hand
  signal first. Impact cards name the areas to avoid. Clamp cards warn that
  taking them off is the intense part. Pegging cards start outside-only and
  build.
- **Public cards never involve anyone else.** Exhibitionism cards are about the
  thrill between the two of you — discreet, clothed, nothing a stranger would
  notice. Nobody becomes an unwilling audience.
- **Aftercare is guaranteed.** Play any kink card and the game ends with an
  aftercare screen. Don't skip it.

## Consent is in the mechanics

- **Pass** sits next to every card, costs nothing, needs no reason, and is
  counted separately from playing — never as a forfeit.
- **End the game** is on every screen.
- Card types and kink categories are opt-in at setup, so anything either partner
  doesn't want never enters the deck.
- A stop word is chosen before the first card and stays on screen all game.

## Sharing a setup

**Copy a link with these settings** puts your whole configuration — names,
location, toys, card types, kink categories — into the URL and copies it, so
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

Card content lives in the `ASK`, `TOUCH`, `DARE`, `KINK` and `POSE` arrays at the
top of the `<script>` block:

- `l` — heat level, 1–3
- `p` — privacy needed, 1–3 (public / half-private / private)
- `s` — optional countdown, in seconds
- `toys` — array of required item ids, e.g. `["cuffs","blindfold"]`
- `f` — kink category id (kink cards only)
- `d` — difficulty 1–4 (positions only)
- `{you}`, `{them}`, `{dom}`, `{sub}` are replaced with the players' names

## Privacy

Everything runs in the browser. Nothing is stored, sent or logged. Closing the
tab erases the session.
