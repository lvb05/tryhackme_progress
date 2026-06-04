
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
