# PATTERN Program Landscape Map

An interactive, single-file visualization of PATTERN's programs and initiatives
across Indiana's creative economy. It plots every program as a node positioned by
its primary strategic pillar, so you can see at a glance where PATTERN's work
concentrates, where it overlaps, and what's active vs. dormant vs. adjacent.

## Viewing it

It's a self-contained `index.html` — no build step. Open it directly in a browser,
or serve the folder with any static server, e.g.:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

D3 v7 is loaded from a CDN, so an internet connection is needed on first load.

## The four pillars

Programs are laid out around four strategic pillars, anchored to the corners:

- **Conveying** — telling stories, publishing, communicating PATTERN's POV
- **Convening** — bringing people together
- **Cultivating** — supporting talent, creative businesses, and ecosystem-building
- **Advocacy** — organizing for and advancing Indiana's creative economy

Click a pillar label to read its definition in the sidebar.

## Reading a node

| Encoding | Meaning |
| --- | --- |
| **Size** | Program weight — large / medium / small |
| **Color** | Primary pillar (multi-pillar programs render as split-color wedges) |
| **Status dot** | Green = active, grey = dormant, purple = adjacent |
| **Position** | Clustered near its primary pillar; dual-pillar programs sit between two zones; programs spanning all four sit in the center |

**Badges**

- **C** (circle) — Agency / client work
- **$** (circle) — Grant-funded
- **◆** — Incubating
- **External** — Adjacent program operating in PATTERN's orbit but not fully owned

**Industry-focused** programs (e.g. *Industry-Focused: Music*, *Industry-Focused:
Film*) are adjacent bodies of work that cut across pillars; they render as a single
solid color and stay visible regardless of the pillar filter.

## Interaction

- **Click a node** to open its details in the sidebar; active programs pulse while selected.
- **Search** and the **Pillar / Status / Size** filters dim everything that doesn't match.
- **Pan and zoom** the canvas; the view **auto-fits** all nodes on load.
- Toggle the legend sidebar open/closed with the chevron.

## Editing the data

All programs live in the `PROGRAMS` array near the top of the `<script>` block in
`index.html`. Each entry carries its `name`, `size`, `status`, `pillars`,
`primary_pillar`, optional `type` / `incubatory` / `industry` flags, and a `desc`.
Edit that array to add, remove, or re-describe programs.
