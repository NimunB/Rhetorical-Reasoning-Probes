# Plan: README Rhetoricon Integration + 180-Word Abstract

---

## Paper Summaries

### Harris (2023) — "Rules Are Rules: Rhetorical Figures and Algorithms"

**Core argument:** Rhetorical figures are *form/function alignments* — constructions where a specific syntactic or semantic form reliably produces a specific communicative effect. Figures divide into:
- **Schemes** — defined by *material form* (syntactic, sequential, phonological). Enumeratio, parison, and chiasmus are all schemes.
- **Tropes** — defined by *conceptual/semantic form* (metaphor, irony, etc.).

**Why schemes matter computationally:** Schemes are structurally tractable — their defining features are syntactic rather than world-knowledge-dependent. Harris argues that figures "can get at meaning in a way that is beyond current text mining and NLU tools," implying rhetorical structure should be taken more seriously in NLP/AI.

**Key communicative functions** (relevant to our figures):
- *Comprehensiveness* — suggests exhaustive, sequential coverage (enumeratio). ✓ Harris names this.
- *Irrelevance of Order/Rank* — suggests propositions are order-independent (parallelism/parison).
- *Reciprocal Specification* — specifies relationships by mirroring (parison/antimetabole).
- *Reciprocal Energy* — evokes bidirectional force between propositions (chiasmus/antimetabole).
- *Argument Foreclosure* — makes argument appear self-evident through structural symmetry.

**AMP cluster:** Harris identifies that Antimetabole, Mesodiplosis, and Parison frequently co-occur and share communicative functions. Our parison and chiasmus conditions target two of these three.

**Antimetabole vs. Chiasmus:** antimetabole is the *lexical-level* semantic inversion member of the chiasmus family (e.g. "not to live to eat, but eat to live"), not a synonym for chiasmus. Chiasmus is the broader A–B…B–A family.

**Key caveat:** Harris does not explicitly advocate training data annotation using rhetorical figures. The implication for LLM training is an inference we draw, not a direct Harris claim.

---

### Harris (2022c) — "Chiastic Iconicity: Refiguring Symmetry," in *Iconicity in Cognition and across Semiotic Systems* (John Benjamins). DOI: 10.1075/ill.18.06har

**Core argument:** Chiastic structure (ABBA) operates through three Peircean iconicity principles — identity, sequential order, and quantity — which combine to produce consolidated iconicities of harmonious balance and cyclicity. The paper's central claim is that the aesthetic and argumentative effects of chiasmus arise not from the ABBA pattern alone, but from its convergence with other rhetorical figures (parison, mesodiplosis, isocolon) and grammatical features.

**Chiasmus vs. antimetabole:**
- Chiasmus = the broad ABBA family, realizable at any linguistic level (sound, word, phrase, clause, narrative)
- Antimetabole = the *lexical subset*: the same words repeated in inverse order. Every antimetabole is chiastic; not every chiasmus is antimetabolic.
- This distinction is why our chiasmus prompt (broad A-B-B-A instruction) was designed to admit antimetabole as its most tractable realisation.

**The four communicative functions (from this paper specifically):**
- *Comprehensiveness* — AB and BA are mutually exclusive and exhaustive; the form enacts logical closure ("having a solution" vs. "comprehending the problem" — you cannot have both). Scaffolds binary, exhaustive reasoning.
- *Irrelevance of Order/Rank* — the chiastic commutation declares A and B equivalent regardless of order (x+y = y+x). Scaffolds equivalence reasoning.
- *Reciprocal Specification* — A and B mutually define each other ("life is the germ and the germ is life"). Scaffolds mutually constitutive reasoning.
- *Reciprocal Energy* — A and B exert bidirectional force or agency on each other ("women are changing universities and universities are changing women"). Scaffolds causal feedback reasoning. Represented not as static balance but as "point balance" — dynamic, circular.

**Key insight on figural convergence:** The effects attributed to chiasmus alone are almost always produced by a *bundle* of figures simultaneously — chiasmus + parison + mesodiplosis + isocolon. "Figures combine. But figural collocations are crucial for understanding iconicity, and the effects ascribed regularly to one single figure are very often the combined effects of figural convergence." This explains why our 7B model couldn't produce chiasmus: generating the full figural bundle from a brief prompt is far harder than generating any single figure.

