# Sequence Runner

Sequence Runner is a dependency-free first-person rhythm platformer served by a Cloudflare Worker. Choose Easy, Medium, or Hard, then jump across separated platforms with gaps, turns, and elevation changes while activating targets in order before the timer expires.

## Controls

- `W A S D` — move relative to horizontal facing
- Mouse — look around (click the game to capture the cursor)
- `Space` — jump
- Left click — activate the panel in your reticle
- `Esc` — release the cursor

The routes use distinct target counts, platform geometry, timers, and generated musical motifs. Falls respawn at the latest safe platform with a small time penalty. Yaw and pitch are separate and pitch is clamped to ±85 degrees. Future targets remain dim and cannot advance the fixed sequence.

## Worker

`worker.js` is an ES module Worker with the page embedded in the script. It has no runtime dependencies and can be deployed with the Cloudflare API or any compatible Worker deployment tool.

## Verification and handoff

The previous deployment is available at https://sequence-runner.exo1ite.workers.dev/; redeploy this revision before relying on it. `git diff --check` and source assertions pass. Node/Wrangler are unavailable here, so real-browser profiling and 60 FPS measurement remain to be run on a device.
