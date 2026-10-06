# beat-the-market prompts

Replace everything in `{braces}`. Run in order, one prompt per step.

## 1. Rules

```text
My rules for today: bankroll ${bankroll}, minimum edge {x}% measured as EV per $1
after fees, sizing {fraction} Kelly. Confirm the rules and the formulas you'll use
for edge and stake. Don't size anything yet.
```

## 2. Fair price

```text
Here are screenshots of {prediction market} and {sportsbook} for {event}.
Remove the vig from the sportsbook price (show proportional and power methods)
and compare it to the prediction-market price, including its fees.
Use ONLY the prices in these screenshots as the market reference.
```

## 3. Data and sanity checks

```text
Pull {data sources: nflverse play-by-play, injury reports, depth charts, Open-Meteo}
for {game}. Before modelling, verify the starting QBs from play-by-play, list
current injuries for both teams, and get the kickoff weather forecast.
Flag any data that contradicts other sources.
```

## 4. Build and test the model

```text
Build a win-probability model from this data. Tune it only on older seasons and
test it on the most recent {n} seasons it never saw. Report how it compares to the
closing market (log loss, RMSE, early-season weeks) and whether it adds anything
beyond the market price. Keep the code in the project so it can be rerun.
```

## 5. Prediction and scenarios

```text
Run the model on {game}. Give: raw model probability, market no-vig probability,
the model+market blend, projected margin and total. Add one scenario for each key
uncertainty (e.g. backup QB starts).
```

## 6. Position decision

```text
Using my rules from step 1 and the blended probability, check every way I could
open the position (taker, resting order, better price). Show cost after fees, EV,
whether it clears my minimum, and the stake. If nothing clears, say "no position"
and the price at which it would.
```

## 7. Challenge it

```text
Argue against this result. Why might the market be right and me wrong? Check that
every number traces back to the inputs from steps 2–3.
```

## 8. Summary page (optional)

```text
Make a single-page brutalist HTML summary: the position call first, then the
probabilities, the price check, what to verify before opening, and how far to
trust the model.
```
