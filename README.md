# Splunk Security Basics

## Project Overview

This project is a beginner-level Splunk security monitoring lab designed to develop practical skills in log ingestion, searching, filtering, event analysis, and basic security investigation.

The lab uses a synthetic security log containing authentication and security-related events.

## Objectives

* Import security logs into Splunk.
* Understand Splunk indexes, sources, sourcetypes, and hosts.
* Search and filter security events using SPL.
* Identify successful and failed login activity.
* Group authentication failures by username.
* Identify source IP addresses associated with failed logins.
* Practice basic SOC-style investigation and documentation.

## Splunk Data Configuration

| Field      | Value          |
| ---------- | -------------- |
| Index      | `main`         |
| Source     | `security.log` |
| Sourcetype | `security_lab` |
| Host       | Automatic      |

## Lab Searches

### 1. View all security events

```spl
index=main sourcetype=security_lab
```

### 2. Search for successful logins

```spl
index=main sourcetype=security_lab "Successful login"
```

### 3. Search for failed logins

```spl
index=main sourcetype=security_lab "Failed login"
```

### 4. Count failed logins by username

```spl
index=main sourcetype=security_lab "Failed login"
| stats count by username
| sort - count
```

### 5. Count failed logins by source IP

```spl
index=main sourcetype=security_lab "Failed login"
| stats count by src_ip
| sort - count
```

### 6. Analyze username and source IP together

```spl
index=main sourcetype=security_lab "Failed login"
| stats count by username, src_ip
| sort - count
```

## Investigation Summary

The investigation demonstrated how Splunk can be used to:

1. Search authentication events.
2. Separate successful and failed login activity.
3. Count failed authentication attempts.
4. Identify usernames associated with repeated failures.
5. Identify source IP addresses associated with authentication failures.
6. Organize security evidence for further investigation.

The results are based on a synthetic training dataset and are intended for educational purposes.

## Screenshots

Screenshots documenting the investigation are stored in the `screenshots/` directory.

Examples include:

* Successful login events
* All security events
* Failed-login analysis
* Authentication analysis by username and source IP

## Skills Practiced

* Splunk Search & Reporting
* SPL fundamentals
* Event filtering
* `stats`
* `sort`
* Authentication-log analysis
* Basic SOC investigation
* Security-event documentation

## Disclaimer

This project uses synthetic security data for cybersecurity education and laboratory practice. It does not contain real user credentials or real security incidents.
