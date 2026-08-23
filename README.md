# Kama · A Game for Two

A single-file card game for couples, built around the classical Kama Sutra.
No install, no accounts, no network — open `index.html` in any browser (phone,
tablet, laptop) and play.

## Playing

1. Open `index.html`.
2. Enter both names, agree together on the ceiling for the evening, and turn
   off any card type either of you isn't in the mood for.
3. Agree a stop word out loud.
4. Draw cards, take turns.

## How it works

**Four kinds of card**

| Type | What it does |
|---|---|
| **Ask** | Questions that get you talking honestly about wanting each other |
| **Touch** | Specific, timed, unhurried physical cards (with an on-screen countdown) |
| **Position** | Classical Kama Sutra positions — Sanskrit name, plain description, difficulty rating, and a practical note |
| **Dare** | Playful challenges and small games inside the game |

**Three intensity levels** — Spark, Simmer, Fire. Whatever ceiling you choose,
the game *always* opens at Spark and escalates gradually: the first third of the
deck is gentle, the last third runs at your ceiling. You can't accidentally
start at the deep end.

**Turn-taking** — Ask, Touch and Dare cards are addressed to one player and the
turn alternates. Position cards are for both of you and don't consume a turn.

**No repeats** — cards don't come back until the deck is exhausted, and the game
avoids dealing two of the same type in a row.

## Consent is part of the design, not a disclaimer

- **Pass** sits next to every card, costs nothing, and needs no reason. Passing
  is counted separately from playing, never as a penalty or a forfeit.
- **End the game** is on every screen.
- Setup asks you to choose a stop word and say it to each other before the first
  card; it stays visible at the bottom of the screen all game.
- Card types are opt-out at setup, so anything either partner doesn't want never
  enters the deck.
- Position cards carry practical notes (support the hips, test a lift with
  clothes on first, swap legs when it gets tiring) rather than assuming everyone
  is equally flexible.

## Files

- `index.html` — the entire game. HTML, CSS, JavaScript and all card content in
  one file with no dependencies.

Card content lives in the `ASK`, `TOUCH`, `POSE` and `DARE` arrays at the top of
the `<script>` block. Add your own — `{you}` and `{them}` are substituted with
the players' names, `l` is the level (1–3), `s` is an optional countdown in
seconds, and positions take `d` for difficulty (1–4).

## Privacy

Everything runs locally in the browser. Nothing is stored, sent or logged.
Closing the tab erases the session.
