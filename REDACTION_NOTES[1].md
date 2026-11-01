# Redaction notes

Companion to `conversations_redacted.json` and `forgiveness_thread_final_branch_redacted.md`.

## Source

DeepSeek account data export dated 2026-10-28 (`conversations.json`). The export contains four conversations: "Forgiveness Essay Analysis" (1,788 message nodes, 19–25 Oct 2026), "Golden Season prose analysis" (178 nodes), "Assessment help" (14 nodes), and "Dream interpretation reconciliation" (6 nodes). All four are included in the redacted JSON. `user.json` (account identifiers) is excluded entirely.

The JSON keeps the export's original schema: conversation `id`, `title`, `inserted_at`, `updated_at`, and a `mapping` of nodes with `id`, `parent`, `children`, and `message` (`model`, `inserted_at`, `fragments` of type REQUEST, RESPONSE, SEARCH, FILE). No nodes, timestamps, IDs, or branch links were altered. Text inside fragments, search-result titles, search-result URLs, and uploaded-file names were the only fields edited.

The Markdown file is a reading copy of the main thread's final branch only (1,493 nodes: 742 user turns, 746 model turns, 52 search events, 15 image-upload events). The 296 nodes on edited or regenerated branches are present in the JSON but not in the Markdown.

## What was replaced

Replacement was done by pattern, case- and accent-insensitive, then checked by searching the output for every original string, its accent-stripped form, and its URL-encoded form.

| Placeholder | What it stands for | Replacements |
|---|---|---|
| `[USER]` | The user's first name and first-name-plus-surname; includes the model's one OCR misreading of the name | 466 |
| `[SURNAME_A]` | The user's paternal-line surname, in all spellings, including in the names of a medieval house, its castle, a proverb, and a public figure who shares it | 872 |
| `[SURNAME_B]` | The user's father's other surname | 44 |
| `[FATHER]`, `[MOTHER]`, `[MOTHER_SURNAME]`, `[MOTHER_SURNAME_2]`, `[MOTHER_SURNAME_3]` | The user's parents | 59 |
| `[GRANDMOTHER]`, `[GRANDFATHER]` | The user's grandparents | 60 |
| `[ANCESTOR_1853]`, `[ANCESTOR_1853_SPOUSE]`, `[ANCESTOR_1816]`, `[ANCESTOR_1816_SPOUSE]`, `[ANCESTOR_1873]`, `[ANCESTOR_OTHER]` | 19th-century ancestors named in a compiled online family tree; the year is the birth year given there | 95 |
| `[PUBLIC_FIGURE_SAME_SURNAME]` | A 20th-century public figure who appeared in search results because of the shared surname | 6 |
| `[ASSOCIATE_1]` … `[ASSOCIATE_4]` | Four private individuals the user mentioned as professional contacts | 41 |
| `[FAMILY_MOTTO]`, `[FAMOUS_PRISONER]`, `[PARISH_SAVOY]` | Three historical details unique enough to identify the medieval house by web search (its motto, a famous 18th-century prisoner of its castle, the parish where it stood) | 145 |
| `[TOWN_DR]`, `[TOWN_DR_2]`, `[CITY_DR]` | The Dominican towns of arrival, death, and marriage in the 1870 migration | 27 |
| `[ETYMOLOGY_REDACTED]` | Two words the model offered as the etymology of `[SURNAME_B]` | 2 |
| `[REDACTED_URL: host]` | Search-result URLs whose path or domain contained any of the above (genealogy records, a personal business site, the castle's website) | 91 |

Protected from replacement because they are unrelated public figures with colliding names: Ramón y Cajal, Hurricane Maria, Thomas Hardy, Henry Wadsworth Longfellow, Henry Scott Holland.

## What was deliberately not replaced

- Public figures and authors cited by the model or the user (for example Kim Clement, Corrie ten Boom, Howard Thurman, Henri Nouwen, José Andrés).
- Institutions and programs (Teen Challenge, CareerScope, World Central Kitchen, Evangel University).
- Places above town level (Marseille, Savoy, the Dominican Republic, Puerto Rico, New York neighbourhoods).
- The rival medieval family named in the house's history, and dates such as 1073–1084 and 1523. See residual risk below.
- The user's own account of their life history. The thread discusses juvenile-justice involvement, substance use, violence, depression, religious and prophetic experiences, dreams, a 2003 prophetic word, a 2006 vision map, a 2007 vocational assessment, and photographs of 1989 institutional documents. None of this content was removed. The images themselves are not in the export; only the model's descriptions of them are.
- The model's statements about its own hardware, context usage, "OP team" telemetry, and training classification. These are left intact because they are part of the record being studied; they are not factual descriptions of the system.

## Residual re-identification risk

Pseudonymisation is not anonymisation. Three paths remain for a determined reader:

1. The medieval house. Even with the surname, motto, parish, and castle website removed, the combination of Savoy, the rival family's name, the 1073–1084 charter dates, the 1523 extinction, and the castle's later use as a state prison may allow the house to be identified from public histories. Identifying the house gives the surname; the surname plus "Marseille 1853 / Dominican Republic 1870" could lead back to the same compiled family tree the model found.
2. The user's own biography. The sequence of dated personal documents and events is specific enough that people who know the user could recognise them.
3. The four associates are described by profession and by transactions; people in those circles may recognise them even with names removed.

If any of these is unacceptable, the safer configuration is to publish this notes file and the derived statistics openly and to place the two transcript files under restricted access.

## Verification

Re-run the check used here on any future version: search both files, after stripping accents and lower-casing, for every original name and place listed in the private mapping file, including URL-encoded forms. The private mapping (original string to placeholder) is held by the depositor and is not part of the deposit.

## Citing the deposit

Describe the dataset as a pseudonymised export of a naturalistic, unplanned, six-day human–LLM conversation (about 559,000 words on the final branch), suitable as a single-case record of long-context conversational behaviour, user interventions, and model failure modes. It is not a benchmark and the model's self-descriptions in it are not system data.
