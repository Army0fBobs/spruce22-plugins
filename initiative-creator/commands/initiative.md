---
description: Start a new initiative. Walks the 5-step PM coaching flow (Insight → Initiative → KPIs → Epics → Pitch).
argument-hint: [optional topic hint, NOT the title]
---

Invoke the `initiative-creator` skill.

The skill always starts with the **insight** (Step 1), not the title. The title is derived later from what the PM is actually building (Step 2).

If $ARGUMENTS is provided, treat it as a hint about the topic area — useful background for the Step 1 conversation — but NOT as the title. If $ARGUMENTS reads like a feature name ("push notifications," "new pricing page"), the skill will explicitly back the PM up and ask what observation pointed them at that feature.

If $ARGUMENTS is empty, the skill will detect any in-progress draft in the current directory and offer to resume; otherwise it jumps straight to the insight question.
