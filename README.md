# cat-wholeness-coverage

Scores the proportional presence of a cat within an image — how much of the frame it claims and how whole it feels while doing so.

## Overview

`cat-wholeness-coverage` is a scalar function that takes a single image containing a cat and returns a score between **0** and **1**. The score captures a compound judgment: how much visual real estate the cat occupies in the frame, and whether that occupation feels substantial and complete rather than fragmented or insignificant.

- **Score near 1**: The cat fills the frame generously with its whole, intact form — it is large, complete, and unmistakably the subject.
- **Score near 0.5**: The cat is moderately present — perhaps medium-sized, partially cropped, or noticeable but not dominant.
- **Score near 0**: The cat is either tiny and lost in a vast scene, or so aggressively cropped that it feels like a fragment rather than a whole animal.

## Input

The function accepts a single required field:

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `image` | image | Yes | Any photograph, illustration, or rendering containing a cat. |

## Output

A scalar value in the range [0, 1] representing the cat's proportional presence within the image.

## What It Evaluates

The function evaluates three interrelated qualities, each capturing a different dimension of what it means for a cat to be proportionally present.

### 1. Spatial Occupation

How much of the image's total area does the cat physically inhabit? This is the foundational measurement — the raw proportion of the frame that the cat claims. A cat lounging across most of the image is visually dominant; a cat reduced to a speck in a wide landscape is not. Without meaningful spatial occupation, no other quality can make a cat feel present.

### 2. Bodily Completeness

Is the cat's physical form wholly contained within the boundaries of the image? This quality detects whether the framing preserves the cat as a complete subject or fragments it through aggressive cropping. The ideal is a cat whose full body — head, ears, torso, legs, paws, and tail — is generously contained with breathing room from the edges. At minimum, the face and upper body should be unclipped. Cropping that slices away ears, truncates tails, or hides limbs reduces this score, leaving the viewer with a piece of a cat rather than a whole animal.

### 3. Compositional Substantiality

Does the cat produce the holistic impression of being the weighty, anchoring subject of the image? This quality synthesizes the first two: a cat can be moderately sized and intact yet still feel insubstantial if dwarfed by overwhelming surroundings. Conversely, a cat that fills the frame generously with its whole form radiates visual authority. This evaluation captures the gestalt — whether the cat's size and wholeness combine to make it unmistakably the point of the image.

## Use Cases

- **Pet adoption platforms**: Filter for profile photos where the cat fills the frame in its entirety, giving prospective adopters a generous, complete view of the animal.
- **Photography curation**: Surface the best frames from a shoot session — images where the cat landed squarely and fully in the composition.
- **Content pipelines**: Gate automated curation so only images above a threshold are considered cat-centric enough to proceed.
- **Social media curation**: Select images where the cat is the clear, commanding subject for maximum visual impact.
- **ML dataset filtering**: Ensure training images contain cats that are prominent and whole rather than incidental or fragmented.

## Scoring Examples

| Scenario | Expected Score |
|----------|---------------|
| Cat fills 80% of the frame, full body visible, clearly the subject | ~0.9 |
| Cat takes up half the frame, mostly intact, one paw slightly cropped | ~0.7 |
| Cat is medium-sized in the frame, fully visible but surrounded by scenery | ~0.5 |
| Cat is small in a wide shot, fully visible but distant | ~0.3 |
| Extreme close-up of a cat's eye filling the entire frame | ~0.3 |
| Tiny cat barely visible in a landscape photograph | ~0.1 |

## Important Notes

- The function does **not** judge the beauty of the cat, the quality of the photograph, or the artistry of the composition.
- It asks one compound question: *how much of this image belongs to the cat, and does the cat feel whole while occupying that space?*
- Both extremes score low: a tiny distant cat (low spatial occupation) and an aggressively cropped close-up (low bodily completeness) are both penalized.
- The sweet spot is a cat that is large in the frame **and** whole in form — commanding without being fragmented.
