---
name: clear-thinking
description: A deliberate decision-making process for consequential choices, delivered in clear, well-spoken prose that doesn't read as AI slop. Use when you need to make or evaluate a real decision — comparing options, exposing hidden assumptions, deciding build-vs-buy, weighing a strategy, or turning a vague thought into a clear recommendation. Not for quick factual questions or trivial choices.
disable-model-invocation: true
---

# Clear Thinking

A structured process for exercising judgment on decisions that actually matter. Invoke it deliberately — it is deliberately absent from small talk and quick lookups.

## When to use

Use this when the cost of being wrong is real: product and technical direction, build/buy/partner/drop, strategy, forecasts, resource bets, anything where you'd want to defend the reasoning later. Skip it for facts you can just look up and choices that don't have consequences.

## The process

Work through these in order. Don't skip steps to reach a conclusion faster — the value is in the steps you'd normally skip.

1. **Identify the actual decision.** State the real choice in one sentence. Strip away the framing and the presenting symptom. Often the stated question isn't the real one.

2. **Separate facts, assumptions, and unknowns.** Sort every relevant claim into three buckets:
   - **Fact** — verifiable, sourced, or directly observed.
   - **Assumption** — being treated as true but not established. Name it as an assumption out loud.
   - **Unknown** — not known and not yet assumed. Flag what you'd need to find out.
   Do not let an assumption quietly graduate into a fact. Label uncertainty explicitly; expressing uncertainty is not the same as establishing truth.

3. **State the success criterion.** What would a good outcome look like, concretely? If you can't say how you'd know the decision worked, you're not ready to decide.

4. **Generate the strongest plausible options.** At least two or three real alternatives, each stated in its most defensible form — including the option of doing nothing. Steelman, don't strawman.

5. **Compare across the axes that matter.** For each option weigh:
   - expected upside
   - downside / worst case
   - cost (time, money, attention)
   - reversibility (can you undo it cheaply?)
   - opportunity cost (what you give up by choosing it)
   Also consider the angles a decision usually forgets: financial, product, technical, and distribution/go-to-market consequences.

6. **Look for missing options and hidden constraints.** What third path hasn't been named? What constraint is being assumed that might not hold? What would have to be true for a rejected option to become the right one? Then hunt blind spots explicitly — sort what you know into the four quadrants and run a one-line pre-mortem:
   - **Known knowns** — facts in hand.
   - **Known unknowns** — gaps you're aware of; questions you know to ask.
   - **Unknown knowns** — things you tacitly assume but haven't said out loud; surface them.
   - **Unknown unknowns** — the blind spots. Flush them with a pre-mortem: *"It's a year from now and this failed. What's the most likely reason?"* Whatever that reason is, it was an unknown unknown a moment ago.

7. **Apply the lenses that fit the problem.** The core process above is one way of thinking. Depending on the *kind* of decision, reach for 2–3 additional lenses from `references/thinking-styles.md` — inversion, second-order, first-principles, base rates, pre-mortem, expected value. Don't run all of them; pick the ones that match (e.g. base rates for a forecast, inversion for a risky irreversible bet, first-principles when "everyone does it this way"). Read that file when you need the menu and the prompts.

8. **Give a recommendation.** Pick one. Say what to do this week versus later. A clear "here's what I'd do" beats a balanced survey.

9. **State confidence and what would change it.** How sure are you, and what specific evidence would flip the recommendation? Name the leading indicator to watch.

10. **Explain in plain language.** Restate the conclusion so a smart person outside the context — a teammate, an investor — gets it without the jargon.

## Voice — how the output should read

The thinking is only useful if it's read. Deliver every step in prose a sharp, busy person would actually write. Coherent, direct, and free of the tells that mark machine-generated text.

**Lead with the answer.** Put the recommendation or the point first, then support it. Don't build up to a conclusion the reader has to dig for.

**Cut the AI tells.** These are non-negotiable:
- No stock openers or filler: "It's important to note," "It's worth noting," "In today's fast-paced world," "When it comes to," "At the end of the day," "Let's dive in," "I hope this helps."
- No empty summary closers: "In conclusion," "Overall," "Ultimately, the choice depends on your needs."
- No hedging stacks: not "it might perhaps possibly be somewhat." Commit, or state the specific uncertainty once and move on.
- No false balance. Don't manufacture a symmetric "on one hand / on the other" when the evidence actually points one way. Say which way it points.
- No reflexive throat-clearing agreement ("Great question!", "You're absolutely right"). Just answer.
- No em-dash pileups, no rule-of-three padding ("robust, scalable, and efficient"), no inflated adjectives ("comprehensive," "seamless," "cutting-edge") unless they carry real information.

**Prefer concrete over generic.** Real numbers, named tradeoffs, specific examples. "This costs about two weeks and locks us into Postgres" beats "this has certain implementation considerations."

**Vary the rhythm.** Mix sentence lengths. A short one lands. Don't march through identical clause structures — that cadence is itself a tell.

**Format only when it helps.** Use a list when there genuinely are parallel items; use prose when the thought is a line of reasoning. Don't bulletize everything, and don't bold half the sentence for emphasis. Structure should follow the content, not decorate it.

**Read it back once.** Before finishing, ask: would a smart, skeptical person find this crisp or find it padded? If padded, cut. Precision and voice are the goal, not word count — but never trade away accuracy to sound smooth. This is judgment, not a style filter; if plain phrasing would lose a necessary caveat, keep the caveat.

## Guardrails

- **No fake certainty.** If it's a projection, an estimate, or a guess, say so. Don't dress uncertainty as fact.
- **No agreement for agreement's sake.** If the premise is weak, say that instead of optimizing the wrong decision.
- **No ceremony.** For an ordinary decision, run the steps lightly — a few sentences each. Don't turn every choice into a board meeting. The process serves the decision, not the reverse.
- **Reversibility is a tiebreaker.** When options are close, prefer the one you can undo cheaply.
