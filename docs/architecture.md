# Architecture

```text
Trusted scored diagnostic recommendation
  → deriveAuthorizedAction
    → NO_ACTION: stop this bounded decision
    → VERIFY_MORE: provisional skill hypotheses
      → trusted, independently bound follow-up correctness
      → interpretClarifyingOutcome
    → TEACH: confirmed target
      → caller normalizes action shape
      → evaluateTeachAuthorizationGate
      → exact human approval + separately eligible content
      → downstream learning flow (outside this snapshot)
```

The three excerpted modules have no imports, external dependencies, database access, network access, or randomness. Minimum source dependency set: these three files only. Node.js runs the synthetic demonstration and tests.

The action contract returns `authorizedAction` and `confirmedSkill`. The clarifier returns `action` and `convergedSkill`. The caller must normalize these to `{ action, confirmedSkill }` before consulting the teaching gate. The example makes that adapter explicit.

Teaching eligibility and content release are separate decisions. Content availability does not change the evidence contract. Approval must bind the intended target and proposed content identity; content eligibility and delivery are not implemented here.

Source provenance: three selected backend excerpts, published as an independently initialized snapshot. No original repository history is included. These excerpts do not establish the current private Alpha implementation or deployment state.
