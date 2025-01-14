---
category: minorAnalysis
---
* Added a new query, `js/functionality-from-untrusted-domain`, which detects uses in HTML and JavaScript scripts from untrusted domains, including the `polyfill.io` content delivery network
  * it can be extended to detect other compromised scripts using user-provided data extensions of the `untrustedDomain` predicate, which takes one string argument with the domain to warn on (and will warn on any subdomains too).
* Modified existing query, `js/functionality-from-untrusted-source`, to allow adding this new query, but reusing the same logic
  * Added the ability to use data extensions to require SRI on CDN hostnames using the `isCdnDomainWithCheckingRequired` predicate, which takes one string argument of the full hostname to require SRI for.
* Created a new library, `semmle.javascript.security.FunctionalityFromUntrustedSource`, to support both queries.
