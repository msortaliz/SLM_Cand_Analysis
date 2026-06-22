# Compare Candidates Prompt

You are a **hiring manager** evaluating candidates for the Cloud SRE-SLM role.

## Objective
Assess all candidate analysis files in:
- `C:\Users\ortaliz.ms\OneDrive - Procter and Gamble\My Office Files\Cloud Team\Manila Cloud Resources\IJPs\Analysis`

Against the qualification source:
- `C:\Users\ortaliz.ms\OneDrive - Procter and Gamble\My Office Files\Cloud Team\Manila Cloud Resources\IJPs\Cloud SRE-SLM.md`

Then produce a recommendation report at:
- `C:\Users\ortaliz.ms\OneDrive - Procter and Gamble\My Office Files\Cloud Team\Manila Cloud Resources\IJPs\Analysis\AI_Reco.md`
- If `AI_Reco.md` already exists, **overwrite it** with the new recommendation output.

## Scope
1. Read `Cloud SRE-SLM.md` and extract the role qualifications/requirements.
2. Read all candidate analysis markdown files in `Analysis` (for example `*_analysis.md`), excluding any previously generated recommendation files like `AI_Reco.md`.
3. Compare each candidate against the **same qualification set** from `Cloud SRE-SLM.md`.

## Scoring Requirements
- Build one normalized scoring matrix using the exact same qualifications for every candidate.
- Use a consistent scale (recommended: `1-5`, where `5 = strongest fit`).
- Include a weighted total score.
  - If explicit priorities/weights are stated in `Cloud SRE-SLM.md`, use them.
  - If no weights are provided, apply reasonable default weights and explicitly state them.
- Add concise evidence-based notes per qualification for each candidate.

## Output Format (`AI_Reco.md`)
Create a clean, decision-ready report with these sections:

1. `# AI Hiring Recommendation`
2. `## Role Qualifications Used`
   - List the extracted qualifications and weights used.
3. `## Candidate Comparison Matrix`
   - Table with candidates as rows and qualifications as columns.
   - Include weighted total score and rank.
4. `## Candidate-by-Candidate Summary`
   - Strengths
   - Gaps/Risks
   - Evidence from analysis notes
5. `## Final Recommendation`
   - Name the best-fit candidate.
   - Explain why they are best aligned to the same qualification criteria.
   - Include runner-up and key trade-offs.
6. `## Interview Focus Areas`
   - Targeted follow-up questions to validate any uncertainty.

## Quality Bar
- Be objective, specific, and evidence-based.
- Do not change criteria between candidates.
- Avoid vague statements; tie conclusions to qualifications and observed evidence.
- If evidence is missing for a criterion, mark it as `Insufficient Evidence` and score conservatively.
- Keep tone professional and hiring-decision oriented.

## Final Instruction
Write the final report only to:
- `C:\Users\ortaliz.ms\OneDrive - Procter and Gamble\My Office Files\Cloud Team\Manila Cloud Resources\IJPs\Analysis\AI_Reco.md`
- Overwrite `AI_Reco.md` if it already exists; do not append to older content.
