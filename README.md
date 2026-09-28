# DFIR-IRIS for Cyber Exercises

**RTIR to DFIR-IRIS migration for the Ohio Cyber Range (OhCR)**
Senior Design Capstone, 2026–2027 · School of Information Technology, University of Cincinnati

> **Status: Planning.** Requirements and scope are being finalized. Nothing in this repository has been configured yet.

This project moves OhCR's cyber exercise incident response workflow from RTIR to [DFIR-IRIS](https://www.dfir-iris.org/), an open-source incident response and case management platform. DFIR-IRIS is already used operationally at OhCR, so participants practice on the same platform they may encounter outside the exercise.

The work is **configuration and deployment**: workflow, roles and permissions, action tracking, escalation, and exercise-specific fields. The DFIR-IRIS source in [`iris-web/`](iris-web/) is an unmodified copy of release v2.4.29.

## Team

| Member | Program | Role |
|---|---|---|
| Benjamin Wilhelm | BSIT – Software Development | Technical Lead: access control, workflow creation, configuration and deployment |
| Ian Kellenberger | BSIT – Software Development | Repository, branches, and milestone logging |
| Austin Suchanek | BSCyber | TBD |

## Goal

Transition the current RTIR-based incident response workflow into DFIR-IRIS and configure it to support how OhCR conducts cyber exercises. The focus is on how teams communicate, document incidents, assign actions, and track response activity during an exercise.

## Requirements at a glance

The customer's ten priorities, marked against the team's proposed scope.

| # | Customer priority | Scope |
|---|---|---|
| 1 | Map the existing RTIR incident response process into DFIR-IRIS | In scope (current process only) |
| 2 | Configure a simple and intuitive incident workflow | In scope |
| 3 | Develop clear roles and permissions | In scope |
| 4 | Improve action assignment and tracking | In scope |
| 5 | Improve communication and escalation between teams | In scope |
| 6 | Create useful incident timelines and dashboards | In scope |
| 7 | Improve reporting and data exports | Partial: basic export templates only |
| 8 | Tie incidents back to exercise scenarios/MSEL events | Partial: manual tagging via exercise fields; no automated linking |
| 9 | Create a training/development environment | In scope |
| 10 | Document the new process and develop a basic user guide | In scope |

## Detailed requirements

Source: OhCR's *RTIR to DFIR-IRIS Improvement* project brief.

### Incident response workflow
Support an incident from initial identification through response and closure, simple enough to use during an exercise without losing meaningful response data.

- [ ] Incident creation and initial details
- [ ] Priority/severity
- [ ] Assignment to a team or individual
- [ ] Status changes
- [ ] Actions taken
- [ ] Evidence or supporting information
- [ ] Escalations
- [ ] Communications
- [ ] Incident closure

### Action tracking
Users can understand the current state of an incident without reading the entire record.

- [ ] What needs to be done
- [ ] Who is responsible
- [ ] When the action was assigned
- [ ] Current status
- [ ] What has been completed
- [ ] What still needs follow-up

### Communication between teams
Make it clear when an incident or action is escalated or transferred, with a history of who was notified, what was passed, and when.

- [ ] Exercise teams
- [ ] Incident response personnel
- [ ] Leadership
- [ ] Legal
- [ ] Law enforcement
- [ ] Intelligence/Fusion functions
- [ ] Other supporting organizations

### User interface
Keep the participant-facing workflow simple and avoid exposing administrative functions.

- [ ] View assigned incidents
- [ ] Create and update an incident
- [ ] Add comments or actions
- [ ] Assign or transfer an action
- [ ] Upload supporting information
- [ ] Close or resolve an action

### Roles and permissions
Roles as proposed by the customer. The final role model will be decided during planning, and it should support different exercise structures without major changes each time.

- [ ] **Participant:** create and update incidents, view team-assigned incidents, add actions and comments
- [ ] **Team Lead:** view all team incidents, assign actions, escalate incidents, monitor team activity
- [ ] **Controller / Exercise Staff:** view activity across teams, monitor incident progression, review actions, support injects
- [ ] **Administrator:** manage users, configure roles and workflows, manage exercise data

