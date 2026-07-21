# Framework: Trace Execution and Modules

## Input
- Packed XML file from Step 1
- Structure analysis from Step 2

## Process

1. **Entry Point Discovery**: Grep the packed XML for:
   - CLI commands: `#!/usr/bin/env`, `bin/`, `main()`, `argparse`, `click`, `cobra`
   - HTTP listeners: `listen()`, `app.listen()`, `:PORT`, `bind()`
   - Event handlers: `subscribe()`, `.on(`, `event_listener`
   - Imports/exports: `module.exports`, `export`, `__main__`
   - Package entry points: `main`, `bin` fields in package manifests

2. **Key Module Tracing**: Identify core responsibilities:
   - Business logic (domain models, rules engines)
   - Data access (repositories, DAOs, queries)
   - API/routing (controllers, handlers, middleware)
   - Utilities and shared libraries
   - Configuration and setup

3. **Data Flow**: Trace request → processing → output:
   - Where does input enter (HTTP, CLI, files, streams)?
   - What validates and transforms it?
   - Where is state stored (database, cache, file)?
   - How does output leave the system?

## Output

Trace report containing:
- Entry point list with file paths and type (CLI/HTTP/event/library)
- Key module list with one-line responsibility per module
- Data flow diagram (input → [validation] → [processing] → [storage] → output)
- Major code paths and their files

## Success Criteria
✓ Entry points are concrete file paths  
✓ Each key module has a stated responsibility  
✓ Data flow traces real code, not inference
