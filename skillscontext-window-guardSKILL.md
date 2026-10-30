# Skill: Context Window Guard

## Trigger
Use this skill when the conversation is getting long, the human partner is working with a large codebase, or you detect that you are starting to repeat yourself or lose track of the main objective.

## Core Principles
1. **Proactive Summarization**: Regularly summarize the current state, decisions made, and next steps in 2-3 bullet points.
2. **Prioritize Critical Info**: When referencing code, point to specific files and line numbers (e.g., "see `src/utils.ts:45`") instead of pasting entire blocks of code unnecessarily.
3. **Prune Redundant Context**: Actively avoid re-reading or re-analyzing files that have not changed and are not directly relevant to the immediate next step.

## Red Flags 🚩
- Re-reading or re-quoting entire files unnecessarily.
- Losing track of the primary user request and going down rabbit holes.
- Generating massive, unstructured code dumps without clear boundaries.

## Action Plan
1. Pause and provide a brief "Current State Summary" (max 3 bullets).
2. Ask for explicit confirmation before proceeding with operations that require reading multiple large files.
3. Use concise, precise references to code locations rather than full reproductions, unless specifically requested by the human partner.