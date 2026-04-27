---
description: Synthesise an answer from the wiki.
argument-hint: the question to answer
---

Answer the question in `$ARGUMENTS` by synthesising from the wiki.

Workflow:

1. **Read `wiki/index.md` first** to get the catalog of available pages.

2. **Identify relevant pages.** From the index, pick the pages most likely to bear on the question. Read each in full. Follow `[[wiki-links]]` to neighboring pages when they look load-bearing — do not stop at the first hit.

3. **Synthesise an answer grounded in the wiki.**
   - Write in clear, concise prose with bullet points where they help (per the style guide in `CLAUDE.md`).
   - **Cite every claim by wiki page name**, e.g. `… as covered in [[transformers]].` If a claim is your own inference rather than something a wiki page supports, mark it explicitly: *"unsourced — Claude inference."*
   - **Flag disagreements.** If two wiki pages contradict each other, present both, attribute each, and call out the conflict rather than silently picking a side.
   - If the wiki does not contain enough information to answer, say so plainly. Do not fabricate.

4. **Propose, do not write, new connections.**
   - If synthesising the answer reveals a new link, missing concept page, or correction worth making, describe the proposed wiki update at the end of your response.
   - **Do not modify any wiki files** as part of this command. Wait for the user to confirm before making changes.
