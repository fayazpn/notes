# Using this vault

[[Home]]

## 1. Choose where to write

| What you are trying to record | Where it goes | Example |
| --- | --- | --- |
| Something unfinished that you need to sort out | [Inbox](Inbox/Capture.md) | “Why does Go append sometimes change another slice?” |
| What happened on a particular day | Today's note in `Daily/` — optional | “Read about slices; investigated order creation.” |
| Something you understand and want to look up again | A subject folder under `Notes/` | [Go slices](Notes/Go/Slices.md): explanation, example, and the shared-array caveat. |
| An action you need to take | [Tasks](Inbox/Tasks.md) | “Trace the order acknowledgement handler.” |

**Use Inbox as your default. Daily notes are optional. You do not need to use both for the same thought.**

## 2. Inbox and Daily have different jobs

### Inbox = unfinished material

Inbox is a temporary working area, regardless of when you captured something. Put unclear questions, rough bullets, pasted snippets, and source links in [[Inbox/Capture|Capture]]. A longer draft can be its own file inside `Inbox/`.

**Keep one Inbox folder.** Start with quick bullets in Capture. If one dump grows into a longer draft, give it a separate file in that same folder. You do not need a Python inbox, a Go inbox, or a new inbox every day. Move a useful draft to its subject folder when it becomes a note you can revisit.

Example:

> Go slices seem to share data. Need to understand when `append` allocates another array.

Later, explain it in [[Notes/Go/Slices|Slices]], turn it into an action in [[Inbox/Tasks|Tasks]], or delete it if it is no longer useful. You do not have to empty Inbox every day.

### Daily = a dated record

Daily answers **“What happened today?”** It is useful for work logs, study logs, and remembering the order of events. Open it from the calendar icon. The file is named for that day.

Example:

> Studied [[Notes/Go/Slices|Slices]]. Tried the shared-array example. Next: trace cancellation in the order gateway.

The explanation of slices belongs in the subject note. The daily note links to it. This keeps the explanation in one place and the day's history in another.

If a dated log does not help you, skip Daily entirely.

## 3. When to write a knowledge note

Write a note when you can explain something that future-you may need again: a concept, a bug's cause, a code path, a useful distinction, or a reading takeaway.

You can write it directly in the correct subject folder. Inbox is available when you are unsure; it is not a mandatory first step.

**One note means one coherent topic, not one sentence.** Usually aim for roughly 100–300 words, plus a small example if needed. A five-line note is fine when it fully explains the idea. A command reference or code example may be longer.

A useful note lets you answer:

1. What is this?
2. How or when does it matter?
3. What example or caveat will help me remember it?

### Too little to revisit

> Slices are flexible arrays.

### Enough to revisit

Open [[Notes/Go/Slices|Slices]] for the complete example. Its summary explains what a slice is, its key points describe sharing and capacity, and its example shows the effect of changing a shared element.

Avoid copying a whole conversation into a finished note. Keep the explanation, example, evidence, and remaining question. Remove greetings, repeated advice, and claims you cannot support.

## 4. Use the same small structure

```markdown
# Clear topic title

Map: a link to the relevant topic map

## Summary
Explain the idea in one or two sentences.

## Key points
- The details needed to understand or use it.
- A limitation, mistake, or caveat if useful.

## Example
A small example, snippet, or concrete situation.

## Related
Links to closely related notes.

## Sources
A source link, or repository path and symbol.
```

**Summary is the starting point. Other sections are optional.** Delete empty sections. Existing practice exercises remain under **Practice** when useful; they are not required for new notes.

**Cmd+N** creates a new draft in Inbox. Give it a descriptive title, press **Cmd+T**, and choose **Note**. When it is ready, use **Move file to…** in Obsidian to place it under the right subject.

## 5. Put each note in one subject folder

