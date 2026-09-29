# Lab 01 — Splunk Search and Filtering

**Level:** Beginner  
**Dataset:** `data/security.log` (20 fictional events)

## Part A — Import
- [ ] Upload `security.log` into Splunk.
- [ ] Set sourcetype to `security_lab`.
- [ ] Search `index=main sourcetype=security_lab`.
- [ ] Confirm that the dataset returns 20 events.

## Part B — Search and filter
1. Run `index=main sourcetype=security_lab "Failed login"`.
   - How many failed login events appear?
   - Which username appears most often?
2. Run `index=main sourcetype=security_lab level=ERROR`.
   - What types of errors are present?
3. Run `index=main sourcetype=security_lab level=WARN`.
   - What does WARN communicate in a log?

## Part C — Summarize
4. Run `index=main sourcetype=security_lab | stats count by level`.
   - Record the count for INFO, WARN, and ERROR.
5. Run `index=main sourcetype=security_lab "Failed login" | stats count by src_ip`.
   - Which source IP has the most failed attempts?
6. Run `index=main sourcetype=security_lab "Blocked inbound connection" | stats count by src_ip`.
   - How many blocked connections are recorded for each source?

## Part D — Explain your findings
Write 3–5 sentences:
- What did you observe?
- What might repeated failed logins suggest?
- What additional evidence would you need before classifying activity as an attack?

## Completion checklist
- [ ] Imported the log
- [ ] Ran all six searches
- [ ] Recorded results
- [ ] Wrote a short, cautious findings summary
- [ ] Captured sanitized screenshots for GitHub

**Reminder:** The data is synthetic. A repeated failure pattern is a clue to investigate, not proof of compromise.
