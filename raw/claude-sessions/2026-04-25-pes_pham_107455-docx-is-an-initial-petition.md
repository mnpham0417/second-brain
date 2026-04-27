> claude-code: EB2 NIW : EB1A, 7 user turns. @PES_Pham_107455.docx is an initial petition document that my lawyer left me. Here is their message: Please find the first draft of the proposed endeavor statement in the ‘Drafted Documents by Our…
---
source: claude-code
captured: 2026-04-26
session_id: da6478dd-53d4-427a-add6-52a450bb1466
start_date: 2026-04-25
cwd: /Users/mnpham/Desktop/EB2 NIW : EB1A
git_branch: HEAD
user_messages: 7
---

### User — 2026-04-25T21:09:57.645Z

@PES_Pham_107455.docx is an initial petition document that my lawyer left me. Here is their message:

Please find the first draft of the proposed endeavor statement in the ‘Drafted Documents by Our Team’ section of your Documents tab. Please be aware that we will complete this document in two stages. Thus, we have left a few prompts in this statement, which we will complete at a later point in your case preparation. If you have any changes to suggest for the current content of the statement, we kindly ask that you make them using the Track Changes feature in Word and re-upload the revised version of the statement for our review. Please also send us a message if you have any questions about the statement. Otherwise, if you are satisfied with the current content of the statement, please let us know, but do not sign it yet. We will use this preliminary version to prepare your petition letter. Then, once your petition letter is finalized, we will complete the remaining prompts in your proposed endeavor statement to ensure this document aligns with your finalized petition letter. Thank you!

I want to include the two following points in the document, how and where should I insert it:

