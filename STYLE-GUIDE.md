# Weaviate Documentation - Style Guide

This style guide provides a framework for creating clear, consistent, and user-friendly documentation for Weaviate. It emphasizes practical guidelines to help you write effectively for our audience.

---

## Table of Contents

- [1. Core content & voice guidelines](#1-core-content--voice-guidelines)
  - [Audience](#audience)
  - [Voice & tone](#voice--tone)
  - [Inclusion & accessibility](#inclusion--accessibility)
- [2. Structural & organizational principles](#2-structural--organizational-principles)
  - [Information typing](#information-typing)
  - [Docusaurus structure](#docusaurus-structure)
  - [Page layout](#page-layout)
- [3. Formatting & presentation rules](#3-formatting--presentation-rules)
  - [Design principles](#design-principles)
  - [Text elements](#text-elements)
- [4. Terminology & linking](#4-terminology--linking)
  - [Terminology](#terminology)
  - [Term linking](#term-linking)
- [5. Visual assets & versioning](#5-visual-assets--versioning)
  - [Visual assets](#visual-assets)
  - [Docs versioning](#docs-versioning)
- [6. Areas for further definition](#6-areas-for-further-definition)

---

## 1. Core content & voice guidelines

### Audience

- **Roles:** Write for developers, data scientists, students, and Weaviate admins.
- **Quickstart focus:** Tailor quickstart guides primarily for developers, data scientists, and students, with secondary consideration for system evaluators. Assume minimal knowledge of vector databases (VDBs).

### Voice & tone

- **Person:** Address the reader directly using the **second person ("you")**.
- **Tone:** Maintain a **conversational, non-academic, and friendly** tone. Avoid being overly formal or frivolous.
- **Knowledge level:** Adjust the assumed level of user knowledge based on the specific page content.

### Inclusion & accessibility

- **Inclusive language:** Follow **Google's inclusion guidelines** to ensure documentation is bias-free and respectful of all users.
- **Accessibility:**
  - Prioritize clear and useful documentation for everyone, including users with disabilities.
  - **Follow Google's accessibility guidelines.**
  - Provide **alt text** for all images, summarizing their intent. Use empty alt text for purely decorative images.
  - Ensure meaning is conveyed without relying solely on sound, images, or color.
  - Verify content is navigable and usable with **keyboard-only input**.
  - Avoid ableist language, unnecessary font formatting, and forced line breaks.
  - Use descriptive headings and titles.
  - Test documentation with a **screen reader** where possible.

---

## 2. Structural & organizational principles

### Information typing

Categorize content using these types:

- **Concept:** Explains fundamental ideas and principles.
- **Guides (how-to):** Provides step-by-step instructions to achieve a specific goal.
- **Reference:** Offers detailed information about APIs, configurations, and technical specifications.
- **Tutorial:** Guides users through a complete process, often combining concepts and guides.

### Docusaurus structure

The documentation is organized into key sections. When contributing, understand where your content fits:

- **Weaviate database (`/docs/weaviate`):** Get started, How-to manuals & guides, Model integrations, Reference & APIs, Concepts, Recipes, Other (Release notes, Benchmarks, Modules, FAQ, Glossary, Example datasets).
- **Deploy (`/docs/deploy`):** Get started, Configuration, Production guides, Tutorials, FAQs, Migration.
- **Weaviate agents (`/docs/agents`):** Documentation, Recipes.
- **Weaviate cloud (`/docs/cloud`):** Get started, Weaviate embeddings, Account management.
- **Academy (`/docs/academy`):** Get started.
- **Integrations (`/docs/integrations`):** Documentation, Recipes.
- **Contributor guide (`/docs/contributor-guide`):** Get started, Weaviate database, Weaviate modules, Weaviate clients, Contextionary.

### Page layout

- **Top-level headings:** Do not include redundant top-level headings like "Introduction" or "Overview" within the body content; the page title serves this purpose.
- **Related pages:** Place links to related pages at the **bottom of the page** within a `:::info Further resources` block.
- **Quickstart guides:**
  - Include links to environment setup guides.
  - Provide **complete, runnable example code** requiring minimal edits.
  - Focus on demonstrating VDB functionality, not installation or general system setup.

---

## 3. Formatting & presentation rules

### Design principles

- **Visuals:** Aim for a **clean design with ample whitespace**.
- **Usability:** Apply **"Don't make me think"** guidelines to ensure intuitive navigation and clear information presentation.

### Text elements

- **Capitalization:** Use **sentence case for all headings**.
  - _Example:_ `## This is a heading about Weaviate`
- **Lists:**
  - Transform "cascading sentences disguised as lists" into proper lists.
  - Use **numbered lists for sequences**.
  - Use **bulleted lists for most other lists**.
  - Use **description lists for pairs of related data**.
- **Headings hierarchy:**
  - Use Markdown for headings: `## Section title`, `### Subsection title`, `#### Sub-subsection title`.
  - Do not skip heading levels (e.g., go directly from `##` to `####`).
  - Be aware that H4 and lower headings may not appear in the right-hand-side table of contents.
- **Code & UI elements:**
  - Use **code font** for all code-related text.
  - Use **bold** for UI elements.
- **Dates:** Use **unambiguous date formats**.
- **Punctuation:** Use **serial commas**.
- **American English:** Assume **US style for dates, numbers, and dialect for English spelling and usage**. Write for a global audience.

---

## 4. Terminology & linking

### Terminology

- **General:** Use clear, direct language. Define acronyms and abbreviations on first use.
- **Specific terms (pending definition):** Decisions are pending for the precise usage of:
  - `query` vs. `search`
  - `filter`, `threshold`, `(.with_limit)`
  - `method`, `operator`, `function` (e.g., `functionMethodOrOperator.whatDoWecallThisPart()`)

### Term linking

- On the **first mention** of a Weaviate method or term on a page, **link to its corresponding reference or concept page**.

---

## 5. Visual assets & versioning

### Visual assets

- **Screenshots:** **Avoid using screenshots** due to maintenance challenges.
- **Diagrams:** Diagrams are acceptable where they add clarity.
- **Videos:** Videos can supplement written documentation but should **not replace it**. Ensure videos are kept up-to-date as the UI evolves.
- **Dark/light mode images:**

  - For simple images, use Markdown suffixes:
    ```markdown
    ![Light mode image](./_includes/image_light.png#gh-light-mode-only)
    ![Dark mode image](./_includes/image_dark.png#gh-dark-mode-only)
    ```
  - For images requiring width adjustment, use the Docusaurus `ThemedImage` component:

    ```jsx
    import ThemedImage from "@theme/ThemedImage";
    import MyImageLight from "./_img/my_image_light.png";
    import MyImageDark from "./_img/my_image_dark.png";

    <ThemedImage
      alt="My image alt text"
      sources={{
        light: MyImageLight,
        dark: MyImageDark,
      }}
      width="300"
    />;
    ```

- **Social/preview images:** Use the `image:` frontmatter for social media previews.

### Docs versioning

- Indicate new features with a version tag: **`:::info Added in version vX.Y.Z`**
- For experimental features, use a caution block to warn users:
  ```
  :::caution Do not use in production
  Available starting in `vX.Y.Z`. This is an experimental feature and shouldn't be used in a production environment for now.
  :::
  ```

---

By adhering to these guidelines, we can ensure the Weaviate documentation is consistent, clear, and highly valuable to our users.
