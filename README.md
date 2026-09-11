# Sequence Runner

Sequence Runner is a dependency-free first-person browser puzzle served by a Cloudflare Worker. Choose a route, walk the forward corridor, and activate each glowing panel in numerical order.

## Controls

- `W A S D` — move
- Mouse — look around (click the game to capture the cursor)
- `Space` — jump
- Left click — activate the panel in your reticle
- `Esc` — release the cursor

The three routes have different lengths and generated musical motifs. Panel activation has a bright confirmation sound; incorrect attempts produce a low warning tone. The route positions always increase down the corridor, so there is no backtracking or circular route.

## Worker

`worker.js` is an ES module Worker with the page embedded in the script. It has no runtime dependencies and can be deployed with the Cloudflare API or any compatible Worker deployment tool.

## Verification and handoff

The current local commit is `a37509a`. The embedded browser script was compiled and initialized with V8 using DOM, canvas, pointer-lock, timer, and Web Audio stubs. Behavior checks passed for all three route completions, far-panel rejection, forward barriers, reverse-movement clamping, music restart on a second level, and paused movement without pointer lock. These are execution checks against the game functions; they are not a substitute for a real browser session.

The local Git commit succeeded, but pushing to the configured HTTPS remote needs a GitHub credential. The GitHub Contents connector returned HTTP 403, and the Cloudflare Worker upload returned an authentication error, so an account with GitHub write and Cloudflare Workers write permissions must complete the external sync/deploy step. The deployment input is this file (`worker.js`), uploaded as an ES module Worker.
