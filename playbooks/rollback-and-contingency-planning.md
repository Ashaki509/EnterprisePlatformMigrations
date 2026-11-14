# Rollback and Contingency Planning

A rollback plan answers one question before cutover starts: if this goes wrong, how do we return to a working state, and who decides? This playbook covers rollback triggers, decision authority, the point of no return, and contingencies for the most common failure scenarios.

---

## Principles

- Write the rollback plan before the cutover plan is approved.
- Define the triggers in advance, so the decision during cutover is a check against criteria.
- Name one person with the authority to call a rollback.
- Test the rollback. A plan that has never been run is an assumption.
- Know the point of no return and get explicit approval before crossing it.

---

## Rollback Triggers

Agree on the triggers with the sponsor and system owners during planning. Fill in thresholds that fit your platform.

| Trigger | Threshold | Measured by |
|---------|-----------|-------------|
| Data validation failure | Record counts or checksums differ by more than [X] | Validation script |
| Performance degradation | Response time above [X] for [Y] minutes | Monitoring |
| Error rate | Above [X]% for [Y] minutes | Monitoring |
| Critical function unavailable | Any function on the critical list fails testing | Smoke test |
| Cutover window exceeded | Step [N] not complete by [time] | Runbook clock |
| Security or compliance control missing | Any required control fails verification | Security checklist |

---

## Decision Authority

| Role | Responsibility |
|------|----------------|
| Cutover lead | Monitors the triggers and recommends continue or roll back |
| Rollback decision owner | Makes the call. One named person, with a named backup. |
| Technical leads | Confirm system state and carry out the rollback steps |
| Business owner | Confirms business impact and accepts the outcome |
| Communications lead | Notifies stakeholders of the decision |

Record the decision owner's name and contact details in the cutover plan. Confirm their availability for the entire window.

---

## The Point of No Return

Most migrations have a step after which rollback becomes much harder or impossible. Common examples are the first write of new production data to the target, the decommissioning of the source, and an irreversible schema change.

1. Identify the step in the runbook and mark it clearly.
2. Schedule a checkpoint immediately before it.
3. At the checkpoint, confirm every validation has passed.
4. Get explicit approval from the rollback decision owner to proceed.
5. After this point, the response to a problem is to fix forward. Plan for that as well.

---

## Rollback Plan Template

| Step | Action | Owner | Duration | Verification |
|------|--------|-------|----------|--------------|
| 1 | Announce the rollback decision | Communications lead | | |
| 2 | Stop traffic or writes to the target | | | |
| 3 | Restore or re-enable the source | | | |
| 4 | Redirect traffic to the source | | | |
| 5 | Reconcile any data written to the target | | | |
| 6 | Validate the source is fully operational | | | |
| 7 | Confirm with the business owner | | | |
| 8 | Send the all-clear | Communications lead | | |

**Total rollback time:** [X hours]. This must fit inside the cutover window with margin.

---

## Keeping Rollback Possible

- Keep the source platform intact and running until stabilization is complete.
- Take verified backups before cutover and confirm they can be restored.
- Plan how to handle data written to the target between cutover and a rollback.
- Freeze changes to the source and the target during the cutover window.
- Set a retention period for the source and get agreement before decommissioning.

---

## Contingency Scenarios

Rollback is one response. Plan for these as well.

| Scenario | Contingency |
|----------|-------------|
| A key person is unavailable during cutover | A named and briefed backup for every critical role |
| A dependency team is not ready | A go or no-go check [X] days ahead, plus an alternate cutover date |
| A vendor or third-party service fails | Vendor escalation contacts confirmed in advance and on standby |
| Data migration runs longer than planned | Timing checkpoints with a defined cutoff, and a partial migration option where possible |
| A defect is found after the point of no return | A fix-forward team on standby with a defined triage process |
| Users cannot work after cutover | Extra support staffing, a documented workaround, and a clear way to report issues |

---

## Testing the Rollback

- [ ] Rollback rehearsed in a non-production environment
- [ ] Rollback run during the pilot and timed
- [ ] Backups restored successfully in a test
- [ ] Every person in the rollback plan has read it and knows their steps
- [ ] The rollback duration fits within the cutover window

---

## After a Rollback

1. Confirm the source is stable and the business is operating.
2. Tell stakeholders what happened and what comes next.
3. Hold a review within [X] days to find the cause.
4. Update the runbook, the risk register, and the plan.
5. Set the new cutover date only after the cause has been addressed.

A rollback that returns the business to a working state is the plan working as designed.

---

*Part of the [Enterprise Platform Migrations](../README.md) framework.*
