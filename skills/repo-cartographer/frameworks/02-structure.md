# Framework: Structure Analysis

## Input
- Packed XML file from Step 1

## Process

1. **Directory Tree**: Parse the XML and build a hierarchical tree showing:
   - Top-level directories and their roles (src/, tests/, docs/, config/, etc.)
   - Second-level subdirectories for major packages/modules
   - Per-directory file count and size summary

2. **File Metrics**: For each file, extract or estimate:
   - Language (detected from extension)
   - Approximate token count (rough: chars ÷ 4)
   - Complexity indicator (lines, nesting depth if parseable)

3. **Tech Stack Detection**:
   - Parse `package.json`, `Gemfile`, `requirements.txt`, `go.mod`, `Cargo.toml`, etc.
   - Identify frameworks, runtime, major dependencies
   - Detect build tools (webpack, Gradle, Make, etc.)

## Output

Structure report containing:
- Directory hierarchy tree (first 4 levels)
- Tech stack summary (language, framework, runtime)
- Large files or hot spots (files >50KB, deeply nested)
- Language distribution (% Python, JS, Go, etc.)

## Success Criteria
✓ Directory tree reflects actual repo structure  
✓ Tech stack matches manifest files  
✓ Large files are flagged for manual inspection
