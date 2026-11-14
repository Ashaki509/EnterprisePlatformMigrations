# Migration Lifecycle Playbook

An end-to-end guide to running an enterprise platform migration in five phases. Each phase lists its goal, the key activities, the templates to use, and the exit criteria that must be met before the next phase begins.

---

## The Five Phases

| Phase | Goal | Main output |
|-------|------|-------------|
| 1. Discovery | Understand what is being migrated and why | Approved migration charter |
| 2. Planning | Decide how the migration will run | Baseline plan, RACI, and risk register |
| 3. Pilot | Prove the approach on a small, representative scope | Validated runbook and a go decision |
| 4. Execution | Migrate in waves with controlled cutovers | Migrated workloads and a retired legacy platform |
| 5. Stabilization | Confirm the new platform performs and capture the benefits | Benefits report and lessons learned |

---

## Phase 1: Discovery

**Goal:** establish the business case, the scope, and the starting point.

**Key activities**
- Define the business reason for migrating and the outcomes expected
- Inventory what is in scope: systems, data, integrations, and users
- Map dependencies, including downstream consumers that are easy to miss
- Identify stakeholders and assess their interest and influence
- Record baseline measures for cost, performance, and reliability
- Identify constraints: compliance, contractual dates, freeze periods, and budget

**Templates:** [Migration Charter](../templates/migration-charter.md), [Benefits Register](../templates/benefits-register.md), [Stakeholder Communication Plan](../templates/stakeholder-communication-plan.xlsx)

**Exit criteria**
- [ ] Charter approved by the executive sponsor
- [ ] Inventory and dependency map reviewed by system owners
- [ ] Baseline measures recorded
- [ ] Expected benefits named, each with an owner

---

## Phase 2: Planning

**Goal:** turn the charter into a plan the teams have agreed to.

**Key activities**
- Choose the migration strategy for each workload, for example rehost, replatform, rebuild, or retire
- Group workloads into waves, starting with lower risk and fewer dependencies
- Assign responsibilities across teams
- Identify and score risks, with a mitigation and a contingency for each high risk
- Define success criteria and rollback criteria for cutover
- Build the timeline and confirm capacity with each team
- Plan communications for each stakeholder group

**Templates:** [RACI Template](../templates/raci-migration-template.xlsx), [Risk Assessment Matrix](../templates/risk-assessment-matrix.xlsx), [Milestone Tracker](../templates/milestone-tracker.xlsx)

**Exit criteria**
- [ ] Wave plan agreed with workload owners
- [ ] RACI reviewed, with one accountable owner per activity
- [ ] High and critical risks have mitigations and owners
- [ ] Rollback criteria defined and approved
- [ ] Timeline confirmed against team capacity

---

## Phase 3: Pilot

**Goal:** test the approach on real workloads before committing the full plan.

**Key activities**
- Select pilot workloads that are representative but not business critical
- Write the cutover runbook and rehearse it
- Run the pilot migration and measure it against the success criteria
- Test the rollback procedure, including the time it takes
- Update estimates, the runbook, and the risk register with what was learned

**Templates:** [Cutover Plan](../templates/cutover-plan.md), [Rollback and Contingency Planning](rollback-and-contingency-planning.md)

**Exit criteria**
- [ ] Pilot workloads meet the success criteria on the new platform
- [ ] Rollback has been tested and timed
- [ ] The runbook reflects what happened in the pilot
- [ ] Estimates for the remaining waves are updated
- [ ] Sponsor gives a go decision for execution

---

## Phase 4: Execution

**Goal:** migrate the remaining scope in waves without disrupting the business.

**Key activities**
- Run each wave using the runbook: prepare, cut over, validate, and monitor
- Hold a go or no-go review before each cutover
- Communicate before, during, and after each wave
- Track progress, risks, and issues, and report on a regular cadence
- Review each wave briefly and apply the lessons to the next one
- Decommission legacy components once each wave is stable

**Templates:** [Cutover Plan](../templates/cutover-plan.md), [Milestone Tracker](../templates/milestone-tracker.xlsx), [Risk Assessment Matrix](../templates/risk-assessment-matrix.xlsx)

**Exit criteria**
- [ ] All in-scope workloads migrated or formally removed from scope
- [ ] Validation complete for every wave
- [ ] No open critical issues
- [ ] Legacy decommissioning scheduled or complete

---

## Phase 5: Stabilization

**Goal:** confirm the platform is stable, hand it to operations, and measure the benefits.

**Key activities**
- Run a period of heightened support with clear escalation paths
- Compare performance, cost, and reliability against the baselines
- Complete the handover to the operating teams, including documentation and training
- Finish decommissioning and confirm the legacy costs have stopped
- Hold the lessons learned session and publish the results
- Report on benefits, and assign ongoing tracking for those that take longer to appear

**Templates:** [Benefits Register](../templates/benefits-register.md), [Lessons Learned Log](../templates/lessons-learned-log.md)

**Exit criteria**
- [ ] Platform meets its agreed service levels for the stabilization period
- [ ] Operating teams have accepted the handover
- [ ] Legacy platform retired and costs confirmed as stopped
- [ ] Benefits report delivered to the sponsor
- [ ] Lessons learned published

---

## Governance Across All Phases

| Forum | Frequency | Purpose |
|-------|-----------|---------|
| Core team sync | Weekly | Progress, blockers, and next steps |
| Risk review | Every two weeks | Review and re-score the risk register |
| Steering committee | Monthly | Decisions, tradeoffs, and escalations |
| Go or no-go review | Before each cutover | Confirm readiness |
| Phase gate review | End of each phase | Confirm exit criteria and approve the next phase |

---

*Part of the [Enterprise Platform Migrations](../README.md) framework.*
