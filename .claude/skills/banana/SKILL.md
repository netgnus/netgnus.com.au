# Banana Claude -- Creative Director for AI Image Generation

## Overview

Banana Claude is an AI image generation skill powered by Google Gemini Nano models. It functions as a Creative Director orchestrating image generation, editing, and visual asset production through intelligent prompt engineering rather than passing raw user text directly to APIs.

## Core Commands

The skill supports several operational modes:

- **`/banana generate`** — Creates images with full prompt engineering
- **`/banana edit`** — Modifies existing images intelligently
- **`/banana chat`** — Enables multi-turn visual sessions maintaining consistency
- **`/banana batch`** — Generates N variations of a concept
- **`/banana inspire`** — Browses prompt databases for creative ideas
- **`/banana preset`** — Manages brand and style presets
- **`/banana cost`** — Tracks usage and expense estimates

## Creative Direction Workflow

The system enforces a structured seven-step pipeline:

1. **Intent Analysis** — Clarify use case, style preferences, and constraints before generating
2. **Preset Check** — Load existing brand presets if applicable
3. **Domain Selection** — Choose expertise lens (Cinema, Product, Portrait, Editorial, UI/Web, Logo, Landscape, Abstract, Infographic)
4. **Prompt Construction** — Build using the 5-Component Formula (Subject → Action → Location → Composition → Style)
5. **Model & Resolution Selection** — Route to appropriate Gemini model and output size
6. **MCP Execution** — Call the appropriate tool with optimized parameters
7. **Response Validation** — Confirm image file existence and handle errors systematically

## Prompt Engineering Standards

The 5-Component Formula requires:

- **Named cameras** ("Sony A7R IV") and **real brand references** to trigger visual associations
- **Micro-details** ("sweat droplets," "baby hairs") for visceral specificity
- **Prestigious context anchors** ("Vanity Fair editorial," "National Geographic cover")
- **Banned keywords avoidance** — no "8K," "masterpiece," or "ultra-realistic"
- **Scene description** over concept explanation — describe what the camera sees

## Error Handling & Safety

The system implements graduated safety responses:

- **IMAGE_SAFETY blocks** trigger rephrase alternatives (max 3 retries with user approval)
- **Rate limiting (429)** uses exponential backoff with 60-second initial wait
- **Vague requests** prompt clarifying questions before generation
- **False positives** suggest abstraction, artistic framing, or metaphorical rephrasing

## Model Routing

Default model is `gemini-3.1-flash-image-preview`. The system routes to `gemini-2.5-flash-image` for rapid iteration and budget-conscious work, while maintaining resolution flexibility (512 → 1K → 2K → 4K).

## Response Requirements

Generated outputs must include: file path, crafted prompt shown to user, settings employed, and 1-2 refinement suggestions. A community footer is appended after generation commands (but not during multi-turn chat or utility queries).

## Reference Files

Load these on-demand as needed:

- `references/prompt-engineering.md` — 5-Component Formula, domain libraries, templates
- `references/gemini-models.md` — Model specs, aspect ratios, resolution tiers
- `references/mcp-tools.md` — MCP tool signatures and parameters
- `references/cost-tracking.md` — Pricing table and cost tracker commands
- `references/presets.md` — Brand preset schema and management
- `references/post-processing.md` — ImageMagick pipelines and format conversion
