# ReStyle AI — Product Requirements

## Problem

Users often struggle with two questions:

1. What should I wear from clothes I already own?
2. What should I look for when I need something new?

ReStyle AI acts as a personal fashion-expert assistant that combines
wardrobe intelligence, color compatibility, user-controlled styling goals,
occasion context, preferences, and relevant trend signals.

## Core Experience 1 — Manage My Wardrobe

Users upload images of clothes they already own.

The system should:

- store wardrobe items
- categorize clothes
- extract dominant colors
- organize items by category
- allow manual corrections
- generate mix-and-match outfits
- support occasion-based recommendations
- support natural-language prompts
- explain why an outfit was recommended

Example:

User:
"I have an interview tomorrow. Suggest something professional."

Output:
- White shirt
- Navy trousers
- Beige blazer

Explanation:
- strong occasion match
- compatible colors
- aligns with user preferences
- all items already exist in the wardrobe

## Core Experience 2 — Find Something

Users ask what they should look for when they need something new.

Example:

User:
"I need something for a party."

The system should consider:

- optional user-provided photo
- editable color profile
- color compatibility
- personal preferences
- user-confirmed styling goals
- occasion
- relevant trend signals

Output:

Recommended colors:
- Deep teal
- Emerald
- Midnight blue

Recommended direction:
- structured silhouette
- defined waist
- statement accent

Explanation:
- color-profile compatibility
- occasion relevance
- preference match
- personalized trend relevance

## V1 Features

### Manage My Wardrobe

- [ ] Upload clothing image
- [ ] Store clothing item
- [ ] View wardrobe
- [ ] Filter by category
- [ ] Manually edit item metadata
- [ ] Extract dominant color
- [ ] Generate basic outfit combinations
- [ ] Select occasion
- [ ] Rank outfit recommendations
- [ ] Explain recommendations

### Find Something

- [ ] Upload user photo
- [ ] Validate image quality
- [ ] Extract color features
- [ ] Build editable color profile
- [ ] Recommend color families
- [ ] Select occasion
- [ ] Select styling goals
- [ ] Generate clothing-direction recommendations
- [ ] Explain recommendations

## Explicitly Not in V1

- Virtual try-on
- E-commerce checkout
- Social network
- Celebrity cloning
- AR
- Marketplace
- Automatic purchasing
- Large-scale microservices

## Success Criteria

A user should be able to:

1. Upload at least 10 wardrobe items.
2. Browse and filter their wardrobe.
3. Select an occasion.
4. Receive at least 3 outfit combinations from existing clothes.
5. Understand why each outfit was recommended.
6. Upload a personal photo for optional analysis.
7. Receive an editable color profile.
8. Receive occasion-specific recommendations for what to look for next.
