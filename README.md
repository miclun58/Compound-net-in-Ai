# Compound-net-in-Ai

Abstract
Compound Net is an architecture in which under-dimensioned generalizing expert networks (professors) are trained exclusively on their respective domains, frozen, and thereafter contribute their outputs via concatenation with the original input features to a minimal serial combiner network. This report presents the results of experiments CN1 through CN4. In every version a linear combiner containing 13–17 trainable weights matched or outperformed a standalone baseline network containing 449–897 weights, corresponding to parameter ratios of 26:1 to 56:1. The central hypothesis of the project is thereby confirmed.

## Research Documents

- **[Original Scientific Report — Compound Net (PDF)](Compound%20Net%20in%20Ai.pdf)** — The original report covering the architecture, methods, and experiments CN1–CN4.
- **[Open Research Challenge: Integrating Mixed Expert Knowledge](OPEN_RESEARCH_CHALLENGE.md)** — A companion research note outlining unresolved questions, limitations, and suggested directions for further investigation.
- **[Fingerprint Handling – Method and Tendencies (Swedish, PDF)](Compond%20net%20och%20Data%20dom%C3%A4ner.pdf)** — Focused note on how domain fingerprint (Di) is handled, including size comparisons and gating experiments.
- **[Fingerprint Handling – Method and Tendencies (English, PDF)](Compound%20net%20and%20Data%20domains.pdf)** — English version of the fingerprint handling research note.
- **[The Combination Network and Concatenation (Swedish, PDF)](Compound_Net_Kombinationsnatet.pdf)** — Describes how concatenation and the combination network work, with diagram and results (16.7% relative RMSE).
- **[The Combination Network and Concatenation (English, PDF)](Compound_Net_Combination_Network_EN.pdf)** — English version of the combination network document.

## Invitation to Continue the Research

This project is open to independent investigation, replication, critique, and further development. Researchers and AI developers are invited to explore the documents above and share ideas or findings in **[Issue #1 — Invitation](../../issues/1)**.
