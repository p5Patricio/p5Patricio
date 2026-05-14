# Design: Terminal Dashboard + AI Prompt Aesthetic

## 1. Architecture

The profile is composed as a vertical stack of visual layers:

```
Layer 0: header.svg           — Window chrome (terminal frame)
Layer 1: prompt-user.svg      — User query (cyan, actionable)
Layer 2: card-*.svg           — AI response container (card frame)
Layer 3: markdown code block  — Actual content (syntax highlighted by GitHub)
Layer 4: divider-terminal.svg — Section separator
Layer 5: prompt-input.svg     — Open invitation (blinking cursor)
Layer 6: footer.svg           — Status bar (editor footer)
```

Each "conversation turn" consists of Layer 1 + Layer 2 + Layer 3. The divider (Layer 4) separates turns.

---

## 2. Visual System

### 2.1 Color Tokens

| Token | Hex | Usage |
|-------|-----|-------|
| `--bg-primary` | `#0d1117` | Page background, card backgrounds |
| `--bg-secondary` | `#161b22` | Title bars, elevated surfaces |
| `--border` | `#21262d` | Card borders, dividers |
| `--text-primary` | `#c9d1d9` | Main code content |
| `--text-secondary` | `#8b949e` | Comments, metadata |
| `--accent-cyan` | `#39d0d8` | User prompts, active elements |
| `--accent-blue` | `#58a6ff` | Secondary highlights |
| `--accent-purple` | `#a371f7` | Tertiary accents |
| `--accent-green` | `#3fb950` | Status indicators (ready, success) |

### 2.2 Typography

| Element | Font | Size | Weight | Color |
|---------|------|------|--------|-------|
| Prompt prefix (`>`) | monospace | 14px | 600 | `--accent-cyan` |
| Prompt text | monospace | 14px | 400 | `--accent-cyan` |
| Prompt comment | monospace | 11px | 400 | `--text-secondary` |
| Card title | monospace | 12px | 600 | `--accent-cyan` |
| Card status | monospace | 10px | 400 | `--text-secondary` |
| Divider text | monospace | 9px | 400 | `--accent-cyan` opacity 0.3 |
| Input text | monospace | 14px | 400 | `--text-secondary` |

### 2.3 Spacing

- Vertical rhythm: 16px between prompt and card, 8px between card and code block
- Card internal padding: 16px top (below title bar), 16px sides
- Divider height: 24px (compact separator)
- Prompt height: 40px
- Input height: 48px

### 2.4 Card Border Pattern

Cards use subtle rectangular borders, not literal ASCII art (cleaner rendering):
- `rect` with `stroke="#21262d"`, `stroke-width="1.5"`, `rx="8"`
- Title bar: `rect` with `fill="#161b22"`, height 32px
- No literal `┌─┐` characters — too fragile across renderers

---

## 3. Component Design

### 3.1 prompt-user.svg

**Layout**:
```
┌────────────────────────────────────────┐
│ > about --verbose   // 200 OK          │
└────────────────────────────────────────┘
```

- Full-width background `#0d1117`
- Left-aligned at x=20
- Comment right-aligned or following with gap
- Height: 40px

### 3.2 card-*.svg

**Layout**:
```
┌─ ~/about.ts ──────────────── ● ready ─┐
│                                       │
│         (content goes below)          │
│                                       │
└───────────────────────────────────────┘
```

- Outer border: 1.5px `#21262d`, rounded corners rx=8
- Title bar: 32px height, `#161b22`, top corners rounded
- Title text: left side, cyan
- Status: green dot + text, right side
- Content area: transparent — code block rendered by GitHub below

**Responsive behavior**: `width="100%"` scales to container. Height is fixed per card.

### 3.3 prompt-input.svg

**Layout**:
```
┌────────────────────────────────────────┐
│ > building with AI... █                │
└────────────────────────────────────────┘
```

- Full-width background
- Input text left-aligned
- Blinking cursor rectangle after text
- SMIL animation: opacity 1→0→1, duration 1s

---

## 4. Animation Strategy

| Element | Animation | Type | Timing |
|---------|-----------|------|--------|
| Input cursor | Blink | SMIL opacity | 1s loop |

**No other animations** on cards or prompts. The existing snake animation in the workflow is the only other motion. This keeps the profile clean, fast, and professional.

---

## 5. File Organization

```
p5Patricio/
├── README.md                          # Restructured profile
├── header.svg                         # Terminal window bar (existing)
├── footer.svg                         # Status bar (existing)
├── prompt-user.svg                    # User prompts (new)
├── card-about.svg                     # About card frame (new)
├── card-stack.svg                     # Stack card frame (new)
├── card-contact.svg                   # Contact card frame (new)
├── prompt-input.svg                   # Blinking cursor (new)
├── divider-terminal.svg               # Minimal divider (new)
├── divider-brackets.svg               # REMOVED
├── divider-circuit.svg                # REMOVED
├── divider-code.svg                   # REMOVED
├── divider-hex.svg                    # REMOVED
└── .github/workflows/snake.yml        # Kept
```

---

## 6. Implementation Order

1. **Create divider-terminal.svg** — Simplest, establishes visual baseline
2. **Create prompt-user.svg** — Three variants, establishes prompt style
3. **Create card-about.svg** — Template for all cards
4. **Create card-stack.svg** — Clone of about with different title/status
5. **Create card-contact.svg** — Clone of about with different title/status
6. **Create prompt-input.svg** — Blinking cursor
7. **Modify README.md** — Wire everything together
8. **Remove old dividers** — Clean up
9. **Test render** — Push and verify on GitHub
