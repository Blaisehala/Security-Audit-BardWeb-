## OWASP Top 10 Mapping (2021)

### A01: Broken Access Control
- Insecure Direct Object References (IDOR)
  - Viewing other users' donation history
  - RSVPing to unauthorized events
  - Editing other user profiles via URL manipulation
- Admin panel exposure
  - Predictable `/admin/` URL
  - Lack of IP whitelisting
- Excessive data exposure in alumni directory
- Unauthorized access to API endpoints

---

### A02: Cryptographic Failures
- M-Pesa payment integrity issues
  - Amount manipulation before processing
- Insecure handling of sensitive data
- Missing Secure and HttpOnly flags on cookies
- Weak session protection mechanisms

---

### A03: Injection
- SQL Injection risks
  - Directory search functionality (`/directory/?search=`)
  - Improper use of raw SQL instead of Django ORM
- Potential injection through unvalidated input fields

---

### A04: Insecure Design
- Missing rate limiting on authentication
- No account lockout policy
- Race conditions in payment verification
- Weak payment workflow design
- No replay attack protection on transaction IDs

---

### A05: Security Misconfiguration
- `DEBUG=True` enabled in production
- Admin panel exposed with default settings
- Missing brute force protection
- No IP whitelisting for sensitive endpoints
- Incomplete CSRF protection coverage

---

### A06: Vulnerable and Outdated Components
- Third-party integrations (M-Pesa, Cloudinary)
- Dependency version management not enforced
- Lack of vulnerability scanning for packages

---

### A07: Identification and Authentication Failures
- No rate limiting on login attempts
- No 2FA for admin accounts
- Secret code brute-forcing possible
- Member number enumeration
- Weak session timeout configuration

---

### A08: Software and Data Integrity Failures
- Webhook authentication weaknesses
- Unverified M-Pesa callbacks
- Lack of signature verification on external integrations
- Risk of tampered payment confirmation data

---

### A09: Security Logging and Monitoring Failures
- Missing alerts for failed login attempts
- No logging for suspicious payment activity
- Lack of monitoring for admin access abuse
- No audit trail for critical actions

---

### A10: Server-Side Request Forgery (SSRF)
- Indirect risk through file uploads and external integrations
- Cloudinary media handling endpoints not fully validated
