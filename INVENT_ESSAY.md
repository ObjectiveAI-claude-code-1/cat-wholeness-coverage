
# Cat Wholeness Coverage

## Purpose

There is a particular satisfaction in looking at a photograph of a cat and feeling that the cat is truly *there* — not a minor detail lost in the background, not a sliver of fur peeking from the edge of the frame, but a full, undeniable feline presence that commands the image. The purpose of cat-wholeness-coverage is to measure exactly that feeling. Given a single image containing a cat, this function produces a score between 0 and 1 that captures how proportionally present the cat is within the frame — how much of the visual space it claims, and how complete it feels while doing so.

This is not merely a question of pixel count. A tightly cropped macro shot of a cat's eye might technically fill the frame with cat, yet it leaves the viewer with a fragment, not a subject. Conversely, a wide landscape photograph with a tiny cat perched on a distant fence post gives us the whole animal but robs it of any visual weight. The function seeks the sweet spot between these extremes: the cat as a generous, whole, commanding subject within its frame.

The input to this function is an image — any photograph, illustration, or rendering that contains a cat. The output is a single scalar value. A score approaching 1 tells us the cat dominates the image with its complete form, filling the frame substantially while remaining visually intact. A score approaching 0 tells us the cat is either lost in the vastness of the scene, or so aggressively cropped that it no longer registers as a whole being. The function does not judge the beauty of the cat, the quality of the photograph, or the artistry of the composition. It asks one compound question: how much of this image belongs to the cat, and does the cat feel whole while occupying that space?

## Use Cases

The applications for such a measurement are numerous. Anyone curating a collection of cat photographs — whether for a website, a social media account, a product catalog for pet supplies, or a dataset for machine learning — needs a way to filter for images where the cat is the clear, substantial subject. A pet adoption platform, for instance, wants profile photos where the animal fills the frame in its entirety, giving prospective adopters a generous, complete view. A photographer reviewing hundreds of shots from a session needs to quickly surface the frames where the cat landed squarely and fully in the composition. In content moderation or automated curation pipelines, this score can serve as a gate: only images above a certain threshold are considered cat-centric enough to proceed. In each case, the function acts as an automated eye, replicating the instinctive judgment a person makes when flipping through photos and pausing on the ones where the cat feels prominent and whole.

## Three Qualities of Evaluation

To arrive at its score, cat-wholeness-coverage must evaluate three interrelated but distinct qualities of the image. Each quality captures a different dimension of what it means for a cat to be proportionally present, and the final score emerges from the balance among them.

### 1. Spatial Occupation

The first and most foundational quality is spatial occupation — the sheer amount of the image's area that the cat physically inhabits. This is the most intuitive dimension of proportional presence. When a cat stretches across the majority of the frame, it is visually dominant. When it occupies only a small fraction, it recedes into the scenery. Spatial occupation asks: if you were to draw a boundary around the cat and measure the area inside, what proportion of the total image would that area represent?

A cat lounging across a couch cushion in a tightly framed portrait might occupy seventy or eighty percent of the image. A cat sitting in the middle of a sprawling backyard might occupy five percent. The difference in visual impact is immediate and dramatic. Spatial occupation is the raw metric of size-within-frame, and it forms the baseline of the score. Without meaningful spatial occupation, no amount of completeness or composure can make a cat feel proportionally present. The cat must take up room. It must claim visual real estate. This quality measures whether it does.

### 2. Bodily Completeness

The second quality is bodily completeness — the degree to which the cat's physical form is wholly contained within the boundaries of the image. A cat can be large in the frame and still feel incomplete if the photograph crops away significant portions of its body. Ears sliced off at the top edge, a tail truncated by the right margin, paws hidden below the bottom of the frame — each of these subtractions chips away at the viewer's sense that they are seeing a whole animal. Bodily completeness asks: is the cat *all here*?

This quality is what separates a commanding portrait from an awkward crop. The ideal is a cat whose full body is visible and generously contained, with breathing room between the animal and the edges of the frame. At minimum, the cat's face and upper body should be intact and unclipped, preserving the identity and expression of the subject. The more of the cat that is present — head, torso, legs, tail — the higher the bodily completeness. When a photographer zooms in so aggressively that the cat becomes a wall of fur with no discernible boundaries, or when the framing accidentally amputates limbs and features, the completeness score drops. The viewer is left with a piece of a cat rather than a cat, and that fragmentation undermines the sense of presence no matter how much of the frame is filled.

### 3. Compositional Substantiality

The third quality is compositional substantiality — the overall impression that the cat is not merely present in the image but is the weighty, anchoring subject of it. This quality is more holistic than the first two. Spatial occupation measures area. Bodily completeness measures intactness. Compositional substantiality measures the *feeling* that emerges when the two combine well — or the feeling that is absent when they do not.

A cat can occupy a moderate amount of space and be fully intact, yet still feel insubstantial if it is dwarfed by overwhelming surroundings or positioned as an incidental element in a busy scene. Conversely, a cat that fills the frame generously with its whole form radiates a sense of visual authority — it is unmistakably the point of the image. Compositional substantiality captures this gestalt. It reflects whether the cat's size and wholeness together produce the impression of a subject that matters within its frame, one that a viewer's eye is drawn to not because they are searching for it, but because it demands attention through its sheer proportional presence. This is the quality that ties the evaluation together, ensuring the score reflects not just measurable attributes but the lived experience of looking at the image and feeling that the cat is truly, substantially there.
