# Markdown Writing Guide for Docs

Welcome to the Markdown writing guide for the docs/ folders. This document teaches you everything you need to know to create neat, well‑structured Markdown files for your research papers, guides, and documentation. By the end of this guide, you will be comfortable writing full papers in Markdown, organized cleanly for our projects.

### Where to put your Markdown Files

- Each project has a `docs/` folder. Inside, you may find subdirectories such as `research/`, `guide/`, or `setup/`.
- For research papers, create a file under `docs/research/` with a descriptive filename (e.g., `rf_methodologies.md`). Use lower-case names with hyphens, not spaces.
- If your document belongs to another area (like a design guide), place it in a suitable subdirectory.

---

### Getting Started with Markdown

Markdown is a lightweight markup language that allows you to format text easily. Here are the basics:

#### Headers

Use `#` signs to create headings. One `#` creates a top-level heading; two `#` for second level, and so on.

```markdown
# Title

## Section Heading

### Subsection

#### Fourth Level
```

Each file should have a single Level 1 heading at the very top. Keep headings in sentence case (capitalize first letters of main words) and avoid ending them with punctuation.

---

#### Paragraphs & Line Breaks

Leave a blank line between paragraphs to separate them. A single line break inside a paragraph does not create a new line in the output.

If you need a line break inside a paragraph, add two spaces at the end of the line:

```markdown
This is the first line. <- two trailing spaces
This line will appear directly below without a blank line.
```

---

#### Emphasis (Bold & Italic)

Use single asterisks or underscores for _italic_. Double asterisks or underscores for **bold**.

```markdown
This is _italic text_ and this is **bold text**
```

You can combine them: `***bold italic***` will produce **_bold italic_** text.

Avoid overusing bold; use it only for important terms or emphasis.

---

#### Lists

**Unordered Lists (Bullet Points)**
Start each item with a hyphen (-), plus (+), or asterisk (\*). Use a single space after the symbol.

```markdown
- First item
- Second item
  - Sub-item (two spaces indent)
    - Sub-sub item
- Third item
```

- First item
- Second item
  - Sub-item (two spaces indent)
    - Sub-sub item
- Third item

