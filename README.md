# Astraios Cursor Rules

Cursor IDE rules for satellite mission operations — tailored to the Aurora LEO constellation on OHB platform with GMV HiFly/AutoFly ground system.

## Rules

| Rule File | Scope | Description |
|-----------|-------|-------------|
| `satellite-ops-specialist.mdc` | Always | Core persona and domain knowledge base. Defines the AI as a senior Satellite Operations Specialist with expertise across all spacecraft subsystems, orbital mechanics, RF link budgets, anomaly resolution, and regulatory compliance. Includes Aurora-specific key standards (ECSS, CCSDS, IADC) and criticality classification table. |
| `aurora-mission-context.mdc` | Always | Aurora mission-specific reference data: OHB platform details, subsystem-to-FOP prefix mappings, V5000 TM/TC mnemonic tables, PUS service catalog, spacecraft mode state machine, and flight rules (FR-01 through FR-11). |
| `mib-data-security.mdc` | Always | **Mandatory security rule.** Prohibits sending MIB, telecommand, telemetry, or satellite configuration data to any cloud service or external API. All analysis must be performed locally. |
| `installer-requirements.mdc` | Always | Enforces standalone installer packaging: no git or network dependencies at install time, vendored wheels in `vendor/`, and a build process that produces a self-contained `PAE-<version>.zip`. |
| `spell-script-conventions.mdc` | `**/*.py` | SPELL procedure script conventions for the GMV HiFly/AutoFly runtime. Defines the required header block, import structure, procedure skeleton, safety rules, and SPELL primitive reference. |
| `docx-generation.mdc` | `**/generate_docx*.py, **/generate_c13*.py` | Word document generation conventions using `python-docx`. Covers appendix ordering, MIB/SRDB enrichment from `mib.db`, markdown-to-DOCX heading mapping, and table formatting rules. |
| `fop-document-structure.mdc` | `**/FOP_Script_Documentation*.md` | Formatting template for FOP Script Documentation files: document header, per-procedure entry structure (steps, telecommands, TM verification, PPF parameters), and naming conventions. |
| `sme-verification-report.mdc` | `**/*SME*Verification*.md, **/*FOP*Verification*.md` | Structure and numbering rules for per-subsystem SME Verification Reports. Defines the six required top-level sections, per-FOP sequential numbering convention, and gap severity levels. |
| `markdown-ops-docs.mdc` | `**/*.md` | General markdown formatting conventions for all operations documentation: metadata blocks, section numbering, table syntax, inline formatting for TC/TM mnemonics, and cross-reference patterns. |
