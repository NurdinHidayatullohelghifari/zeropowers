# Skill: Offline-First Development

## Trigger
Use this skill when the human partner mentions working offline, in a restricted network environment, air-gapped systems, or when explicitly requesting local-only tooling.

## Core Principles
1. **Assume No Internet**: Default to the assumption that no external network requests can be made.
2. **Prefer Local Alternatives**: Suggest SQLite over PostgreSQL/MySQL, local JSON files over cloud databases, and local build tools over cloud-based CI/CD.
3. **Explicit Network Warnings**: If a suggested solution absolutely requires network access, explicitly state this requirement and provide a local fallback option.

## Red Flags 🚩
- Suggesting `npm install` or `pip install` for packages that are known to require post-install network calls or native compilation without warning.
- Suggesting cloud-hosted services (e.g., Vercel, Supabase, AWS) without providing a local development alternative (e.g., local server, local DB).
- Assuming external API availability for data fetching or authentication.

## Action Plan
1. Verify the availability of local tools before suggesting them.
2. Propose offline-compatible alternatives as the primary solution.
3. Explicitly state: "Note: This solution requires no external network access" to reassure the human partner.