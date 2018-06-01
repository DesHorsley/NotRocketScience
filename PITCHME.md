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

## 1 - Injection

+++@transition[none]

## 1 - Injection

@ul

* SQL
* NoSQL
* LDAP

@ulend

@transition[none]
+++
@transition[none]

## 1 - Injection - Prevention

@ul

* Parameterized Queries
* Don't wrap your own - ORM @note[Entity Framework, NHibernate, CakePHP, Laravel. Keep up to date]
* Validate input - white lists / black lists

@ulend

---

## 2 - Broken Authentication

@ul

* Credential stuffing
* Brute Force
* Allowing weak passwords
* Improper token invalidation

@ulend

---
## 3 - Sensitive Data Exposure

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