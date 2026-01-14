**Authentication & Authorization**

 [] Test brute force on login (no lockout?)

 [] Test secret code brute forcing

 [] Test member number enumeration

 [] Verify CSRF protection on all forms

[] Test session timeout

 [] Verify secure cookies (HttpOnly, Secure flags)

 [] Test password reset flow for vulnerabilities

 [] Check for account takeover vectors

**Input Validation**

 Test XSS in bio, event descriptions, donation messages

 Test SQL injection in search functionality

 Test file upload with malicious files (SVG with JS, shell scripts)

 Test negative donation amounts

 Test excessively long inputs (buffer overflow?)


**Authorization (IDOR)**

 [] Can user A view user B's donation history?

 [] Can user edit other users' profiles by changing URL?

 [] Can user RSVP to private events?

 [] Can user access admin endpoints without privilege?


**Payment Security**

 [] Test M-Pesa webhook authentication

 [] Test transaction ID replay attacks

 [] Test amount manipulation

 [] Test double-spending scenarios


**Data Exposure**

 [] Check DEBUG=False in production

 [] Verify error messages don't leak sensitive info

 [] Check what data is exposed in directory

 [] Test API responses for information leakage

**Infrastructure**

 [] Verify HTTPS is enforced (HSTS header?)

 [] Check for outdated dependencies (pip list --outdated)

 [] Verify database credentials are in environment variables

[]  Check if admin panel is IP-restricted