# Codebase Map Report

## Summary

[One or two sentences: what is this repo and why does it matter to your evaluation?]

## Repository Structure

**Tech Stack**: [Languages, frameworks, runtimes]

**Top-Level Directories**:
- `src/`: [description]
- `tests/`: [description]
- `docs/`: [description]

**Directory Tree**:
```
repo-name/
├── src/
│   ├── main.js
│   └── handlers/
├── tests/
├── docs/
└── package.json
```

**File Metrics**:
- Total files: [count]
- Language distribution: [% JS, % Python, etc.]
- Largest files: [files >50KB]

## Entry Points

Where does code start?

| File | Type | Purpose |
|------|------|---------|
| `src/main.js` | CLI | Command-line interface entry |
| `src/server.ts` | HTTP | Web server on port 3000 |
| `src/index.js` | Library | npm package entry point |

## Key Modules

What drives behavior?

| Module | Responsibility |
|--------|-----------------|
| `src/domain/` | Business logic and domain models |
| `src/api/routes.ts` | HTTP routing and handlers |
| `src/db/` | Data access and persistence |
| `src/utils/` | Shared utilities |

## Dependencies & License

**License**: [MIT / Apache / GPL / AGPL / Unknown]

**License Concern**: [Yes/No] — [explanation if copyleft or unknown]

**Direct Dependencies**: [count]

**Major Dependencies**: [list of 5–10 largest/most important packages]

**Lock-in Risk**:
- Vendor platform: [AWS / GCP / None]
- Proprietary runtime: [Yes/No]
- Fork risk: [Low/Medium/High] — [explanation]
- Community health: [Active / Dormant / Unmaintained]

## Rubric Evaluation

| Criterion | Score | Rationale |
|-----------|-------|-----------|
| **Fit** | 8/10 | Directly solves the stated problem; mature examples |
| **Maturity** | 7/10 | Stable API; active maintenance; 2-year history |
| **Alignment** | 8/10 | JavaScript, modern frameworks; team expertise exists |
| **Risk** | 6/10 | Permissive license; single lead maintainer |
| **Effort** | 7/10 | 1–2 weeks to integrate; minimal customization |
| **Average** | 7.2/10 | — |

## Recommendation

**Verdict**: `rec:adopt` / `rec:watch` / `rec:drop`

**Reasoning**: [2–3 sentences explaining the recommendation and top trade-offs]

**Eval Tags**: `[mature]` `[well-tested]` `[active-community]` `[license-clear]` `[low-vendor-lock]`

**Next Steps**:
1. [If rec:adopt] Schedule architecture review with team
2. [If rec:adopt] Create integration spike (1–2 weeks)
3. [If rec:watch] Revisit in 6 months when [condition]
4. [If rec:drop] Explore alternatives: [names]

---

**Report Generated**: [date]  
**Repository**: [URL or path]  
**Evaluated By**: Cartographer v0.1.0
