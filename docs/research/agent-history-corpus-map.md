# Agent History Corpus Map

## Purpose

The `.maxi/agent-history` corpus is private field material for Hearthands. It should be used to identify Max's values, code taste, agent frustrations, preferred metaphors, and writing style. Public Hearthands docs should distill from it rather than quote it directly.

## Privacy Rule

Do not copy private conversation text into public docs. Use paraphrase and distillation unless Max approves a specific quote.

## Corpus Root

Use this path as the authoritative corpus root for this pass:

- `/Users/mboch/.maxi/session-archive`

The archive contains per-agent session material, including directories for Claude, Codex, Gemini, Augment, Rovo, Kiro, Cline, and parallel runs. Many entries are JSONL session archives under agent-specific session ids or `unknown/` buckets.

## Current Evidence

On June 25, 2026, filesystem checks did not find a plainly named `agent-history` path under `/Users/mboch/.maxi` or project-local `.maxi` directories at the searched depths. Max identified `/Users/mboch/.maxi/session-archive` as the relevant corpus root.

Bounded searches against `/Users/mboch/.maxi/session-archive` found recurring material around verification/completion claims, care/maintenance/handoff language, and historical/metaphorical naming work. Some hits are task-output summaries rather than conversation prose, so extraction should distinguish user/assistant conversation from tool output before making stronger claims.

## Measurement Procedure

When local tool access is available, characterize the corpus before reading deeply:

```bash
find "/Users/mboch/.maxi/session-archive" -maxdepth 2 -type d -print
find "/Users/mboch/.maxi/session-archive" -maxdepth 3 -type f -print
```

Record file count, approximate bytes, storage format, and date range when discoverable from filenames or metadata.

## Next Extraction Step

Parse or grep `/Users/mboch/.maxi/session-archive` in bounded batches to produce paraphrased findings for `docs/research/hearthands-values-map.md`. Prefer user-authored messages and agent responses over tool-output records. Do not publish raw transcript text.

## Extraction Targets

- Values Max repeatedly defends.
- Agent behaviors Max rejects.
- Code style and review preferences.
- Writing style and metaphor preferences.
- Repeated moments that should become Hearthands skills.

## Public Distillation Rule

Use the corpus to derive principles and pressure scenarios. Do not publish raw transcript lines, emotionally specific private context, or identifying details unless Max explicitly asks for that exact material to be public.
