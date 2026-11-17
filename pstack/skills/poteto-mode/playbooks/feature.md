### Feature

**You own the design. Plan, build, verify.** Work in the main thread.

1. Trace the affected subsystem.
2. `architect` for the shape.
3. Write the code yourself with a specific scope (file paths, named data shape and its organizing structure per **principle-model-the-domain**, a state machine over scattered booleans, a table/registry over branching, a typed model over repeated shape assumptions, chosen before you write logic, and success criteria). When the implementation admits multiple valid shapes (error handling, abstraction layer, test structure), pick the simplest that keeps the data shape from step 2 and say why. Surgical edits, re-ground against the source for upstream-derived files. Port shared-primitive improvements to all consumers and verify each. Commit liberally.
4. Verify on the matching surface. "Inconclusive" or wrong-surface is not a pass. Flag it.
5. Rebase into small, ordered commits. Stack follow-ups.
   Use the **sequence-verifiable-units** principle skill, building, verifying, and committing each small unit before the next.
6. If the design is contested, review it against the data shape and boundaries from step 2 before shipping.
7. Run **Opening a PR**.

**Reply:** what you built, what you chose and why, open decisions. Tables for design alternatives.
