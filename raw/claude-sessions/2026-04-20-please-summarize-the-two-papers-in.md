> claude-code: Paper Review, 23 user turns. Please summarize the two papers in this directory and create an md file called "claude_summary.md" with the summary.
---
source: claude-code
captured: 2026-04-26
session_id: 9615bd3d-2375-42dc-b564-42eb212a2ab6
start_date: 2026-04-20
cwd: /Users/mnpham/src/Paper Review
git_branch: HEAD
user_messages: 23
---

### User — 2026-04-20T17:29:09.124Z

Please summarize the two papers in this directory and create an md file called "claude_summary.md" with the summary.

### Assistant — 2026-04-20T17:29:11.713Z

[tool_use: Bash]

### Assistant — 2026-04-20T17:29:15.835Z

[tool_use: Read]

### Assistant — 2026-04-20T17:29:17.781Z

[tool_use: Read]

### Assistant — 2026-04-20T17:29:23.382Z

[tool_use: Read]

### Assistant — 2026-04-20T17:29:29.333Z

[tool_use: Read]

### Assistant — 2026-04-20T17:29:36.702Z

Now let me read the second paper.

### Assistant — 2026-04-20T17:29:38.110Z

[tool_use: Read]

### Assistant — 2026-04-20T17:29:44.672Z

[tool_use: Read]

### Assistant — 2026-04-20T17:29:54.360Z

[tool_use: Read]

### Assistant — 2026-04-20T17:30:01.697Z

Now I have enough information to write the summary. Let me create the file.

### Assistant — 2026-04-20T17:30:46.794Z

[tool_use: Write]

### Assistant — 2026-04-20T17:45:36.281Z

Created `claude_summary.md` with summaries of both papers:

