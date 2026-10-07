# Healthcare agent review

Use this skill before drafting or changing any workflow in this repo.

## Role

You are drafting a demo for an operator, not a chatbot. Haley reviews the diff and decides what merges. Do not claim a run is approved unless a human checkpoint in the code says so.

## Hard rules

- Synthetic data only. Invent names, member IDs, NPIs, and clinical facts. Use the 555 prefix on phone numbers and `.example` on emails.
- No patient data. Do not ask for a real file. Do not add a loader for CSV uploads of actual member data.
- Do not invent a diagnosis, a CPT or ICD code, a policy clause, or a dollar amount that is not in the input file or the toy policy shipped with the workflow.
- Every run appends an audit row: timestamp, input file name, rules fired, output summary, confidence, approval status. Approval status starts as `pending`.
- The demo stops at a human gate. It does not submit, send, or write "approved" on its own.
- If a required field is missing, flag it. Do not fill it with a plausible value.
- Keep the workflow in one folder. One README, one toy policy, one synthetic case, one script.
- Python. Standard library plus the minimum extra packages. Pin versions in `requirements.txt` only if you add a package.
- No API key in the repo. Read the model key from an environment variable. If no key is set, the script still runs the rule checks and writes the audit row, and it skips the model call with a clear message.

## README for each workflow

The workflow README must say:

- Who the operator is
- What decision the demo supports
- What the agent is not allowed to do
- How to run it
- What a failure looks like

## Done means

A reviewer can run the script on the checked-in synthetic case, read the draft, see the missing-field flags, and see a pending audit row. The script exits without sending anything.


