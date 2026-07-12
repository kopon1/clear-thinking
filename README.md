# Clear Thinking

A decision-making skill for coding agents. Point it at a real decision and it works through the choice out loud — separates facts from assumptions, hunts blind spots, weighs the options, and hands back a straight recommendation in prose that doesn't read like AI slop.

This skill follows the [Agent Skills specification](https://skills.sh) so it can be used by any skills-compatible agent, including Claude Code, Codex, and OpenCode.

## How it works

You give it a decision — often a vague one. Instead of guessing or dumping a checklist, it stops and figures out what you're actually deciding.

First it separates what's known from what's assumed from what's just unknown, and refuses to let an assumption pass itself off as a fact. It states what a good outcome would concretely look like, then lays out the real options — including doing nothing — and weighs each on upside, downside, cost, reversibility, and what you give up by picking it.

Then it goes looking for what you missed. It sorts the situation into known and unknown quadrants and runs a quick pre-mortem — *"it's a year from now and this failed; why?"* — to drag the blind spots into the open. Depending on the kind of decision, it reaches for a few thinking lenses that fit — inversion for a risky bet, base rates for a forecast, first-principles when "everyone does it this way" — instead of running the same tired checklist every time.

It ends with one recommendation, not a balanced survey: what to do this week versus later, how confident it is, and what evidence would change its mind. And it says all of this in plain, direct prose — no filler, no hedging stacks, no AI slop.

The skill is manual-only by design. You reach for it when a call is actually worth the thought, and it stays out of the way the rest of the time.

## Installation

### Marketplace

```
/plugin marketplace add kopon1/clear-thinking
/plugin install clear-thinking@clear-thinking
```

### npx skills

```
npx skills add git@github.com:kopon1/clear-thinking.git
```

Instead of ssh, if you prefer to use https:

```
npx skills add https://github.com/kopon1/clear-thinking
```

### Manually

**Claude Code**

Copy the skill folder into your skills directory (`~/.claude/skills/` for global, or `.claude/skills/` in a project):

```
cp -r skills/clear-thinking ~/.claude/skills/clear-thinking
```

**Codex**

Copy the `skills/` directory into your Codex skills path (typically `~/.codex/skills`). See the [Agent Skills specification](https://skills.sh) for the standard skill format.

**OpenCode**

Clone the entire repo into the OpenCode skills directory (`~/.opencode/skills/`):

```
git clone https://github.com/kopon1/clear-thinking.git ~/.opencode/skills/clear-thinking
```

Do not copy only the inner `skills/` folder — clone the full repo so the structure is `~/.opencode/skills/clear-thinking/skills/<skill-name>/SKILL.md`. OpenCode auto-discovers all `SKILL.md` files and they become available after a restart.

## Usage

Invoke it deliberately, with your decision on the same line:

```
/clear-thinking <the decision you're facing>
```

Give it a vague request and it won't stall. It scopes the problem, states its assumptions out loud, and asks only the questions whose answers would change the recommendation.

The skill is **manual-only** (`disable-model-invocation: true`) by design — a decision ritual shouldn't fire on every message. You reach for it when a call is worth the thought. To make it trigger automatically, delete that line from `SKILL.md`.

## Skills

| Skill | Description |
| --- | --- |
| clear-thinking | Work through a consequential decision — separate facts from assumptions, hunt blind spots with a pre-mortem, apply the thinking lenses that fit, and return a straight recommendation with stated confidence |

## What's inside

The skill runs ten steps in order — kept light for small calls, thorough for big ones: identify the real decision, sort facts from assumptions from unknowns, state the success criterion, generate the strongest options, compare them (upside, downside, cost, reversibility, opportunity cost), hunt blind spots, apply fitting lenses, recommend, state confidence, explain plainly.

Two things make it more than a checklist:

- **Blind-spot hunting is built in.** The process forces out "unknown unknowns" with a pre-mortem — *"it's a year from now and this failed; why?"* — instead of hoping you thought of everything.
- **A toolkit of lenses, not one fixed process.** [`references/thinking-styles.md`](skills/clear-thinking/references/thinking-styles.md) holds seven thinking styles — inversion, pre-mortem, second-order, first-principles, base rates, expected value, reversibility — each with a "when to use it" line and a runnable prompt. The skill picks the two or three that fit the problem instead of running all seven.

It's also tuned for **voice**: lead with the answer, cut the stock phrases and hedging stacks, prefer concrete numbers over "certain considerations." Precision wins over polish — it won't drop a real caveat to sound smooth.

## License

MIT © 2026 Justine Ladlad ([@kopon1](https://github.com/kopon1))
