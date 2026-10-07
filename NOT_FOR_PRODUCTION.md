# Not for production

These workflows are design demos. They have not been cleared to touch a covered entity, a payer platform, or a patient, and they should not be used that way.

Moving any of them into production would take real work. The list below covers the minimum, not everything:

- **A signed BAA** with whoever hosts the model and stores the logs.
- **Access control tied to a real workforce identity,** not a shared API key sitting in a notebook.
- **An evaluation set drawn from the actual workflow,** reviewed by the operator who owns the decision.
- **Retention and deletion rules** for prompts, outputs, and audit records.
- **An escalation path** for low confidence, missing fields, and conflicts with policy, so the agent knows when to stop and hand off.
- **Monitoring for drift** between the sample payer policy used here and the real policy, which will change over time.
- **A named human owner** for every approval gate, so accountability sits with a person and not a process.

Until all of that exists, the only allowed inputs are the files in `data/synthetic/`.

I hold this rule for my own work too. If a coding agent ever suggests using a real export, a scraped clinical note, or a live payer portal, I would reject the change.
