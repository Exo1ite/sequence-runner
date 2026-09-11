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
