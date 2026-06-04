
**[OWASP Top 10 2025: IAAA Failures](https://tryhackme.com/room/owasptopten2025one)**

### IAAA
The four items are:
- Identity - the unique account (e.g., user ID/email) that represents a person or service.
- Authentication - proving that identity (passwords, OTP, passkeys).
- Authorisation - what that identity is allowed to do.
- Accountability - recording and alerting on who did what, when, and from where.

---
### A01: Broken Access Control

Broken Access Control happens when the server doesn’t properly enforce who can access what on every request.
A common occurence of this is IDOR (Insecure Direct Object Reference): if changing an ID (like ?id=7 → ?id=6) lets you see or edit someone else’s data, access control is broken.

#### Privilege escalation
- Horizontal privilege escalation (same role, other user’s stuff) Accessing another account with similar privileges.
- Vertical privilege escalation (jumping to admin-only actions) Moving from a lower-privileged account to a higher-privileged account.
---
### A07: Authentication Failures
Authentication Failures happen when an application can’t reliably verify or bind a user’s identity.
Common issues include:
- username enumeration
- weak/guessable passwords (no lockout/rate limits)
- logic flaws in the login/registration flow
- insecure session or cookie handling
ex: if username is admin and we try to fool it with aDmiN and is logged in 

---
### A09: Logging & Alerting Failures
(When applications don’t record or alert on security-relevant event)
Good logging underpins accountability. 
- Failures look like missing authentication events, vague error logs, no alerting on brute-force or privilege changes, short retention, or logs stored where attackers can tamper with them.
---

### Conclusion

- A01 Broken Access Control: Enforce server-side checks on every request
- A07 Authentication Failures: Enforce unique indexes on the canonical form, rate-limit/lock out brute force, and rotate sessions on password/privilege changes.
- A09 Logging & Alerting Failures: Log the full auth lifecycle (fail/success, password/2FA/role changes, admin actions), centralise logs off-host with retention, and alert on anomalies (e.g., brute-force bursts, privilege elevation).
