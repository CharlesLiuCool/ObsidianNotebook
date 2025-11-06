---
tags: CyserWorkshop2025
date: 5/21/2025
---

___

**Dr. Xu Lin**

- Web stores an ID on the client
- The client returns the ID to the server
- The ID is what allows re-identification
- "Stateful"

You can clear/reject/choose cookies, so websites are trying to find tricker ways to track your data.

Fingerprints are used to fully or partially *identify individual users or devices* even when cookies are turned on.

Things tracked in digital fingerprint
- Headers
- Browser Type
- Timezone
- Screen Resolution
- Fonts
- Canvas
- Platform
- WebGL

Browser fingerprinting is a double-edged sword

*Pros:*
- Bot Detection: Differentiate between bots and real users
- Authentication: Differentiate between real owner and impersonator

*Cons:*
- Track users against their will (stateless tracking)

**Key point:** Don't solely rely on digital fingerprint, add extra measures to ensure safety.

*Web Services*
- Always trigger 2FA challenges
- Chain sessions using one new and one old Canvas element
- Use strict IP address checks and require the presence of specific cookies
- Follow layered multi-modal strategy to enhance security

Dr. Lin's research: we don't need JavaScript, implicit stylistic browsing.

We can look at some features of the styles of the operator/browser such as size and track 
