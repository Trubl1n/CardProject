---
name: Forma
description: A calm studio for composing editable project cards.
colors:
  primary: "#c9f272"
  ink: "#292b29"
  workspace: "#f3f3f0"
  paper: "#ffffff"
  page: "#f7f7f4"
  line: "#e9e9e4"
  muted: "#85877f"
  focus: "#688938"
  selection: "#83a745"
  artboard: "#faffee"
  artboard-dark: "#20251f"
typography:
  display:
    fontFamily: "Manrope, sans-serif"
    fontSize: "59px"
    fontWeight: 800
    lineHeight: 1.14
  title:
    fontFamily: "Manrope, sans-serif"
    fontSize: "12px"
    fontWeight: 700
  body:
    fontFamily: "Manrope, sans-serif"
    fontSize: "12px"
    fontWeight: 500
  label:
    fontFamily: "Manrope, sans-serif"
    fontSize: "10px"
    fontWeight: 500
  card-description:
    fontFamily: "Manrope, sans-serif"
    fontSize: "18px"
    fontWeight: 400
    lineHeight: 1.65
rounded:
  field: "6px"
  control: "7px"
  tab: "5px"
  screenshot: "14px"
spacing:
  compact: "4px"
  control-gap: "8px"
  field-padding: "10px"
  panel-section: "23px"
components:
  button-primary:
    backgroundColor: "#282c26"
    textColor: "{colors.paper}"
    rounded: "{rounded.control}"
    padding: "12px 15px"
  input:
    backgroundColor: "{colors.paper}"
    textColor: "#464e3c"
    rounded: "{rounded.field}"
    padding: "{spacing.field-padding}"
  navigation-active:
    backgroundColor: "{colors.paper}"
    textColor: "#30382a"
    rounded: "{rounded.tab}"
---

# Design System: Forma

## Overview

**Creative North Star: "The Working Studio"**

A calm working studio: cream workspace, white tool surfaces and a precise lime accent. Manrope gives the interface a consistent, approachable voice; the editable project title provides the strongest visual statement inside each card. Controls stay compact so the composition remains the center of attention.

This records the implemented visual world in `src/style.css` and `src/main.tsx`. Descriptive names describe the observed system; they do not introduce additional product claims or unimplemented states.

**Key Characteristics:**

- Cream workspace and white sidebars
- Manrope throughout the editor
- Lime identity with olive selection feedback
- Dominant project titles and editable positioned blocks

## Colors

### Primary

**Studio Lime** is the identity accent: brand mark, default card accent, selected text and small graphic details. **Olive Focus** and **Selection Green** communicate keyboard focus and the active editing block. Dark ink on lime preserves readable emphasis.

### Neutral

**Workspace Cream** separates the canvas from **White Paper** tool panels. **Page Chalk** supplies the outer base. **Graphite Ink** carries primary copy, **Muted Olive Gray** supports secondary labels and **Warm Hairline** separates sections. **Artboard Ivory** and **Artboard Forest** are default light/dark card surfaces; card palettes can change independently of editor chrome.

**The One Main Accent Rule.** A card has one dominant visual accent; secondary metadata supports it.

## Typography

**Display Font:** Manrope, sans-serif.
**Body Font:** Manrope, sans-serif; bundled weights 400, 500, 600, 700 and 800.

### Hierarchy

The default card title uses the display token at the internal artboard scale. The description is lighter and more open; repository and star metadata use 16px semibold/bold. Editor section titles use the title token, ordinary UI uses body, and compact form labels use label. Supporting interface annotations range from 8–11px in the implementation.

Card typography is editable. The editorial template uses Georgia for the title; the terminal template uses monospace. Those choices belong to the artwork, while editor chrome remains Manrope.

## Layout

The desktop editor has a 76px white header and three columns: 260px template/layer sidebar, flexible canvas and 284px inspector. A 61px canvas toolbar and 59px bottom bar frame the working area. Panels use hairline dividers, compact controls and section padding of 23px rather than a repeated stack of floating cards.

