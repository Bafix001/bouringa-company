# Standard Operating Procedures

---

## 📋 SOP 1 : Developer Onboarding

### Day 1
- [ ] Welcome email with agenda
- [ ] Add to Slack, GitHub, communication tools
- [ ] Setup laptop & dev environment (SSH, Git config, IDEs)
- [ ] Access to project repos
- [ ] Review of Bouringa culture & values (30 min)

### Day 2-3
- [ ] Technical stack deep-dive (architecture, frameworks, DB)
- [ ] Review codebase (30-60 min walkthrough)
- [ ] Assign first small task (bug fix or minor feature)
- [ ] Code review of first PR (feedback & learning)

### Week 1-2
- [ ] Shadow senior dev (observe project work)
- [ ] Deploy code to staging (first time experience)
- [ ] Write unit tests (practice)
- [ ] Pair programming on small task (learn practices)

### Week 3-4
- [ ] Deliver independent task
- [ ] Attend client call (understand customer perspective)
- [ ] Document learnings / feedback
- [ ] 1-on-1 with Dev Lead (how's it going?)

---

## 📋 SOP 2 : Code Review Standards

### Code Review Checklist

**Functionality :**
- [ ] Does it work as intended?
- [ ] All requirements addressed?
- [ ] No new bugs introduced?
- [ ] Edge cases handled?

**Code Quality :**
- [ ] Follows project style guide?
- [ ] DRY (no code duplication)?
- [ ] SOLID principles applied?
- [ ] Readable (clear variable names, etc.)?

**Testing :**
- [ ] Unit tests included?
- [ ] Coverage >70%?
- [ ] Tests meaningful (not just mocking)?

**Security :**
- [ ] Input validation?
- [ ] No hardcoded secrets?
- [ ] SQL injection protection?
- [ ] XSS protection (if web)?

**Performance :**
- [ ] No obvious inefficiencies?
- [ ] Database queries optimized?
- [ ] Caching considered?

**Documentation :**
- [ ] Comments on complex logic?
- [ ] Function docs updated?
- [ ] README if new feature?

### Review Response Time
- Aim for <24 hours
- Critical fixes: <4 hours
- Communicate if delayed

---

## 📋 SOP 3 : Client Communication

### Initial Contact Response
- **Timeline** : Within 2 hours (business hours)
- **Format** : Email or Slack (depending on how contacted)
- **Content** : Acknowledge receipt, give next steps

### Proposal Response Time
- **Timeline** : Within 5 business days
- **Format** : PDF + email + optional call
- **Content** : Scope, timeline, cost, next steps

### During Project
- **Weekly update** : Progress, blockers, next week plan
- **Issue reports** : Same day acknowledgment, ETA for resolution
- **Change requests** : Discuss scope & cost impact

### Monthly Reporting (For Support Contracts)
- Executive summary of work
- Issues resolved
- Performance metrics
- Upcoming priorities

---

## 📋 SOP 4 : Bug Triage

### Bug Report Received
1. **Log it** : Create issue in tracking system
2. **Classify** : Assign priority (critical/high/medium/low)
3. **Assign** : Give to appropriate dev
4. **Communicate** : Update client with ETA

### Priority Definitions

**Critical :** System down, data loss risk, security breach
- Response: <1 hour
- Fix target: <4 hours

**High :** Major feature broken, significantly impaired
- Response: <4 hours
- Fix target: <24 hours

**Medium :** Feature partially broken, workaround exists
- Response: <24 hours
- Fix target: <3 days

**Low :** Minor UI issue, nice-to-have fix
- Response: <3 days
- Fix target: <1 week

### Bug Fix Process
1. Reproduce issue
2. Write unit test to catch bug
3. Fix code
4. Test passes
5. Code review
6. Merge
7. Deploy to staging
8. QA test
9. Deploy to production
10. Notify client

---

## 📋 SOP 5 : Meeting Best Practices

### Standup (Daily, 15 min)
- **When** : 9:30 AM or convenient time
- **Format** : Each person says: yesterday done, today plan, blockers
- **No** : Rabbit holes, status report, long discussions
- **Follow-up** : Blockers discussed after standup offline

### 1-on-1 (Monthly, 30 min)
- **When** : Scheduled weekly or bi-weekly
- **Format** : How are you doing? Goals? Feedback? Growth?
- **Owner** : Dev Lead (for devs), CEO (for leads)
- **No** : Status updates (use standup instead)

### Client Call (Weekly or Bi-weekly, 30 min)
- **When** : Same day/time each week (if possible)
- **Format** : Progress demo, questions, next week plan
- **Owner** : Developer or Dev Lead
- **Agenda** : Sent 24 hours before

### All-Hands (Monthly, 30 min)
- **When** : End of month or start of month (consistent)
- **Format** : Company updates, wins, learning share, culture talk
- **Owner** : CEO
- **Attendance** : Everyone (time-block, no excuses)

---

## 📋 SOP 6 : Time Tracking (If T&M Model)

### Timesheet Submission
- **When** : End of day or weekly
- **Format** : Hours per project, per task
- **Tools** : Spreadsheet or Toggl or GitHub (if tracking in issues)
- **Accuracy** : No estimates after-the-fact, track as you work

### Sample Format
```
Date    | Project | Task            | Hours | Notes
--------|---------|-----------------|-------|--------
Jan 15  | Client1 | Develop API     | 4     | GET /users
Jan 15  | Client1 | Code review     | 1     | PR #45
Jan 15  | Admin   | Meeting prep    | 0.5   | Client call
```

### Invoice Generation
- Dev Lead or CEO tallies hours
- Group by client and project
- Create invoice with breakdown
- Send to client with details

---

## 📋 SOP 7 : Confidentiality & IP

### What's Confidential
- Client business information
- Client code (if applicable)
- Salaries / compensation
- Strategic plans
- Security vulnerabilities (before patch)

### What's Not Confidential
- Our tech stack (public anyway)
- General learnings (no client names)
- Public portfolio pieces (with permission)

### IP Ownership
- **Code written for client** : Owned by client
- **Ourcode, our tools** : Owned by Bouringa
- **Hybrid** : Negotiate in contract (typically 70/30 split)

### Social Media Guidelines
- No client names without permission
- No code examples without permission
- Share learnings in general terms
- Respect client confidentiality always

---

**Last Updated:** January 2025
