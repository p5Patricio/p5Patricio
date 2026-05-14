# Tasks: Terminal Dashboard + AI Prompt Aesthetic

## Task 1: Create divider-terminal.svg
- [ ] Simple minimal divider with line and comment
- ViewBox: 0 0 1200 24

## Task 2: Create prompt-user.svg (3 prompts)
- [ ] `> about --verbose` with `// 200 OK — response generated`
- [ ] `> stack --list` with `// 15 modules found`
- [ ] `> contact --details` with `// 3 channels available`
- ViewBox: 0 0 1200 40 each

## Task 3: Create card-about.svg
- [ ] Terminal card frame with title bar
- Title: `~/about.ts`, Status: `● ready`
- ViewBox: 0 0 1200 64 (just the frame, content below)

## Task 4: Create card-stack.svg
- [ ] Clone of card-about with title `~/stack.ts`, status `● 15 modules`
- ViewBox: 0 0 1200 64

## Task 5: Create card-contact.svg
- [ ] Clone of card-about with title `~/contact.ts`, status `● 3 channels`
- ViewBox: 0 0 1200 64

## Task 6: Create prompt-input.svg
- [ ] Input line with blinking cursor
- Text: `> building with AI...`
- SMIL blink animation on cursor rect
- ViewBox: 0 0 1200 48

## Task 7: Modify README.md
- [ ] Restructure with prompt → card → code block → divider flow
- [ ] Preserve all existing content (about, stack with devicons, contact)
- [ ] Add snake animation before footer

## Task 8: Remove old dividers
- [ ] Delete divider-brackets.svg
- [ ] Delete divider-circuit.svg
- [ ] Delete divider-code.svg
- [ ] Delete divider-hex.svg

## Task 9: Commit and push
- [ ] Stage all changes
- [ ] Commit with conventional commit message
- [ ] Push to origin/main
