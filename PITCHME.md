## Security, it's not rocket science
### Lessons learnt from NDC Security Sydney 2018

---
@title[Its harder]

We all know rocket science is easy.
Note:
At least compared to security
Resources:
  - time
  - people
  - money
  - training
---
## Attack Vectors
It's tough to protect what you don't know.
- OWasp (Open Web Application Security Project)
- Pluralsight @note[devops]

Note:
Educate, keep up to date, share
---

## 1 - Injection

+++

## 1 - Injection

* SQL |
* NoSQL |
* LDAP |

+++

### 1 - Injection - Prevention

@ul

* Parameterized Queries
* Don't roll your own - ORM @note[Entity Framework, NHibernate, CakePHP, Laravel. Keep up to date]
* Validate input - white lists / black lists

@ulend

---

## 2 - Broken Authentication

+++

## 2 - Broken Authentication

* Credential stuffing
* Brute Force |
* Allowing weak passwords |
* Improper token invalidation |

+++

### 2 - Broken Authentication - Prevention

@ul
* MFA @note[How to deal with account lockouts]
* Don't allow weak passwords @note[Have I been pwned, Okta etc]
* Harden against enumeration attacks
* Delay failed login attempts <sup>*</sup>
* More details
@ulend

+++
### 2 - Broken Authentication - References

---

## 3 - Sensitive Data Exposure

+++

## 3 - Sensitive Data Exposure

@ul
* Transmission of data over clear text (HTTP, SMTP, FTP) @note[External traffic, load balancers, internal routing]
* Storage of sensitive data @note[Plain text, encryption at rest, backups, logs]
* Use of old or weak cryptographic algorithms
* Use of weak keys
* Not enforcing encryption (Missing headers)
@ulend

+++

### 3 - Sensitive Data Exposure - Prevention

@ul
* Identify sensitive data (Laws, regulation, policy) @note[HIPA, Australian Privacy Act 1988]
* Apply appropriate controls for the class of data
* Don't store sensitive Data unnecessarily @note[They can't take what you don't have]
* Encryption at rest @note[Opinions in regards to cloud?]
* HSTS (HTTP Strict Transport Security)
* Disable caching of sensitive data
* Store passwords with strong encryption @note[Argon2, scrypt, bcrypt, PBKDF2]
@ulend
---

## 4 - XML External Entities (XXE)

+++

## 4 - XML External Entities (XXE)

@ul
* Application that accept xml either directly or as an uploaded file
* SAML for authentication @note[SAML uses XML for identity assertions]
* SOAP pre 1.2
* DDOS - Billion laughs attack
@ulend

+++ 4 - XML External Entities (XXE) - Prevention

@ul
* Developer training to identify and mitigate
* Where possible use less complex formats like JSON
* Patch and upgrade all XML processors Update to SOAP 1.2+
* Disable XML external entitiy and DTD processing in all parsers in the application
* Implement server-side whitelisting of input validation
* Utilise manual source control review
@ulend

+++ 4 - XML External Entities (XXE) - Prevention

Additionally API sercurity gateways, Web Application Firewalls , and virtual patching can be used to detect, monitor and block XXE attacks.

---

## 5 - Broken Access Control

+++

## 5 - Broken Access Control

@ul
* Bypassing control checks
* Allowing primary key to be changed to another users
* Elevation of privileges
* Metadata manipulation - JWT, Cookies, Hidden Fields
* CORS misconfiguration - unauthorized API access
* Missing access controls for POST, PUT and DELETE
@ulend

Note:
Static Application Security Testing, Dynamic Application Security Testing, Automation tools for detection

+++

## 5 - Broken Access Control - Prevention

@ul
* Deny by default (except public)
* DRY @note[implment access control once, reuse where possible]
* Disable web server directory listing
  * Ensure metadata is not present in webroots
* Log access control failures
* Rate limit APIs where appropriate
* Invalidate JWT tokens on the server after logout
@ulend

---

## 6 - Security Misconfiguration

+++

## 6 - Security Misconfiguration

@ul
* Missed opportunities to harden the application stack
* Unnecessary features enabled - ports, services, pages, privileges
* Default accounts left active with unchanged passwords
* Exceptions and errors leaking info
* Latest features not enabled or configured on recent upgrades
* Security headers @note[OWasp- CSP, HSTS, X-Frame-Options]
@ulend

+++

## 6 - Security Misconfiguration - Prevention

@ul
* Repeatable hardening process
* Fast easy deploys, identical environments with different credentials
* Remove and disable unneeded features of the platform
* Least required permissions
* Automated checks of security
* Segmented application architecture
@ulend

---

## 7 - XSS (Cross-Site Scripting)

+++

## 7 - XSS (Cross-Site Scripting)

@ul
* Use of frameworks to excape XSS @note[Ruby on Rails, React JS]
* CSP's in the absince of other vulnerabilities
* Escaping data and context-sensitive encoding
@ulend

---

## 8 - Insecure Deserialization

---

## 9 - Known Valnerabilities in Componentes

---

## 10 - Insufficient Monitoring

---
# Passwords

---?image=assets/spectrum_wave_by_monkeymagico.png

[comment]: # (Image found at https://monkeymagico.deviantart.com/art/Spectrum-Wave-133641157)

# The Spectrum
<span class="dark-background"><span>Security a journey, not a destination</span></span>
@ul
* Pick the low hanging fruit and take the win @note[If you don't the attackers will]
@ulend

---
## Thanks for listening

### References

https://www.owasp.org
https://haveibeenpwned.com/