At 1500px and above, side columns expand to 280px and 306px. At 1150px and below they contract to 220px and 250px. At 950px and below, the inspector moves below the canvas in three columns; the left sidebar is 190px. At 600px and below, the header is 64px, the canvas comes first, templates follow in four columns and the inspector uses two columns with full-width content sections.

The internal artboard is 640px wide with heights 800px (4:5), 853.333px (3:4) or 640px (square). Zoom transforms the artboard without changing artwork coordinates; PNG output is 1080px wide. Blocks use percentage positions and dimensions. The default composition places title at x 8%, y 13%, width 85%; description at y 34%; screenshot at y 49%; repository and stars at y 91%. The screenshot is 84% wide. These are starting positions, not restrictions on editing. Safe guides sit 3.25% inside the card edge and are editor-only.

## Elevation & Depth

The shell is predominantly flat. Tonal surfaces and borders establish panels. A diffuse artboard shadow separates the designed object from its workspace; tiny active-tab shadows mark a selected control. Screenshot and toast shadows have distinct object and feedback roles.

### Shadow Vocabulary

- **Artboard:** `0 10px 35px #3b442316`.
- **Screenshot:** `0 9px 24px #283b1618`.
- **Active tab:** `0 2px 4px #252b1a0a`.
- **Toast:** `0 8px 30px #0002`.

## Shapes

Controls are gently squared: fields and format tiles use the field radius; export buttons and grouped controls use the control radius. Selected sub-tabs use the tab radius. Default artwork screenshots use the screenshot radius, independently editable. Accent swatches and small status dots are circular. Flat panel boundaries remain straight.

## Components

### Buttons

The primary export action is dark with white text and a download icon. Secondary actions use a light outlined surface; toolbar actions are compact ghosts. Hover applies brightness `.96`; disabled controls use opacity `.35`. Keyboard focus uses a 2px Olive Focus outline with 3px offset.

### Inputs / Fields

White inputs use a 1px `#e4e7dd` border, field radius and field-padding token. Textareas use line-height 1.6. Paired numeric fields use two equal columns with 10px horizontal gaps. Form errors and export/import failures appear in the status toast; the current implementation does not define an inline invalid-field style.

### Navigation

Template/layer tabs sit on a pale neutral tray with a white active segment. Page tabs run along the bottom of the canvas with a white active state. On mobile the template selector becomes a four-column row below the canvas. Tiny design/demo badges use subdued neutral color and minimal rounding.

### Template Tiles

Two-column desktop previews show actual typographic and color distinctions between Studio, Editorial, Terminal and Accent. The selected preview uses a 2px olive border, pale 3px outer ring and a check marker. Template identity belongs to artwork previews rather than the shell.

### Editable Artboard Blocks

Each title, description, screenshot, repository and star block is positioned independently. Hover reveals a faint olive outline; selection uses Selection Green, a label above the block and a square bottom-right resize handle. Inspector controls edit text, font, weight, alignment, position, size, internal padding and rounding. Arrow keys move focused blocks by one percentage point. Selection adornments and guides are excluded from PNG output.

The artboard size transition lasts .18s; outline feedback lasts .12s; the switch thumb moves over .15s. Reduced-motion preference disables transitions and animations.

## Do's and Don'ts

### Do:

- Do keep project titles visually dominant over descriptions, repository names and star counts.
- Do use the cream workspace to separate the exported card from white editing panels.
- Do keep selection labels, resize handles and safe guides out of exported artwork.
- Do preserve readable screenshot geometry and verify text contrast for each chosen card palette.

### Don't:

- Don't treat the selected card theme as an editor-wide theme.
- Don't replace the editor typeface when changing a card template.
- Don't make repository or star metadata compete with the title.
- Don't imply that illustrative demo content is verified GitHub data.
