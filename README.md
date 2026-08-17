# Blackjack Dealer Trainer v15 — Full Rebuild

This is a clean rewrite, not another patch on Versions 1–14.

## Why it was rebuilt
The older versions accumulated overlapping CSS rules for portrait, landscape, grid, flex, overlays, and multiple phone sizes. That made one change fix one screen while breaking another.

Version 15 uses a single simple mobile architecture:
- fixed top utility bar
- one full blackjack table rectangle
- five fixed-size player pods
- one thin bottom HUD
- one independent compact payout tray

Player pods never stretch vertically.

## Live dealer order
1. Opening deal: two cards to each player and dealer up/hole cards.
2. Poker side bets FIRST:
   - Top 3 = left
   - Lucky Ladies = center
   - 21+3 = right
3. Insurance / dealer blackjack check if applicable.
4. Player blackjack action using H17 basic strategy assumptions.
5. Dealer automatically plays H17.
6. Main blackjack settlement.
7. Collect all cards.

## Poker side bets
Top 3 — player's first two + dealer up card
- Suited Three of a Kind 270:1
- Straight Flush 180:1
- Three of a Kind 90:1
- wager $5 or $10

Lucky Ladies — player's first two cards
- Any 20 3:1
- Suited 20 6:1
- Pair totaling 20 9:1
- Queens totaling 20 20:1
- wager $5–$50 in $5 increments

21+3 — player's first two + dealer up card
- Straight Flush / Three of a Kind / Straight / Flush = 9:1
- randomized wagers up to $250

## Blackjack rules
- Dealer hits soft 17
- Blackjack pays 3:2
- Doubles have a second wager and horizontal third card
- Splits create separate hands
- Non-ace pairs can re-split up to four hands
- Aces cannot be re-split
- Split aces get one additional horizontal card and stop
- Busted hand is cleared immediately after the dealer correctly presses BUST
- Original winning wager stays out; chip tray builds only the added payout

## Other modes
- 10-second 2–5 card hand-total trainer
- 3:2 blackjack payout trainer using common wager amounts
