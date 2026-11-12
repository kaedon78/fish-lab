# Fish Lab

Procedural, seeded side-view pixel fish — a single self-contained page, no build step.

**Live:** https://kaedon78.github.io/fish-lab/

- **Gallery** — the same seed + habitat always renders the same fish. Eight habitats from Pond to Cosmic Void, with Lovecraftian traits growing more common the deeper you go.
- **Species** — fish, sharks (great white, hammerhead, thresher, tiger, whale shark), whales (humpback, sperm, orca, blue, narwhal) and jellyfish (moon, box, lion's mane, sea nettle, comb). Each habitat has its own species mix, or pin one in the sidebar. Only the same species can breed; kinds within a species cross freely.
- **Ocean view** — the 32 seed variants of the current seed swim together in a scene themed to the habitat: reeds and lily pads in the pond, kelp on the coast, corals on the reef, glowing vents in the trench, floating rocks in the void. Each kind is drawn at its own size: fish and small jellies at 1x, sharks around 1.6-1.8x, whale sharks and the great whales 2-3x. The big ones are painted at that resolution rather than upscaled, so every creature has the same pixel size and the giants get finer detail. They swim in three depth layers: further back they are painted smaller (still at the same pixel size), swim slower and sink into darker water; the big kinds lean to the back. Every few seconds two random creatures of the same species and depth pair up (hearts float over them), swim to meet and have two young, bred as in the pen with its mutation and effect odds; a little later the parents swim out of the scene (jellies fade), so the crowd keeps changing while its size holds. Young can breed once they are 25 seconds old. Hover a creature to hold it in place and get a tooltip: its kind, seed (or for the young, generation and parents), colours, effects, depth and what it's up to. Click it to open it in the creator. **Maximize** fills the window with the scene (Esc to restore).
- **Creator** — edit every feature by hand, preview the swim animation, copy the feature JSON.
- **Breeding pen** — cross two fish of the same habitat into a litter of 16. Gene groups come from one parent, numbers and colours can blend, and a mutation rate pulls genes from a fresh fish of that habitat. Children can be promoted to parents for later generations.
- **Mutation effects** — bred fish can roll up to three of Shiny, Glowing, Golden, Albino, Frozen, Spotted and Crystal; each extra effect is much rarer (Rare / Epic / Legendary).

## Running locally

Open `index.html` directly in a browser, or serve the folder:

```bash
python -m http.server 3300
```

then visit http://localhost:3300/.

## Reusing the generator

Everything above the `lab UI` banner in `index.html` is the generator. Lift it into `fishGen.js` and export `drawFish`, `featuresFromSeed`, `drawFishFeatures`, `fishAnim`, `renderFishDataURL`, `renderFishFeaturesDataURL`, `breedFeatures`, `makeOcean` (the ocean scene painter), `oceanScale` (how big each kind is drawn in a shared scene) and `frameSize`. `drawFishFeatures` takes an optional `res` after `anim` to paint a creature `res` times bigger at the same pixel size, into a canvas of `frameSize(res)`.
