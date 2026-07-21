# Framework: Analyze Boundaries and Risk

## Input
- Packed XML file from Step 1
- Structure analysis from Step 2

## Process

1. **Dependency Extraction**:
   - Parse manifest files: `package.json`, `Gemfile`, `requirements.txt`, `go.mod`, `Cargo.toml`
   - Extract all direct and transitive dependencies
   - Identify runtime, development, and optional dependencies
   - Flag any unusual or proprietary dependencies

2. **License Detection**:
   - Search for `LICENSE`, `COPYING`, or license field in manifests
   - Classify as: MIT, Apache 2.0, GPL, AGPL, Proprietary, or Unknown
   - **Gate**: Copyleft or unknown license forces `rec:watch` or `rec:drop`

3. **Lock-in Risk Assessment**:
   - Vendor lock: Does it tie to a specific cloud provider or SaaS platform?
   - Proprietary runtime: Does it require paid tools, custom runtimes, or closed ecosystems?
   - Fork risk: Is the project actively maintained? Single maintainer?
   - Community: How large is the user/contributor base?

## Output

Boundary report containing:
- Dependency summary (count, categories, risk flags)
- License verdict and copyleft warning (if applicable)
- Lock-in risks: cloud lock, runtime proprietary, fork risk, maintenance
- Community health: stars, contributors, commit frequency

## Success Criteria
✓ License status is clear; copyleft is flagged  
✓ Lock-in risks are specific (not vague)  
✓ Dependency tree is extracted, not estimated
