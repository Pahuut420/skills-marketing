# Framework: Pack the Repository

## Input
- Repository URL (remote) or local directory path
- Compression preference (use `--compress` for >50k files)

## Process

Use the `repomix-explorer` skill to execute repomix. Command pattern:

```bash
# Remote repo
node <repomix>/bin/repomix.cjs --remote owner/repo --compress --style xml -o /tmp/repo-pack.xml

# Local repo
node <repomix>/bin/repomix.cjs /path/to/repo --compress --style xml -o /tmp/repo-pack.xml
```

**Key flags:**
- `--style xml`: Use XML output (more parseable than Markdown for structured analysis)
- `--compress`: Reduce token overhead for large repos
- `--source-only`: Default behavior; excludes logs, diffs, binaries

## Output
- **File**: XML document (`/tmp/repo-pack.xml`) containing the full source tree
- **Token count**: Measured from the packed file; informs downstream compression strategy
- **Failure modes**: Network timeout (remote), permission denied (local), >1GB source (escalate)

## Success Criteria
✓ Packed file is valid XML and readable  
✓ All source directories are included  
✓ No binary files or git history in output
