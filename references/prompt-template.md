# Prompt Template

Use this for final page prompts or component-level prompts after the memory structure, object manifest, visual route, and component draft are clear. Fill every bracket with page-specific content. Do not write "same as above".

For low-fidelity planning previews, use the shorter preview prompt in `references/authoring-workflow.md` instead of this final-art prompt. Planning previews should show layout and object IDs, not polished final illustration.

```text
Create a [aspect ratio] memory-first travel scrapbook / visual journal page using the selected visual route: [East Asian sticker comic / kawaii sticker journal / black-and-white cartoon doodle / map infographic scrapbook / polaroid photo collage / watercolor travel journal / vintage ephemera scrapbook / urban sketch journal / minimalist line journal / comic book travel page / mixed-media collage / hybrid]. The page should feel handmade, layered, object-rich, and memory-first, not like a clean travel itinerary board or generic photo book.

First-draft art quality:
Make this first polished image feel like a finished, save-worthy digital scrapbook page, not a layout plan. Use a strong cover-like title area, confident visual hierarchy, rich sticker density, polished tape and shadow details, expressive reaction stickers, and a complete page border or notebook binding when appropriate. The page should look ready to share before any later edits.

Page concept:
[Page title, date, city/place, emotional theme, and chosen form: daily scrapbook / multi-day spread / mini-comic / hybrid scrapbook-comic.]

Visual route:
[Name the route and explain why it fits the user's materials. Keep this stable across related pages unless the user asks for a style change.]

Memory scenes:
[List 3-8 memory scenes with place, event, emotion, and source material. Preserve exact user facts.]

Layout:
[Describe title/date zone, anchor scene, supporting clusters, comic panels, photo/ticket/map/food slots, character positions, caption zones, and decorative sticker/tape/stamp areas.]

Editable object slots:
[Use object IDs as agent-facing planning anchors and revision targets. These IDs should guide composition but should NOT be rendered as visible labels in the final artwork unless the user requested an object-map preview.]
[List object IDs and roles, e.g. P1-IMG1 city park night photo, P1-TXT1 title "DAY 1 城市乐园夜游", P1-CHR1 traveler pair smiling, P1-PNL1 roller-coaster reaction panel.]

Character consistency:
[Use provided/local character references if available. Otherwise use public-safe generic traveler avatars. Specify identity, outfit family, pose, expression, and memory object interaction.]

Visual style:
[Write route-specific rendering language. Examples: East Asian sticker comic with light manga diary details; kawaii sticker journal with soft rounded icons; black-and-white cartoon doodle with thick marker lines, simple icons, and no grey wash; map infographic with numbered memory stops; polaroid photo collage with taped instant-photo frames; watercolor travel journal with soft washes; vintage ephemera scrapbook with aged paper and stamps; urban sketch journal with loose pen-and-wash architecture notes; minimalist line journal with sparse accents. Keep scrapbook cues such as white-border slots, tape, torn paper, notebook paper, stamp marks, handwritten labels, and legible composition.]

For sticker-comic and dense scrapbook routes, raise the completion level: large playful header lettering, ring-binder or notebook-page edge, lively but organized sticker clusters, speech bubbles, emotion badges, mini diary cards, decorative icons, and scene-specific motifs. Do not leave large empty placeholder areas unless the selected route is minimalist.

Text handling:
Use large readable handwritten Chinese for intentional text. Keep labels short. Exact text to render: [list exact titles, captions, labels, speech bubbles]. Avoid tiny paragraphs or garbled small text.

Negative constraints:
Do not make a route-first travel guide page unless explicitly requested. Do not invent bookings, place facts, or personal events. Do not change character identity. Do not cover important photos, tickets, captions, or object slots. Do not render internal object IDs in the final artwork. Do not make the page look like a wireframe, asset sheet, or editable template unless this is a planning preview. Do not use proprietary character likenesses unless provided by the user.
```

## Prompt Assembly Rules

- Put exact text in a separate list before or after the prompt when text correctness matters.
- Use object IDs in the page plan and in the prompt so later revisions can target them.
- Keep object IDs as hidden planning language in final-art prompts; explicitly say they should not be visible in the image.
- If the user wants staged control, write separate prompts for character stickers, scene panels, photo-slot backgrounds, text-card layouts, or decorative sticker sheets before the final page prompt.
- For generated model prompts, describe visual text as large labels and keep the precise text list outside the image when possible.
- For multi-day spreads, keep each day visually separated while sharing one style bible.
- For mini-comics, include panel count and panel purpose.
- For photo replacement workflows, ask the image model to leave clear, separate sticker slots.
- For style diversity, explicitly name the visual route; do not let every prompt drift back to colorful chibi manga or any single default style.
- For direct generation, spend more prompt budget on finished-page visual quality than on explaining the editability mechanism.
