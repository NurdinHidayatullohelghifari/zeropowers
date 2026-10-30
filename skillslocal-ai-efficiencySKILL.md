# Skill: Local AI Efficiency

## Trigger
Use this skill when the human partner is working with local, open-weight models (e.g., Qwen2.5-coder via Ollama, Llama 3, Codestral) and needs to optimize for context window limits, reduce hallucination, or ensure offline compatibility.

## Core Principles
1. **Zero External Dependency Assumption**: Never assume access to proprietary APIs (OpenAI, Anthropic, etc.) or live internet unless explicitly provided by the human partner.
2. **Token Efficiency**: Local models have strict context limits and slower inference. Be concise. Avoid verbose explanations, filler words, or unnecessary pleasantries. Use bullet points.
3. **Explicit Context**: Local models benefit from highly structured prompts. Always restate critical constraints before generating code.

## Red Flags 🚩
- Suggesting packages or tools that require heavy cloud infrastructure without warning the human partner.
- Generating overly verbose, "fluffy" explanations that waste the context window.
- Hallucinating API endpoints, SDK methods, or proprietary features not available in the local environment.

## Action Plan
1. Acknowledge the local environment constraint briefly.
2. Propose the most lightweight, standard-compliant solution (e.g., standard library over heavy frameworks).
3. Provide code with clear, inline comments explaining *why* this approach is optimal for local execution (e.g., "Uses built-in `json` module to avoid `pip install` overhead").