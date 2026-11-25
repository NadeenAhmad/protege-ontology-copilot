# Ontology Copilot requirements

Ontology Copilot was designed against the requirements below. FR is a functional requirement and NFR a non-functional requirement.

## Functional requirements

| ID | Requirement |
|---|---|
| FR1 | Allow users to define the project's domain, purpose, scope, languages, and constraints. |
| FR2 | Accept competency questions, user stories, domain documentation, and existing ontologies or ontology fragments as input. |
| FR3 | Identify candidate concepts and relationships in the supplied input. |
| FR4 | Recommend a peer-reviewed generation method based on project information and documented method capabilities. |
| FR5 | Explain the suitability, prerequisites, and limitations of the recommended method. |
| FR6 | Allow users to override the method recommendation. |
| FR7 | Allow users to compare the capabilities of supported methods. |
| FR8 | Generate a complete ontology draft using the selected method. |
| FR9 | Generate a selected ontology fragment, such as a topic module or a model addressing specified competency questions. |
| FR10 | Allow users to compare outputs produced by different methods for the same task. |
| FR11 | Allow users to select ontology elements as context for subsequent operations. |
| FR12 | Support ontology editing through natural-language instructions. |
| FR13 | Present proposed changes for user review before applying them. |
| FR14 | Allow users to accept, reject, or request revisions to proposed changes. |
| FR15 | Allow users to undo accepted changes. |
| FR16 | Record the triggering inputs, method, underlying model where applicable, and rationale for each change set. |
| FR17 | Generate labels in user-selected languages for ontology elements. |
| FR18 | Translate existing labels into user-selected languages. |
| FR19 | Export ontologies in a format compatible with Protégé. |

## Non-functional requirements

| ID | Requirement |
|---|---|
| NFR1 | Preserve existing identifiers and unaffected ontology content during incremental editing. |
| NFR2 | Preserve ontology structure and language annotations during label generation and translation. |
| NFR3 | Minimize repeated context entry across generation and editing operations. |
