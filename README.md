# score-cat-authenticity

A Vector Function that ranks cat photographs by authenticity, emotional resonance, and personality expression.

## Overview

The `score-cat-authenticity` function identifies and celebrates cat photographs that capture genuine moments and reveal authentic feline character. In a landscape of curated pet content, this function serves as a curator of truth—ranking photographs that show cats being themselves over those that are staged, posed, or artificially constructed.

The function evaluates three fundamental dimensions of cat photography quality:

1. **Authenticity** - How well the photograph captures unguarded, natural moments
2. **Emotional Resonance** - How effectively the image creates genuine emotional connections
3. **Personality Expression** - How distinctly the photo reveals the individual cat's unique character

## Input

The function accepts an array of cat photo objects to be ranked. Each photo object contains:

- **url** (required): The URL or file path to the cat photo image
- **title** (optional): A descriptive title or label for the photo
- **photographer** (optional): Attribution or credit to the photographer

**Example Input:**
```json
[
  {
    "url": "https://example.com/photo1.jpg",
    "title": "Midnight's afternoon nap",
    "photographer": "Sarah Johnson"
  },
  {
    "url": "https://example.com/photo2.jpg",
    "title": "Luna playing with string",
    "photographer": "Sarah Johnson"
  },
  {
    "url": "https://example.com/photo3.jpg",
    "title": "Tiger on the windowsill"
  }
]
```

**Constraints:**
- Minimum 2 photos required
- Maximum 100 photos per request

## Output

The function returns an array of ranking scores that sum to approximately 1.0. Each score represents the relative ranking position of the corresponding input photo, with higher scores indicating photos that better capture authenticity, emotional resonance, and individual personality.

**Example Output:**
```json
[0.35, 0.28, 0.37]
```

This indicates that photos at indices 0, 1, and 2 ranked with relative weights of 35%, 28%, and 37% respectively.

## What Gets Evaluated

### Authenticity (Vector Task)
The function ranks photos by how authentically they capture genuine, unguarded moments. This evaluation considers:
- Natural body language and relaxed posture
- Unforced facial expressions
- Real behaviors and activities (playing, resting, exploring)
- Absence of signs of positioning or arrangement
- Candid timing and natural lighting

Photos showing cats in their true element—engaged in real activities without awareness of the camera—rank significantly higher than those with awkward poses or signs of staging.

### Emotional Resonance (Vector Task)
The function ranks photos by how effectively they create emotional bridges between viewers and the cat. This evaluation considers:
- Expressions of genuine emotions (joy, curiosity, vulnerability, contentment)
- Visibility of the cat's inner life and personality
- Ability to evoke empathy and human understanding
- Emotional authenticity and depth
- Moments that reveal vulnerability, playfulness, or affection

Photos that move viewers and create meaningful emotional connections rank higher than technically perfect but emotionally hollow images.

### Individual Personality (Scalar Task)
The function scores each photo for how distinctly it reveals the specific, unique character of the individual cat. This evaluation considers:
- Distinctive traits and behavioral quirks
- Habits and preferences specific to this cat
- Characteristic expressions or mannerisms
- The cat's unique way of being in the world
- Whether the photo helps viewers truly "know" the cat

Photos that showcase what makes this particular cat unique—its humor, temperament, and distinctive personality—score higher than generic images of cat behavior.

## Use Cases

### Personal Photography Organization
Cat owners can use this function to identify and organize their most meaningful photos of their pets, creating curated collections that capture genuine moments and personality over technically perfect shots.

### Professional Pet Photography
Pet photographers can evaluate their portfolios to understand which images most successfully capture authentic personality and emotional authenticity, guiding their artistic development and client selection.

### Social Media Content Curation
Platforms and cat appreciation communities can use this function to surface authentic, emotionally resonant cat content, creating spaces where genuine connection matters more than staged perfection.

### Cat Photography Communities
Photography groups and forums can use this function to recognize and celebrate photography that honors cats' true nature, encouraging a culture of authentic documentation.

### Content Selection for Publications
Magazines, websites, and content curators can use this function to select cat photography that tells genuine stories and creates real human-cat connections rather than relying on artificially constructed imagery.

## Architecture

This function is built on three specialized sub-functions:

### Sub-Functions

1. **assess-authenticity** (Vector Task)
   Repository: https://github.com/ObjectiveAI-claude-code-1/rank-cat-candids
   Ranks all photos by how authentically they capture genuine, unguarded moments

2. **evaluate-emotional-resonance** (Vector Task)
   Repository: https://github.com/ObjectiveAI-claude-code-1/{{ .Task1 }}
   Ranks all photos by their emotional impact and viewer connection

3. **recognize-personality** (Scalar Task)
   Repository: https://github.com/ObjectiveAI-claude-code-1/score-cat-personality
   Scores each photo for how well it reveals individual personality traits

Each sub-function specializes in one dimension of authentic cat photography, and their combined evaluations produce the final ranking. The function uses weighted averaging of the three task outputs to create a comprehensive assessment of each photo's authenticity and charm.

## Design Philosophy

The `score-cat-authenticity` function is built on the belief that genuine moments are far more valuable and meaningful than constructed ones. Rather than rewarding technical perfection or commercial appeal, it prioritizes:

- **Authenticity over Aesthetics** - Real moments over carefully arranged compositions
- **Emotional Truth over Emotional Manipulation** - Genuine human-cat connection over engineered sentiment
- **Individual Character over Generic Appeal** - What makes each cat unique and memorable
- **Respect for Subjects** - Honoring cats as beings with their own agency and nature

By systematically recognizing photographs that capture cats authentically, the function creates incentives for a different kind of pet photography—one that sees cats not as props but as individuals worthy of genuine documentation.

## Learn More

For detailed information about how each sub-function evaluates its specific dimension, visit the individual repository pages linked above.