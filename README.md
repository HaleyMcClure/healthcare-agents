# Healthcare Agents

A set of governed workflow demos for prior authorization, denial appeals, revenue cycle, clinical operations, and population health. Each one tackles a real problem that healthcare teams face every day, and each one is built to show not just what an agent can do, but how it should be controlled.

Everything here runs on synthetic data. There is no patient data in this repository, and nothing here is a production system.

Started in October 2026 by [Haley McClure](https://github.com/Haley-ideate).

## Rules for every workflow

Every workflow in this repository follows the same six rules.

1. **It does one operator job.** Each README names who uses the workflow and what decision it supports.
2. **It runs on synthetic inputs** stored in `data/synthetic/`. Every name, member ID, and clinical fact is invented.
3. **It leaves an audit trail.** Every run records what went in, what came out, which rule fired, and whether a human approved the result.
4. **A human signs off** before anything is treated as submitted, sent, or final.
5. **It does not make things up.** The agent never invents a diagnosis, a policy clause, or a dollar amount that is not in the input or the sample policy.
6. **It is honest about its limits.** A `NOT_FOR_PRODUCTION.md` file in each workflow explains what a real deployment would still need.

## Status

| Workflow | Status |
| --- | --- |
| Prior authorization packet | Scaffolded, with a synthetic case checked in. Agent not yet built. |
| Governance review | Not started |
| Denial appeal | Not started |
| Revenue cycle variance | Not started |
| Clinical huddle | Not started |
| Population health outreach | Not started |

## Build order

1. **Prior authorization packet agent.** It takes a synthetic referral and a sample payer policy, drafts the authorization packet, flags missing fields, writes an audit record, and stops for human approval.
2. **Governance review agent.** It reads the design of a workflow and returns a checklist of the controls it has and the ones it is missing.
3. **The remaining four workflows,** built on the same foundation.
4. **An evaluation set** of 25 synthetic cases run against the first two agents, with any failures documented.

## Rights

Copyright Haley McClure. All rights reserved.

You are welcome to read this repository and link to it. Please do not copy it into another product, republish it, or use it commercially without my written permission.
