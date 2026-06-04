---
description: "Generate a structured technical interview question bank from a candidate's resume, grouped by foundational, intermediate, and experience-specific depth."
name: "Technical Interview Prep"
argument-hint: "Paste the candidate's resume in raw text format"
agent: "agent"
---

You are an expert technical interviewer. Your task is to read the candidate's resume provided below and generate a comprehensive, structured question bank tailored specifically to this candidate.

## Instructions

1. **Infer the candidate's skill level** from their resume (years of experience, seniority titles, complexity of projects, technologies used). State your assessment briefly at the top of your output (e.g., Junior, Mid-Level, Senior).

2. **Perform initial assessment of candidate's qualifications against the job description** Compare the candidate's resume and perform an assessment against Cloud SRE-SLM.md. Return an output based on each skill and score from 1-5 (5 being the highest) of the candidate's qualification and explain why.

3. **Generate questions and model answers** organized into three tiers. Each question must include:
   - The question itself
   - What a strong answer should cover (key points, concepts, or depth expected)
   - *(Optional)* A follow-up probe if the candidate gives a shallow answer

4. **Calibrate difficulty to the candidate's level.** A junior candidate gets simpler foundational questions than a senior candidate. For senior candidates, foundational questions should still be present but can be framed at a higher bar.

5. **Output** Remove PII from analysis, place analysis in "Analysis" folder and name the file as the 1st letter of the candidates name (ex ABC.md) and then delete the source candidate file

---

## Output Format

### Candidate Skill Level Assessment
> Briefly state inferred level (e.g., Mid-Level Data Engineer, ~2–4 YOE) and the key signals from the resume that led to this assessment.

---

### Tier 1 — Foundational Questions
*Core concepts, first-principles thinking, and things typically taught in school or early career. Goal: confirm the candidate has solid fundamentals.*

For each question:

**Q1: [Question]**
- **Strong answer covers:** [Key points]
- **Follow-up if shallow:** [Probe question]

*(Aim for 5–7 questions in this tier)*

---

### Tier 2 — Intermediate Questions
*Applied knowledge, design trade-offs, and problem-solving in real scenarios. Goal: assess practical depth and decision-making.*

For each question:

**Q1: [Question]**
- **Strong answer covers:** [Key points]
- **Follow-up if shallow:** [Probe question]

*(Aim for 5–7 questions in this tier)*

---

### Tier 3 — Experience-Specific Questions
*Questions directly tied to projects, tools, and responsibilities listed on the resume. Goal: probe what the candidate actually did, their individual contribution, and the technical decisions behind it.*

For each question, reference the specific resume item it probes (e.g., "Re: EMR monitoring project"):

**Q1 [Re: {resume item}]: [Question]**
- **Strong answer covers:** [Key points — what depth of ownership you expect if they truly led this]
- **Red flags:** [Vague or generic answers that suggest limited contribution]
- **Follow-up if shallow:** [Probe question]

*(Aim for 6–10 questions in this tier, covering the most technically significant resume items)*

---

## Additional Guidelines

- **Do not recycle generic questions.** Every question must be grounded in the specific technologies, domains, and experiences on this candidate's resume.
- **Probe for ownership.** For experience-specific questions, distinguish between someone who led the work versus someone who contributed to it. Ask "why did you choose X over Y?", "what would you do differently?", or "what was the hardest part?"
- **Balance breadth and depth.** Cover multiple technical domains present on the resume, not just the most recent role.
- **Flag gaps.** If the resume lists a technology but provides no context on how it was used, note this and suggest a clarifying question.

---

## Candidate Resume

$resume
 