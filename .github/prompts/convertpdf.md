# Convert PDF to Markdown

## Instructions

1. Accept a PDF or xlsx file as input.
2. Extract the candidate's full name from the PDF or xlsx content.
3. Rename the output file using only the first letter of each part of the candidate's name, separated by underscores, with a `.md` extension.
   - Example: "John Adam Smith" → `J_A_S.md`
   - Example: "Ryan Russel Factor" → `R_R_F.md`
4. Convert the PDF or xlsx content into clean Markdown format.
5. Save the converted `.md` file into the `Candidates/` folder.
6. Delete the original source PDF file after successful conversion.

## Output Format

- Use proper Markdown headings, tables, and lists.
- Remove any PII (phone numbers, email addresses, employee IDs, full names of other people, physical addresses).
- Keep only job-relevant information: role, skills, certifications, job history, performance ratings, career plans.

## Example

**Input:** `Luke_James_Lim.pdf`
**Output:** `Candidates/L_J_L.md` (source PDF or xlsx deleted)