- **OBLIVIATE (#8021)**: Concept erasure for autoregressive T2I models (LIQUID, Emu3-Gen, Janus-Pro) via aligned visual prefixes, trajectory-level KL supervision, and pseudo-unconditional branching. Reduces nudity on RAB from 91.58 → 3.15.
- **LULU (#8732)**: Training-free, feature-level concept erasure for SD v1.4 via mid-block activation classification + injection from a guided "safe" concept. Best EA/RA trade-off on EMMA.

The file also includes strengths, weaknesses, and a comparison table showing they target different architectures (AR vs. diffusion) and different mechanisms (LoRA fine-tuning vs. inference-time injection).

### User — 2026-04-20T17:46:39.284Z

Now using the template from @review_template.md , please         
   write the reviews for both papers and create an md file          
   called "claude_review.md" with the reviews

### Assistant — 2026-04-20T17:48:11.335Z

[tool_use: Write]

### Assistant — 2026-04-20T18:15:43.097Z

Created `claude_review.md` with full reviews for both papers following the template structure.

**Summary of recommendations:**
- **Paper #8021 (OBLIVIATE):** 5 — Weak Accept. Novel contribution filling a real AR concept-erasure gap with strong adversarial benchmark results, but evaluation breadth (no adaptive adversary, no multi-concept, limited sensitivity analysis) keeps it from stronger acceptance.
- **Paper #8732 (LULU):** 3 — Borderline Reject. The feature-space detection idea is genuinely novel and addresses the implicit-prompt failure mode of prior work, but evaluation is limited to SD v1.4 + COCO objects, skipping the safety-critical domains (NSFW/style/identity) that motivate the research area. Detector robustness, inference cost, and cross-model claims are unsupported.

Each review includes specific rebuttal questions the authors could address to strengthen their submissions.

### User — 2026-04-20T18:16:07.616Z

Please cross reference with reviews made by another model @gemini_review.md

### Assistant — 2026-04-20T18:16:30.689Z

## Cross-Reference: Claude vs. Gemini Reviews

### Paper #8021 (OBLIVIATE)

**Agreement (both reviewers):**
- Same recommendation: **5 — Weak Accept**
- Both praise the timeliness of AR concept erasure, the motivated design choices, and strong RAB results
- Both flag **multi-concept erasure** as untested
- Both flag **hyperparameter sensitivity** (η tuning across models) as a concern

**Claude emphasized (Gemini missed):**
- No adaptive adversarial evaluation — relies only on pre-existing benchmarks
- Teacher-dependency: method hinges on the teacher actually generating the concept
- LoRA rank not ablated
- Inconsistent loss notation; curation of 500 unbranding prompts undocumented

**Gemini emphasized (Claude missed/underweighted):**
- **Computational overhead of full-trajectory training** — memory/time cost vs. token-wise updates. This is a legitimate gap in my review; I should have flagged it.
- Granular analysis of impact on semantically proximate safe concepts

**Verdict:** Strong convergence on recommendation and core weaknesses. Gemini caught the compute-overhead angle I missed; I was more adversarial/robustness-focused.

---

### Paper #8732 (LULU)

**Disagreement on recommendation:**
- **Claude: 3 (Borderline Reject)** — cited narrow evaluation scope (only SD v1.4, only COCO objects, no NSFW/style/identity)
- **Gemini: 5 (Weak Accept)** — weighted methodological novelty more heavily than evaluation breadth

**Agreement:**
- Both praise the feature-space insight, weight-preservation, and coherent substitution
- Both flag the **guided/safe concept selection** heuristic as a major concern
- Both flag cross-architecture generalization as asserted-but-unsupported

**Claude emphasized (Gemini missed):**
- The mismatch between safety framing and benign-object evaluation (no NSFW/style/identity) — this is the main reason for my lower score
- Detector trained only on SD v1.4 synthetic images; no real-image or cross-checkpoint evaluation
- Adversarial prompt evasion of the detector untested
- LLM-generated training prompts (Claude Sonnet) potentially biasing the detector

**Gemini emphasized (Claude underweighted):**
- **Classifier-per-concept scalability** at inference when monitoring many concepts. Valid practical concern I didn't raise explicitly.
- False positive rate on safe concepts

**Verdict:** The two-point gap is real. Gemini graded on methodological contribution; I graded on whether the evaluation supports the safety claims. Both positions are defensible — a reviewer discussion would likely center on whether "novel mechanism on narrow benchmark" clears the acceptance bar for a safety-motivated paper.

---

### Summary
We align closely on OBLIVIATE. On LULU we diverge because I penalized evaluation scope relative to the paper's safety framing, while Gemini rewarded the novel mechanism. Both reviews surface complementary weaknesses — Gemini is stronger on practical/compute concerns; mine is stronger on adversarial robustness and evaluation-claim mismatch.

### User — 2026-04-20T18:30:12.849Z

Let's create an md file with the cross reference

### Assistant — 2026-04-20T18:31:04.372Z

[tool_use: Write]

### Assistant — 2026-04-20T18:31:11.733Z

Created `claude_cross_reference.md` with the full cross-reference analysis.

**Key takeaways captured:**
- **OBLIVIATE:** Both reviewers gave 5 (Weak Accept). Gemini caught the compute-overhead gap I missed; I caught adversarial/ablation gaps Gemini missed.
- **LULU:** Two-point disagreement (Claude: 3, Gemini: 5). Principled, not accidental — Gemini weighted novelty; I weighted evaluation-scope vs. safety framing. Each reviewer surfaced non-overlapping weaknesses (Claude: detector robustness & evaluation breadth; Gemini: inference scalability & false positives).
- **Meta-point:** A composite review from both would be stronger than either alone, especially for LULU where the disagreement exposes a real axis of judgment about novelty vs. evaluation support.

### User — 2026-04-21T01:05:36.654Z

I have added the supplementary materials of Obliviate in @ECCV_26_Obliviate_Supplemental_Material/ . Would you like to update your review?

### Assistant — 2026-04-21T01:05:47.986Z

Yes, let me review the supplementary materials before deciding whether to update.

### Assistant — 2026-04-21T01:05:48.769Z

[tool_use: Bash]

### Assistant — 2026-04-21T01:05:56.568Z

[tool_use: Bash]

### Assistant — 2026-04-21T01:06:01.372Z

[tool_use: Read]

### Assistant — 2026-04-21T01:06:14.413Z

[tool_use: Read]

### Assistant — 2026-04-21T01:06:25.682Z

[tool_use: Read]

### Assistant — 2026-04-21T01:07:01.515Z

The appendix and code release address several concerns from my original review. Let me create an updated review.

### Assistant — 2026-04-21T01:08:07.025Z

[tool_use: Write]

### Assistant — 2026-04-21T01:08:29.476Z

Created `claude_review_updated.md` with the revised assessment.

**Key changes after reviewing the supplementary materials:**

- **Recommendation unchanged: 5 (Weak Accept)** — but with higher confidence.
- **Major concerns addressed:** Cross-evaluator robustness via Section A8 (Gemini 3 Flash + per-VLM breakdown) directly speaks to my "no adaptive adversary" concern. Hyperparameter transparency (Table A1) and prompt artifacts (A6/A7) are now reproducible. Code is released.
- **Major concerns still open:** No multi-concept erasure, no true adaptive adversarial prompt attack, teacher-reliability untested, LoRA rank still not ablated, Janus-Pro's 10× larger η is documented but not explained.
- **Net assessment:** The appendix demonstrably strengthens the paper, especially on evaluator robustness (which I'd weighted heavily), but the two breadth-of-evaluation gaps that anchored my original score remain. A rebuttal with even a small multi-concept or adaptive-adversary experiment would likely move me to Accept.

The LULU review and the Gemini cross-reference remain unchanged since no new materials were provided for that paper.

### User — 2026-04-21T01:09:18.551Z

Please use humanizer skill to humanize @claude_review_updated.md

### Assistant — 2026-04-21T01:09:27.692Z

[tool_use: Skill]

### Assistant — 2026-04-21T01:10:28.039Z

I'll read the current file and produce a humanized rewrite.

### Assistant — 2026-04-21T01:10:28.286Z

[tool_use: Read]

### Assistant — 2026-04-21T01:11:47.154Z

## Draft rewrite

```markdown
# Updated Review: Paper #8021 (OBLIVIATE) — After Supplementary Materials

I went back through Paper #8021 after the supplementary materials landed (the appendix PDF and the anonymized code at `obliviate-code-anonymized/`). My LULU review is untouched since nothing new came in for that paper.

---

## Title
OBLIVIATE: Erasing Concepts from Autoregressive Image Generation Models

## Paper Summary
*(Same as the original review in `claude_review.md`.)*

OBLIVIATE is a guidance-based concept erasure method for autoregressive T2I models (LIQUID, Emu3-Gen, Janus-Pro). The authors diagnose two ways naive ports of diffusion-based ESD fall over (distribution divergence and unstable single-token supervision) and propose three fixes: aligned visual prefixes that form a pseudo-unconditional branch, trajectory-level supervision over full rollouts, and KL-divergence distribution matching on visual logits. They evaluate on three AR backbones across explicit content, gory content, and unbranding, and report strong erasure on adversarial benchmarks (RAB drops from 91.58 to 3.15 on LIQUID) without obvious utility damage.

## What the Supplementary Materials Add

The appendix is 11 pages of real content, not filler, and the authors released anonymized code. The pieces I found useful:

1. **Section A1, Fig. A1.** A conceptual figure that contrasts single-timestep vs. trajectory-based erasure across both diffusion and AR. Honestly, this clarifies the intuition better than the main paper does.
2. **Section A2 + Table A1.** Full hyperparameter dump: LR, total steps, and η for all 9 model × concept combinations. This is where you can see Janus-Pro is a different beast: η in the 10–12 range and lr=2e-3, vs. η=1–2 and lr=1e-4 for LIQUID and Emu3-Gen.
3. **Section A3.** A careful SLD* derivation. They explain why warm-up and momentum don't transfer (temporal vs. spatial generation dynamics) and why the hyperparameter scales need to change (logit space vs. noise space). This is the kind of work that's easy to skip and they didn't.
4. **Section A4 + Fig. A2.** Explanation for EAR's FID=31.63 spike on Janus-Pro. The MJHQ samples make it visually clear: EAR pushes outputs toward low-structure, semantically off-target generations.
5. **Fig. A3.** Janus-Pro qualitative samples in the same grid format as Fig. 4.
6. **Sections A6, A7.** Exact `c_simple` / `c_comprehensive` prompts from the Table 3b ablation, plus 10 examples from the augmented unbranding set.
7. **Section A8 + Table A2.** Cross-evaluator robustness check for Coca-Cola erasure. They run each open-source VLM on its own (LLaVA, Qwen2.5-VL, Phi-3.5-Vision) instead of just reporting the ensemble, and they add Google Gemini 3 Flash as a proprietary evaluator. OBLIVIATE wins under every single one. This is the addition I cared about most.
8. **Section A9 + the code.** Modular training pipeline, YAML configs (`configs/unlearning/baseline_nudity.yaml` is the reference template), and `train_unlearning.py` exposes every hyperparameter. LoRA defaults (rank=32, α=16, dropout=0.05) are visible in the code rather than buried.

## How This Changes My Assessment

### Things they addressed

- **Cross-evaluator robustness.** Section A8 is a real response to my "no adaptive adversarial evaluation" complaint. It's not the same thing as a true red-team with prompts crafted against the edited model, but evaluator gaming is one of the obvious Goodhart failure modes for this kind of work, and the paper now shows the CDR drop holds across every individual open-source VLM and a proprietary one (Gemini 3 Flash) the method couldn't have been tuned against. That's a meaningful safety check.
- **Hyperparameter transparency (Table A1).** Now fully on the page. My original complaint about per-model η tuning is confirmed — Janus-Pro really does need η=10–12 while the others sit at η=1–2 — but at least readers can see it.
- **The 500 unbranding prompts.** Section A7 describes the curation (human-written templates with LLM-generated variations) and lists 10 examples. Fine.
- **Simple vs. comprehensive prompts.** Listed in Section A6. No principled rule for picking between them, but the artifact is reproducible now.
- **Code release.** Resolves the implicit "is this actually reproducible" question.

### Things still open

- **No real adaptive adversarial evaluation.** Cross-evaluator is good, but it doesn't substitute for an attacker who knows what was erased and crafts prompts accordingly. A Ring-A-Bell rerun against the edited checkpoint would be the obvious experiment.
- **Single-concept only.** Every scenario erases one thing at a time. We still don't know what happens when you stack erasures.
- **No LoRA ablation.** Defaults are visible in the code now, but nobody has shown rank=32 is the right choice.
- **Teacher reliability is untested.** The pseudo-unconditional branch reuses the harmful teacher trajectory, so the method's behavior on concepts the base model generates inconsistently is unknown.
- **Janus-Pro is the outlier and we don't know why.** Table A1 shows the 10× η gap and 20× lr gap; the appendix gestures at Janus-Pro's decoupled visual encoding as the cause but doesn't actually isolate it.

### What this does to my weakness list

Compared to the original review:

- *No adaptive adversarial evaluation* — partially addressed via cross-evaluator robustness. I'd downgrade this from major to minor.
- *No multi-concept erasure* — unchanged. Still major.
- *Hyperparameter sensitivity under-reported* — the data is there now (Table A1) but the underlying behavior isn't analyzed. Call it minor-leaning-major.
- *Teacher reliability* — unchanged. Still major.
- *500 prompts, simple/comprehensive prompts, appendix access* — fully resolved.
- *LoRA rank ablation* — unchanged.
- *Loss notation* — unchanged.

## Updated Recommendation

**5: Weak Accept** — same number, more confidence behind it.

My original score already assumed there'd be a decent appendix. The supplement does deliver on several fronts, but the two weaknesses I weighted most (multi-concept erasure, teacher reliability) are still untouched. Section A8 moves one major concern to minor, which is real progress, but one downgrade isn't enough on its own to push me to 6. The paper is a clean, well-executed contribution to a genuine gap; what holds it back from a stronger accept is breadth of evaluation, not the core idea.

## Updated Justification

The appendix helps in three concrete ways. First, the cross-evaluator robustness check (A8) is the missing piece I most wanted — it shows the CDR gains aren't tied to a single judge. Second, the SLD* derivation in A3 is more careful than the main paper let on; I hadn't called this out as a weakness, but it would have been one if I'd looked harder. Third, the code release plus Table A1 means the method is reproducible and the per-model hyperparameter variation is at least honest.

What I can't get past with the current evidence: I still don't know how OBLIVIATE behaves when you erase two concepts at once, and I still don't know how it behaves against a teacher that doesn't reliably produce the target. Either of these in a rebuttal — even a small experiment — would probably move me to Accept.

## Updated Suggestion For Rebuttal

If the authors want to move my score up, in rough priority order:

1. **Multi-concept erasure.** Even erasing just two concepts simultaneously on one model (LIQUID with nudity + Coca-Cola, say) and reporting CDR plus utility on both would do a lot. This is the biggest gap.
2. **Adaptive prompt attack.** Rerun a Ring-A-Bell-style search against the OBLIVIATE-edited LIQUID checkpoint instead of the original model. Report CDR under that stronger setting.
3. **LoRA rank sensitivity.** A single row of ranks (8, 16, 32, 64) on LIQUID nudity. The erasure literature has burned reviewers on this before; defending the chosen rank would help.
4. **Janus-Pro η sensitivity curve.** CDR/FID vs. η for Janus-Pro on one scenario. Is the η=10–12 region a knife-edge or a wide plateau? That changes the story.
5. **Teacher-reliability control.** Pick a concept the base LIQUID generates less than ~60% of the time and check whether OBLIVIATE still drives CDR down. Just a sanity check on the regime where the method is supposed to work.

---

## Paper #8732 (LULU) — Review Unchanged

Nothing new arrived for #8732, so my **3: Borderline Reject** stands. The reasons in `claude_review.md` haven't moved: narrow evaluation scope, no NSFW/style/identity coverage, detector robustness isn't tested, inference cost isn't reported, and the cross-model generalization claim has no experiment behind it. None of that gets fixed without new work.

---

## Cross-Reference Update

The supplement also shifts a few things in the Claude vs. Gemini comparison from `claude_cross_reference.md`:

- **Compute overhead (Gemini's concern).** Still not addressed. The code shows on-the-fly logits computation as the default rather than caching, which implies real memory and time costs, but nobody has put a number on it. Gemini's complaint stands.
- **Semantically proximate safe concepts (Gemini's concern).** No targeted analysis added, though the Janus-Pro Coca-Cola samples in Fig. A3 show OBLIVIATE substitutes with generic bottles and apparel rather than other branded items. Circumstantial, not a proper experiment.
- **Cross-evaluator robustness (my concern).** Now addressed via Section A8. Gemini didn't raise this one, so the supplement adds something neither review explicitly demanded.

Bottom line for the comparison: both reviewers still land on Weak Accept for OBLIVIATE with slightly more confidence post-supplement. The LULU disagreement is unchanged.
```

## What makes the below so obviously AI generated?

- Em dashes are still doing a lot of work in places.
- A few "is a meaningful response" / "real response" framings still feel a bit reviewer-as-LLM.
- Some bolded inline-header bullet starts ("**Cross-evaluator robustness.**") survive — that's an AI-list tell.
- "Bottom line for the comparison" closer is a faint signpost.

## Final rewrite

### Assistant — 2026-04-21T01:12:15.091Z

[tool_use: Write]

### Assistant — 2026-04-21T01:12:27.657Z

Humanized `claude_review_updated.md` is saved.

**Changes made:**
- Removed bolded inline-header bullets in favor of flowing prose where appropriate
- Cut "materially strengthens," "on three axes," "is a meaningful response," "crucially" framing
- Replaced signposty section intros with direct openings
- Switched title-case headings to sentence case
- Kept em dashes only where they genuinely beat commas; removed the rest
- Let opinions show ("This is the addition I cared about most," "Honestly, this clarifies the intuition better than the main paper does," "is a different beast")
- Varied rhythm: short punchy lines next to longer ones
- Cut the "Bottom line for the comparison" closer that read like a presentation slide

The core technical content, recommendation (5: Weak Accept), and rebuttal priorities are unchanged — only the voice is different.

### User — 2026-04-21T01:20:37.724Z

What is SLD mentioned in the paper

### Assistant — 2026-04-21T01:20:57.898Z

**SLD = Safe Latent Diffusion** (Schramowski et al., reference [32] in the paper).

It's an **inference-time** safety mechanism originally developed for diffusion models. Instead of modifying weights, SLD steers the denoising trajectory away from unsafe concepts at generation time using an extra classifier-free-guidance-style term: it computes the direction from the unconditional prediction toward the unsafe concept and subtracts a thresholded portion of it from the noise estimate, controlled by a guidance scale, safety threshold, warm-up parameter (δ), and momentum (s_m, β_m).

In the OBLIVIATE paper SLD shows up two ways:
- As a **baseline** (denoted **SLD\***), since the original SLD was designed for continuous noise predictions in diffusion and needs adaptation to operate on AR token logits.
- The adaptation is described in detail in **Appendix A3**: warm-up is dropped (AR generates spatially, so an early "warm-up" would just leave the top-left of the image unguided), momentum is dropped (each AR step produces a brand-new token with no shared temporal state to accumulate over), the safety threshold is rescaled (λ=1 instead of ~0.015 because logit differences span a much wider range than noise differences), and the guidance scale is reduced (s_S=3 instead of ~1000) with explicit clamping to keep token distributions stable.

So when the OBLIVIATE results table lists "SLD\*", it means *SLD adapted by the authors for the autoregressive setting* — not the off-the-shelf diffusion version.

### User — 2026-04-21T01:23:41.250Z

But does modifying SLD make the method SLD any more?

### Assistant — 2026-04-21T01:24:26.130Z

Genuinely good question — and I think the honest answer is "barely."

Here's what SLD* keeps from the original:
- The CFG-style guidance equation structure (target = unconditional + s·(conditional - unconditional - safety adjustment))
- The directional difference d = z(p) - z(c) between prompt and target concept
- The safety threshold λ that gates whether to apply the penalty at all
- The conceptual stance: inference-time steering, no weight changes

Here's what SLD* drops or changes:
- **Warm-up (δ): removed entirely.** In the original this delays guidance during early diffusion steps to avoid wrecking global composition.
- **Momentum (s_m, β_m): removed entirely.** In the original this accumulates the safety penalty over time for the same latent.
- **Hyperparameter scales: 100–300× different.** s_S goes from ~1000 to 3, λ goes from ~0.015 to 1.
- **A clamp added** (φ_clamped = min(φ, 1)) that wasn't in the original formulation.

If you look at the original SLD paper, warm-up and momentum are not minor knobs — they're two of the four core hyperparameters and a major part of why SLD works rather than catastrophically over-steering. The OBLIVIATE authors argue (Section A3.1 of the appendix) that both are *architecturally incompatible* with AR generation:
- Warm-up makes no sense because early AR steps are spatial (top-left tokens), not coarse-to-fine in time.
- Momentum makes no sense because each AR step generates a fresh token with no shared temporal state.

So they have a principled reason for removing them. But the resulting method is closer to "negative classifier-free guidance with a thresholded penalty on AR logits" than to SLD as anyone would have recognized it. That's basically just **negative prompting with a threshold gate** — which the paper *also* compares against, separately, as "Negative Prompting."

This raises a real question about baseline fairness:

1. **Is SLD\* a strawman?** It's been stripped of two of the components that made the original work, then compared against a method (OBLIVIATE) that *does* have a temporal/trajectory equivalent (full-rollout supervision). If the authors are claiming SLD doesn't work well in the AR setting, the comparison is partly arguing that "SLD without warm-up or momentum doesn't work well," which is closer to a tautology than a finding.

2. **Is the asterisk doing real work?** The naming convention (SLD\*) is at least honest signaling, but in the results tables it gets read as "we beat SLD." A reader skimming Table 1 sees OBLIVIATE crushing SLD\* on RAB and walks away thinking SLD is the wrong tool — when really, *the SLD-shaped object compatible with AR* is the wrong tool, and the gap between SLD and SLD\* might be larger than the gap between SLD\* and Negative Prompting.

3. **What would a fairer baseline look like?** Possibly some hybrid like a "trajectory-aware SLD" that tries to recover momentum-equivalent behavior across token positions (e.g., accumulating the penalty across nearby spatial neighbors). The authors don't try this.

How this affects my view of the paper: it doesn't change my recommendation, but it does soften the practical meaning of the SLD\* comparison numbers. The strong baseline in this paper is really **EAR** (the only fine-tuning-based AR concept erasure method), and OBLIVIATE genuinely beats EAR on most metrics. The SLD\* comparison is more "we adapted an existing inference-time method as faithfully as we could and it doesn't work as well" than "we beat a serious baseline." That's a defensible move, but it's worth reading the table with that caveat in mind.

If I were rebutting the authors I'd push them to either rename SLD\* something more honest (e.g., "Thresholded Negative Guidance") or report a sensitivity row showing what happens if you try to *port* warm-up/momentum to AR via some approximation, even imperfectly — to confirm those components really can't help, rather than just asserting it.

### User — 2026-04-21T01:25:41.816Z

Also, do you think EAR can be adopted for LIQUID and EMU3-GEN

### Assistant — 2026-04-21T01:26:42.415Z

Good question, and one I underweighted in my original review. Short answer: **yes, in principle, but with non-trivial engineering, and the authors' decision not to do it is itself a meaningful gap.**

## Architectural portability

EAR's core mechanism — extending ESD-style distillation to operate over sampled image token sequences with weight updates on disjoint token windows — isn't tied to anything Janus-Pro-specific at the algorithm level. It just needs:
- Access to image-token logits (all three models produce these)
- A way to apply negative guidance against a target concept
- A LoRA-friendly weight surface

LIQUID, Emu3-Gen, and Janus-Pro all expose all three. So the math ports.

## Where the engineering gets messy

1. **The EAR official codebase is almost certainly Janus-Pro-specific.** The OBLIVIATE authors say they "train new checkpoints using their official implementation" only for Janus-Pro. That phrasing strongly implies the implementation is Janus-Pro-bound — Janus-Pro's decoupled architecture (separate understanding encoder, generation encoder, generation head) means hooks for "where does the image token logit live" are written for that specific layout. Porting to LIQUID's unified Gemma-7B backbone or Emu3-Gen's MoVQGAN-based pipeline means rewriting that scaffolding from scratch.

2. **Sequence-length scaling.** Janus-Pro generates at 384×384, which is the smallest of the three. Emu3-Gen at 720×720 produces 4096 image tokens per image; LIQUID at 512×512 produces 1024. EAR operates on disjoint token windows over the image sequence, so longer sequences mean either more windows per update or larger windows — both cost compute. Janus-Pro is also the smallest model (vs. LIQUID's 7B), so compute per gradient step jumps as well.

3. **Hyperparameter retuning would be brutal.** EAR caused FID=31.63 on Janus-Pro (vs. 13.16 for the unedited model) — a 2.4× jump that signals fragile training even in its native setting. On a different backbone with different sequence length and tokenizer, every knob (negative guidance strength, window size, LoRA capacity, learning rate) needs to be re-found from scratch.

## Why this matters for the OBLIVIATE evaluation

This is actually a fairer-baseline critique I should have raised more sharply originally. Look at Table 1 of the paper: EAR appears as a baseline **only for Janus-Pro**, where it produces the worst utility number in the entire table (FID 31.63). That single data point becomes the centerpiece of the paper's "we substantially out-perform fine-tuning baselines on the utility-erasure trade-off" story.

But Janus-Pro is also the model where:
- *OBLIVIATE itself* needs η=10–12 (vs. 1–2 elsewhere)
- The decoupled visual encoder is uniquely fragile
- Every method seems to behave worse than on the other two backbones

So the EAR result might be telling us less about EAR than about Janus-Pro. If EAR were ported to LIQUID or Emu3-Gen, two scenarios are possible:

- **Scenario A:** EAR works decently on LIQUID/Emu3 (say, FID 14–16 with mediocre CDR). Then OBLIVIATE's win is real but more modest, and the headline "EAR collapses utility" framing is overstated — it collapses utility *on Janus-Pro specifically*.
- **Scenario B:** EAR collapses utility on all three. Then the OBLIVIATE story strengthens substantially, and the paper's claim that fine-tuning-based AR erasure has fundamental problems (which OBLIVIATE then solves) gets real empirical weight.

We don't know which one is true, and the paper doesn't tell us.

## What I'd push for in a rebuttal

Adding even one EAR run on LIQUID or Emu3-Gen would meaningfully strengthen the comparison story. The authors don't need both — pick whichever has the easier engineering path (probably Emu3-Gen, since it's also a unified-backbone AR generator like Janus-Pro and might require less codebase surgery than LIQUID's Gemma-based architecture).

If they really can't port EAR for time/compute reasons, the paper should at least say so explicitly and frame the EAR comparison as "the only published AR concept-erasure method, available only on Janus-Pro" rather than letting the table suggest a head-to-head across all three backbones.

This is a real gap I'd add to my updated weakness list, somewhere between the "no LoRA ablation" minor and the "no multi-concept erasure" major. Probably minor-leaning-major, since the load-bearing comparison in the paper rests on it.

### User — 2026-04-21T01:29:31.890Z

Please update review

### Assistant — 2026-04-21T01:29:41.866Z

[tool_use: Read]

### Assistant — 2026-04-21T01:29:50.209Z

I'll add the SLD\* baseline-fairness concern and the EAR portability gap that came out of our discussion. Both belong in "Things still open" and the rebuttal list.

### Assistant — 2026-04-21T01:30:13.890Z

[tool_use: Edit]

### Assistant — 2026-04-21T01:30:28.697Z

[tool_use: Edit]

### Assistant — 2026-04-21T01:30:51.260Z

[tool_use: Edit]

### Assistant — 2026-04-21T01:30:57.152Z

Now let me update the recommendation/justification paragraphs to reflect that two new gaps were added, and refresh the cross-reference section.

### Assistant — 2026-04-21T01:31:15.569Z

[tool_use: Edit]

### Assistant — 2026-04-21T01:31:31.779Z

Updated `claude_review_updated.md` with the two new gaps that came out of our discussion:

**Added to "Things still open":**
- **EAR only on Janus-Pro.** The headline fine-tuning-baseline comparison rests on a single data point from the model where every method behaves badly. Without an EAR run on LIQUID or Emu3-Gen, we can't tell if EAR's utility collapse is a general AR-erasure problem or a Janus-Pro-specific one.
- **SLD\* baseline fairness.** Stripping warm-up and momentum is architecturally defensible, but it leaves SLD\* closer to "thresholded negative prompting" than to SLD proper. The Table 1 framing leans on SLD's name recognition more than the comparison can carry.

**Added to weakness list:**
- EAR-baseline coverage: minor-leaning-major
- SLD\* fairness: minor

**Added to rebuttal suggestions:**
- An EAR run on Emu3-Gen (probably the easier port)
- Either rename SLD\* or run a sensitivity check confirming warm-up/momentum approximations don't help

**Updated recommendation/justification:**
- Score stays at 5 (Weak Accept), but I noted that confidence is mixed: A8 raised it, the new gaps lowered it.
- Three concrete things would push me to Accept: small multi-concept experiment, teacher-reliability control, or an EAR run on Emu3-Gen.

### User — 2026-04-21T01:40:58.297Z

please update claude_review.md

### Assistant — 2026-04-21T01:41:22.999Z

[tool_use: Read]

### Assistant — 2026-04-21T01:41:49.497Z

[tool_use: Edit]

### Assistant — 2026-04-21T01:42:11.330Z

[tool_use: Edit]

### Assistant — 2026-04-21T01:42:32.310Z

[tool_use: Edit]

### Assistant — 2026-04-21T01:42:58.883Z

[tool_use: Edit]

### Assistant — 2026-04-21T01:43:12.952Z

Updated `claude_review.md` with the new concerns from our discussion, keeping the original review's formal style intact.

**Changes to the OBLIVIATE review:**

- **New major weakness:** EAR baseline only on Janus-Pro. Single data point carrying the "we beat the only fine-tuning AR baseline" claim, on the model where every method behaves worst.
- **New minor weakness:** SLD\* baseline fairness. Removing warm-up and momentum leaves SLD\* closer to thresholded negative prompting than to SLD proper; the framing leans on name recognition.
- **Justification updated** to mention both new gaps.
- **Rebuttal list expanded from 6 to 8 items**, with two new entries: an EAR run on Emu3-Gen (or honest reframing), and either renaming SLD\* or running the warm-up/momentum sanity check.

The LULU review is unchanged, and the recommendation stays at **5: Weak Accept** for OBLIVIATE — the new concerns add weight on the "what holds it back" side of an already-borderline score, but don't push it down further.

### User — 2026-04-21T01:56:51.127Z

What do you mean by:

- References to figures/sections mix numeric and appendix pointers (A1, A2, A3, A4, A6, A7), making the main paper feel incomplete without the appendix.
- Some loss notation is slightly inconsistent between Eq. 6, 7, 8, and 9 (target construction in Eq. 4/7 and final KL in Eq. 9 could be unified more clearly).

### Assistant — 2026-04-21T01:57:47.060Z

Good — these are the kind of nitpicks I should be more concrete about. Let me unpack each.

## 1. Mixed numeric/appendix references

The main 14-page paper repeatedly punts important content to the appendix. Examples (from my reading):

- **Methodological overview:** "Fig. 3 provides an overview of OBLIVIATE, with additional details and illustrations deferred to Appendix A1."
- **Training/hyperparameter details:** "Full training configurations and hyperparameter settings are provided in Appendix A2."
- **Baseline definition:** "[SLD] which we adapt to the autoregressive setting and denote as SLD\* (see Sec. A3)." — this is critical, because SLD\* is one of the main baselines in Table 1, and its actual definition lives only in the appendix.
- **Qualitative samples:** "A similar grid of samples for Janus-Pro is provided in Fig. A3 in the Appendix."
- **Prompt artifacts:** "We provide example prompts from that set in the Appendix (see Sec. A7)" and "We provide the remaining prompts in Appendix A6."

The complaint isn't that the appendix exists — long appendices are normal for ECCV. The complaint is **what** got pushed there. A reader of just the main paper:

- Can't fully understand SLD\* (a method they're being compared against, and which they were significantly modified) without flipping to A3.
- Can't reproduce the experiments without A2's hyperparameter table.
- Sees qualitative results for only 2 of the 3 evaluated models (Janus-Pro samples are appendix-only).
- Can't audit the simple vs. comprehensive prompts that drive the Table 3b ablation.

A self-contained main paper should at least put baseline definitions and headline qualitative coverage in the main body. As written, the main paper feels like a teaser for the appendix on those fronts.

## 2. Inconsistent loss notation across Eq. 6, 7, 8, 9

The reader has to track three things across these equations, and the paper doesn't help:

**Which prefix?** The text introduces two different visual prefixes:
- $\hat{x}_{<k}$ — the prefix generated with the harmful prompt $c$
- $\bar{x}_{<k}$ — the prefix generated with the empty prompt $\varnothing$

But the equations move between them inconsistently:
- **Eq. 4** (the unaligned version) uses $\hat{x}_{<k}$ for the conditional branch and $\bar{x}_{<k}$ for the unconditional one.
- **Eq. 7** (the aligned version, which is the actual method) uses $\hat{x}_{<k}$ for both branches.
- **Eq. 6** (single-step CE) writes $x_{<k}$ with no hat at all.
- **Eq. 8** (trajectory CE) puts the hat back on: $\hat{x}_{<k}$.

So in three consecutive equations the same conceptual prefix gets three different decorations. The reader has to read the surrounding prose carefully to know whether each $x_{<k}$ refers to the teacher's rollout, the student's rollout, or an abstract sequence position.

**Whose model?** The teacher is $z_{\theta^*}$ (frozen) and the student is $z_\theta$ (trained). In Eq. 7 the target $p_\text{tgt}^{(k)}$ comes from the teacher. In Eq. 9 the student prediction $p_\theta^{(k)} = \text{softmax}(z_\theta(\hat{x}_{<k}, c))$ comes from the student. That's fine, but the convention is never spelled out as a notation block — the reader has to infer it from the asterisks.

**Aligned vs. unaligned target?** Eq. 4 and Eq. 7 are *almost identical* on the page (same right-hand-side structure), but Eq. 4 is the version the paper rejects and Eq. 7 is the version the paper proposes. The whole point of Section 3 is the move from one to the other, but visually the two equations don't broadcast that they're saying different things — the difference lives entirely in whether the unconditional prefix matches or not, which is buried in subscripts.

What would fix it: a short notation table at the top of Section 3 listing $\hat{x}$, $\bar{x}$, $z_\theta$, $z_{\theta^*}$ once and for all, plus a clearer visual contrast between Eq. 4 and Eq. 7 (e.g., color-coding the differing prefix, or restating the equations side-by-side with the difference highlighted). As written, the reader has to flip back and forth between equations on different pages to keep the bookkeeping straight, which makes a methods section that is conceptually clean feel harder to read than it needs to be.

Neither of these is a deal-breaker — they're presentation issues, not science issues — which is why I put them in Minor Weaknesses rather than Major. But both are easy fixes for the camera-ready.

### User — 2026-04-21T02:04:55.503Z

How feasible is it to run EAR on other models? Can you check?

### Assistant — 2026-04-21T02:05:10.118Z

Good question. Let me check the EAR paper and codebase to ground this with actual evidence.

### Assistant — 2026-04-21T02:05:10.423Z

[tool_use: ToolSearch]

### Assistant — 2026-04-21T02:05:31.876Z

[tool_use: WebFetch]

### Assistant — 2026-04-21T02:05:48.087Z

[tool_use: WebSearch]

### Assistant — 2026-04-21T02:06:09.866Z

[tool_use: WebFetch]

### Assistant — 2026-04-21T02:06:27.376Z

Wrong repo — `shaochenze/ear` is a different paper with the same acronym. Let me get the actual EAR-concept-erasure code URL from the paper itself.

### Assistant — 2026-04-21T02:06:30.776Z

[tool_use: WebFetch]

### Assistant — 2026-04-21T02:06:52.185Z

[tool_use: WebFetch]

### Assistant — 2026-04-21T02:07:07.810Z

[tool_use: WebFetch]

### Assistant — 2026-04-21T02:07:14.536Z

[tool_use: WebFetch]

### Assistant — 2026-04-21T02:07:23.756Z

[tool_use: WebFetch]

### Assistant — 2026-04-21T02:07:35.739Z

[tool_use: WebFetch]

### Assistant — 2026-04-21T02:07:42.926Z

[tool_use: Bash]

### Assistant — 2026-04-21T02:07:50.553Z

[tool_use: Bash]

### Assistant — 2026-04-21T02:08:52.112Z

Checked the actual EAR codebase. Here's what I found, which sharpens my earlier answer considerably.

## The code is 1:1 with Janus-Pro

The published repo ([immc-lab/ear](https://github.com/immc-lab/ear)) has a minimal structure: one training script (`train/ear_train_church.py`), one inference script, one eval script. No model registry, no config system, no abstraction layer. And the training script is explicitly tied to Janus-Pro's API:

```python
from janus.models import VLChatProcessor
model_path = "/path/to/huggingface/Janus-Pro-7B"
...
vl_chat_processor = VLChatProcessor.from_pretrained(model_path)
vl_gpt = AutoModelForCausalLM.from_pretrained(model_path, trust_remote_code=True)
model = vl_gpt.language_model.model
...
positive_logits = vl_gpt.gen_head(positive_hidden_states[:, -1, :])
```

The concrete Janus-Pro dependencies:

1. **`from janus.models import VLChatProcessor`** — DeepSeek's Janus library as a hard dependency.
2. **`vl_gpt.language_model.model`** — assumes Janus-Pro's decoupled module layout where the LLM is nested inside the multimodal wrapper.
3. **`vl_gpt.gen_head(...)`** — this is the load-bearing one. Janus-Pro has a **separate generation head** distinct from the language-model head. This is literally the "decoupled visual encoding" design choice that defines Janus-Pro. LIQUID and Emu3-Gen don't have this — they use a unified head where image tokens are just a vocabulary slice.
4. **`tqdms = tqdm(range(576))`** — 576 = 24×24, Janus-Pro's image-token grid at 384×384. LIQUID is 1024 (32×32 at 512×512), Emu3-Gen is ~4096.
5. **`num_layers=5`** — fine-tunes the top 5 transformer layers, which is a Janus-Pro-specific choice that'd need retuning.

## What porting would take

**To Emu3-Gen** (probably the easier port — it's also a unified AR generator):
- Swap the tokenizer/processor interface entirely (MoVQGAN-based, not Janus's chat processor).
- **Drop the `gen_head` call and project through Emu3's unified `lm_head` instead, then slice to the image-token vocab range.** This is the biggest structural rewrite because the whole loss is built around the separate-head assumption.
- Change `range(576)` to the Emu3 image-token count (~4096) — that's ~7× more gradient accumulations per image, so compute cost jumps accordingly.
- Rewrite the CFG batching (the `[0::2, :]` / `[1::2, :]` splits assume Janus-Pro's conditional/unconditional stacking convention).

**To LIQUID** (7B Gemma backbone, unified vocab):
- Same unified-head rewrite as above, but against LIQUID's `lm_head` which spans the 256K+8K Gemma-plus-VQ vocab.
- Image token count goes from 576 → 1024.
- Compute per step roughly doubles-to-triples since LIQUID is ~2× Janus-Pro's size and the sequence is longer.

Neither port is "write from scratch," but neither is "run the config and go." Realistic estimate: **1–2 weeks of focused engineering per backbone** for someone already fluent in the Janus-Pro and target-model internals, plus hyperparameter resweeping (the `lr=1e-4`, `num_layers=5`, `accumulation_steps=48`, `negative_guidance=1.0` settings were chosen for Janus-Pro and probably won't transfer cleanly).

## So how does this affect the review?

A couple of updates:

**1. The "EAR only on Janus-Pro" gap is weaker than I framed it in the updated review.** It's not that OBLIVIATE's authors were lazy — the EAR public implementation is genuinely tied to Janus-Pro through a non-trivial architectural dependency (the separate `gen_head`). Porting isn't a weekend job, and reviewers should account for that. My critique should be "acknowledge this constraint in the text and reframe the claim" rather than "go run EAR on LIQUID."

**2. There's an interesting second-order observation.** EAR's own paper claims to work on "unified AR models" generally, but their public code is just as Janus-Pro-specific as I accused OBLIVIATE of being in its EAR comparison. So the generality gap I'm pointing at is really in the EAR paper, not the OBLIVIATE paper. OBLIVIATE is actually *better* on this axis — they evaluate on three different AR backbones, while EAR's codebase covers one.

**3. The rebuttal ask should shift.** Instead of "please run EAR on Emu3-Gen," it should be closer to: *"Please acknowledge in the main paper that EAR's public implementation is Janus-Pro-specific, so the EAR comparison is effectively a single-backbone data point. This doesn't invalidate the comparison, but it should be framed as 'we compare against the only published AR concept-erasure method on the model it was designed for' rather than as evidence that fine-tuning-based AR erasure broadly has utility problems."*

Want me to update `claude_review.md` to reflect this sharper picture — softening the EAR weakness from "they should have ported it" to "they should reframe what the comparison is actually evidence of"?

Sources:
- [EAR: Erasing Concepts from Unified Autoregressive Models (arXiv)](https://arxiv.org/abs/2506.20151)
- [EAR: Erasing Concepts from Unified Autoregressive Models (HTML)](https://arxiv.org/html/2506.20151)
- [immc-lab/ear GitHub repository](https://github.com/immc-lab/ear)

### User — 2026-04-21T02:11:05.547Z

Is this work somewhat an extension of ESD to AR models?

### Assistant — 2026-04-21T02:12:12.870Z

Yes — and I'd argue this is the most honest way to read the paper. OBLIVIATE is essentially **ESD ported to AR, with three fixes for why the naive port breaks.**

## The core is ESD, unchanged

Here's ESD's target construction (Gandikota et al., 2023, Eq. 3 of the OBLIVIATE paper):

$$\epsilon_\text{tgt}(x_t, c) = \epsilon_{\theta^*}(x_t, \varnothing) - \eta\big(\epsilon_{\theta^*}(x_t, c) - \epsilon_{\theta^*}(x_t, \varnothing)\big)$$

Here's OBLIVIATE's target construction (Eq. 7):

$$z_\text{tgt}^{(k)} = z_{\theta^*}(\hat{\mathbf{x}}_{<k}, \varnothing) - \eta\big(z_{\theta^*}(\hat{\mathbf{x}}_{<k}, c) - z_{\theta^*}(\hat{\mathbf{x}}_{<k}, \varnothing)\big)$$

These are **the same formula** with two substitutions:
- Noise prediction $\epsilon_\theta$ → logits $z_\theta$
- Noisy latent $x_t$ → token prefix $\hat{\mathbf{x}}_{<k}$

The teacher-student framing, the classifier-free-guidance-style negative target, the η hyperparameter — all inherited. The paper is upfront about this; Section 3 literally opens with "Our starting point is the standard teacher-guided formulation used in the diffusion-based concept erasure ESD."

## What's actually new in OBLIVIATE

Only one of the three contributions is genuinely AR-native; the other two are ports of diffusion-era ideas:

1. **Aligned visual prefixes (the pseudo-unconditional branch).** This one *is* new. Diffusion doesn't need it because the noisy latent $x_t$ is shared by construction between conditional and unconditional branches. In AR, rollouts from the same prompt under different conditioning diverge, which creates the distribution-divergence problem Fig. 2a diagnoses. Noticing this and fixing it with a shared prefix is a real AR-specific contribution.

2. **Trajectory-level supervision over full rollouts.** This is a port of **EraseFlow** (Ref. [19] in the paper), which already extended ESD-style erasure to full diffusion trajectories. OBLIVIATE's framing is "we import trajectory-level training from diffusion into AR," which is honest but not new machinery.

3. **KL distribution matching instead of CE on hard targets.** This is the natural AR-space substitute for ESD's MSE — when your output space is a discrete distribution rather than a continuous vector, KL is the obvious match. Table 4 shows it helps utility (FID 23.24 → 15.41), but methodologically it's a reasonable-default choice, not a novel construction.

## So what is OBLIVIATE, really?

It's a **careful empirical adaptation paper**, not a new-paradigm paper. The contribution profile is:

- **Methodological novelty: moderate.** One genuinely AR-specific idea (aligned prefixes) on top of an ESD + EraseFlow scaffold.
- **Empirical novelty: high.** First working concept-erasure method demonstrated across three modern AR backbones, with strong adversarial-benchmark numbers.
- **Diagnostic value: high.** Fig. 2a's divergence analysis is the kind of methodologically informative result that makes follow-up work easier.

That's a legitimate ECCV contribution, but it does contextualize a few things:

- **The novelty framing in the abstract and intro is a bit generous.** Phrases like "Our method builds on three key design choices" suggest three novel choices; really it's one novel choice and two adaptations.
- **The EAR comparison looks different in this light.** EAR actually departs further from ESD (their WGA/TLM are new constructions, not direct ports). So EAR is methodologically more ambitious but architecturally narrower; OBLIVIATE is methodologically more conservative but architecturally broader. Reasonable tradeoff, but worth seeing clearly.
- **"Concept erasure for AR models works" is a solid and publishable finding.** It doesn't need to also be a new paradigm to be worth accepting.

## Does this change my review?

Not the score, but it could sharpen the **Paper Strengths** section. Right now my review lists "Methodological Novelty" as a strength without qualifying that two of the three pillars are ports. A fairer version would say something like:

> The paper's genuine AR-specific contribution is the aligned-prefix / pseudo-unconditional branch — a concrete fix for a failure mode that doesn't exist in diffusion. Trajectory-level supervision and KL matching are sensible adaptations of existing diffusion-era ideas (EraseFlow, and the natural discrete-distribution analogue of MSE), which is fine but should be read as careful engineering rather than methodological novelty.

Want me to fold this into `claude_review.md`? I'd soften the "Methodological Novelty" strength to "Careful, honest diagnosis-and-fix work with one genuinely AR-native contribution," and maybe add a sentence to the Justification noting that the paper's real value is the empirical breadth plus the prefix-alignment insight, not the loss-function choices.

### User — 2026-04-21T02:12:27.606Z

yes please

### Assistant — 2026-04-21T02:12:41.214Z

[tool_use: Read]

### Assistant — 2026-04-21T02:13:19.053Z

[tool_use: Edit]

### Assistant — 2026-04-21T02:13:45.379Z

[tool_use: Edit]

### Assistant — 2026-04-21T02:14:02.901Z

Updated `claude_review.md` to reflect the ESD-lineage framing.

**Changes made:**

1. **Sharpened the "Principled diagnosis before design" strength** to point at the prefix-alignment insight specifically as the AR-native contribution, rather than treating all three design choices as equally novel.

2. **Added a new "Note on novelty framing" section** between Strengths and Major Weaknesses. It lays out the ESD lineage explicitly:
   - Eq. 7 is structurally identical to ESD with two substitutions (logits for noise, prefixes for latents).
   - Of the three "key design choices," only **aligned prefixes** is genuinely AR-native; **trajectory supervision** is a port of EraseFlow, and **KL matching** is the natural discrete analogue of MSE.
   - Frames this as honest accounting, not a critique — the paper doesn't oversell, but the abstract is more generous than the methodology.
   - Notes the methodologically-conservative-but-architecturally-broad tradeoff against EAR.

3. **Updated the Justification** to lead with what the paper actually contributes (prefix-alignment + empirical breadth) rather than reciting "three design choices" as if all three are novel. Also softened the EAR-coverage critique to acknowledge that the EAR public codebase is genuinely Janus-Pro-bound (per the GitHub investigation), so the single-backbone EAR comparison is partly a field constraint rather than an authorial choice.

Score remains **5: Weak Accept** — the framing is now more accurate to what the paper actually offers.

### User — 2026-04-21T02:25:11.301Z

Which methods did the original SLD paper compare with

### Assistant — 2026-04-21T02:25:19.745Z

[tool_use: WebSearch]

### Assistant — 2026-04-21T02:25:42.691Z

[tool_use: WebFetch]

### Assistant — 2026-04-21T02:25:57.285Z

[tool_use: Read]

### Assistant — 2026-04-21T02:26:51.257Z

Short answer: surprisingly few. Here's the actual comparison set from the original SLD paper (Schramowski et al., CVPR 2023):

## Empirical comparisons in the original SLD paper

**Table 1 (inappropriate content on I2P benchmark):**
- **SD 1.4** — unmodified Stable Diffusion baseline
- **Negative Prompting (Neg. Prompt)** — replacing the unconditional estimate with a negatively-conditioned one
- **SLD itself** at four hyperparameter presets (Hyp-Weak, Hyp-Medium, Hyp-Strong, Hyp-Max) — this is really ablation over guidance strength

**Table 2 (image fidelity on COCO FID-30k and user study on DrawBench):**
- **SD** (baseline)
- **SLD** at the same four configurations

**Briefly discussed in prose (not in tables):**
- **SD 2.0** — mentioned as a comparison point because it applied dataset-level filtering of sexual content before training. The paper notes SLD on SD 1.4 is competitive and that combining dataset filtering + SLD works best.
- **SD's built-in safety checker** — explicitly rejected as "post-hoc intervention" that SLD aims to avoid, not tabulated.

That's the entire head-to-head. No ESD, no UCE, no MACE, no CA, no fine-tuning-based erasure method, no learned safety classifier, no Receler or Ablating Concepts.

## Why the list is so short

**ESD (Gandikota et al.) hadn't been published yet.** SLD first appeared on arXiv in November 2022 (v1 at [2211.05105v1](https://arxiv.org/abs/2211.05105v1)) and was published at CVPR 2023. ESD came after — so SLD literally couldn't compare against the method that would later become the dominant baseline. Checking the SLD references confirms: no concept-erasure methods are in the bibliography. The only relevant prior work they cite in the "existing mitigation" bucket is classifier-free guidance variants and SD's safety checker.

This is actually consistent with SLD's positioning in its own paper: it's not framed as "the best concept-erasure method," it's framed as "a first principled alternative to post-hoc safety checkers that uses the model's own knowledge of inappropriateness." The original paper's contribution is as much the **I2P benchmark** (4,703 prompts across seven harm categories, still widely used) as the SLD method itself.

## Why this matters for the OBLIVIATE review

This actually sharpens my SLD\* critique in a useful direction.

When OBLIVIATE reports "we beat SLD\*," the reader's natural frame is "we beat a strong established baseline from a top-tier venue." But SLD itself only ever benchmarked against plain SD and negative prompting — it was never empirically validated against competitive concept-erasure methods in its own paper, because none of the competitors existed yet. What SLD really established was that **guidance-time safety steering works better than no mitigation and better than naive negative prompting.**

So when OBLIVIATE shows SLD\* sitting very close to Negative Prompting in Table 1, that's not just a quirk of the AR adaptation — it's recovering the **original empirical finding** of the SLD paper: SLD's advantage over simple negative prompting is modest (the original paper's Table 1 shows Neg. Prompt at 0.18 overall inappropriateness vs. Hyp-Weak SLD at 0.29 — negative prompting actually *beat* weak SLD in the original setting). SLD's real wins come from Hyp-Strong and Hyp-Max, which rely heavily on warm-up and momentum to be usable without wrecking image composition.

Once you strip warm-up and momentum (as SLD\* does for AR reasons), you're left with the "weak SLD" regime, which even the original paper didn't claim was a knockout over negative prompting. So the OBLIVIATE result "SLD\* ≈ Negative Prompting, both worse than OBLIVIATE" is actually a defensible replication of what we'd expect — it's just that the SLD\* column implicitly borrows credibility from Hyp-Strong/Max that never actually made it into the AR port.

**Revised take on the review:** my SLD\* minor-weakness critique is if anything more justified than I originally wrote it, but it's also a softer kind of unfair — it's not that OBLIVIATE is strawmanning SLD; it's that the SLD name carries a lot of empirical weight that was only ever established in regimes (Hyp-Strong/Max with warm-up + momentum) that don't survive the AR translation. I'd leave the weakness text roughly where it is, but this is useful context if the user ever needs to defend the critique in a discussion.

Sources:
- [Safe Latent Diffusion: Mitigating Inappropriate Degeneration in Diffusion Models (CVPR 2023 PDF)](https://openaccess.thecvf.com/content/CVPR2023/papers/Schramowski_Safe_Latent_Diffusion_Mitigating_Inappropriate_Degeneration_in_Diffusion_Models_CVPR_2023_paper.pdf)
- [Safe Latent Diffusion (arXiv 2211.05105)](https://arxiv.org/abs/2211.05105)
- [Official SLD implementation](https://github.com/ml-research/safe-latent-diffusion)

### User — 2026-04-21T02:31:20.096Z

I want to suggest another baseline, can something like mapping concept name to safe images a good idea?

### Assistant — 2026-04-21T02:32:33.724Z

Yes — this is a useful baseline direction, and its absence from the OBLIVIATE comparison set is a real gap. Let me unpack the flavors it could take, because "map concept name to safe images" can mean several different things with very different evaluation stories.

## Three flavors of "name → safe images" baseline

**Flavor 1: Retrieval replacement.** Detect the unsafe concept in the prompt (keyword match or small classifier). When detected, skip generation entirely and return a random image from a pre-curated safe bank for that concept.

- *What it measures:* the absolute floor. If concept erasure methods don't beat "just return a stock photo," they aren't doing anything.
- *Strengths:* trivial to implement, zero training.
- *Weaknesses:* terrible diversity (low utility metrics like FID), ignores everything else in the prompt ("A naked woman in Paris at sunset" → you get back a generic clothed-person photo with no Paris and no sunset).

**Flavor 2: Anchor-image conditioning.** When the unsafe concept is detected, condition the AR model's image-generation branch on a safe anchor image and regenerate. All three evaluated models (LIQUID, Emu3-Gen, Janus-Pro) support image conditioning natively because they're unified multimodal.

- *What it measures:* whether fancy weight-editing / guidance is needed at all, or whether cheap image conditioning gets you most of the way there.
- *Strengths:* uses AR models' native capabilities; preserves some prompt semantics.
- *Weaknesses:* changes the task setup (you're now image-to-image), and anchor selection is arbitrary for diffuse concepts like "nudity."

**Flavor 3: Supervised distillation with safe-image targets.** Fine-tune the student model with plain cross-entropy: input = unsafe prompt, target tokens = VQ-tokenized safe anchor image. No ESD-style guidance, no trajectory tricks, no KL — just supervised next-token prediction on safe image tokens.

- *What it measures:* whether OBLIVIATE's teacher-guided target construction is actually needed, or whether just pointing the model at safe outputs is enough.
- *Strengths:* directly ablates the guidance machinery; isolates the "guidance vs. brute-force supervision" question.
- *Weaknesses:* needs a concept-specific anchor set; will probably collapse diversity for broad concepts.

## What's already out there in this direction

You're not alone in having this intuition — the literature has explored related ideas:

- **LULU** (the other paper we reviewed) is essentially this, done at feature level: detect the unsafe concept, substitute features from a "safe alternative" concept. Same family of idea, but acting in activations rather than pixels.
- **Ablating Concepts** (Kumari et al., 2023) maps the target concept's text embedding to an anchor concept's embedding.
- **MACE** uses anchor concepts in its closed-form remapping.
- **SDD / SAFEGEN** have used safe reference images as fine-tuning targets.

So the concept-level idea is well-established. What's missing from OBLIVIATE's comparison is the **crude, pixel-space version** — Flavors 1 or 3 especially, which act as a "cheap baseline" check.

## Which flavor I'd actually propose to OBLIVIATE

**Flavor 3 (supervised distillation to safe image tokens) is the most useful missing baseline.** Reasons:

1. It's the natural ablation of OBLIVIATE itself. OBLIVIATE = "teacher-guided target construction + trajectory KL." Flavor 3 = "just fine-tune the student to predict safe image tokens directly, no teacher guidance." If OBLIVIATE only marginally beats this, it tells us the ESD-style guidance isn't doing much and you could have just supervised on safe outputs.
2. It isolates the contribution of the prefix-alignment trick. Flavor 3 doesn't need aligned prefixes because there's no unconditional/conditional contrast happening.
3. It's feasible to run on all three AR backbones — no architecture-specific dependencies, unlike EAR.
4. It gives a fair comparison to an honest "dumb baseline" approach that's genuinely missing from the paper.

Flavor 1 is also worth running because it's so cheap — it'd take a reviewer 20 minutes to implement and it establishes a floor. Flavor 2 is more experimental and probably not worth pushing as a required baseline.

## Should this go into the review?

I'd add this as a **rebuttal suggestion** rather than a major weakness. The paper doesn't *claim* to be exhaustive against supervised baselines, and Flavor 3 isn't a standard comparison in the diffusion concept-erasure literature either (where people compare against ESD, UCE, MACE, CA, etc.). But the absence is notable, especially because the paper's contribution framing ("ESD + three fixes") makes the reader ask "well, what about without the three fixes, just supervised learning to safe outputs?" — and there's no answer currently.

Want me to add this as rebuttal item #9 in `claude_review.md`? Something like:

> **Supervised distillation to safe image tokens as a baseline.** A natural ablation of OBLIVIATE's guidance machinery would be to fine-tune the student model with plain cross-entropy where targets are image tokens from a safe anchor image corresponding to the unsafe prompt (no teacher guidance, no prefix alignment, no trajectory KL — just supervised next-token prediction on safe outputs). This isolates how much of OBLIVIATE's gain comes from the ESD-derived target construction vs. how much is just "the student now sees safe outputs during training." Running this on one concept × one model would sharpen the novelty claim.

### User — 2026-04-21T02:33:24.669Z

i mean fine-tuning the unsafe concept name and map to safe images

### Assistant — 2026-04-21T02:34:32.009Z

Got it — so the proposed baseline is: **fine-tune the AR model directly on (unsafe prompt, safe image tokens) pairs**, with plain cross-entropy. No teacher guidance, no prefix alignment, no trajectory KL — just standard supervised fine-tuning where targets are VQ-tokenized safe anchor images.

This is a genuinely good baseline, and I think you're right that it's missing from the paper. Let me sharpen why.

## Why this baseline is compelling

1. **It's the natural ablation of OBLIVIATE's entire target-construction machinery.** OBLIVIATE spends Eq. 4–9 building a guidance-based target `z_tgt` from the teacher. Your baseline replaces that whole pipeline with "the target is just the tokens of a safe image." If OBLIVIATE's ESD-derived guidance math doesn't substantially beat this, then the core contribution shrinks a lot.

2. **It has a direct precedent in the diffusion literature.** This is essentially **Ablating Concepts** (Kumari et al., ICCV 2023) ported to AR: map the concept to a safe anchor, fine-tune to match. Ablating Concepts is a standard baseline in diffusion concept erasure, and its absence from the AR comparison is notable.

3. **It isolates three distinct claims in the paper at once:**
   - Do we need the pseudo-unconditional branch? Your baseline doesn't have one.
   - Do we need full-trajectory KL? Your baseline uses plain CE on concrete targets.
   - Do we need the teacher's `z_tgt` construction? Your baseline doesn't.
   
   If OBLIVIATE beats this baseline, it tells us at least one of the three is genuinely needed. If not, the paper's three "key design choices" are over-engineered.

## How I'd expect it to do

**On unbranding (Coca-Cola):** Probably competitive, maybe even comparable to OBLIVIATE. Brand logos are localized visual patterns; a model fine-tuned to map "Coca-Cola" → generic bottle tokens will likely do well on the CDR metric. The question is whether utility (FID) stays high or whether the model collapses toward the anchor image. Probably worse FID than OBLIVIATE, but the delta might be small.

**On nudity:** Trickier. "Naked" is a diffuse attribute, not a localized visual pattern. You'd need to pick safe anchor images that span enough variation (different poses, settings, styles) to avoid collapsing the distribution. Done naively, this would either undererase (the model interpolates around the anchor and nudity slips through) or over-collapse (every "person" prompt starts looking like the anchor). OBLIVIATE's guidance-based target is arguably better here because it gives the model a *direction* rather than a *destination*.

**On gory content:** Similar to nudity — diffuse attribute, anchor selection matters a lot.

So my expected result: your baseline would be close to OBLIVIATE on unbranding, meaningfully worse on nudity/gore. That would actually be a **useful finding** for the paper — it'd sharpen the story to "guidance-based target construction matters for diffuse concepts; for localized concepts you can get away with plain supervised fine-tuning."

## What it looks like in practice

Concrete recipe a rebuttal could run:

1. For each target concept, generate or retrieve ~500 safe anchor images using a paraphrase prompt (e.g., "nudity" → "a person wearing clothes," "Coca-Cola" → "a generic beverage bottle").
2. Tokenize each anchor with the VQ-VAE to get token sequences.
3. Build training pairs: unsafe prompt → anchor image tokens.
4. Fine-tune with standard cross-entropy, same LoRA rank and LR as OBLIVIATE for a fair comparison.
5. Evaluate on the same benchmarks.

This is roughly the same compute as OBLIVIATE itself — a day or two on a single GPU per concept.

## Want me to add this to the review?

I'd add it as a new major weakness and a rebuttal item. Something like:

**As a Major Weakness:**
> **Missing supervised-fine-tuning baseline.** The paper's three inference-time baselines (Negative Prompting, SLD*) and one fine-tuning baseline (EAR, Janus-Pro only) leave a key comparison off the table: plain supervised fine-tuning to safe anchor images (pairs of unsafe prompt → VQ-tokenized safe image, with standard cross-entropy). This is the AR analogue of Ablating Concepts (Kumari et al., 2023), a standard baseline in diffusion concept erasure. It also directly ablates OBLIVIATE's entire target-construction machinery — no pseudo-unconditional branch, no trajectory KL, no teacher guidance, just supervised learning to safe outputs. Without this comparison we cannot tell how much of OBLIVIATE's gain comes from the ESD-derived guidance versus how much comes from simply training on safe targets. Expected result based on diffusion-world precedent: the gap would be small on localized concepts like Coca-Cola and larger on diffuse concepts like nudity, which would actually sharpen the paper's story rather than hurt it.

**As a Rebuttal Item:**
> **Anchor-image supervised fine-tuning baseline.** For each concept, generate ~500 safe anchor images from a paraphrase prompt, tokenize with the VQ-VAE, and fine-tune the AR model on (unsafe prompt, safe image tokens) pairs with standard cross-entropy, matching OBLIVIATE's LoRA settings. Report CDR and FID on at least one concept × one model. This is likely a day of compute and would meaningfully strengthen the novelty story.

Want me to fold both into `claude_review.md`?

### User — 2026-04-21T02:34:32.147Z

Yes

### Assistant — 2026-04-21T02:34:38.994Z

[tool_use: Read]

### Assistant — 2026-04-21T02:35:01.394Z

[tool_use: Edit]

### Assistant — 2026-04-21T02:35:15.046Z

[tool_use: Edit]

### Assistant — 2026-04-21T02:35:23.410Z

Let me also update the Justification to mention this new gap, since it's a Major Weakness and the recommendation section should reflect it.

### Assistant — 2026-04-21T02:35:35.076Z

[tool_use: Edit]

### Assistant — 2026-04-21T02:35:48.754Z

Updated `claude_review.md` with the new baseline concern.

**Changes made:**

1. **Added a new Major Weakness** — "Missing supervised-fine-tuning baseline." Frames it as the AR analogue of Ablating Concepts (Kumari et al., ICCV 2023) and as the natural ablation of OBLIVIATE's entire target-construction pipeline. Notes the expected outcome pattern (close on localized concepts, larger gap on diffuse ones) as a useful finding rather than a threat to the paper.

2. **Added Rebuttal Item #9** — Concrete recipe: ~500 safe anchor images per concept, VQ-tokenize, fine-tune on (unsafe prompt, safe image tokens) pairs with plain CE at OBLIVIATE's LoRA settings. Frames compute cost honestly (a day or two per run) so the authors can't push back on feasibility.

3. **Updated the Justification** to mention the missing supervised-fine-tuning baseline alongside the other evaluation gaps, so the weakness properly carries weight in the overall recommendation.

Score stays at **5: Weak Accept**. This is now the third major weakness around baseline/ablation coverage (EAR-coverage, SLD\*-framing, and missing-SFT-baseline). Combined, they could plausibly push the score down to 4 if the authors don't address any of them in a rebuttal — but the prefix-alignment insight and cross-backbone empirical breadth still carry the score into accept territory on the current evidence.

### User — 2026-04-21T03:00:40.899Z

Have you humanize the review for LULU

### Assistant — 2026-04-21T03:00:49.267Z

No, I haven't — only the OBLIVIATE side got humanized (in `claude_review_updated.md`). The LULU review in `claude_review.md` is still in the original formal/AI-ish style. Let me fix that.

### Assistant — 2026-04-21T03:00:49.883Z

[tool_use: Read]

### Assistant — 2026-04-21T03:01:06.904Z

## Draft rewrite

Here's the plan: rewrite the LULU review section (lines 71–115) with a more natural voice — flowing prose where bolded-header bullets weren't carrying weight, real opinions where the original hedged, varied rhythm, and fewer AI tells. I'll keep the structure (Title / Summary / Strengths / Weaknesses / etc.) and all technical content intact.

## What makes the current LULU review obviously AI-generated?

- Every bullet starts with a bolded header + period + explanation (classic AI list format).
- "Elegantly sidesteps," "thoughtful piece of methodology," "compellingly," "well-motivated."
- Heavy em dashes.
- "I believe the contribution has real merit and could become" (sycophantic-hedge combo).
- Rule-of-three framing in the Justification.
- "Crucially," "Notably," signposting.

## Final rewrite

### Assistant — 2026-04-21T03:02:17.424Z

[tool_use: Edit]

### Assistant — 2026-04-21T03:02:35.287Z

Humanized the LULU review. All technical content, the recommendation (**3: Borderline Reject**), and the rebuttal asks stay intact.

**Changes made:**

- **Summary:** broke the wall-of-text into readable prose, cut the "(1)... (2)..." construction.
- **Strengths:** dropped the bolded-header bullet format in favor of flowing paragraphs. Replaced AI tells ("elegantly sidesteps," "thoughtful piece of methodology," "compellingly") with direct language ("sharp motivation," "nice piece of methodology"). Added real voice ("The literature has mostly hand-waved this away," "That's exactly what you want from a safety guardrail").
- **Major Weaknesses:** dropped the bolded headers, turned each into a punchy paragraph with opinions. Key rewrites: "The evaluation scope is the big problem" (instead of "Narrow experimental scope"), "Inference cost gets zero discussion" (instead of "No inference-cost accounting"). The NSFW/style/identity critique now lands with more force: "You can't claim a safety contribution and then only demonstrate benign object substitution."
- **Minor Weaknesses:** mostly kept the bulleted format since they're genuinely discrete nits, but dropped AI-ish phrases like "commendably honest" and tightened the prose.
- **Justification:** cut "I believe the contribution has real merit and could become" (sycophantic-hedge combo), replaced rule-of-three framing with more direct language. Added the concrete contrast: "Showing the method works on COCO objects at SD v1.4 is not the same as showing it works on nudity, style, or identity — and the gap between 'object substitution' and 'content moderation' is where safety methods tend to fail."
- **Rebuttal:** dropped the bolded-header bullets; each item is now a direct ask in plain language.

The review now matches the voice of the humanized OBLIVIATE review in `claude_review_updated.md`.

### User — 2026-04-21T03:02:41.479Z

please revert

### Assistant — 2026-04-21T03:04:04.916Z

[tool_use: Edit]

### Assistant — 2026-04-21T03:04:10.908Z

Reverted. The LULU review in `claude_review.md` is now back to the original bolded-header bullet format, matching the style of the OBLIVIATE review in the same file.

### User — 2026-04-21T03:16:17.673Z

Our results show that feature-level detection generalizes 067 068 substantially better to indirect and correlation-driven prompts than token-based 068 069 baselines

genralizes to what?

### Assistant — 2026-04-21T03:17:00.910Z

Good catch — this is one of those sentences that reads confidently but leaves ambiguous exactly what's been demonstrated. Let me unpack what's actually being claimed.

## What the paper means by "generalizes substantially better"

The claim is narrow, despite the rhetoric. Concretely, it means:

**Within the EMMA benchmark on Stable Diffusion v1.4, LULU's Erasing Ability (EA) degrades less than token-based methods do when the prompt *describes the concept indirectly instead of naming it*.**

That's it. The generalization is **across prompt phrasings for the same concept**, not across backbones, domains, or concept types.

EMMA tests each target concept with five prompt variants:
- **Name** — "a cat"
- **Prefix** — "a cat sitting on a mat"
- **Variant** — paraphrases / synonyms
- **Short** — brief description without the word "cat"
- **Long** — elaborate description without the word "cat"

Token-based methods (ESD, UCE, MACE, CA) do fine when the concept name is in the prompt — they hook onto the token for "cat." They degrade on **Short** and **Long** prompts because there's no "cat" token to hook onto. LULU is the same across all five, because it looks at visual features rather than tokens. That's the "generalizes better" claim.

## What "correlation-driven prompts" means

This is the EMMA **Similar** setting on the retention side. A retention concept is considered "correlation-driven" or "visually similar" when it shares visual features with the target — e.g., if you erased "cat," does a "dog" prompt still produce a dog, or does the eraser bleed damage into nearby animals? Token-based methods often over-erase because the text embedding for "dog" sits near "cat" in embedding space. LULU, operating on visual features, is supposed to distinguish them better.

So "correlation-driven prompts" in the paper's language means *prompts for concepts correlated with the target through visual co-occurrence*, not prompts that describe the target through correlation. The grammar is a bit ambiguous.

## Why your question matters for the review

The sentence implies a broad generalization claim that the experiments don't actually support. What LULU has shown:

- ✅ Generalizes across **prompt phrasings** for the same concept (EMMA Name/Prefix/Short/Long)
- ✅ Generalizes across **visually-similar retention concepts** on the same backbone (EMMA Similar)

What LULU has *not* shown but the rhetoric suggests:

- ❌ Generalizes across **concept domains** (only COCO objects tested; no NSFW, style, identity)
- ❌ Generalizes across **backbones** (only SD v1.4)
- ❌ Generalizes across **prompt distributions** (detector trained on LLM-generated prompts, not real users)
- ❌ Generalizes to **adversarial prompts** (untested)

This is exactly the evaluation-scope-vs-framing mismatch I flagged as the main weakness. The "generalizes substantially better" language does real rhetorical work in the intro — readers come away thinking "this method is a robust safety mechanism" — but what it empirically means is "this method survives prompt paraphrasing on benign object-substitution benchmarks within SD v1.4."

If I were the author, I'd either:
- Tighten the sentence to say "generalizes substantially better **across prompt phrasings for the same concept** than token-based baselines," or
- Run the experiments that would actually support the broader claim.

Want me to add this specific framing issue as an explicit minor weakness in the LULU review? It's somewhat covered by the existing "Narrow experimental scope" major weakness, but the sentence you highlighted is a clear case of the framing outrunning the evidence, and calling it out line-by-line can be more actionable for the authors in a rebuttal.

### User — 2026-04-21T03:17:07.025Z

Yes

### Assistant — 2026-04-21T03:17:24.352Z

[tool_use: Edit]

### Assistant — 2026-04-21T03:17:33.804Z

Added the overreaching-generalization-claim critique as a new minor weakness, with specific line references (067–069) and a concrete rewrite suggestion the authors can act on directly. It ties back to the broader evaluation-scope-vs-framing mismatch in the Major Weaknesses without duplicating it.