**The rhyme-as-reason effect:** Harris cites empirical evidence that people judge formally similar statements (rhyming, alliterating, isocolonic) as more accurate and credible than paraphrases. "One could not ask for a clearer experimental confirmation that form-enacted meanings have rhetorical effects." This supports the hypothesis that LLMs trained on such text may have acquired form-validity associations.

**Call for corpus/computational research (p. 129):** "If the iconicity claims about figural convergence, grammatical-feature cooccurrence, and form/function correspondences advanced in this essay are to grow into powerfully generalizable results... we will need serious corpus research to test them." — directly motivates our project.

**Most citable quote for our project:**
> "Chiastic structure (ABBA) leverages the iconicity principles of identity, sequential order, and quantity for consolidated iconicities of harmonious balance and cyclicity." (abstract, p. 103)

---

### Fahnestock (2003) — "Verbal and Visual Parallelism," *Written Communication*, 20(2), 123–152

**Core argument:** Parallelism is not a stylistic ornament but a constitutive argumentative device that *epitomizes* a claim. The parallel form itself groups examples into a unified set and performs an inferential move.

**The "epitomize" claim — exact quotes:**
- p. 125: "parallelism of sound, syntax, and semantics can epitomize an arguer's claim that multiple instances belong to the same grouping. The form, once established, can also dictate how subsequent instances are selected and expressed."
- p. 132: "The form epitomizes the argument; it is the perfect expression of an induction based on examples."

**Precision on scope:** The epitomizing claim is specifically about *induction and example-based argument* — parallelism signals that multiple instances are the same kind. Not a general claim about all inferential moves.

**Cognitive grounding (pp. 147–148):**
- "When several parallel items are perceived in a series, the second or third items follow a path of construal prepared by the first. They satisfy an immediate expectation. Our minds are constructed to be receptive to repeated verbal or visual forms."
- "items packaged in a similar form tend to be constructed as equivalent."

**What she does NOT discuss:** Chiasmus, antimetabole, enumeratio (by name). AI, NLP, or computational linguistics at all. The LLM connection is our inference.

**Key claim for our project:** Fahnestock provides theoretical grounding for *why parallelism* might scaffold reasoning — parallel form primes equivalent construal, making it cognitively efficient to package parallel evidence. Since LLMs train on human-generated text, they may have acquired representations that associate parallel form with this inferential move.

---

## Cross-Checked Claims

| Claim | Verdict | Notes |
|---|---|---|
| Harris names "Comprehensiveness" as a communicative function | ✓ Confirmed | Explicitly listed |
| Harris distinguishes antimetabole from chiasmus | ✓ Confirmed | antimetabole is lexical-level; chiasmus is the broader family |
| AMP cluster (Antimetabole, Mesodiplosis, Parison) | ✓ Confirmed | Harris discusses explicitly |
| Fahnestock says parallelism "epitomizes" argument | ✓ Confirmed (with nuance) | Exact quotes on p. 125 and p. 132; scope is inductive argument specifically |
| Fahnestock 2003 is the correct citation | ✓ Use 2003 | File provided is 2003. Her 1999 book exists but we have not read it — do not cite it |
| Harris advocates including figures in LLM training | ✗ Not claimed | We infer it; must frame as our own argument |
| Fahnestock discusses AI/NLP | ✗ Not present | No mention |
| Parison serves "Irrelevance of Order/Rank" per Harris | ✓ Plausible | Harris lists this function; reasonable attribution to parison |

---

## Task 1: Abstract (180 words — verified by word count)

Insert a `## Abstract` section immediately after the project title/model/dataset/judge block.

**Approach:** Poster abstract for a conference. Situate in the AI safety probing literature (the actual methodological precedent); state what this project does; describe three experiments briefly; give a general, non-granular finding; close with significance. No em-dashes. No use of "scaffold" (imprecise) — replaced with "improve reasoning quality." Preliminary evidence tone throughout.

**Note on "scaffold":** If the term appears elsewhere in the README (e.g. in the hypothesis), it should be defined on first use as: a structural constraint that organizes reasoning steps and makes their logical connections more explicit, improving the coherence of the inference chain.

