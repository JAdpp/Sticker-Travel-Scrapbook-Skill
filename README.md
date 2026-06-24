![Sticker Travel Scrapbook banner](assets/brand/banner.jpg)

# Sticker Travel Scrapbook Skill

[English](README.md) | [简体中文](README.zh-CN.md) | [日本語](README.ja.md)

`sticker-travel-scrapbook` is a Codex Skill for creating, planning, revising, and interactively editing East Asian sticker-style travel scrapbook pages and mini-comic travel diaries.

It is built for memory-first visual authoring: personal scenes, moods, companions, meals, objects, ticket-like scraps, photo slots, stickers, maps, polaroids, line sketches, and small comic moments. It is not a route-first itinerary board or a clean travel photo book.

## Example Gallery

These are public-safe generated examples. They do not use private travel photos, commercial characters, brand mascots, real tickets, or private people. The same editable object workflow can support different visual routes, not only cute comic rendering.

<table>
  <tr>
    <td width="50%" valign="top">
      <strong>Cute comic sticker page</strong><br>
      <img src="assets/examples/kyoto-rainy-temple.jpg" alt="Kyoto rainy temple scrapbook example" width="100%">
    </td>
    <td width="50%" valign="top">
      <strong>Black-and-white line drawing</strong><br>
      <img src="assets/examples/ink-line-rainy-temple.jpg" alt="Black-and-white line drawing travel scrapbook example" width="100%">
    </td>
  </tr>
  <tr>
    <td width="50%" valign="top">
      <strong>Map-based information scrapbook</strong><br>
      <img src="assets/examples/map-infographic-coastal-train.jpg" alt="Map infographic travel scrapbook example" width="100%">
    </td>
    <td width="50%" valign="top">
      <strong>Polaroid photo collage</strong><br>
      <img src="assets/examples/polaroid-weekend-notes.jpg" alt="Polaroid photo collage travel scrapbook example" width="100%">
    </td>
  </tr>
</table>

Additional layout examples:

<table>
  <tr>
    <td width="50%" valign="top">
      <strong>Single page: Seoul hanok village and night market</strong><br>
      <img src="assets/examples/seoul-hanok-market.jpg" alt="Seoul hanok market scrapbook example" width="100%">
    </td>
    <td width="50%" valign="top">
      <strong>Two-page spread: Taiwan coastal train and lantern old street</strong><br>
      <img src="assets/examples/taiwan-coastal-train.jpg" alt="Taiwan coastal train scrapbook example" width="100%">
    </td>
  </tr>
</table>

## What The Skill Does

- Structures travel materials into scrapbook-ready memory scenes.
- Plans East Asian sticker-style layouts and mini-comic pages.
- Chooses among visual routes such as cute comic stickers, black-and-white line sketch, map infographic, and polaroid photo collage.
- Creates editable object manifests with stable IDs such as `P1-IMG1`, `P1-TXT1`, `P1-CHR1`, `P1-STK1`, and `P1-PNL1`.
- Maintains character and style consistency across pages.
- Generates copyable image prompts for new pages or targeted revisions.
- Supports localized revision prompts, such as replacing one image slot without redesigning the full page.
- Includes a local web GUI for project editing, prompt building, JSON import/export, and optional API-backed image generation.

## Repository Layout

```text
Sticker-Travel-Scrapbook/
  SKILL.md
  README.md
  README.zh-CN.md
  README.ja.md
  agents/
    openai.yaml
  scripts/
    server.py
  assets/
    brand/
      banner.jpg
    examples/
      ink-line-rainy-temple.jpg
      kyoto-rainy-temple.jpg
      map-infographic-coastal-train.jpg
      polaroid-weekend-notes.jpg
      seoul-hanok-market.jpg
      taiwan-coastal-train.jpg
    gui/
      index.html
      blank-project.json
      demo-project.json
  references/
    authoring-workflow.md
    memory-structure.md
    east-asian-visual-language.md
    comic-panel-patterns.md
    character-consistency.md
    editable-object-manifest.md
    prompt-template.md
    revision-protocol.md
    qa-checklist.md
    gui-workflow.md
    public-asset-policy.md
    default-config.yaml
    character-profile.example.yaml
```

## Installation

Copy this repository folder into a Codex skills directory and keep the folder name as `sticker-travel-scrapbook`.

On Windows, a user-level location is typically:

```powershell
C:\Users\<you>\.codex\skills\sticker-travel-scrapbook
```

If Codex does not detect the Skill immediately, restart Codex or start a new thread.

## Basic Usage In Codex

Explicitly invoke the Skill:

```text
Use $sticker-travel-scrapbook.
I want to create an East Asian sticker-style travel scrapbook / mini-comic page.

Trip content:
June 19, city park night visit, summer festival. Key memories include night lights, a small parade, a roller coaster, snacks, fireworks, and walking back through a lively crowd. The mood is excited, warm, and celebratory.

Please output:
1. A structured travel-memory table
2. Page format and layout suggestions
3. An editable object manifest using IDs such as P1-IMG1 / P1-TXT1 / P1-CHR1 / P1-PNL1
4. A selected visual route, style settings, and character settings
5. A copyable image-generation prompt
6. A localized revision instruction for replacing only the fireworks area later
```

Revision example:

```text
Use $sticker-travel-scrapbook.
I like the whole scrapbook page. Only replace P3-IMG2 with my uploaded real photo.
Keep the people, title, museum cards, captions, and overall layout unchanged.
Give me only a localized revision prompt.
```

## Local GUI

The Skill includes a lightweight local GUI. It starts from a blank project by default.

Launch it with:

```powershell
python "C:\Users\<you>\.codex\skills\sticker-travel-scrapbook\scripts\server.py" --project ".\sticker-travel-scrapbook-project.json"
```

Then open the printed local URL, usually:

```text
http://127.0.0.1:8765/
```

The GUI supports travel-brief editing, style-bible editing, material notes, page and object creation, editable object IDs, current-page image prompt generation, project JSON import/export, and a generated-image gallery when API generation is enabled.

## Optional GUI Image Generation

The GUI can call the OpenAI Images API if `OPENAI_API_KEY` is set in the server environment before launch:

```powershell
$env:OPENAI_API_KEY="sk-..."
python "C:\Users\<you>\.codex\skills\sticker-travel-scrapbook\scripts\server.py" --project ".\sticker-travel-scrapbook-project.json"
```

## Validation

Validate the Skill with the built-in skill creator validator:

```powershell
$env:PYTHONUTF8='1'
python "C:\Users\<you>\.codex\skills\.system\skill-creator\scripts\quick_validate.py" "C:\Users\<you>\.codex\skills\sticker-travel-scrapbook"
```

Expected output:

```text
Skill is valid!
```

## Current Boundary

This is a Skill plus local GUI prototype. The GUI can either build/export prompts for Codex or another image tool, or call the OpenAI Images API directly when `OPENAI_API_KEY` is configured.

