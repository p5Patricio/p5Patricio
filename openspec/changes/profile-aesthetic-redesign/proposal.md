# Proposal: Terminal Dashboard + AI Prompt Hybrid Profile Redesign

## Intent

Transform the GitHub profile README into a cohesive "AI-assisted terminal dashboard" visual identity. Merge the structural clarity of ASCII-bordered terminal cards (Option B) with the narrative rhythm of an AI prompt conversation (Option C). The result should feel like an engineer interacting with their own AI pair-programming interface — reflecting both "Software Engineer" and "AI learner" identities without appearing flat or text-crowded.

## Scope

### In Scope
- Restructure `README.md` into a prompt->response narrative flow
- Design new SVG assets: `prompt-input.svg` (user query), `response-card.svg` (terminal card frame), `ascii-divider.svg` (minimal section break)
- Replace the four existing animated divider SVGs with 1-2 simpler dividers that match the terminal aesthetic
- Update content padding and spacing to solve the "flat/crowded" text problem
- Preserve `header.svg`, `footer.svg`, snake workflow, and DevIcon stack row

### Out of Scope
- Changes to `.github/workflows/snake.yml`
- Modifications to contact information or stack content
- Dark/light mode toggle logic

## Capabilities

### New Capabilities
- `ai-prompt-narrative`: User prompts as visual inputs, profile sections as AI terminal responses
- `terminal-card-system`: SVG-rendered ASCII-bordered cards for content blocks with internal padding
- `minimal-divider-grammar`: Reduced, cohesive divider set replacing four distinct animated styles

### Modified Capabilities
- None

## Approach

1. **Narrative Structure**: Each profile section begins with a `prompt-input.svg` (user message styling: `>` prefix, muted color). The content follows inside a `response-card.svg` — an SVG terminal window with `┌─┐│└─┘` borders and padded interior, rendered at `width="100%"`.
2. **New SVGs**:
   - `prompt-input.svg`: Monospace prompt symbol with section title (e.g., `> describe --profile`)
   - `response-card.svg`: Reusable terminal frame with top border, content area, and bottom border — internally padded so text never touches edges
   - `ascii-divider.svg`: Static `─` line or minimal bracket pair for breathing room between major sections
3. **Solving Flat/Crowded Text**: Replace raw code blocks with SVG cards that have internal padding (16-24px). Add vertical whitespace between prompt->response pairs. The narrative frame breaks monotony by making the reader alternate between "user" and "AI" visual modes.
4. **Identity Reflection**: The meta-narrative (an engineer querying an AI about themselves) reinforces the "AI learner" role. TypeScript syntax highlighting inside cards preserves the "Software Engineer" core.

## Affected Areas

| Area | Impact | Description |
|------|--------|-------------|
| `README.md` | Modified | Restructured into prompt->response pairs; reduced raw code blocks |
| `divider-*.svg` (×4) | Removed | Replaced by simpler `ascii-divider.svg` |
| `prompt-input.svg` | New | SVG user prompt labels per section |
| `response-card.svg` | New | Reusable terminal card frame for content |
| `ascii-divider.svg` | New | Minimal section separator |
| `header.svg` | Kept | Already matches terminal metaphor |
| `footer.svg` | Kept | Already matches terminal metaphor |

## Risks

| Risk | Likelihood | Mitigation |
|------|------------|------------|
| SVG card text scaling on mobile | Med | Use `viewBox` + relative widths; test GitHub mobile render |
| README becomes too tall vertically | Low | Compress prompt inputs; keep responses concise |
| Loss of animated divider visual interest | Low | Subtle CSS/SVG opacity animation on `ascii-divider.svg` if needed |

## Rollback Plan

Revert `README.md` to the previous commit (pre-redesign). All new SVGs are additive and can be deleted without breaking the old layout. `header.svg` and `footer.svg` remain untouched.

## Dependencies

- None (static Markdown/SVG repo)

## Success Criteria

- [ ] README renders as a clear prompt->response narrative on desktop and mobile
- [ ] No text touches SVG borders; padding is consistent
- [ ] Header, footer, and snake animation remain functional
- [ ] Overall word count and information density are preserved or reduced
- [ ] Visual identity feels cohesive (terminal + AI, not two competing styles)
