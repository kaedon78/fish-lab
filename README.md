# Fish Lab

Procedural, seeded side-view pixel fish — a single self-contained page, no build step.

**Live:** https://kaedon78.github.io/fish-lab/

- **Gallery** — the same seed + habitat always renders the same fish. Eight habitats from Pond to Cosmic Void, with Lovecraftian traits growing more common the deeper you go.
- **Species** — fish, sharks (great white, hammerhead, thresher, tiger, whale shark), whales (humpback, sperm, orca, blue, narwhal) and jellyfish (moon, box, lion's mane, sea nettle, comb). Each habitat has its own species mix, or pin one in the sidebar. Only the same species can breed; kinds within a species cross freely.
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

Everything above the `lab UI` banner in `index.html` is the generator. Lift it into `fishGen.js` and export `drawFish`, `featuresFromSeed`, `drawFishFeatures`, `fishAnim`, `renderFishDataURL`, `renderFishFeaturesDataURL` and `breedFeatures`.
