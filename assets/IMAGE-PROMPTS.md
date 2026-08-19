# Image prompts — Solene checkout-recovery email

**Status: delivered 2026-08-19.** `solene-hero.jpg` (1200×800) and `solene-product.jpg`
(264×264) are final and in place. Keep these prompts for regenerating or extending the
set — any future image must match the same product, lighting, and bone/terracotta palette.

Two images. Generate #1 first, then generate #2 **in the same session / from the same
image** so the product, materials, and lighting match. Hand me the raw files at any size —
I crop, resize, and compress them to the exact dimensions the email needs.

Save as:
- `marketing/outreach/templates/assets/solene-hero.jpg`
- `marketing/outreach/templates/assets/solene-product.jpg`

Hard rules for both, keep these lines in the prompt: **no text, no letters, no numbers, no
logos, no branding, no packaging copy, no people, no hands, no medical clutter.** Any
generated lettering will look fake and kill the piece.

---

## 1. Hero — `solene-hero.jpg` (3:2, aim for 1800×1200 or larger)

```
Premium product still-life photograph for a modern direct-to-consumer telehealth brand.
A slim, unbranded matte-white medical injector pen resting at a slight diagonal on a
smooth warm bone-colored surface (#F5F2ED), beside a minimal soft-cream folding carton
box with clean rounded edges and a single thin terracotta clay stripe (#A8492A) along
one edge. Soft directional daylight from the upper left, gentle diffused shadows, subtle
depth of field, quiet and calm. Apple product photography: generous negative space,
restrained composition, immaculate surfaces, no props or decoration. Warm neutral palette
of bone, cream and soft beige with a single terracotta accent. Editorial, premium,
expensive-looking, high resolution, ultra sharp.
No text, no letters, no numbers, no logos, no branding, no packaging copy, no people,
no hands, no medical clutter, no syringes with needles visible, no clinical instruments.
3:2 landscape.
```

Composition note: keep the product roughly centered with breathing room on all sides. The
email crops this to 600×400, so nothing important should sit near the edges.

## 2. Product thumbnail — `solene-product.jpg` (1:1, aim for 800×800 or larger)

```
Same product, same lighting, same warm bone surface. Reframe as a tight square close-up
of the cream folding carton box standing upright with the slim matte-white pen leaning
against it. Centered, generous even margins, soft daylight from the upper left, gentle
shadow. Same terracotta clay accent stripe. Clean, premium, catalog-style.
No text, no letters, no numbers, no logos, no branding, no people, no hands.
1:1 square.
```

---

## If a generation comes back with garbled text on the packaging

Regenerate rather than accept it. Add to the prompt: `completely blank unmarked packaging,
plain unprinted carton, no printed surface details of any kind`.

## Fallback if the images never land

The email is built so it still reads correctly with images off: the hero slot collapses to
a bone-colored band with alt text, and the Saved Session card keeps its layout with the
thumbnail replaced by alt text. Nothing essential — headline, saved-session data, CTA — is
inside an image.
