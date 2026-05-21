---
name: nook-card
description: |
  Create reusable knowledge cards and optional card-to-video handoff specs from user topics, copy, and style references.
  Use when the user asks for knowledge cards, card images, social cards, cover cards, OpenDesign card generation, card style systems, or Remotion-ready card videos. Always confirm production intent, card count, card asset ratio, output layers, and motion needs before generating.
---

# nook-card

Use this skill to produce knowledge cards with a reusable style system. The skill is interactive: do not generate final visual assets until content hierarchy and output constraints are confirmed, unless the user explicitly says to decide directly.

## Read First

- Workflow: `references/workflow.md`
- Global production rules: `references/global-production-rules.md`
- Style registry: `references/style-registry.md`
- Interaction protocol: `references/interaction-protocol.md`
- Motion registry: `references/motion-registry.md`
- Default style: `references/styles/tactile-soft-skeuomorphic-card.md`
- OpenDesign adaptation notes: `references/opendesign-adapter.md`
- OpenDesign card contract: `references/opendesign-card-contract.md`
- Quality checklist: `references/checklist.md`
- Remotion handoff: `references/remotion-handoff.md`

Load only the references needed for the current task.

## Default Process

1. Identify production intent first: static-only, motion-ready assets, or static plus motion video.
2. Always ask for requirements first unless the current request already includes enough detail.
3. Ask in the two-dimension model: selected preset and concrete requirements.
4. For static cards, read the global production rules, style registry, and selected style reference.
5. Confirm both the video/stage canvas and the card asset ratio. Do not assume they are the same.
6. Confirm card count and split method before rendering if the content has steps, categories, chapters, or list structure.
7. If motion is possible, confirm `transparent_asset` output before generating final assets. Generate `preview_composite` separately for human review.
8. Prepare `card-spec.json` using `references/opendesign-card-contract.md` and the selected style tokens.
9. Render and quality-check the card assets.
10. If and only if video is requested, read the motion registry, confirm the selected motion preset, then prepare `remotion-handoff.json` and render the video.

## Defaults

- Default style: `tactile_soft_skeuomorphic_card`
- Default output: motion-ready transparent card asset plus preview composite when motion is possible; preview composite only when static-only is confirmed.
- Default video/stage canvas: landscape `1920 x 1080` / `16:9`.
- Card asset ratio is separate from video/stage canvas; in landscape videos, portrait or vertical cards may be better for multi-card layouts.
- Portrait stage `1080 x 1920` remains an explicit option at task start.
- Default motion preset: `pop_breathe`
- Default primary video delivery: MOV / ProRes 4444 / alpha
- Optional preview video: WebM / VP8 / alpha
- Default engine path: OpenDesign-compatible HTML/CSS preview plus structured JSON spec

## Do Not

- Do not treat one reference image as a fixed template.
- Do not skip content hierarchy confirmation when the user expects collaboration.
- Do not mix style tokens from different styles unless the user asks for a hybrid.
- Do not enter motion/video workflow if the user only asks for a static card.
- Do not ask motion questions before static cards are accepted, unless the user explicitly starts with a video request.
- Do not generate a Remotion video before the static card direction is approved.
- Do not generate final static assets before deciding whether they must be motion-ready and transparent.
- Do not bake a full-canvas decorative background into card assets that may be used for alpha video; put that background in `preview_composite` or the Remotion scene instead.
