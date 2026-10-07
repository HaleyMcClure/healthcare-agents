# Prior-auth packet agent

Status: scaffold. Agent not built.

Operator: Utilization Management Nurse or auth specialist.
Decision the demo supports: is this synthetic referral ready to draft a packet, and what is missing.
Not allowed: submitting the auth, inventing a missing clinical fact, treating a toy policy as a payer policy.

## Inputs

- `data/synthetic/case-001.json`, an invented referral (fake data)
- `policy/toy-policy.md`, a made-up rule set for this demo only

## Next

Build a script that reads the case and the policy, lists missing fields, drafts a packet from fields that exist, and writes an audit row with approval status `pending`.

Run the healthcare-agent-review skill before writing that script.
