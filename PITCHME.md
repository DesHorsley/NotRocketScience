## Security, it's not rocket science
### Lessons learnt from NDC Security Sydney 2018

---?image=assets/Falcon_Heavy.jpg&size=cover
@title[Its harder]

We all know rocket science is easy.
Note:
At least compared to security
---
## Attack Vectors
It's tough to protect what you don't know.
- OWasp (Open Web Application Security Project)
- Pluralsight

Note:
Educate, keep up to date, share
--- ?image=https://upload.wikimedia.org/wikipedia/commons/thumb/7/7d/Syringe_with_Certolizumab_pegol-1800.jpg/1024px-Syringe_with_Certolizumab_pegol-1800.jpg
@transition[none]

## 1 - Injection

@transition[none]
+++
@transition[none]

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

@transition[none]
+++
@transition[none]

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

@footnote[https://www.owasp.org/index.php/Top_10-2017_A2-Broken_Authentication]
---

## 3 - Sensitive Data Exposure

@transition[none]
+++
@transition[none]

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
* HTTPS
* Disable caching of sensitive data
* Store passwords with strong encryption @note[Argon2, scrypt, bcrypt, PBKDF2]
@ulend
---

## 4 - XML External Entities

---

## 5 - Broken Access Control

---

## 6 - Security Misconfiguration

---

## 7 - XSS (Cross-Site Scripting)

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
