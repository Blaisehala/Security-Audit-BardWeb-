## Potential Attack Surface (Initial Assessment)

### Critical Risks

#### M-Pesa Payment Integration
- Webhook authentication (is it properly secured?)
- Replay attacks on transaction IDs
- Amount manipulation before payment processing
- Race conditions in payment verification

#### Admin Panel Exposure
- Default `/admin/` URL (predictable)
- No IP whitelisting visible
- No 2FA mentioned
- Brute force protection concerns

#### Authentication Weaknesses
- No rate limiting on login attempts
- No account lockout after failed attempts
- Secret code brute-forcing possible
- Member number enumeration


### High Risks💀
____

#### File Upload Vulnerabilities
- Profile picture uploads (Cloudinary sanitization must be verified)
- File type validation
- File size limits
- Malicious file uploads

#### Insecure Direct Object References (IDOR)
- Ability to view other users' donation history
- Ability to RSVP to unauthorized events
- Ability to edit other profiles via URL manipulation

#### SQL Injection
- Search functionality in directory (`/directory/?search=`)
- Verification that Django ORM is used properly (parameterized queries)


### Medium Risks💀
___

#### Cross-Site Scripting (XSS)
- User bio field (stored XSS)
- Event descriptions
- Donation messages
- Verification that Django auto-escaping is enabled

#### Cross-Site Request Forgery (CSRF)
- Verification that all state-changing operations use CSRF tokens
- Donation processing
- Profile updates
- RSVP actions

#### Information Disclosure
- Error messages revealing stack traces (`DEBUG=True` in production)
- Alumni directory exposing excessive personal data
- API endpoints leaking sensitive information

#### Session Management
- Session timeout configuration
- Secure and HttpOnly flags on cookies
- Session fixation attacks



### Low risks💀
___

#### password Policy
- Django's default validators are decent 
- But verify : minimum length, complexity requirements 
- Password reset functionality secure


#### Email verificarion
- No email verification during registration
- Can attacker register with someone else's email?


#### Rate Limiting
- No rate limiting visible on any endpoints
- Vulnerable to brute force and DOs attacks