### Exercise-specific configuration
Capture data that connects response activity back to the scenario and exercise objectives.

- [ ] Exercise day
- [ ] Team
- [ ] Scenario
- [ ] Inject/card number
- [ ] Incident category
- [ ] Related task or objective
- [ ] Severity and status
- [ ] Assigned organization
- [ ] Time reported and time resolved

### MSEL integration (manual tagging only)
Record the MSEL context on each incident so injects can be compared with actual responses after the exercise.

- [ ] MSEL number
- [ ] Scenario
- [ ] Exercise objective
- [ ] Team
- [ ] Expected response

### Incident timeline
Usable during the exercise and afterward for reviewing team performance.

- [ ] Incident reported and acknowledged
- [ ] Action assigned
- [ ] Escalation
- [ ] Information shared
- [ ] Response action completed
- [ ] Incident resolved

### Reporting and data extraction (basic templates)
Reduce the manual work needed to reconstruct what happened after an exercise.

- [ ] Incidents by team and by severity
- [ ] Incident response timelines
- [ ] Open vs. closed actions
- [ ] Escalations
- [ ] Average response time
- [ ] Actions by organization
- [ ] Comments/activity history
- [ ] Full incident log

### Dashboard
Real-time view for controllers and exercise leadership without opening every incident.

- [ ] Active incidents
- [ ] Open actions
- [ ] High-priority incidents
- [ ] Incidents awaiting response
- [ ] Incidents by team
- [ ] Recent activity
- [ ] Escalated incidents

### Notifications
Useful without becoming overwhelming during an exercise. *Scope still to be decided.*

- [ ] Incident assigned
- [ ] Action assigned
- [ ] Incident escalated
- [ ] Important information added
- [ ] Status changed

### Training environment
A separate environment (similar to MATT) for training and development.

- [ ] Train participants and run a short hands-on orientation before an exercise
- [ ] Test new workflows, roles, and permissions
- [ ] Build exercise scenarios
- [ ] Practice incident response
- [ ] Test upgrades without affecting live exercise data

### Migration from RTIR
Document what exists in RTIR and decide what to recreate or improve, not necessarily copy.

- [ ] Current incident workflow
- [ ] Current queues
- [ ] User roles
- [ ] Required fields
- [ ] Statuses
- [ ] Reporting requirements
- [ ] Historical data requirements (documented only; data is not migrated)
- [ ] Custom RTIR functionality currently relied on

## Out of scope

- Automated inject-to-incident linking
- Advanced analytics or a full AAR-generation suite beyond basic export templates
- Migration of historical RTIR ticket data
- Integration with external systems beyond DFIR-IRIS itself

## Deliverables

- Configured and documented DFIR-IRIS instance (workflow, roles/permissions, exercise-specific fields) deployed in a training/exercise VM environment
- Migration document mapping RTIR's current process to its DFIR-IRIS equivalent
- Basic reporting and data export templates for after-action review
- Training environment for participants
- Basic user guide for participants and exercise staff

## Timeline

| Semester | Focus |
|---|---|
| Fall 2026 | Environment setup, RTIR mapping, deployment, incident workflow, roles and permissions, action tracking and escalation |
| Spring 2027 | Exercise-specific fields, communication workflows, timeline and dashboard, reporting templates, end-to-end testing, training environment and user guide |

## Open questions

- Final role model: all four customer roles, or fewer?
- Notifications: in or out of scope?
- VM platform and resources provided by OhCR
- Access to the current RTIR configuration for the migration mapping

## Upstream project

The `iris-web/` folder contains an unmodified copy of DFIR-IRIS [v2.4.29](https://github.com/dfir-iris/iris-web/releases/tag/v2.4.29) from [dfir-iris/iris-web](https://github.com/dfir-iris/iris-web). For installation and platform documentation, see the [upstream repository](https://github.com/dfir-iris/iris-web#readme) and the [DFIR-IRIS documentation](https://docs.dfir-iris.org/).

DFIR-IRIS is licensed under the GNU Lesser General Public License v3.0. See [iris-web/LICENSE.txt](iris-web/LICENSE.txt).
