# Framework: Evaluate Against 5-Criteria Rubric

## Input
- All prior analysis: structure, trace, boundaries
- User-stated goals or use case (implicit from request)

## Process

Apply a scoring rubric across 5 criteria. Each criterion scores 0–10; recommendation threshold is 6+.

### Criterion 1: Fit (Does it solve the problem?)
- 8–10: Directly solves the stated problem; mature examples in the same domain
- 6–7: Solves the problem with some workarounds or customization needed
- 4–5: Tangentially related; would require significant adaptation
- 0–3: Does not fit the use case

### Criterion 2: Maturity (Is it stable/production-ready?)
- 8–10: v1.0+, stable API, active maintenance, >1 year history
- 6–7: Beta, recent changes, but documented and tested
- 4–5: Early alpha; undocumented; or dormant (no commits in 1 year)
- 0–3: Proof-of-concept; known instability; or abandoned

### Criterion 3: Alignment (Does it match our tech stack?)
- 8–10: Same language, framework, and ecosystem as your team
- 6–7: Different language but well-supported; minor skill gap
- 4–5: Unfamiliar tech; high learning curve
- 0–3: Incompatible runtime or platform

### Criterion 4: Risk (What's the adoption/maintenance burden?)
- 8–10: Low risk; permissive license; active community; no vendor lock
- 6–7: Moderate risk; minor license concerns or single-maintainer
- 4–5: Significant risk; copyleft license, fork risk, or hidden dependencies
- 0–3: High risk; proprietary runtime, vendor lock, or no license

### Criterion 5: Effort (How much work to integrate?)
- 8–10: <1 week to integrate and validate in your stack
- 6–7: 1–2 weeks; some customization needed
- 4–5: 2–4 weeks; significant setup, config, or learning
- 0–3: >4 weeks; major refactoring or architectural work needed

## Recommendation Logic

**rec:adopt** (scores avg ≥7): Safe to adopt after review.  
**rec:watch** (scores avg 5–6): Monitor or use in non-critical path; revisit in 6–12 months.  
**rec:drop** (scores avg <5 OR copyleft/license gate fails): Not recommended for adoption.

## Output

Evaluation report with:
- Scorecard table (5 criteria, scores, rationale)
- Eval tags: `[mature, well-tested, high-coupling, license-clear, active-community, vendor-lock, single-maintainer, proof-of-concept, …]`
- Eval note: Paragraph explaining the recommendation and trade-offs
- Final recommendation: `rec:adopt`, `rec:watch`, or `rec:drop`
- License field: Stated license or "Unknown"

## Success Criteria
✓ Scores are justified by prior analysis  
✓ License gate is enforced (copyleft → rec:watch/drop)  
✓ Recommendation is clear and actionable
