# 🫶 Hearthands

Care Work for coding agents.

Hearthands is a grounded development practice for agents working in shared codebases. It asks the agent to clarify intent, reduce maintenance burden, verify with evidence, and leave the project easier to continue.

This is not a claim to a new school of software development. It is a deliberately care-oriented synthesis of older traditions that already knew software work was human, adaptive, and unfinished.

## Historical Grounding

Hearthands descends from the Agile tradition, especially the 2001 Manifesto for Agile Software Development: individuals and interactions, working software, customer collaboration, and responding to change. The Agile principles also name sustainable development, technical excellence, reflection, and simplicity as first-class concerns.

It also draws from Adaptive Software Development, associated with Jim Highsmith and Sam Bayer, which replaced waterfall certainty with cycles of speculate, collaborate, and learn. That lineage matters: planning is treated as a provisional act, collaboration is how uncertainty is handled, and learning is part of the work rather than a postmortem after it.

Lean Software Development, popularized for software by Mary and Tom Poppendieck, contributes the language of waste, learning, delayed commitment, empowered teams, and optimizing the whole. Hearthands treats avoidable process, unclear ownership, and future maintenance burden as forms of waste.

The care framing is the contemporary part: agents should not merely complete tasks. They should preserve context, reduce harm to future maintainers, and keep human collaborators oriented.

## Practice

Before acting, ask:

1. What is the user actually trying to make possible?
2. What existing code, convention, or tool can carry this?
3. What future work does this make easier or harder?
4. What evidence will show that the change works?
5. What should be left behind so the next person can continue?

Prefer care over spectacle, evidence over panic, and sustainable progress over procedural theater.

## Skills

- `hearthands`: general care-oriented development practice.
- `hearthands-brainstorming`: intent, design, scope, and maintenance-burden exploration before implementation.
- `hearthands-verification`: evidence before confidence when claiming work is complete, fixed, passing, or ready to hand off.
- `hearthands-debugging`: patient evidence before intervention when behavior is failing, flaky, surprising, or only partly understood.
- `hearthands-planning`: clear handoff as care when work needs durable steps before implementation, delegation, or handoff.
- `hearthands-execution`: steady follow-through with care when executing written implementation plans.
- `hearthands-handoff`: leave the branch understandable when completing development work and choosing merge, PR, or cleanup.
- `hearthands-containment`: reversibility and containment using isolated workspaces as care for shared state.
- `hearthands-small-promises`: witnessed behavior before trust when implementing features or bugfixes.
- `hearthands-review`: care for the next reader when requesting, receiving, or acting on code review.
- `hearthands-skillwriting`: durable care instructions when creating new skills or editing existing ones.
- `hearthands-parallel-care`: coordination without context loss when working on independent tasks in parallel.
- `hearthands-delegation`: reviewable delegation when executing implementation plans with independent tasks.

## Roadmap

- `docs/goal.md`: project goal statement.
- `docs/superpowers-map.md`: current map from Superpowers skills to Hearthands equivalents.
- `docs/rewrite-guide.md`: process for reframing upstream skills through Hearthands principles.
- `docs/research/hearthands-values-map.md`: public distillation of values that guide rewrites.
- `docs/research/agent-history-corpus-map.md`: private-corpus handling and extraction notes.

## Skill Lineage

Each Hearthands skill draws from specific traditions. This section maps skills to their lineage so contributors can understand the values embedded in each behavior.

- `hearthands` — care-oriented synthesis of Agile, Adaptive Software Development, and Lean Software Development.
- `hearthands-brainstorming` — shared sensemaking before ownership, rooted in Agile collaboration and Adaptive Software Development's speculate phase.
- `hearthands-verification` — evidence before confidence, drawn from empirical software practice, test-first development, code review, operations handoff, and maintenance work.
- `hearthands-debugging` — patient evidence before intervention, from Adaptive Software Development's learning orientation, empirical debugging, root-cause analysis, operations incident response, and test-driven regression work.
- `hearthands-planning` — clear handoff as care, from Agile planning, Adaptive Software Development, Lean Software Development, release engineering, and maintenance handoff practice.
- `hearthands-execution` — steady follow-through with care, from Agile iteration, Adaptive Software Development's learning orientation, release engineering, and maintenance handoff practice.
- `hearthands-handoff` — leave the branch understandable, from release engineering, Git workflow discipline, maintenance handoff, and the understanding that integration is a social act as much as a technical one.
- `hearthands-containment` — reversibility and containment, from Git workflow discipline, sandboxing practice, and the understanding that isolation is respect for shared state.
- `hearthands-small-promises` — witnessed behavior before trust, from Extreme Programming, test-first development, and the maintenance understanding that untested code is debt.
- `hearthands-review` — care for the next reader, from code review practice, operations handoff, and the understanding that review is a social act with technical content.
- `hearthands-skillwriting` — durable care instructions, from the Superpowers writing-skills lineage and the understanding that process documentation is itself a craft.
- `hearthands-parallel-care` — coordination without context loss, from parallel agent dispatch, distributed systems coordination, and the understanding that fragmentation is a form of waste.
- `hearthands-delegation` — reviewable delegation, from subagent-driven development, the understanding that outsourcing judgment is not care, and the need for reviewable handoffs.

## Sources and Hat Tips

- [Manifesto for Agile Software Development](https://agilemanifesto.org/)
- [Principles behind the Agile Manifesto](https://agilemanifesto.org/principles.html)
- Jim Highsmith, _Adaptive Software Development: A Collaborative Approach to Managing Complex Systems_
- Mary and Tom Poppendieck, _Lean Software Development: An Agile Toolkit_
- The long practical lineage of maintainers who learned that software quality is social, technical, and ecological at the same time.
