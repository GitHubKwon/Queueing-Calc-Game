# Take a Number

**Play it:** https://githubkwon.github.io/Queueing-Calc-Game/

**Queueing theory, played.** A browser game that teaches queueing theory through challenge levels, plus a full queueing calculator anyone can use.

Run a coffee cart, a bank, a food truck, a car wash and a stadium. Adjust staff, speed and space, watch the line react live, and hit each level's targets for up to three stars. Every number comes from the standard closed-form formulas.

## Features

- **11 challenge levels in 5 worlds**, each built on a different model:
  | World | Model | What you control |
  |---|---|---|
  | The Coffee Cart | M/M/1 | Barista speed, customer demand |
  | The Bank | M/M/c | Number of tellers, teller speed |
  | The Food Truck | M/M/1/K | Curb space, cook speed |
  | The Car Wash | M/D/1 | Wash cycle speed, demand |
  | The Stadium | M/M/c | Number of stands, stand speed |
- **Live simulation**: an animated shop floor where customers line up, get served, and get grumpier the longer they wait.
- **Results screen**: compares the formula's prediction with a simulated 4,000-customer day and teaches one concept per level (Little's Law, Erlang C, blocking probability, Pollaczek–Khinchine).
- **Daily Rush**: five 20-second puzzles a day. Everyone gets the same puzzles on the same date. Includes combos, streaks and a copyable result grid.
- **Progression**: XP and ranks, 12 badges, and unlockable formula cards.
- **Calculator**: M/M/1, M/M/c, M/M/1/K and M/D/1, with any time unit, P(n) chart, live animation and the formulas shown.
- Light and dark themes, works on phones, and sound effects you can mute.

## Run it locally

No build step and no dependencies. Open `index.html` in any modern browser.


Deep links: add `#calculator`, `#daily` or `#badges` to the URL to open those sections directly.

## The math

Rates are per hour in the game. Assumptions: Poisson arrivals, first-come first-served, one shared line.

| Model | Key formulas |
|---|---|
| M/M/1 | ρ = λ/μ, L = ρ/(1−ρ), W<sub>q</sub> = λ/(μ(μ−λ)) |
| M/M/c | a = λ/μ, ρ = a/c, Erlang C: C = a<sup>c</sup>/(c!(1−ρ)) · P<sub>0</sub>, W<sub>q</sub> = C/(cμ−λ) |
| M/M/1/K | P<sub>n</sub> = ρ<sup>n</sup>(1−ρ)/(1−ρ<sup>K+1</sup>), P(block) = P<sub>K</sub>, λ<sub>eff</sub> = λ(1−P<sub>K</sub>) |
| M/D/1 | L<sub>q</sub> = ρ²/(2(1−ρ)) (Pollaczek–Khinchine) |

Little's Law (L = λW, L<sub>q</sub> = λW<sub>q</sub>) links the counts and times.



## Privacy

Progress (stars, XP, badges, streaks) is saved only in each player's browser with `localStorage`. Nothing is sent to a server. The only external request is for Google Fonts.

## License

MIT. See [LICENSE](LICENSE).
