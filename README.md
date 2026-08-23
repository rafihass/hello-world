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
| **Kink** | Ten separate decks — power play, restraint, impact and more — off by default, each opted into separately |

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

## Kink — ten decks

Kink is off until you switch it on. Then each kink is a **full deck of its own**,
not a card or two mixed into the pile — 131 cards in total:

| Deck | Cards |
|---|---|
| Domination & submission | 14 |
| Restraint & bondage | 14 |
| Impact play / spanking | 13 |
| Degradation & humiliation | 13 |
| Pegging & strap-on | 13 |
| Exhibitionism & risk | 13 |
| Sensation & temperature | 13 |
| Orgasm control & denial | 13 |
| Worship & service | 13 |
| Roleplay | 12 |

**Every deck has its own arc.** The opening cards negotiate and warm up — agree
the safe signal, set the word list, outside only, ten slow ones over clothes —
and the last cards are the deep end. Turn a deck on and you get that whole
progression, not a random sample of it.

**Tonight's shape.** Select two or more decks and a focus picker appears: mix
them, or give one deck the entire evening. In focus mode the game deals only
from that deck, so its arc becomes the shape of the night — a bondage night
starts by practising the release signal and ends by untying you slowly.

**Deck primers.** The first card drawn from any deck carries that deck's primer:
the thing you need to know before the deck's first card, in the deck's own
terms. Rope's says scissors within reach and check the hands. Pegging's says
more lube than you think and {sub} sets every pace. It appears once per deck per
game.

You also choose who leads — swap each turn, or one person all night — and kink
cards address the two of you by role.

Other design decisions worth knowing about:

- **Nothing is a surprise.** The panel tells you to switch on only what you have
  already talked about. Every deck's first cards are negotiation cards.
- **Safety is in the card text, not a disclaimer.** Rope cards say two fingers
  under every wrap. Gag cards make you agree and test a hand signal first.
  Impact cards name the areas to avoid and make you warm up. Clamp cards warn
  that taking them off is the intense part. Degradation cards start with the
  receiving partner naming the allowed words and the forbidden ones, and the
  deck contains a card that breaks character entirely.
- **Public cards never involve anyone else.** Exhibitionism is about the thrill
  between the two of you — discreet, clothed, nothing a stranger would notice.
  Nobody becomes an unwilling audience.
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
