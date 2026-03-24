---
name: nk-modeling-simulation
description: Guide researchers through the full workflow of NK landscape modeling and simulation for strategy/organization research. Use this skill whenever the user mentions NK model, NK landscape, fitness landscape, rugged landscape, complexity theory in organizations, interdependence modeling, or wants to model organizational design, modular vs integrated architectures, exploration vs exploitation, or similar strategy/organization theory questions using computational simulation. Also trigger when the user wants to extend classic NK models (e.g., adding agent search, multi-population dynamics, temporal shocks, or coupling across landscapes). This skill covers the entire pipeline from research question formulation to model specification, simulation coding, parameter sweeps, and result interpretation.
---

# NK Modeling & Simulation for Strategy Research

This skill guides the full workflow of translating a strategy or organization theory research question into an NK landscape model and simulation. It follows a structured pipeline that mirrors how experienced researchers approach computational theory building.

## Why this matters

NK models are powerful tools for studying complexity, interdependence, and adaptation in organizations. But the gap between having a research question and producing meaningful simulation results is large. This skill bridges that gap step by step — helping with conceptual mapping, model specification, code generation, and interpretation.

## The Workflow

The pipeline has 5 phases. Always work through them in order, though iteration back to earlier phases is natural and expected.

---

### Phase 1: Research Question → Conceptual Mapping

Start by understanding the research question deeply before touching any model.

**Ask the researcher:**
1. What is the core theoretical question? (e.g., "When does modularity help organizational adaptation?")
2. What is the key tension or tradeoff? (e.g., modularity enables local search but may miss global optima)
3. What are the main constructs involved? (e.g., organizational structure, task interdependence, environmental change)

**Then help map constructs to NK elements:**
- **N (elements):** What are the decision variables or design choices? These should be the atomic-level choices that collectively define an organizational design, strategy, or configuration. For example: N individual practices, routines, policies, or technology choices.
- **K (interdependence):** What is the pattern of interaction among these elements? K captures how many other elements each element's fitness contribution depends on. Think about: which decisions constrain or interact with which others?
- **Fitness function:** What does "performance" mean in this context? How is fitness calculated from the individual element contributions?
- **Search process:** How do agents explore the landscape? (e.g., local search flipping one bit at a time, long jumps, imitation of others)

**Provide a conceptual mapping summary** in this format:

```
Research Question: [question]
N represents: [what the elements are]
K represents: [what the interdependence pattern captures]
Fitness: [how performance is defined]
Search: [how agents move on the landscape]
Key mechanism: [the core theoretical insight the model should reveal]
```

This mapping is the most important step. Push back if the mapping feels forced — not every question fits NK naturally.

---

### Phase 2: Classic NK or Extended Model?

After the conceptual mapping, evaluate whether the classic NK model is sufficient or needs extension.

**The classic NK model handles:**
- Single population of agents searching a fixed landscape
- Uniform random interdependence structure
- Single-bit local search
- Static fitness landscape

**Common extensions (and when they are needed):**

| Extension | When to use |
|---|---|
| **Structured interdependence** (block-diagonal, modular, hierarchical) | When organizational structure creates non-random patterns of interaction |
| **Multi-agent / multi-population** | When firms interact, imitate, or compete on the same or coupled landscapes |
| **Dynamic landscapes** (temporal shocks, drifting fitness) | When the environment changes over time |
| **Alternative search strategies** (long jumps, recombination, directed search) | When you want to compare different adaptation processes |
| **Coupled landscapes** (NKCS model) | When multiple interacting systems co-evolve |
| **Decomposition / near-decomposability** | When modeling Simon-style hierarchical systems |
| **Stochastic fitness evaluation** | When agents have imperfect information about payoffs |

**Help the researcher decide** by asking:
- Does your theory require features beyond the classic model?
- What is the minimum extension needed to capture your mechanism?
- Simpler is better — every extension needs theoretical justification.

Document the model choice and rationale before proceeding.

---

### Phase 3: Model Specification

Now formalize the model parameters. Work with the researcher to specify:

**Core parameters:**
- **N** (number of elements): Typical range 6–20 for strategy research. Larger N increases computational cost exponentially. Justify the choice.
- **K** (interdependence): Range 0 to N-1. K=0 is fully decomposable, K=N-1 is maximally complex. Often the key independent variable.
- **Number of landscapes**: How many independent landscape realizations to average over (typically 100–1000 for stable results).
- **Number of agents per landscape**: How many independent searchers per landscape.
- **Search rounds (T)**: How many time steps of adaptation. Should be long enough for convergence but not wastefully long.

**Interdependence structure:**
- Random (classic): Each element's K neighbors are randomly assigned
- Block-diagonal / modular: Elements grouped into modules with dense within-module and sparse between-module links
- Custom: Specify the interaction matrix explicitly if theory requires it

