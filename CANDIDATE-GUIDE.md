# Candidate guide: take-home project

## Purpose

This project gives you room to demonstrate how you turn an ambiguous product request into working software. We care about the decisions you make, the risks you notice, how you verify your work, and how clearly you can explain the result.

You may use any reasonable programming language, framework, database, hosting platform, editor, AI model, coding assistant, or agent workflow. AI is optional. Whether you use it or not, you remain responsible for understanding and validating everything you submit.

## Time and scope

The assignment is intentionally open-ended, with no minimum time commitment. Before starting, choose and record a time box that is realistic for you. If you have two hours, spend two hours, narrow the project deliberately, and tell us what you would do with more time. We suggest treating five hours or less as a compact submission; optional extensions may occupy several days if you genuinely want to explore them.

We do not award points for spending more time. We evaluate the coherence, safety, evidence, and tradeoffs of the scope you chose. Stop when your time box ends, document what remains, and be prepared to discuss what you would do next.

If a take-home project is not workable for you, ask for the equivalent live exercise. This does not affect evaluation.

## Shared product assumptions

- All data is synthetic. Never use data or source code from a current/former employer or real customer.
- A `company` is the tenant boundary. Records from one company must never be visible or mutable from another company’s session.
- Financial amounts must avoid binary floating-point errors and always include currency.
- State-changing actions require current server-side authorization. A hidden client button is not authorization.
- Mobile clients, jobs, webhooks, and networks may retry or deliver messages more than once.
- You may simplify authentication, but document the trust boundary and provide at least two seeded users/roles when authorization matters.

## Mobile assignment guidance

When the selected assignment is mobile-first, React Native is preferred only when the assignment says so. Expo, native iOS/Android, Flutter, a PWA, or a convincing web simulation may also be appropriate. Explain what your choice demonstrates and what it does not; for example, a web simulation can prove state transitions and retry behavior but not native background execution or secure-storage integration.

Choose one primary review target and make that path dependable. Cross-platform completeness is not required unless you include it in your chosen scope. In the README, state:

- the platform, device or simulator, and OS version you actually tested;
- exact build, run, test, and five-minute demo steps;
- any prerequisites, synthetic login/demo data, permissions, or environment variables;
- which platform or native behaviors are simulated, untested, or deliberately omitted.

A reviewer should not need a paid Apple/Google developer account, your signing credentials, or a particular physical device. An unsigned simulator build, Expo preview with a reproducible local fallback, installable test artifact, or clean local build is sufficient. Commit the required native configuration and lockfiles, but never signing keys, provisioning profiles, tokens, or service secrets. Screenshots or a short recording are welcome as backup evidence, but do not replace a runnable or reproducibly buildable submission.

Prioritize the mobile risks central to your chosen scope rather than treating this as a checklist. Relevant risks may include:

- app restart, foreground/background transitions, interrupted requests, and late callbacks;
- honest local, queued, uploading, processing, failed, and server-confirmed states;
- offline persistence, retry/idempotency, and cleanup on logout or company switch;
- secure storage boundaries and avoiding sensitive data in ordinary local storage or logs;
- permission denied/blocked/cancel paths, file URI lifetime, and untrusted file handling;
- accessibility, small screens, keyboard/inset behavior, and meaningful iOS/Android differences.

Make simulated conditions deterministic when practical—for example, an online/offline toggle, fake API outcomes, seeded secure-storage adapter, or controllable permission state. Test the highest-risk pure state and data logic first; add component, native-boundary, or end-to-end coverage where it materially strengthens your claims. A large device matrix, both production-signed platforms, real third-party services, and full E2E automation are optional extensions.

If the mobile client uses an API, provide a hosted synthetic API or a reproducible local fake/backend and explain simulator networking or base-URL setup. The destination API remains authoritative for company scope, record access, and state-changing authorization; possession of a deep link, cached record, biometric unlock, or visible button is not authorization.

Keep this explanation concise in the existing `README.md` and `DECISIONS.md`; no additional mobile document is required.

## Required submission and documentation

- Source repository or archive.
- Deployed preview or reproducible deployment instructions.
- A concise project `README.md` based on the submission template.
- A concise `DECISIONS.md` covering assumptions, important tradeoffs, deliberate omissions, and next steps.
- Automated tests or another executable verification harness focused on the highest risks.
- A short demo path reviewers can follow in five minutes.

Those are the only two required supporting documents. Diagrams are welcome when they make the design easier to understand, but are not required.

If an external service requires a key, provide a local fake or documented degraded mode. Do not send us personal API keys.

## AI and tool-use policy

You may use AI for ideation, architecture, coding, tests, debugging, documentation, deployment, or review. You may use one model or many, a single assistant or several agents—or no AI at all. AI use is not an evaluation requirement and there is no preferred model or workflow.

In the README, briefly list the development tools you used. If AI materially contributed, summarize:

- model/product and editor, CLI, agent, or harness used;
- one or two consequential contributions or assumptions;
- how you verified or changed the output;
- any meaningful failure, rejected suggestion, or added review burden.

If you did not use AI, simply say so; this is scored neutrally. The optional `AI-WORKLOG.md` template is available if a more involved model/agent workflow deserves additional explanation. Full private transcripts are never required. Do not include credentials, personal information, or proprietary material.

## Discussion afterward

Expect a 60-minute conversation that includes:

- a short live demo;
- architecture and data-flow discussion;
- a code/test deep dive chosen by the interviewer;
- failure modes, security, deployment, and operations;
- your development workflow and tools, including AI validation if applicable;
- one new requirement or incident scenario;
- what you would change with another day and what you would deliberately leave alone.

You should be able to explain any submitted code, including generated code. It is fine to identify a mistake during the discussion and explain how you would correct it.

## Evaluation priorities

We use the same six competencies as the live interview path:

1. Correctness, security, and data isolation.
2. Design and maintainability.
3. Debugging, testing, and operational reliability.
4. Stack fluency and learning agility.
5. Product and financial-domain judgment.
6. Collaboration, ownership, and communication.

Deployment is evidence within design, reliability, and ownership. When AI is used, directing and verifying it is evidence within learning, debugging, and ownership. Neither is a separate score.