# COMPOUND NET

*What We Have Learned – and What We Are Waiting For*

**Closing Research Document  |  9 November 2026**

Original idea and research direction: Michael Lundqvist, Sweden. Research and documentation: Michael Lundqvist in collaboration with ChatGPT.

## An Idea Still Worth Exploring

Compound Net (CN) began with a simple but far-reaching idea: specialist knowledge previously acquired by independently trained neural networks could be made available to a new combination network (KN). The experts provide their assessments of a problem; KN also receives the original information and independently decides whether, when, and how those expert assessments should be used.

The ambition has never been that CN must outperform conventional AI on every task. Rather, it is to investigate whether relevant knowledge already learned can be reused – perhaps with lower prediction error, fewer new training observations, or a smaller new KN.

## What the Research Has Shown So Far

Early synthetic proof-of-principle experiments produced clear positive indications with frozen experts and small combination networks. Later studies using more realistic objectives, stronger controls, and measured real-world data yielded mixed or negative results. Some expert representations helped; others were redundant or made predictions worse.

The technical work has demonstrated that expert models can be pretrained, frozen, and reused. It has not demonstrated that CN is generally more efficient than well-optimized conventional networks. Most importantly, the research has not yet established the broad, robust specialist competence that the full concept requires. In several tests, KN capacity was also too limited to permit a fair assessment.

**The project’s most important outcome is therefore not a final winner, but a clearer understanding of the capabilities that still need to be developed.**

## Six Research Areas We Are Waiting For

**F1 · Mixed Knowledge Within an Expert Domain**

An expert must be able to learn multiple techniques, principles, and relationships within its own specialty, keep them distinct, and apply the appropriate knowledge in the appropriate context.

**F2 · Mixed Levels of Difficulty**

The same expert must be able to handle both simple and complex problems without learning one class of problems at the expense of the other.

**F3 · Variable Numbers of Inputs**

Networks must reliably handle few or many input values without manual reconfiguration for each new problem.

**F4 · Variable Input Positions**

The same quantities should be representable as A–B–C or C–B–A without confusing their meanings. This requires the network to understand identity and structure, rather than relying solely on positional indices.

**F5 · Physical Quantities and Units as Part of the Data**

A numerical value should be accompanied by what it measures, the unit in which it is expressed, and the conditions under which it applies. Semantic and dimensional correctness are essential to knowledge transfer.

**F6 · Information Allocation and Dimensionality**

As control signals, expert assessments, and internal representations grow, the system must be able to determine which information each network component needs, how that information should be represented, and how useful relationships can be preserved without unnecessary complexity.

## What Else Is Needed to Test CN

Even if progress is made in these six areas, reliable research data will remain essential: independently trained and broadly qualified experts, relevant new tasks, known pretraining exposure, sufficient KN capacity, and genuinely independent final tests. A fair comparison requires both CN and conventional alternatives to receive serious optimization, with the cost of the complete expert system reported separately from the number of newly trainable KN parameters.

## When the Research Can Resume

We do not need to wait until all six problems are fully solved. A reasonable next stage becomes possible when the technology provides at least one broadly qualified expert, a relevant new problem, and data that allow knowledge transfer to be tested without building the desired result into the experiment. One robust positive scenario could then provide a starting point for studying how and why CN works.

## A Closing Note – Not a Farewell

Compound Net is now being set aside as an open foundational research concept. We close this phase with more questions than definitive answers, but also with a much clearer map of the road ahead. Several of the obstacles are central challenges for AI research as a whole; progress in those areas may eventually give CN entirely new possibilities.

**The idea has not been proven – but neither has it been disproven. It has been formulated, tested, critically examined, and preserved for the future.**

*Compound Net can wait for the technology. Curiosity need not wait.*