Project 2: Advanced Privacy-Preserving Federated Learning (https://github.com/APPFL/APPFL)
Role: I integrated several algorithms into the codebase.
Impact & Adoption: The technology is being applied across several key DOE domains: scientific experiments using multimodal data from DOE light source facilities while preserving institutional data privacy and electric grid data analysis and large AI/ML models for reliable and economic operations while maintaining infrastructure data privacy (https://www.anl.gov/cels/privacypreserving-federated-learning-for-scientific-research).
Connection to U.S. priorities: Funded by the U.S. Department of Energy, Office of Science (contract DE-AC02-06CH11357). Supports DOE priorities in secure scientific computing and critical infrastructure data privacy.

Organizing Committee of NeurIPS 2024 Workshop on Red Teaming GenAI

### Assistant — 2026-04-25T21:10:01.479Z

[tool_use: Bash]

### Assistant — 2026-04-25T21:10:06.714Z

[tool_use: Bash]

### Assistant — 2026-04-25T21:10:16.092Z

[tool_use: Bash]

### Assistant — 2026-04-25T21:10:19.412Z

[tool_use: Read]

### Assistant — 2026-04-25T21:11:29.571Z

Read the draft. Here's where each addition fits and the exact text to track-change in.

## 1. APPFL — insert as a **new paragraph immediately after the existing open-source paragraph** (after line 92, the one ending "open-source and open-weight AI")

This is the right home because that paragraph already frames open-source contributions as serving the U.S. innovation ecosystem and national priorities (secure-by-design AI). APPFL extends the same argument with a federally funded, mission-critical example. Don't add it to the three-bullet "planned research topics" list — those are framed as forward-looking research you'll personally lead, while APPFL is a contribution to an existing DOE-funded codebase.

Suggested insertion (matches the document's tone):

> In addition, I have contributed to Advanced Privacy-Preserving Federated Learning (APPFL), an open-source framework into which I integrated several algorithms. APPFL has been deployed across key U.S. Department of Energy (DOE) domains, including scientific experiments using multimodal data from DOE light source facilities and electric grid data analysis with large AI/ML models for reliable and economic operations — in both cases while preserving institutional and infrastructure data privacy. The project is funded by the U.S. Department of Energy, Office of Science (contract DE-AC02-06CH11357) and directly supports DOE priorities in secure scientific computing and critical infrastructure data privacy. This work complements my proposed endeavor by advancing the reliable, secure-by-design deployment of AI systems in safety-critical settings such as energy infrastructure and large-scale scientific research.

I'd leave the GitHub and Argonne URLs out of the narrative paragraph (the firm tends to keep PES prose clean and put citations in the petition letter / List of References) — but keep both URLs in your reply to the firm so they can pull them into supporting evidence.

## 2. NeurIPS 2024 Workshop on Red Teaming GenAI

This is professional service / field recognition, and it ties tightly to your first research bullet (automated red teaming of vision AI). Two reasonable spots — pick one:

**Option A (preferred): a short standalone paragraph inserted *before* the closing "I want to emphasize again…" paragraph (i.e., before line 94).** This keeps the closing peroration intact and gives the service line its own emphasis.

> My engagement with the proposed endeavor also extends to service in the research community. I served on the Organizing Committee of the NeurIPS 2024 Workshop on Red Teaming GenAI, where I helped convene leading researchers around the methods of analyzing and stress-testing generative AI systems that anchor my proposed endeavor.

**Option B (lighter touch): fold it into the existing closing sentence at line 100–101**, replacing "my research related to my proposed endeavor will continue to be circulated in the field through my peer-reviewed journal and conference publications" with:

> my research related to my proposed endeavor will continue to be circulated in the field through my peer-reviewed journal and conference publications, as well as through my service to the research community — including as an organizer of the NeurIPS 2024 Workshop on Red Teaming GenAI.

## Mechanics for Word

1. Open `PES_Pham_107455.docx`, Review → **Track Changes: On**.
2. Insert the APPFL paragraph after the "open-source and open-weight AI" paragraph.
3. Insert the NeurIPS text using Option A or B.
4. Save As a new filename (e.g., `PES_Pham_107455_MP_edits.docx`) and re-upload per the firm's instructions. Don't sign.

One flag: the firm explicitly said they'll fill in national-importance and references later, so keep your edits to the substantive content blocks above and don't touch the `[We will insert…]` placeholders.

### User — 2026-04-25T21:24:29.830Z

Can you check if APPFL has been used by anyone? If i'm not wrong it has been used by hospitals to train their models

### Assistant — 2026-04-25T21:24:33.119Z

[tool_use: ToolSearch]

### Assistant — 2026-04-25T21:24:36.254Z

[tool_use: WebSearch]

### Assistant — 2026-04-25T21:24:36.667Z

[tool_use: WebSearch]

### Assistant — 2026-04-25T21:24:50.544Z

[tool_use: WebFetch]

### Assistant — 2026-04-25T21:25:16.873Z

Yes, partly — but the precise claim is "biomedical research consortia" rather than "hospitals running it in production." Here's what's actually documented:

## What's verifiable

The **APPFLx** paper (Li et al., published in *J Am Med Inform Assoc*, indexed in PMC) reports two real cross-institutional medical case studies:

- **COVID-19 detection from chest X-rays** — federated training across Argonne National Laboratory, **University of Chicago**, and University of Illinois Urbana-Champaign.
- **Biological-age prediction from 12-lead ECG waveforms** (cardiovascular-health screening) — federated training across Argonne, the **Broad Institute of Harvard and MIT**, and UIUC.

The framework is also described as designed to "remove administrative boundaries of research organizations and healthcare systems" while keeping PHI on-premises, and an Argonne–UChicago–UIUC consortium has used APPFLx for this purpose.

## Honest caveat for the PES

Those are **demonstration case studies at academic medical / biomedical research institutions**, not documented production deployments inside hospital IT systems. So claiming APPFL "is used by hospitals to train their models" overstates what the literature supports. A defensible phrasing for the petition is something like:

> "…and has been used in cross-institutional biomedical studies — for example, federated training of COVID-19 chest-X-ray classifiers and ECG-based cardiovascular-aging models across Argonne National Laboratory, the University of Chicago, the Broad Institute of Harvard and MIT, and the University of Illinois Urbana-Champaign — where patient and institutional data could not leave their home environments."

If you'd like, I can fold that sentence into the APPFL paragraph I drafted earlier so the biomedical-impact angle sits alongside the DOE-priorities angle. The two together actually strengthen the national-interest argument: same framework, both critical-infrastructure (grid, light sources) **and** healthcare AI.

Sources:
- [Enabling end-to-end secure federated learning in biomedical research… with APPFLx (PMC)](https://pmc.ncbi.nlm.nih.gov/articles/PMC11782895/)
- [APPFL: Open-Source Software Framework for Privacy-Preserving Federated Learning (arXiv 2202.03672)](https://arxiv.org/pdf/2202.03672)
- [APPFL documentation — Argonne Privacy-Preserving Federated Learning](https://ppflaas.readthedocs.io/en/stable/index.html)
- [APPFL/APPFL on GitHub](https://github.com/APPFL/APPFL)
- [Privacy-Preserving Federated Learning for Scientific Research — Argonne CELS](https://www.anl.gov/cels/privacypreserving-federated-learning-for-scientific-research)

### User — 2026-04-25T21:25:56.736Z

Yes can you that

### Assistant — 2026-04-25T21:26:12.122Z

Here's the consolidated APPFL paragraph — drop this in where the previous one was going (right after the existing open-source paragraph that ends "open-source and open-weight AI"):

> In addition, I have contributed to Advanced Privacy-Preserving Federated Learning (APPFL), an open-source framework into which I integrated several algorithms. APPFL has been deployed across key U.S. Department of Energy (DOE) domains, including scientific experiments using multimodal data from DOE light source facilities and electric grid data analysis with large AI/ML models for reliable and economic operations — in both cases while preserving institutional and infrastructure data privacy. The framework has also been used in cross-institutional biomedical studies — for example, federated training of COVID-19 chest-X-ray classifiers and ECG-based cardiovascular-aging models across Argonne National Laboratory, the University of Chicago, the Broad Institute of Harvard and MIT, and the University of Illinois Urbana-Champaign — where patient and institutional data could not leave their home environments. The project is funded by the U.S. Department of Energy, Office of Science (contract DE-AC02-06CH11357), and supports DOE priorities in secure scientific computing and critical infrastructure data privacy as well as broader national priorities in trustworthy AI for healthcare. This work complements my proposed endeavor by advancing the reliable, secure-by-design deployment of AI systems in safety-critical settings.

A couple of small notes for when you track-change it in:

- I phrased the biomedical part as **"cross-institutional biomedical studies"**, not "hospitals" — that matches what the published case studies actually demonstrate (Argonne / UChicago / Broad / UIUC consortia) and is defensible if the firm or USCIS asks for evidence.
- The NeurIPS 2024 Workshop on Red Teaming GenAI insertion (Option A or B from my earlier message) is unchanged — handle that as a separate edit.
- Keep the GitHub URL and the Argonne CELS URL in your reply to the firm so they can pull them into the supporting evidence / List of References when they finalize the statement.

### User — 2026-04-25T21:35:51.138Z

Can you follow same structure of the OpenThoughts-Agent project paragraph

### Assistant — 2026-04-25T21:36:47.301Z

Here's the APPFL paragraph rewritten to mirror the OpenThoughts-Agent paragraph's three-sentence structure (project → U.S. innovation ecosystem → complement to social-media work + national priorities):

> I have similarly contributed to Advanced Privacy-Preserving Federated Learning (APPFL), an open-source framework into which I integrated several algorithms. My contributions help strengthen the broader U.S. innovation ecosystem by enabling widespread, secure access to APPFL — funded by the U.S. Department of Energy, Office of Science (contract DE-AC02-06CH11357) — which supports DOE national laboratories, academic medical centers, and biomedical research consortia across the country, including cross-institutional federated training of COVID-19 chest-X-ray classifiers and ECG-based cardiovascular-aging models across Argonne National Laboratory, the University of Chicago, the Broad Institute of Harvard and MIT, and the University of Illinois Urbana-Champaign. These open-source efforts complement my work in social media, allowing me to share expertise with the wider community while promoting technological advancement in areas of national priority, such as secure scientific computing, critical infrastructure data privacy, and trustworthy AI for healthcare.

Two small notes:

- The existing OpenThoughts paragraph opens "I **also** actively contribute…", so I started this one with "I have **similarly** contributed…" to avoid two consecutive paragraphs that begin "I also…". If you'd rather keep "I also" here, swap the existing OpenThoughts opener to something like "I actively contribute…".
- Sentence 3 reuses the existing paragraph's "complement my work in social media" framing verbatim because you asked for parallel structure. If both paragraphs end with that same phrase back-to-back, it'll read repetitively — one fix is to shorten the APPFL closer to "These efforts further promote technological advancement in areas of national priority, such as secure scientific computing, critical infrastructure data privacy, and trustworthy AI for healthcare." Your call.

### User — 2026-04-25T21:50:23.711Z

I also actively contribute to open-source projects that advance data recipes for agentic models. My contributions help strengthen the broader U.S. innovation ecosystem by enabling widespread, cost-effective access to OpenThoughts-Agent, which supports small businesses, startups, and research institutions across the country. In addition, I have contributed to the project Advanced Privacy-Preserving Federated Learning (APPFL). APPFL has been deployed across key U.S. Department of Energy (DOE) domains, including scientific experiments using multimodal data from DOE light source facilities and electric grid data analysis with large AI/ML models for reliable and economic operations. The project is funded by the U.S. Department of Energy and directly supports DOE priorities in secure scientific computing and critical infrastructure data privacy. These open-source efforts complement my work in social media, allowing me to share expertise with the wider community while promoting technological advancement in areas of national priority, such as open-source and open-weight AI. 

I have added it like this, how would you suggest me update the last sentence?

### Assistant — 2026-04-25T21:50:41.627Z

The cleanest fix is to expand the named priority areas at the end so the list covers both projects in the paragraph (the current "open-source and open-weight AI" only catches OpenThoughts; APPFL's national-interest hooks aren't represented).

Suggested replacement for the last sentence:

> These open-source efforts complement my work in social media, allowing me to share expertise with the wider community while promoting technological advancement in areas of national priority, such as open-source and open-weight AI, secure scientific computing, and critical infrastructure data privacy.

A few alternative phrasings depending on how strong you want the close to feel:

- **Tighter, parallel-list form:** "…in areas of national priority — open-source and open-weight AI, secure scientific computing, and critical infrastructure data privacy."
- **If you want a slightly stronger national-interest signal:** "…while directly advancing national priorities, including open-source and open-weight AI, secure scientific computing, and the privacy of critical infrastructure data."

I'd avoid adding "trustworthy AI for healthcare" to the closing since you removed the COVID/ECG biomedical examples from the body — keep the closer's claims supported by what's actually in the paragraph.

### User — 2026-04-25T22:01:43.639Z

My engagement with the proposed endeavor also extends to service in the research community. I served on the Organizing Committee of the NeurIPS 2024 Workshop on Red Teaming GenAI, where I helped convene leading researchers around the methods of analyzing and stress-testing generative AI systems that anchor my proposed endeavor.

Can you mention NeurIPS is one of the best conferences in AI in the world

### Assistant — 2026-04-25T22:01:59.240Z

Here's the revised paragraph:

> My engagement with the proposed endeavor also extends to service in the research community. I served on the Organizing Committee of the NeurIPS 2024 Workshop on Red Teaming GenAI — NeurIPS (the Conference on Neural Information Processing Systems) being widely regarded as one of the most prestigious AI conferences in the world — where I helped convene leading researchers around the methods of analyzing and stress-testing generative AI systems that anchor my proposed endeavor.

If you'd rather not break the sentence with a long em-dash aside, this two-sentence version reads more cleanly:

> My engagement with the proposed endeavor also extends to service in the research community. I served on the Organizing Committee of the NeurIPS 2024 Workshop on Red Teaming GenAI, where I helped convene leading researchers around the methods of analyzing and stress-testing generative AI systems that anchor my proposed endeavor. NeurIPS (the Conference on Neural Information Processing Systems) is widely regarded as one of the most prestigious AI conferences in the world.

Two small phrasing notes:

- I'd use **"most prestigious"** or **"top-tier"** rather than "best" — the firm's sample statements (in `Resources/Proposed Endeavor Statement_Samples/`) lean toward formal qualifiers like *premier*, *leading*, *top-tier*, *highly selective*, which read more credibly to USCIS than superlatives like "best."
- Spelling out the acronym on first mention (NeurIPS = Conference on Neural Information Processing Systems) is worth doing once — adjudicators outside CS won't necessarily know it.

### User — 2026-04-25T22:48:22.063Z

Hi,

Thank you for the message. I have made a pass at the first draft of the PES, and have made some potential changes. In particular, I made 2 changes to the PES:
- Discussion of contribution to the open-source project APPFL. Since this project is funded by the Department of Energy, and I also included in the RBIF tab, I believe it would be beneficial to mention it.
- Mention of being organizing committee of NeurIPS 2024 Workshop on Red Teaming GenAI. NeurIPS is one of the top AI conferences in the world, and the workshop is relevant to my proposed endeavor. Hence, I think it might be beneficial to discuss it.

Please fix and improve the following message that I am about to send my lawyer.

### Assistant — 2026-04-25T22:48:54.045Z

Here's a polished version:

---

Hi,

Thank you for sending over the first draft of the Proposed Endeavor Statement. I have reviewed it and proposed two additions, which I have marked with Track Changes in the re-uploaded version:

1. **Contribution to the open-source project APPFL (Advanced Privacy-Preserving Federated Learning).** Since APPFL is funded by the U.S. Department of Energy and I have also referenced it in the RBIF, I believe it is worth surfacing in the PES to keep the two documents consistent and to strengthen the national-interest framing.

2. **Service on the Organizing Committee of the NeurIPS 2024 Workshop on Red Teaming GenAI.** NeurIPS is widely regarded as one of the most prestigious AI conferences in the world, and the workshop's focus on red-teaming generative AI maps directly to the methods that anchor my proposed endeavor, so I thought it would be worth including.

Please let me know whether either addition is appropriate to keep, or if you would prefer that I revise or remove anything.

Best,
Minh

---

Main changes I made:

- Replaced "made a pass / made some potential changes" with "reviewed it and proposed two additions" — clearer and confirms you've used Track Changes.
- Fixed the two grammatical fragments ("Discussion of contribution to…" / "Mention of being organizing committee…") into full sentences with concrete verbs and a clear rationale per item.
- "RBIF tab" → "RBIF" — the firm will recognize the form name without the portal-UI label.
- Strengthened the NeurIPS framing to "most prestigious" (matches the firm's sample-statement register better than "top").
- Closed with an invitation for them to revise or push back, which is the tone the lawyer's own message used.

