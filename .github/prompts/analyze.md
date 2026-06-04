---
description: "End-to-end candidate analysis: convert PDF to markdown, generate interview question bank, and push changes to GitHub."
name: "Analyze Candidate"
agent: "agent"
---

You are an automated candidate analysis pipeline. Execute the following steps in order:

## Step 1 — Convert PDF to Markdown

Run the `convertpdf` prompt workflow:

1. Accept the PDF file as input.
2. Extract the candidate's full name from the PDF content.
3. Rename the output file using only the first letter of each part of the candidate's name, separated by underscores, with a `.md` extension (e.g., "John Adam Smith" → `J_A_S.md`).
4. Convert the PDF content into clean Markdown format.
5. Save the converted `.md` file into the `Candidates/` folder.
6. Delete the original source PDF file after successful conversion.
7. Use proper Markdown headings, tables, and lists.
8. Remove any PII (phone numbers, email addresses, employee IDs, full names of other people, physical addresses).
9. Keep only job-relevant information: role, skills, certifications, job history, performance ratings, career plans.

## Step 2 — Generate Interview Question Bank & Analysis

Run the `prompt` workflow using the converted candidate markdown from Step 1:

1. Infer the candidate's skill level from their resume (years of experience, seniority titles, complexity of projects, technologies used). State your assessment briefly.
2. Perform initial assessment of candidate's qualifications against `Cloud SRE-SLM.md`. Score each skill from 1-5 and explain why.
3. Generate questions and model answers organized into three tiers (Foundational, Intermediate, Experience-Specific). Each question must include the question itself, what a strong answer should cover, and an optional follow-up probe.
4. Calibrate difficulty to the candidate's level.
5. Remove PII from the analysis, place the analysis in the `Analysis/` folder named as the first letter of each part of the candidate's name (e.g., `A_B_C_analysis.md`), and delete the source candidate file from `Candidates/`.

## Step 3 — Push Changes to GitHub

After completing the analysis:

1. Stage all changes: `git add -A`
2. Commit with message: `feat: add analysis for [candidate initials]`
3. Push to the remote repository: `git push`

---

## Important Notes

- Execute each step sequentially — do not proceed to the next step until the current one is complete.
- If any step fails, report the error and stop.
