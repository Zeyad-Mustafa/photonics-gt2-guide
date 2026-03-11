# Content Guidelines

## The Purpose of This Guide

This guide is written for someone who has never used a GT2 before. The target reader is a new graduate student, a researcher from a different field who has just gained access to the machine, or an engineer evaluating the system for a new application. They are intelligent and technically capable, but they have no assumed background in photonics, nanofabrication, or laser physics.

Every contribution must serve that reader. Ask yourself: if someone read this file on their first day in the lab, would it make sense to them? If the answer is no, more context is needed.

---

## Tone and Voice

Write in plain, direct prose. Avoid jargon where plain English works. When technical terms are necessary, introduce them with a brief explanation on first use.

Good: "The resin drop must be semi-spherical — a drop that has spread flat into a thin puddle will prevent the machine from detecting the substrate surface."

Not good: "Adequate meniscus geometry is requisite for optimal interface finder performance."

Do not use bullet points as a substitute for explanation. A list of facts with no connecting logic is not a useful guide. Write in sentences and paragraphs. Use lists only for procedures with discrete numbered steps, or for compact comparison data that genuinely needs tabular format.

Do not hedge excessively. "It might possibly be the case that in some situations the development time could perhaps be insufficient" is not useful. "If your structure has internal channels, add 5 to 10 minutes to the development time" is useful.

Do not use emojis anywhere in the guide. The tone is technical and professional.

---

## Formatting Rules

Headings: use a single top-level heading (H1, one hash) for the file title. Use H2 (two hashes) for major sections. Use H3 (three hashes) sparingly for subsections within a major section. Do not use H4 or deeper.

Tables: use Markdown tables for structured comparative data. Every table must have a header row. Column headers must be descriptive. Do not use tables to present information that reads more naturally as prose.

Code blocks: use fenced code blocks (triple backtick) for GWL code, command-line instructions, and file paths. Do not use code blocks for general text or for emphasis.

Bold text: use sparingly, only for genuinely critical warnings or key terms on first introduction. Do not bold entire sentences or use bold for decorative emphasis.

File naming: all new files must use lowercase letters, underscores instead of spaces, and the .md extension. No special characters. No spaces. Examples: development_times_table.md, fiber_ring_installation.md.

---

## What Belongs in This Guide

Factual, actionable information about operating the GT2, preparing samples, using the software, and characterizing results.

Parameter values that have been verified by actual use on a GT2 system.

Explanations of why a procedure works the way it does — not just what to do, but what happens physically or chemically when you do it.

Clearly documented warnings about failure modes, irreversible mistakes, and safety hazards.

Cross-references to other sections of the guide where relevant.

---

## What Does Not Belong in This Guide

Promotional language. This guide is not an advertisement for the GT2 or for Nanoscribe. State capabilities accurately without exaggeration.

Speculation. If you are not certain a parameter value or procedure is correct, do not include it. Open an issue asking for clarification instead.

Content copied from Nanoscribe's own documentation, application notes, or website. Paraphrase and synthesize rather than reproduce.

Content copied from academic papers. Cite the paper and describe the result in your own words.

Personal anecdotes without practical value. "In my lab we always do it this way" is not a sufficient basis for a procedure unless the procedure is accompanied by an explanation of why it works.

Application examples from Section 10 that are not supported by at least one published result. New application files should reference at least one paper demonstrating the claimed capability.

---

## Accuracy Standards

Parameter values (laser power percentages, development times, voxel sizes) must be consistent with values reported in the Nanoscribe documentation or in peer-reviewed literature. If you are proposing a change to a parameter value, explain briefly in your pull request description why the current value is wrong and what evidence supports the new value.

Resin compatibility claims must be consistent with Nanoscribe's published compatibility information. Do not claim a resin is compatible with an objective if Nanoscribe's documentation does not support this.

Safety information must be conservative. If there is any doubt about whether a statement is accurate, do not include it. Errors in the safety section are more serious than errors elsewhere.

---

## Adding a New Application File to Section 10

New application files are optional contributions. If you want to add a new entry to Section 10, the file must follow this structure:

1. Why the GT2 is used for this application (one to two paragraphs)
2. What specific devices or structures can be fabricated
3. Recommended objective and resist combination with justification
4. Design considerations specific to this application
5. At least one representative published result with full citation (authors, title, journal, year, DOI)
6. Limitations of the GT2 for this application

Do not submit an application file without a representative published result. The result does not have to be from a Nanoscribe system specifically, but it must demonstrate the claimed capability using two-photon polymerization.

---

## Updating the Main README

If your contribution adds a new file, update the table of contents in the relevant section README.md to include the new file. Do not modify the main repository README.md (the root README.md) without first opening an issue — the main README is the public face of the project and changes to it require maintainer review.