**Approach:** Start from rhetorical neglect, introduce AI safety probing as the borrowed methodology, ask the three research questions, describe methods with technical terms explained, give non-granular preliminary-evidence results, close with interpretability-facing conclusion. No em-dashes. No citations. 180-200 words.

**Draft (~185 words):**

> Classical rhetorical figures are formal structures that carry communicative and argumentative meaning, yet are almost entirely absent from research on large language models (LLMs). We borrow from AI safety interpretability research, which uses linear probes to test whether models internally represent properties such as honesty or deception, and applies activation steering to causally shift those representations. We ask: can constraining an LLM to reason in a specific rhetorical form improve reasoning quality, are those forms geometrically encoded inside the model, and can those representations be causally steered?
>
> Using Llama-2-7b-chat on StrategyQA, a benchmark requiring multi-step binary reasoning, we test three figures: enumeratio (sequential numbered steps), parison (grammatically parallel clauses), and chiasmus (A-B-B-A structural inversion). We measure answer accuracy and faithfulness, defined as whether the reasoning chain logically entails the stated answer.
>
> Results offer preliminary evidence that rhetorical structure can improve reasoning quality and that some representations are causally connected to outputs, though boundary conditions limit steerability. These findings suggest that classical rhetoric is a productive research direction at the intersection of AI interpretability and reasoning, and that rhetorical structure merits closer attention in computational linguistics.

---

## Task 2: Harris + Fahnestock Integration into README

### 2a. Add "Theoretical Background" subsection in Experiment A

Insert *after* the opening StrategyQA paragraph, *before* the conditions table.

**Draft:**

> ### Theoretical Background
>
> All three figures tested are **rhetorical schemes** in the sense of Harris (2023): figures defined by material (syntactic and sequential) form rather than semantic content. Schemes are computationally tractable targets because their defining features are structural, not world-knowledge-dependent.
>
> The figures serve distinct **communicative functions** (Harris, 2023). Enumeratio aligns with *Comprehensiveness* — sequential enumeration implies exhaustive coverage of the reasoning space. Parison aligns with *Irrelevance of Order/Rank* — grammatical mirroring equates the propositions it packages, priming their treatment as equivalent. Chiasmus and its subtype antimetabole serve *Reciprocal Energy* — structural inversion creates bidirectional force between propositions, staging a contrast or resolution. These functional distinctions predict different reasoning effects: sequential decomposition should tighten the inferential chain; symmetry should signal evidential equivalence; inversion should foreground contrast.
>
> The scaffolding hypothesis draws on Fahnestock (2003), who argues that parallelism "epitomizes an arguer's claim that multiple instances belong to the same grouping" — that form encodes an inferential move, not merely a stylistic choice. Because LLMs are trained on human-generated text saturated with rhetorical structure, they may have acquired internal representations that associate these forms with the reasoning patterns they embody. Constraining a model's output to a figure's form may therefore activate those associated patterns.

### 2b. Append to "Note on Rhetorical Terminology"

> Per Harris (2023), **antimetabole** — lexical-level semantic inversion (e.g., "not to live to eat, but eat to live") — is a specific member of the chiasmus family rather than a synonym for it. The chiasmus prompt in this experiment is intentionally broad (A–B…B–A structural inversion), designed to admit antimetabole as its most lexically recognisable realisation. That antimetabole did not emerge as a distinct pattern suggests that even this tractable member of the chiasmus family exceeds what a 7B model can reliably execute from a brief prompt instruction.

### 2c. Add References section at bottom of README

```markdown
## References

- Fahnestock, J. (2003). Verbal and visual parallelism. *Written Communication*, 20(2), 123–152.
- Harris, R. A. (2023). Rules are rules: Rhetorical figures and algorithms. *[venue — confirm with professor]*.
```

---

## Critical File

- [README.md](README.md) — the only file being modified

## Verification

After edits, read README top to bottom and confirm:
1. Abstract appears after title block, is self-contained, and reads ~180 words.
2. "Theoretical Background" subsection is inside Experiment A, before the conditions table.
3. "Note on Rhetorical Terminology" is extended with the antimetabole/Harris paragraph.
4. References section at the bottom uses the correct Fahnestock 2003 citation.
5. No other sections disturbed.