| Location | Contents |
| --- | --- |
| `Notes/Python`, `Go`, `Rust`, `JavaScript`, `TypeScript` | Language concepts and examples. |
| `Notes/Web` | React, Next.js, CSS, browser behavior, and frontend testing. |
| `Notes/DSA` | Problem-solving patterns and algorithm notes. |
| `Notes/Systems` | Networks, Linux, databases, system design, deployment, and distributed systems. |
| `Notes/Blockchain`, `Trading`, `Machine learning` | Concepts in those subjects. |
| `Notes/Life`, `Reading` | Personal plans, ideas, and takeaways from sources. |
| `Private/CoinRoutes` | Work investigations and repository-specific notes. |
| `Maps` | Subject indexes that connect the notes. |
| `Templates`, `Attachments` | Reusable note structures and images. |

Pick the main subject once. Use links when a note also matters elsewhere; do not create a second copy. For a new subject, start in Inbox and create a subject folder once you have useful notes to keep.

## 6. Connect notes with links

### Link = a connection you write

Type `[[` and select a note; the completed syntax is `[[Note title]]`. For example, `[[Notes/Go/Slices]]` opens the slices note. `[[Notes/Go/Slices|Go slices]]` points to the same file and displays the label “Go slices”. The full path distinguishes notes with the same title in different subjects.

In today's Daily note, you might write:

```markdown
- Studied [[Notes/Go/Slices|Go slices]] and tried the shared-array example.
```

That is a link from the daily note to Slices. Clicking it opens the explanation. You only need to write the explanation in Slices once.

### Backlink = who links here, found automatically

Open Slices and look at the **Backlinks** pane. Today's Daily note appears there because it contains the link above. You do not have to add a link to today's Daily note inside Slices.

For any note:

- **Outgoing links:** the notes this note points to.
- **Backlinks:** the notes that point to this note.

If the pane is hidden, open **Cmd+P**, search for **Backlinks**, and choose the command to show backlinks.

### Map = a subject's starting page

A map is a normal note with a readable selection of useful starting points. [[Maps/Go|Go]] is your starting page for Go. In a Go note, the template gives you a place for:

```markdown
Map: [[Maps/Go|Go]]
```

**You do not need to add the note to every map, or write both directions of every link.** Choose one main map. The link above makes the note appear automatically in the Go map's Backlinks pane.

When a note is a useful starting point for the subject, also add a link to it in the map's main list so you can browse to it directly. This list is edited by hand; backlinks are automatic. Add a second map or a related-note link only when it helps you find or understand something.

