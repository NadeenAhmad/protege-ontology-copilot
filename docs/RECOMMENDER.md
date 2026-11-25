# How Ontology Copilot recommends a method

In step 1, *Purpose & scope*, **Recommend a method** suggests one of the four ontology generation methods. The recommendation follows fixed rules inside the plugin: it needs no API key, makes no LLM call, and gives the same answer for the same project every time.

It is only a suggestion. You can pick any other method under *LLM-based Ontology Generation Method* before you click **Approve method**.

## The methods and their papers

Each method builds on published research. The recommendation names the same papers.

- **Direct NL→OWL** is inspired by da Silva et al. (2024): da Silva, L. M. V., Köcher, A., Gehlhoff, F., & Fay, A. (2024). "On the Use of Large Language Models to Generate Capability Ontologies." 2024 IEEE 29th International Conference on Emerging Technologies and Factory Automation (ETFA), pp. 1–8. IEEE. https://doi.org/10.1109/ETFA61755.2024.10710775 (This plugin applies the paper's single-prompt generation to any domain, not only capability ontologies.)
- **NeOn-GPT** has two papers, the original pipeline and the extended NeOn-GPT:
  - Fathallah, Nadeen, Arunav Das, Stefano De Giorgis, Andrea Poltronieri, Peter Haase, and Liubov Kovriguina. "NeOn-GPT: A Large Language Model-Powered Pipeline for Ontology Learning." The Semantic Web: ESWC 2024 Satellite Events, LNCS 15344 (2025).
  - Fathallah, Nadeen, et al. "Extended NeOn-GPT: Advancing LLM-Powered Ontology Learning Through Ontology Reuse and Automated Verification." Semantic Web 17.4 (2026): 22104968261453138.
- **Ontogenia**: Lippolis, Anna Sofia, Miguel Ceriani, Sara Zuppiroli, and Andrea Giovanni Nuzzolese. "Ontogenia: Ontology Generation with Metacognitive Prompting in Large Language Models." The Semantic Web: ESWC 2024 Satellite Events, LNCS 15344, pp. 259–265 (2025).
- **RIGOR-Lite** builds on RIGOR: Fathallah, Nadeen, et al. "Retrieval-Augmented Generation of Ontologies from Relational Databases." ISWC (2026). RIGOR's code: https://github.com/NadeenAhmad/RIGOR

## What each method needs

| Method | Needs | Can also use |
|---|---|---|
| Direct NL→OWL | a domain, description or intended purpose | competency questions, user stories, documents about the domain |
| NeOn-GPT | a domain, description or intended purpose | ontologies to reuse, documents about the domain, user stories |
| Ontogenia | competency questions and at least one design pattern | user stories |
| RIGOR-Lite | a database schema (SQL) | documents about the domain, user stories, ontologies to reuse |

An input counts when you tick it under *What do you already have?* in step 1 or add it in step 2. A database schema added in step 2 counts only if it can be read.

## The rules, in order

1. **What you have decides first.**
   - A database schema: **RIGOR-Lite**.
   - Otherwise, design patterns: **Ontogenia**.
   - Otherwise, ontologies to reuse: **NeOn-GPT**.
2. **Otherwise, your methodology decides** (*Ontology engineering methodology* in step 1).
   - eXtreme Design: **Ontogenia**.
   - NeOn methodology: **NeOn-GPT**.
   - None — quick first draft: **Direct NL→OWL**.

   The method is recommended even if some of its inputs are still missing; the recommendation lists what to add.
3. **Otherwise, the inputs are scored.** A method gets 10 points for each required input it has and 3 points for each optional input it can use. Competency questions and user stories suit every method, so as optional inputs they earn no points. Ontogenia loses 5 points while it has no design patterns, because you can add them with one click in step 2 (*Search ODP patterns…*). A method that lacks another required input is not recommended. The highest score wins; on a tie, the more specialized method wins: RIGOR-Lite and Ontogenia before NeOn-GPT, and NeOn-GPT before Direct NL→OWL.
4. **With no domain, description, intended purpose or other input**, nothing is recommended.

## What the recommendation shows

- the recommended method and its paper(s);
- what is still to add before it can run;
- why it fits your project;
- any input you added that the method does not use;
- a note when it does not follow the methodology you chose (for example, a database schema leads to RIGOR-Lite even with the NeOn methodology).

## Examples

| You have | Methodology | Recommended |
|---|---|---|
| a domain | No preference | NeOn-GPT |
| a domain and competency questions | No preference | NeOn-GPT |
| a domain | None — quick first draft | Direct NL→OWL |
| a domain | eXtreme Design | Ontogenia (add design patterns in step 2) |
| competency questions and design patterns | any | Ontogenia |
| a database schema | NeOn methodology | RIGOR-Lite |
| an ontology to reuse | None — quick first draft | NeOn-GPT |
| nothing | No preference | none |
