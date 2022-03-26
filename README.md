# acacia-docs
Markdown Documentation for savannabits/acacia

## Editorial Guide:
- Each folder should have an index.md file, which will act as the table of contents file for the rest of the sub-modules under the same folder. The Index should link other modules as shown in the example below. Take note of the Routing convention:
```md
- ## About POS
    - [Overview](/{{route}}/{{version}}/overview)
    - [Installation](/{{route}}/{{version}}/installation)

- ## User Manual
  - [**Client**](/{{route}}/{{version}}/user-manual/client)
- ## Technical Docs
```
