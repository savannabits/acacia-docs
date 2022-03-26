# Acacia Documentation
Markdown Documentation for [savannabits/acacia](https://github.com/savannabits/acacia)

## Editorial Guide:
### The index.md file
- Each folder should have an index.md file, which will act as the table of contents file for the rest of the sub-modules under the same folder. The Index should link other modules as shown in the example below. Take note of the Routing convention:
```md
- ## Getting Started
    - [Overview](/{{route}}/{{version}}/overview)
    - [Installation](/{{route}}/{{version}}/installation)

- ## Basics
  - [**Client**](/{{route}}/{{version}}/user-manual/client)
- ## Digging Deeper
```
### Table of Contents:
- Each file should specify a ToC at the top using the following syntax:
```md
# Overview

---

- [First Section](#section-1)

<a name="section-1"></a>
## First Section

Write something cool.. 🦊
```
NB:
1. There are three dashes after the main heading
2. Each entry in the ToC specifies a section to go to.
3. In order to specify a section within the document, include an empty link above the heading with specifying the name attribute which will be used in the ToC entry. E.g `<a name="section-1"></a>`
