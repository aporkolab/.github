# Whack-a-Bug: correcting the brief

I wanted a small, playful developer toy for my GitHub Pages address. I already had a project website. The new page needed to be something visitors could enjoy immediately.

The first direction was a generic landing page. I rejected it. The next was an agent-management game with specialists, a task graph, and a budget. That missed the brief too. I asked for something closer to whack-a-mole: cute characters, a simple action, and a reason to play again. The uniform yellow design also had to go.

That correction became [Whack-a-Bug](https://aporkolab.github.io/).

## The game that shipped

Nine holes. Bugs to hit. Friendly bots to spare. A combo multiplier and a rechargeable Bot Buddy that clears the visible bugs. Normal rounds last 45 seconds; Chill rounds last 60. The player can use a mouse, touch, or the QWE / ASD / ZXC keys.

The characters are original SVG artwork defined in the source. The game uses HTML, CSS, and native JavaScript modules, with the engine separate from the browser interface. The maintained files in `dist/` are also the deployable site, so there is no bundling step.

Bot Buddy is a game mechanic. It does not call a model or need an API key. Development used AI assistance; gameplay runs locally in the browser.

## What the checks establish

The engine has 12 tests using Node's built-in test runner. They cover seeded spawning, round timing, scoring, combos, target expiration, pausing, Bot Buddy, finished rounds, and invalid inputs. The Pages workflow runs them before packaging the site; deployment depends on that job succeeding.

Those tests check the game rules. They do not establish whether the art is appealing or the game feels good. Browser inspection and the human response to the result answer different questions.

## What I would carry into the next build

The decisive correction was about the purpose of the page. The earlier implementation had features, but they were features for an experience I had not wanted.

For the next small visual project, I would put a playable slice in front of the person directing it before expanding the mechanics. Keep the technical checks, but ask the basic question early: is this actually fun to use?

## Source and deployment record

- [Repository](https://github.com/aporkolab/aporkolab.github.io)
- [Published revision: `2fffd102`](https://github.com/aporkolab/aporkolab.github.io/commit/2fffd102e17ebda9f31af758fcec446841ebbef0)
- [Deployment workflow run](https://github.com/aporkolab/aporkolab.github.io/actions/runs/37774560112)
- [Engine tests at that revision](https://github.com/aporkolab/aporkolab.github.io/blob/2fffd102e17ebda9f31af758fcec446841ebbef0/tests/engine.test.mjs)
- [SVG artwork at that revision](https://github.com/aporkolab/aporkolab.github.io/blob/2fffd102e17ebda9f31af758fcec446841ebbef0/dist/art.js)

