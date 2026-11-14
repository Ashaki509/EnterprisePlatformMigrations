# Cutover Plan

The cutover plan is the hour-by-hour runbook for moving a workload to the new platform. Complete one for the pilot and one for each wave. Rehearse it before the cutover window.

---

**Migration and wave:**  
**Cutover window:** [start date and time] to [end date and time], [time zone]  
**Cutover lead:**  
**Rollback decision owner:** [name], backup [name]  
**Communication channel during cutover:**

---

## 1. Scope of This Cutover

| Systems and data moving | Users affected | Expected downtime |
|-------------------------|----------------|-------------------|
| | | |

---

## 2. Go or No-Go Checklist

Review this at the go or no-go meeting, [X] days before cutover and again immediately before the window opens.

- [ ] Rehearsal completed and timings recorded
- [ ] Rollback plan tested
- [ ] Backups taken and a restore verified
- [ ] All dependency teams confirmed ready
- [ ] Change freeze in effect on the source and the target
- [ ] Monitoring and alerting configured on the target
- [ ] Support team briefed and staffed
- [ ] Stakeholders notified of the window and the expected impact
- [ ] All roles filled, with backups named
- [ ] No open critical risks or issues

**Decision:** Go | No-go  
**Decided by:**  
**Date and time:**

---

## 3. Roles During Cutover

| Role | Name | Backup | Contact |
|------|------|--------|---------|
| Cutover lead | | | |
| Rollback decision owner | | | |
| Technical lead, source | | | |
| Technical lead, target | | | |
| Data validation lead | | | |
| Business validation lead | | | |
| Communications lead | | | |
| Support lead | | | |

---

## 4. Runbook

| # | Planned time | Step | Owner | Duration | Verification | Actual time | Status |
|---|--------------|------|-------|----------|--------------|-------------|--------|
| | | **Pre-cutover** | | | | | |
| 1 | | Confirm go decision and open the channel | | | | | |
| 2 | | Take final backups | | | | | |
| 3 | | Notify users that the window has started | | | | | |
| | | **Cutover** | | | | | |
| 4 | | Stop writes to the source | | | | | |
| 5 | | Run the final data sync | | | | | |
| 6 | | Validate the data | | | | | |
| 7 | | **Checkpoint: continue or roll back** | | | | | |
| 8 | | Switch traffic or access to the target | | | | | |
| | | **Validation** | | | | | |
| 9 | | Run technical smoke tests | | | | | |
| 10 | | Run business validation | | | | | |
| 11 | | **Checkpoint: point of no return** | | | | | |
| | | **Close** | | | | | |
| 12 | | Confirm monitoring is healthy | | | | | |
| 13 | | Notify users that the cutover is complete | | | | | |
| 14 | | Hand over to heightened support | | | | | |

Add or remove steps to fit the workload. Keep both checkpoints.

---

## 5. Validation Criteria

| Check | Expected result | Owner | Pass or fail |
|-------|-----------------|-------|--------------|
| Record counts match | | | |
| Checksums or sample comparison | | | |
| Critical functions work | | | |
| Integrations respond | | | |
| Performance within threshold | | | |
| Security controls verified | | | |

---

## 6. Rollback

**Triggers:** see [Rollback and Contingency Planning](../playbooks/rollback-and-contingency-planning.md)

**Latest time a rollback can start and still finish inside the window:** [time]

**Point of no return:** step [N]

---

## 7. Communications

| When | Audience | Message | Channel | Owner |
|------|----------|---------|---------|-------|
| [X] days before | Affected users | Window, impact, and what to do | | |
| Start of window | Affected users and support | Cutover has started | | |
| Each checkpoint | Core team and sponsor | Status and decision | | |
| Completion | All stakeholders | Complete, with what changed and how to get help | | |
| If rolled back | All stakeholders | What happened and what comes next | | |

---

## 8. After the Cutover

- **Heightened support period:** [dates]
- **How to report issues:**
- **Wave review scheduled for:**
- **Source decommissioning date, pending stabilization:**

---

*Part of the [Enterprise Platform Migrations](../README.md) framework.*
