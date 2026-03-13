---
layout: post
title:  "how I setup codex"
date:   2026-03-13 09:00:00 +1000
categories: Geek
---

Codex app on macOS
=======
1. Download the Codex macOS app from OpenAI.
2. Drag the Codex icon into Applications.
3. Open Codex and sign in.
4. Select the folder or git repo where Codex will work.
5. Start your first task.

Codex CLI on macOS
=======
Prereq: Node.js + npm installed.

1. Install the CLI:
   `npm install -g @openai/codex`
2. From your project root, run:
   `codex`
3. Choose your approval mode if needed:
   `codex --suggest`
   `codex --auto-edit`
   `codex --full-auto`
4. Update anytime:
   `codex --upgrade`