**Ordered Lists (Numbered)**
Number each item followed by a period (the numbers don't need to be sequential; Markdown will auto-number). Use a single space after the period.

```markdown
1. First step
2. Second step
3. Sub-step
4. Next sub-step
5. Final step
```

1. First step
2. Second step
   1. Sub-step
   2. Next sub-step
3. Final step

---

#### Checklists (Task Lists)

Task lists are great for outlining TODOs or acceptance criteria. Start each item with `- [ ]` (unchecked) or `- [x]` (checked).

```markdown
- [ ] Research RF methodologies
- [x] Install PlatformIO
- [ ] Write the “Results” section
```

- [ ] Research RF methodologies
- [x] Install PlatformIO
- [ ] Write the “Results” section

This produces a checklist with boxes. Use these sparingly; they're ideal for planning tasks.

---

#### Code (Inline & Blocks)

**Inline Code**
Use backticks ( ` ) around a word or phrase to denote code or commands.

```markdown
Use `git clone` to clone this repository
```

Use `git clone` to clone this repository

**Fenced Code Blocks**
For multi-line code or console output, wrap the code in triple backticks. Optionally specify a language for syntax highlighting (e.g., `python`, `bash`, `cpp`, `markdown`)

````markdown
```python
def hello_world():
    print("Hello, world!")
```
````

```python
def hello_world():
    print("Hello, world!")
```

This will produce a code block with proper syntax highlighting. Avoid leaving trailing spaces on blank lines inside the block.

---

#### Tables

Use pipes (`|`) to create tables. Headers are separated from the body by a line with (`---`). Use colons to control alignment (left, center, right).

```markdown
| Component | Description       | Quantity |
| :-------- | :---------------- | -------: |
| ESP32 MCU | Microcontroller   |        1 |
| BMP390    | Barometric sensor |        1 |
| SD Card   | Logging storage   |        1 |
```

| Component | Description       | Quantity |
| :-------- | :---------------- | -------: |
| ESP32 MCU | Microcontroller   |        1 |
| BMP390    | Barometric sensor |        1 |
| SD Card   | Logging storage   |        1 |

This produces a neatly aligned table with right-aligned numbers. Keep tables simple (no more than 3 columns) and avoid long text; use lists instead if the content doesn't fit.

---

#### Links & Images

**Links**
To create a link, put the text in square brackets followed by the URL in parentheses.

```markdown
[PlatformIO Documentation](https://platformio.org)
```

[PlatformIO Documentation](https://platformio.org)

If the link is long or includes special characters, wrap the URL in angle brackets:

```markdown
<https://docs.espressif.com/projects/esp-idf/en/latest/esp32/>
```

<https://docs.espressif.com/projects/esp-idf/en/latest/esp32/>

**Images**
Images are inserted similarly but prefaced with an exclamation mark. Always include alt text in square brackets.

```markdown
![Schematic Example](/docs/images/schematic.png)
```

![Schematic Example](/docs/images/schematic.png)

Images should be stored within the project (e.g., `docs/images/`). Keep image sizes reasonable and use PNG for line drawings, JPEG for photos.

---

#### Dividers & Blockquotes

**Horizontal Rules**
Use three hyphens (`---`) on a new line to insert a horizontal divider. Dividers separate sections and add visual structure.

**Blockquotes**
Use `>` to indent text as a block quote. Nest deeper quotes with an additional `>`. Quotes are useful for callouts or citations.

```markdown
> This is a block quote. It can span multiple lines.

> > Nested quote within a quote.
```

> This is a block quote. It can span multiple lines.

> > Nested quote within a quote.

---

#### Footnotes

Footnotes can be helpful for citations. Use bracketed numbers in the text and then define them at the end of the file.

```markdown
The rocket reached a height of 9,000 m[^1].

[^1]: Flight data recorded on July 15, 2025.
```

The rocket reached a height of 9,000 m[^1].

[^1]: Flight data recorded on July 15, 2025.

Keep footnotes to a minimum. Most citations should appear inline via links.

---

### Writing Research Papers in Markdown

When documenting research, structure matters. Use headings and subheadings to clearly delineate sections. Here's a suggested outline:

Research deliverables go under `docs/research/` and should look like short papers.

Use this template as a starting point:

```markdown
# Title of Research Paper

_Author: Your Name — Date_

## Abstract

One paragraph summary of the problem and findings.  
Example: _This paper explores RF methods for telemetry, comparing LoRa, XBee, and custom FSK systems._

## Background

Introduce the problem and why it matters.  
Example: _Reliable data downlink is critical for rocket recovery. Current options vary in range, bandwidth, and complexity._

## Methods

What you researched, tested, or compared.  
Example:

- Reviewed manufacturer datasheets
- Built range test setup with LoRa modules
- Surveyed ground station antenna options

## Results

Summarize key data or outcomes.  
Example:

- LoRa achieved ~12 km LOS range
- XBee modules failed beyond 3 km
- High-gain Yagi improved SNR by ~6 dB

## Discussion

Interpret results. What worked, what didn’t, what you recommend.  
Example: _LoRa provides best tradeoff of range and simplicity; XBee not suitable; future work: mesh testing._

## References

List datasheets, papers, links.  
Example:

- [LoRa SX1276 Datasheet](https://example.com)
- IEEE paper on RF propagation
```

---

### Checklist Before Submitting Docs

- [ ] Is your filename descriptive and lower-case?
- [ ] Did you include a Level 1 heading at the top?
- [ ] Is your content broken into logical sections?
- [ ] Do your lists, tables, and code blocks render correctly?
- [ ] Did you provide links or footnotes for external references?
- [ ] Are all images/figures stored in `/docs/images/` with appropriate alt text?
- [ ] Did you remove any leftover placeholder text?

If you checked all the boxes above, your Markdown document is ready to commit.

---

### Final Tips

Markdown is designed to be simple but expressive. As long as you follow these guidelines, your docs will look polished and professional. Don't hesitate to look at or steal from existing documents including this one in the `docs/` folder for inspiration or examples.

```

```