**Search process:**
- Local search: Flip one random bit, adopt if fitness improves
- Greedy local search: Evaluate all single-bit flips, adopt the best
- Stochastic: Accept worse solutions with some probability
- Custom: Describe the process and the skill will help formalize it

**Output the specification** as a structured parameter table:

```
=== Model Specification ===
N: [value] — [justification]
K: [values to sweep] — [justification]  
Landscapes: [number]
Agents per landscape: [number]
Search rounds: [T]
Interdependence structure: [type]
Search process: [type]
Extensions: [list any]
Key comparison: [what varies across conditions]
```

---

### Phase 4: Simulation Code

Generate Python simulation code following these principles:

**Code structure:**
1. `generate_landscape(N, K, structure)` — Create the fitness landscape
2. `calculate_fitness(position, landscape)` — Evaluate a position
3. `search_step(position, landscape, strategy)` — One step of adaptation
4. `run_simulation(params)` — Full simulation run for one parameter setting
5. `run_experiment(param_grid)` — Sweep across parameter combinations
6. `plot_results(results)` — Visualization

**Best practices:**
- Use NumPy for performance; avoid pure Python loops over landscapes
- Set random seeds for reproducibility
- Save raw results (not just averages) for statistical analysis
- Use multiprocessing for parameter sweeps when computationally heavy
- Include progress reporting for long runs
- Comment the code to explain the theoretical meaning of each component, not just the technical implementation

**Validation checks to include:**
- Verify K=0 produces smooth (single-peak) landscapes
- Verify K=N-1 produces maximally rugged landscapes
- Check that average fitness increases over search rounds (for greedy local search)
- Confirm results are stable across different numbers of landscape realizations

**Visualization defaults:**
- Fitness over time (mean ± standard error across landscapes)
- Final fitness vs. K (the classic NK result)
- Distribution of final fitness across landscapes for each condition
- Any comparison relevant to the research question

Always generate the code in a single, self-contained Python script that the researcher can run immediately. Use matplotlib for plotting. Include a `if __name__ == "__main__"` block with sensible default parameters.

---

### Phase 5: Interpretation — "Reading the Figures"

After running the simulation, help the researcher interpret results:

**Standard patterns to look for:**
- **Fitness vs. K curve:** Higher K typically leads to lower final fitness due to ruggedness — but the *shape* of this relationship often contains the theoretical insight
- **Convergence speed:** How quickly do agents reach stable configurations? Faster is not always better theoretically.
- **Variance across landscapes:** High variance may indicate that results are fragile or context-dependent
- **Crossing patterns:** When do two conditions (e.g., modular vs. integrated) switch their relative performance? These crossover points are often the most theoretically interesting findings.

**Guide the researcher through:**
1. Does the simulation reproduce the expected baseline behavior? (sanity check)
2. Where is the "a-ha" moment — the non-obvious result that the model reveals?
3. Is the mechanism clear? Can you explain *why* the pattern emerges, not just *that* it emerges?
4. What are the boundary conditions? Under what parameters does the result reverse or disappear?
5. How robust is the result to changes in assumptions?

**If the results are not compelling:**
- Revisit the conceptual mapping (Phase 1) — is the research question well-captured?
- Check the model specification — are parameters in a meaningful range?
- Consider whether an extension is needed to reveal the mechanism
- Try alternative visualizations that might reveal the pattern more clearly

The goal is not just to produce a simulation, but to find and articulate the core theoretical mechanism. The simulation is a tool for building and demonstrating theory.

---

## Iterating

NK modeling is inherently iterative. Common iteration patterns:

- **Mapping doesn't fit** → Rethink whether NK is the right modeling framework, or consider extensions
- **Results are obvious** → The model may be too simple; consider adding a theoretically motivated complication
- **Results are messy** → Increase landscape replications, narrow parameter ranges, or simplify the model
- **Mechanism is unclear** → Add intermediate diagnostics (e.g., track landscape ruggedness, number of local optima, search path characteristics)

At each iteration, always return to the research question: does the model help answer it?

---

## Quick Reference: Common Pitfalls

1. **Forcing a question into NK** — Not every strategy question maps naturally to an NK landscape. If the mapping feels awkward, it probably is.
2. **Too many extensions at once** — Each extension should be theoretically justified. Start simple, add complexity only when needed.
3. **Insufficient replications** — Results based on fewer than 100 landscapes are unreliable. Use 500+ for publication-quality work.
4. **Ignoring boundary conditions** — Always sweep K from 0 to N-1 (or a meaningful range) to see the full picture.
5. **Describing results without mechanism** — "Higher K leads to lower fitness" is a finding, not a contribution. The contribution is explaining *why* and *when* and *what it means* for the theory.
6. **Overfitting the model to desired results** — If you keep tweaking until you get the "right" answer, the model is not building theory. Let the model surprise you.
