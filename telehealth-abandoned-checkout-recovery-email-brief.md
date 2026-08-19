# Brief: Abandoned Intake / Checkout Recovery Email (portfolio sample)

Spec for `telehealth-abandoned-checkout-recovery-email.html`. Fictional brand, built as a
portfolio attachment for lifecycle/cart-recovery proposals (see proposal 027).

## Role

Senior email designer, HTML email developer, and direct-response lifecycle marketer
working in DTC health and telehealth.

## The core problem this email solves

The recipient **does not remember**. They started an intake days ago, gave a name and an
email, and left. They do not remember the brand name, what the product does, or why they
wanted it. An email that opens with "your session is saved" is a logistics notice sent to
someone with no context, and it will not recover them.

So the email has two jobs, in this order:

1. **Re-sell in one skim.** Rebuild the memory: what this brand is, what they picked, and
   why it mattered to them.
2. **Remove the friction.** Then, and only then, resume the exact saved session.

## Brand

**Solene** — fictional premium DTC telehealth brand in **medically supervised weight care
(GLP-1 category)**.

Positioning line, used verbatim in the email as the re-orientation moment:
> Solene is medically supervised weight care. You complete one intake, a licensed provider
> reviews your health history, and if treatment is appropriate, they put a plan together
> for you.

## Visual direction

Apple-email energy: all-light, huge white space, one oversized product image, one bold
headline, ruthless hierarchy, one dominant action. Premium and energetic, not clinical and
not sleepy. The whole email must be readable in one skim.

| Token | Value | Use |
|---|---|---|
| Canvas | `#F5F2ED` | Outer background, warm bone |
| Card | `#FFFFFF` | Content surface |
| Band | `#F7F4EF` | Quiet bands inside the card |
| Ink | `#1A1A18` | Headlines |
| Body | `#57544E` | Body copy (7.5:1 on white) |
| Muted | `#6B6862` | Eyebrows, captions (5.5:1 on white) |
| Clay | `#A8492A` | CTA, icons, accent (5.75:1 with white text) |
| Clay dark | `#9C4221` | Small accent text on light backgrounds |
| Hairline | `#E8E2D9` | Borders, dividers |

Type: bold Helvetica/Arial for headlines with tight tracking (Apple-style), Arial for body,
Georgia italic reserved for the single review quote so it reads as a different voice.

## Structure

1. Hidden preheader
2. Minimal wordmark header (text, no image)
3. Full-bleed hero image
4. Hero: eyebrow, oversized headline, one-line subhead
5. **"What you started"** re-orientation band — the memory fix
6. **Saved Session** card: product thumbnail, `{{selected_treatment}}`, `{{plan_price}}`,
   dynamic progress bar, "nothing to re-enter"
7. Primary CTA + micro-copy + plain-link fallback
8. What happens next, three steps
9. Social proof: rating row and one short review quote
10. Trust row, three icon points
11. Sign-off and a single repeat text CTA (same action, lower hierarchy)
12. Footer: disclaimer, address, unsubscribe, preference center

## Placeholders

Platform-neutral, no ESP-specific merge syntax.

`{{first_name}}` · `{{selected_treatment}}` · `{{plan_price}}` · `{{intake_progress}}` ·
`{{resume_checkout_url}}` · `{{unsubscribe_url}}` · `{{preference_center_url}}`

`{{intake_progress}}` resolves to a percentage string (e.g. `80%`) and is bound to the
`width` attribute of the progress bar's filled cell, so the bar renders the real value
rather than a decorative fixed one.

## Claim boundary

Fictional brand, but the copy stays inside what a real telehealth brand could say.

Not allowed: medical outcome claims, weight-loss numbers, physician endorsements, HIPAA or
other compliance badges, fake urgency, countdowns, aggressive discounting, invented
regulatory certifications.

Allowed and used: process description (intake → provider review → plan), privacy framing,
provider-review conditionality, and a clearly fictional brand rating and member quote.

## HTML requirements

- 600px max width, table-based, mostly inline CSS, `@media screen and (max-width: 600px)`
- Gmail, Apple Mail, Outlook desktop/web, iOS and Android clients
- No JavaScript, no frameworks, no external CSS
- Bulletproof CTA: VML `roundrect` for Outlook, padded anchor everywhere else
- Every image has explicit `width`/`height`, meaningful or empty `alt`, and no essential
  text lives in an image — the CTA and all copy survive blocked images
- Tap targets at least 44px tall; accessible contrast throughout
- Assets referenced with relative paths for local review; swap for absolute HTTPS URLs
  before any real send

## Assets

| File | Size (source) | Display | Source |
|---|---|---|---|
| `assets/solene-hero.jpg` | 1200×800 | 600×400 | Generated (prompt in `assets/IMAGE-PROMPTS.md`) |
| `assets/solene-product.jpg` | 264×264 | 88×88 | Generated (same prompt file) |
| `assets/icon-shield-check.png` | 72×72 | 24×24 | `.context/make-icons.py` |
| `assets/icon-lock.png` | 72×72 | 24×24 | `.context/make-icons.py` |
| `assets/icon-pause.png` | 72×72 | 24×24 | `.context/make-icons.py` |
| `assets/icon-clock.png` | 72×72 | 16×16 | `.context/make-icons.py` |
| `assets/icon-star.png` | 72×72 | 15×15 | `.context/make-icons.py` |

## Validation before shipping

- Narrow-width layout, columns stack, button goes full width
- CTA legible and clickable with images disabled
- All seven placeholders intact, no platform-specific syntax
- Exactly one conversion action across the whole email
- Copy establishes what the brand is before it asks for the resume
- No medical, regulatory, physician, or service claims outside the boundary above
- Footer carries unsubscribe, preference center, address, and the provider-review disclaimer
