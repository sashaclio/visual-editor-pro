# Visual Editor Pro

An open-source skill for professional photo post-production analysis and editorial-style visual direction.

`Visual Editor Pro` is designed for professional photographers, visual creators, image-workflow builders, and AI agent developers who want a reusable, maintainable workflow for moving from raw-image diagnosis to retouching recommendations and editorial-style art direction.

The project does not aim to produce generic social-media filters. Instead, it standardizes a more professional post-production workflow: first identify subject matter and technical issues in the original image, then generate actionable Lightroom and Capture One recommendations, and finally derive a restrained, magazine-style visual direction for downstream creative generation.

## Project Goals

- Provide a reusable open-source skill specification for photography post-production and AI visual workflows.
- Produce structured, actionable, reviewable retouching guidance instead of vague aesthetic commentary.
- Separate image diagnosis, parameter recommendation, and prompt construction into clear stages for evaluation and iteration.
- Create a foundation for future CLI tools, web interfaces, automated evaluation, prompt versioning, and multi-model support.

## Core Capabilities

### Phase 1 · Raw Image Diagnosis and Retouching Parameters

- Classify the image as landscape / architecture, street / documentary, or still life / product.
- Diagnose visible issues in exposure, highlight clipping, shadow loss, white balance, contrast, tonal separation, saturation, hue shifts, sharpness, noise, and visual balance.
- Output two post-production parameter sets:
  - Lightroom
  - Capture One
- Recommend one specific value per parameter so the output is directly usable.

### Phase 2 · Editorial-Style Image Direction

- Extract the subject, key light direction, atmosphere, color tendency, and composition logic from the source image.
- Route the image into a style direction based on category:
  - Landscape / architecture → large-format look, structured light
  - Street / documentary → filmic narrative tension, documentary texture
  - Still life / product → minimal lighting, material detail priority
- Build an internal English generation prompt for image extension or visual reinterpretation.
- Present a user-facing visual direction summary in clear language for photographers, retouchers, or creative directors.

## Use Cases

- Photography post-production guidance
- Standardized retouching workflows
- Prompt engineering for AI image systems
- Visual review and technical feedback
- Agent / skill design and evaluation
- Photography education and case breakdowns

## Repository Structure

```text
visual-editor-pro/
├── README.md
├── SKILL.md
├── LICENSE
├── APPLICATION_DRAFT.md
└── examples/
    └── example-output.md
```

## Design Principles

- All user-facing output should be concise, actionable, and reviewable.
- Professional terms such as Tone Curve, HSL, and Clarity should remain in English.
- Parameters should use one recommended value, not a range.
- Each sentence should provide usable analysis, not empty style language.
- If the image quality is insufficient, the skill should explicitly state what information is missing.
- Editorial references should align more with Vogue, System Magazine, and AnOther Magazine than influencer-style filters.

## Roadmap

- Add a consistent JSON schema for structured outputs.
- Add sample images and benchmark evaluation sets.
- Provide OpenAI, Claude, and Gemini-compatible versions.
- Ship a minimal CLI that takes an image path and returns diagnosis plus parameter recommendations.
- Add prompt regression testing and version comparison workflows.
- Explore a lightweight web demo for creative and educational use.

## Why Open Source

This project is suitable for open source because it is not a one-off prompt. It is a workflow specification that can be iterated, reviewed, extended, and integrated into broader image and creative tooling. An open repository makes it possible for contributors to improve output structure, parameter logic, style routing, benchmarks, and model compatibility over time.

## How to Use

1. Load `SKILL.md` as a system prompt or agent skill.
2. Provide a source image.
3. Generate the following outputs:
   - Original image diagnosis
   - Lightroom parameters
   - Capture One parameters
   - Visual direction
   - Generated image results when supported
4. Use the output for human retouching, workflow design, or prompt refinement.

## License

This project is released under the MIT License. See `LICENSE` for details.
