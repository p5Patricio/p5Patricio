# Specification: Terminal Dashboard + AI Prompt Aesthetic

## 1. Requirements

### Functional Requirements
- FR1: The README must display a conversational flow: user prompt → AI response card → repeat
- FR2: Each section (about, stack, contact) must be visually contained within a terminal-style card
- FR3: A blinking cursor must appear at the bottom as an invitation to interact
- FR4: All existing content (profile data, stack, contact, devicons) must be preserved
- FR5: The profile must reflect "Software Engineer + AI learner" identity within 3 seconds

### Non-Functional Requirements
- NFR1: SVG files must be under 50KB each
- NFR2: README must render correctly on GitHub desktop and mobile
- NFR3: Animations must use SMIL (no CSS animations in SVG)
- NFR4: Total page weight should not exceed 500KB
- NFR5: Must support both light and dark GitHub themes (dark is primary)

---

## 2. SVG Specifications

### 2.1 `prompt-user.svg`
**Purpose**: User prompt line before each section
**ViewBox**: `0 0 1200 40`
**Dimensions**: `width="100%"`, height auto
**Colors**:
- Background: `#0d1117`
- Prompt text: `#39d0d8` (cyan)
- Comment text: `#8b949e`

**Structure**:
```
<rect width="1200" height="40" fill="#0d1117"/>
<text x="20" y="25" font-family="monospace" font-size="14" fill="#39d0d8" font-weight="600">> about --verbose</text>
<text x="220" y="25" font-family="monospace" font-size="11" fill="#8b949e">// 200 OK — response generated</text>
```

**Variants**: 3 instances with different text:
- `> about --verbose` → `// 200 OK — response generated`
- `> stack --list` → `// 15 modules found`
- `> contact --details` → `// 3 channels available`

---

### 2.2 `card-about.svg`
**Purpose**: Terminal card frame for the about section
**ViewBox**: `0 0 1200 320`
**Colors**:
- Background: `#0d1117`
- Border: `#21262d`
- Title bar: `#161b22`
- Title accent: `#39d0d8`
- Status dot: `#3fb950`

**Structure**:
- Outer border: `rect` with stroke `#21262d`, stroke-width `1.5`, rx `8`
- Title bar: `rect` at top, height `32`, fill `#161b22`, rx `8` (top corners only via path)
- Title text: `~/about.ts` at x="20" y="22", cyan
- Status: green dot + `ready` text at right side
- Content area: empty — the README code block goes below/inside this card visually

**Note**: The card is a FRAME. The actual TypeScript code block remains a GitHub-rendered markdown code block inside/after the card image.

---

### 2.3 `card-stack.svg`
**Purpose**: Terminal card frame for the stack section
**ViewBox**: `0 0 1200 400`
**Same styling as card-about.svg** but taller to accommodate devicons.
- Title: `~/stack.ts`
- Status: `15 modules`

---

### 2.4 `card-contact.svg`
**Purpose**: Terminal card frame for the contact section
**ViewBox**: `0 0 1200 200`
**Same styling**.
- Title: `~/contact.ts`
- Status: `3 channels`

---

### 2.5 `prompt-input.svg`
**Purpose**: Final input line with blinking cursor
**ViewBox**: `0 0 1200 48`
**Colors**:
- Background: `#0d1117`
- Input text: `#8b949e`
- Cursor: `#39d0d8`

**Structure**:
```
<rect width="1200" height="48" fill="#0d1117"/>
<text x="20" y="30" font-family="monospace" font-size="14" fill="#8b949e">> building with AI...</text>
<rect x="215" y="18" width="10" height="18" fill="#39d0d8">
  <animate attributeName="opacity" values="1;0;1" dur="1s" repeatCount="indefinite"/>
</rect>
```

---

### 2.6 `divider-terminal.svg`
**Purpose**: Single minimal divider between major sections
**ViewBox**: `0 0 1200 24`
**Colors**:
- Background: `#0d1117`
- Line: `#21262d`
- Accent: `#39d0d8` opacity 0.3

**Structure**:
```
<rect width="1200" height="24" fill="#0d1117"/>
<line x1="50" y1="12" x2="1150" y2="12" stroke="#21262d" stroke-width="1"/>
<text x="50%" y="16" text-anchor="middle" font-family="monospace" font-size="9" fill="#39d0d8" opacity="0.3">// ---</text>
```

---

## 3. README Structure

```markdown
<p align="center"><img src="header.svg" alt="" width="100%"/></p>

<p align="center"><img src="prompt-user.svg" alt="" width="100%"/></p>

<p align="center"><img src="card-about.svg" alt="" width="100%"/></p>

\`\`\`typescript
// ~/about.ts
// ─────────────────────────────────────────────────────────────────────

const profile = {
  name: "...",
  // ... rest of existing about content
}

export default profile
\`\`\`

<p align="center"><img src="divider-terminal.svg" alt="" width="100%"/></p>

<p align="center"><img src="prompt-user.svg" alt="" width="100%"/></p>

<p align="center"><img src="card-stack.svg" alt="" width="100%"/></p>

\`\`\`typescript
// ~/stack.ts
// ... existing stack content
\`\`\`

<p align="center"><img src="divider-terminal.svg" alt="" width="100%"/></p>

<p align="center"><img src="prompt-user.svg" alt="" width="100%"/></p>

<p align="center"><img src="card-contact.svg" alt="" width="100%"/></p>

\`\`\`typescript
// ~/contact.ts
// ... existing contact content
\`\`\`

<p align="center"><img src="divider-terminal.svg" alt="" width="100%"/></p>

<p align="center"><img src="prompt-input.svg" alt="" width="100%"/></p>

<p align="center"><img src="footer.svg" alt="" width="100%"/></p>
```

---

## 4. Asset Mapping

| File | Action | Purpose |
|------|--------|---------|
| `README.md` | Modify | Restructure with new narrative flow |
| `header.svg` | Keep | Terminal window bar |
| `footer.svg` | Keep | Status bar |
| `prompt-user.svg` | Create | User prompt lines |
| `card-about.svg` | Create | About section card frame |
| `card-stack.svg` | Create | Stack section card frame |
| `card-contact.svg` | Create | Contact section card frame |
| `prompt-input.svg` | Create | Blinking cursor input |
| `divider-terminal.svg` | Create | Single minimal divider |
| `divider-brackets.svg` | Remove | Replaced |
| `divider-circuit.svg` | Remove | Replaced |
| `divider-code.svg` | Remove | Replaced |
| `divider-hex.svg` | Remove | Replaced |
| `.github/workflows/snake.yml` | Keep | Snake animation |

---

## 5. Constraints

- GitHub strips CSS animations in SVGs — use SMIL `<animate>` only
- GitHub does not support external fonts — use `font-family="monospace"` (system fallback)
- Mobile: cards should use `width="100%"` to scale down
- Dark theme is primary; light theme is acceptable-fallback (GitHub handles most)
