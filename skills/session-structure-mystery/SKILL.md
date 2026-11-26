---
name: session-structure-mystery
description: Critically review a tabletop adventure, guide mystery-focused improvements, then restructure and save it using the required overview sections and nine session phases.
---

# Session Structure Mystery

Use this skill when the user wants a supplied tabletop adventure reviewed and rewritten as a mystery using this repository's preferred session structure.

## Reference files

Before reviewing or rewriting, read both bundled files:

- [assignment_structure.md](assets/assignment_structure.md) defines the required overview sections and session phases and what each should accomplish.
- [assignment_example.md](assets/assignment_example.md) demonstrates an adventure overview and phase write-up. Use it for format only; do not copy its story content or page labels.

The structure file defines the section order and the purpose of each session phase. Keep the four overview sections first and all nine session phases separate, even though the source allows some phases to be combined and the example combines some phases.

## Inputs and interaction

1. Read the adventure text supplied in the conversation or attached file. If it is missing, ask the user to provide it before proceeding.
2. Use the adventure's existing name if supplied. Otherwise, provide exactly 15 distinct name options grounded in its content and wait for the user's choice. If they ask for more, provide 15 new options. Do not write the output file until a name is chosen.
3. Use the supplied type if it is `short`, `long`, or `oneshot`. If no type is supplied, default to `oneshot`. Map types to `adventures/shortstories`, `adventures/longstories`, and `adventures/oneshots`, respectively. Ask only if a supplied type is unsupported.
4. Keep the source language, names, pronouns, established facts, and uncertainty unless the user requests a change.

## Critical review and improvements

Give a concise critical assessment, then exactly three concrete improvement options for each of the nine session phases listed below: 27 options total. Group the options under their phase headings, including `Optional: Call`, and number them consecutively from 1 to 27 so each can be referenced unambiguously. Do not replace them with one general list. Tailor each option to the supplied adventure, identify the opportunity or problem, propose a change, and explain its benefit. Consider the central question and underlying truth, clue clarity and alternate routes, useful reveals, NPC perspectives, rising danger, twists, consequences, climax, and epilogue. Do not force a conventional crime or suspect structure onto a different kind of mystery.

Ask the user to say which options to apply, modify, or dismiss. They may answer by phase or refer to the numbered options. Resolve requested modifications and wait until all 27 options have a disposition before rewriting. Apply accepted changes, preserve dismissed material, and do not silently make substantive changes the user has not approved.

## Rewriting

Use the sections in `assignment_structure.md` as distinct level-two headings, in this order:

1. Content Warnings
2. Premise
3. What is actually going on here?
4. Details
5. Hook
6. Optional: Call
7. Arrival
8. Exploration I
9. Exploration II
10. Escalation I
11. Escalation II
12. Climax
13. Epilogue

### Rules for the phases

- **Content Warnings:** List warnings supported by the supplied adventure. If none are specified or clearly supported, write `None specified in the source`; do not invent one.
- **Premise:** Give players an atmospheric, spoiler-light preview of the adventure and its opening, with enough mystery left for play. Keep the underlying answer for the GM section.
- **What is actually going on here?:** Explain the hidden truth for the GM, including the central thread. Mark it as GM-only and avoid repeating the premise.
- **Details:** Include relevant themes and atmosphere. Describe the main adversary's appearance, goals, and abilities when known. List threats and how they affect the party or obstruct its goals. For notable figures, include their names, pronouns, visual descriptions, motives, and goals when supplied. Omit unsupported fields rather than inventing details.
- **Hook:** Open on an exciting, pivotal event or high-stakes briefing. Establish the setting, event, and key characters, then give the players an immediate situation to respond to. Avoid a generic “you all meet” opening. It can frame events before the characters arrive and serve as their in-world briefing.
- **Optional: Call:** Keep this phase optional. Invite each player to describe where their character is when the GM calls them in, creating space for personal details and character ownership. Do not make participation necessary to understand or continue the adventure.
- **Arrival:** Let the investigators explore the aftermath of the hook. Orient them with the GM's briefing, NPC perspectives, and clues that point toward the investigation. Identify one critical fact as the Reveal and ensure the players learn it regardless of their approach; use multiple details or routes to communicate it.
- **Exploration I:** Follow the first Reveal to a new location. Show that the investigators are on the right track, expand the scope of the mystery with evidence about the larger truth, and use a new Reveal to point toward the next location. This place is often more dangerous than the Arrival.
- **Exploration II:** Use the previous Reveal to let the investigators pursue the mystery more directly toward an answer and greater danger. Make the consequences of failure clear as tension rises.
- **Escalation I:** Introduce a twist that changes what the investigators think is happening. Push them into greater peril, show the power of the adversary or central threat, raise tension, and direct them toward the climax.
- **Escalation II:** Use what the investigators have learned and the tools they have gathered to move directly toward the finale. Bring them to where the showdown can happen and make the danger feel imminent.
- **Climax:** Bring the drama to its highest tension. Use visceral horror when it suits the adventure's tone, and allow a final reveal or twist to answer the central question when useful. Provide a strong opportunity for action and make failure's consequences meaningful.
- **Epilogue:** Show the world after the investigation and wrap up relevant loose ends. Reflect on what the investigators uncovered, their relationships with notable figures, the adversary's fate, and any character developments; seed a future adventure only when supported by the story.

Keep all phase guidance flexible enough to handle player choices; it is a framework of possible actions and narrative beats, not a prediction of what the players will do. Never make an essential reveal depend on one specific roll, NPC, or player choice. Do not add page numbers or reproduce source pagination.

Keep the amount of material appropriate to the chosen adventure type. Preserve the author's core premise and resolution while integrating approved improvements. If a necessary detail remains genuinely ambiguous, retain or flag the uncertainty rather than resolving it silently.

## Save the adventure

After the user has chosen a name and all 27 improvement options have been handled, create the Markdown file directly in the selected type folder, using the chosen adventure name as its filename and replacing only filesystem-invalid characters. Keep the chosen title as the document's main heading. If a same-named file already exists, inspect it: update it only when it is clearly the same adventure; ask before overwriting an ambiguous or different adventure.

Update the `README.md` in that same type folder, not the parent `adventures/README.md`:

- If there is no overview table, create one with `Adventure`, `System`, `Summary`, and `File` columns, in that order.
- If a table exists, preserve its rows and other columns, adding `System` after `Adventure` if missing and adding `Summary` if missing.
- Add or update one row for this adventure with its chosen name, the game system, a concise summary, and a relative Markdown link to the created file. Use the system stated by the user or clearly identified in the adventure. If it is unclear, ask the user rather than guessing. Use an angle-bracket link destination when the filename contains spaces (for example, `[Title](<Title.md>)`). Avoid duplicate rows for the same adventure.
- If the type-folder README does not exist, create it with the matching heading (`# Short stories`, `# Long stories`, or `# Oneshots`) and this table.

Report the created or updated adventure file and type-folder README with links.
