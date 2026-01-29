# Overview
As a penetration tester, I assessed the effectiveness of brute force protections on a GraphQL-based authentication endpoint. During testing, I identified a logic flaw in the rate-limiting implementation that failed to account for GraphQL aliasing. By crafting a single GraphQL request containing multiple login mutations, I was able to submit numerous credential guesses simultaneously, bypass the brute force controls, and successfully authenticate as another user. This project demonstrates how misunderstanding GraphQL request semantics can render traditional security controls ineffective.

# Steps Undertaken

Step 1: Captured and analyzed the GraphQL login mutation used by the application.

Step 2: Confirmed rate limiting on repeated individual login attempts.

Step 3: Constructed a single GraphQL request using aliases to execute multiple login attempts at once.

Step 4: Identified a successful authentication response and logged in using the recovered credentials.

# Conclusion

This assessment revealed a high-severity authentication weakness where rate limiting was enforced per request rather than per authentication attempt. The findings highlight the need for GraphQL-aware security controls that properly account for request complexity and authentication event volume.