[Obsidian internal links](https://help.obsidian.md/links) · [Backlinks](https://help.obsidian.md/plugins/backlinks)

## 7. Tags are optional

**Use only these two tags for now:**

- **#question:** an unanswered question you want to explore.
- **#review:** a note whose explanation, example, or evidence needs checking.

Put the tag beside the relevant question or passage. Search for `tag:#question` or `tag:#review` to find tagged notes. Remove the tag when the question is answered or the review is complete. You do not need a tag for every subject; folders and maps already provide that structure.

Use a map link to connect ideas. Use a tag to filter notes needing the same action.

[Obsidian tags](https://help.obsidian.md/tags)

## 8. CoinRoutes: record evidence, then explain

Use [[Maps/CoinRoutes|CoinRoutes]] to choose one investigation. Start with a question such as “Where is this order persisted?” Trace files and symbols before writing an explanation of the flow.

The **Code map** template separates observed behavior, evidence, and open questions. An endpoint name or a guess is a lead, not proof of an internal architecture. Put reusable concepts in `Notes/Systems` or `Notes/Trading` and link them from the work note.

## 9. Find and revisit

- **Cmd+O:** open a note by title.
- **Cmd+Shift+F:** search inside notes.
- **Cmd+P:** open the command palette.
- **Open local graph:** inspect a note's connections; try depth 1, then 2.
- [[Home]] and the maps: browse by subject.

Once a week, spend ten minutes choosing one useful capture, improving a note, and checking your next actions. There is no requirement to rewrite everything or maintain a perfect graph.

## 10. Repository sync

### Where would the notes go?

The configured destination is [fayazpn/notes](https://github.com/fayazpn/notes), on branch `main`. Here, **fayazpn is the repository owner** and **notes is the repository name**. GitHub reported this repository as **public on 2026-10-28**. It is currently visible to others; it must be made private before it can serve as a private destination.

This computer currently authenticates to GitHub as **fayazb12**. That account has push access to `fayazpn/notes`; signing in as it does not change the destination to a different repository.

`Private/` is just a folder name. Its notes are now eligible for Git tracking alongside the other notes; they are no longer excluded by `.gitignore`. The remaining ignore rules cover trash, local workspace state, caches, and installed plugin/theme files. Removing an ignore rule does not upload anything.

### Save, commit, and push are different steps

| Step | What it does | Where it happens |
| --- | --- | --- |
| Save | Obsidian saves your writing into Markdown files. | This computer. |
| Commit | Git records a checkpoint of the changes selected for that checkpoint. | This computer. |
| Push | Git sends local commits to the configured GitHub repository. | GitHub receives the committed files. |

A push sends committed changes. A note that has only been saved locally is not uploaded by that push. A private repository would restrict who can access what is uploaded; it would not change these steps.

### When does it push now?

**Automatic sync is off.** The installed Git plugin's backup, push, and pull intervals are all **0**, and backup after file changes is disabled. There is no daily push scheduled. The vault cleanup remains uncommitted, so it has not been uploaded.

The standing instruction is to make no commits or pushes, so those actions have not been run. If daily sync is enabled later, it will need to commit changes as well as push them. The Obsidian plugin runs while Obsidian is running; it cannot guarantee a scheduled upload while the app is closed.

[Git plugin automation](https://publish.obsidian.md/git-doc/Features)

## 11. Colors and visual tools

### Highlight text

Type `==` and choose a color, or use one of these examples:

```markdown
==🟢Key takeaway==
==🟠Question or next action==
==🔴Pitfall or error==
==🟣Idea to explore==
==🔵Reference==
```

==🟢Key takeaway== · ==🟠Question or next action== · ==🔴Pitfall or error== · ==🟣Idea to explore== · ==🔵Reference==

Place the cursor inside a highlight and click its color swatch to change the color. Plain `==text==` uses the theme's default highlight color.

See the examples in [[Notes/JavaScript/Event loop|Event loop]], [[Notes/Rust/Borrowing and mutability|Borrowing and mutability]], [[Inbox/Capture|Capture]], and [[Inbox/Tasks|Tasks]].

### Color the letters themselves

Select a short phrase in editing mode. In the floating Editing Toolbar, hover over **Font Colors** (the palette button) to reveal the color grid, then click a swatch. Clicking the main button applies the current color. Use **Clear formatting** (the eraser) to remove formatting.

For a simple manual example:

```html
<span style="color: #4385be;">Reference text</span>
```

<span style="color: #4385be;">Reference text</span>

Use text color for short labels. Use the native highlights above for key passages; their color is saved directly in Markdown. Text colors use inline HTML, which is visible in Source mode.

### Read and change graph colors

Open **Graph view → settings → Groups**. Each group has a search query and a colored circle. Click the circle to change its color, or choose **New group** to add one.

The graph uses your existing subject folders and matching maps. For example:

```text
path:"Notes/Go/" OR path:"Maps/Go.md"
```

Go is teal, Python is gold, Rust is orange, JavaScript is yellow, TypeScript is blue, Web is purple, Systems is olive, DSA is red, and Machine learning is pink. Inbox is orange. Notes with `#review` take red and notes with `#question` take orange before the subject groups are applied. A note matching several groups uses the first matching group; drag groups to change their priority.

The same subject colors and icons appear in the sidebar. Iconic's rules also apply to new notes in those subject folders. Right-click a file or folder and choose **Change icon** to customize it; use Iconic's rulebook if a subject rule is overriding your choice.

### Adjust the look or draw an idea

- **Style Settings:** change Minimal's heading colors, fonts, spacing, and graph defaults under Settings → Style Settings.
- **Minimal Theme Settings:** colorful headings and active states are enabled.
- **Extended Graph:** adds graph controls, focused-node emphasis, and links that follow node colors. Use the graph's Extended Graph toggle to switch its enhancements on or off.
- **Excalidraw:** open the command palette and search for **Excalidraw: Create new drawing** to sketch a diagram. Link it to a subject note when it helps explain the idea.

[Highlight syntax](https://obsidian.md/help/syntax) · [Graph groups](https://obsidian.md/help/plugins/graph) · [Minimal customization](https://minimal.guide/plugins/style-settings)
