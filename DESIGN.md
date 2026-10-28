# Ziki Workspace UI/UX Design System

## 1. Product direction

Ziki Workspace is a dark-mode-first developer platform with a sleek, modern interface. Use familiar patterns from products such as Linear, GitHub, and Vercel while preserving Ziki's own visual identity. Favor clear hierarchy, generous whitespace, restrained borders, and compact, information-rich controls.

## 2. Visual foundations

### Color and surfaces

| Role | Value | Usage |
| --- | --- | --- |
| Deep navy background | `#0a0f1d` | Primary page background |
| Alternate background | `#0e1626` | Secondary page regions and tonal variation |
| Card surface | `#111c30` | Cards, panels, and table containers |
| Muted text | `#94a3b8` | Supporting copy, metadata, and inactive labels |
| Primary text | High-contrast white | Headings, key values, and important content |
| Interactive accents | Vibrant blue and green | Links, selected controls, chart progress, and positive status |

Use the specified colors consistently. Keep text readable against dark surfaces and use color alongside text or iconography to communicate status. Cards and panels use rounded containers, typically equivalent to `rounded-xl` or `rounded-2xl`, with subtle borders where needed to distinguish adjacent surfaces.

### Typography and spacing

- Use a clean sans-serif font stack.
- Establish a clear hierarchy between page titles, section headings, labels, values, and supporting text.
- Keep page content in a clean vertical flow with generous outer padding and consistent gaps between sections.
- Align related labels, values, actions, and metadata consistently within cards and tables.

## 3. Global layout

### Header

Use a global header with the following content and order:

- **Left:** `ziki` brand, `Zidu` workspace selector, and the `Product`, `Marketing`, and `Security` navigation tabs.
- **Right:** `Agents` quick-action dropdown, `Paul Ajibola` profile badge, `1655 pts` points badge, and a notification bell with an unread indicator badge.

Keep the header compact and visually distinct from the page body while retaining the dark palette. Make navigation, menus, profile controls, and notifications clear interactive targets.

### Dashboard introduction

The main dashboard begins with a page title block containing a prominent greeting, `Welcome back, Paul`, a contextual subtitle, and the primary `+ New issue` action. Maintain a generous but controlled separation between the introduction and the dashboard content.

## 4. Dashboard components

### A. Metric summary cards

Place four metric cards in a single row on wide screens. Cards wrap or stack at narrower viewport widths while preserving their order and readable content.

1. **Points:** Large value `1655`; supporting progress text `500 to go / 500 required this week`.
2. **Created by me:** Value `1`; supporting badge `+1 in the last 30 days`.
3. **Assigned to me:** Value `1`; priority text `0 high priority`.
4. **Resolved issues:** Value `0`; progress text `0% of issues assigned to me`.

Each card uses a dark rounded surface and has a top-right action icon anchor. Emphasize the numeric value, with supporting status or progress text below it.

### B. Issues assigned to me

Use a rounded, dark-surface section containing a header and an issues table. The header shows `Issues assigned to me`, the count and sort summary (`1 issue • sorted by top votes`), and a secondary `View all issues` button.

The table columns, in order, are:

| Column | Content and presentation |
| --- | --- |
| `VOTES` | Interactive vote pill, such as an upvote chevron and count (`▲ 35`). |
| `ISSUE` | Issue icon, title, issue ID, and comment count. Example: `Signing Out of Workspace and Deleting Organization B...`, `#90`, `2 comments`. Truncate long titles cleanly without obscuring other columns. |
| `TYPE` | Compact category tag, such as `Fix` or `Feature`. |
| `PRIORITY` | Color-coded pill, such as yellow or orange for `Medium`. |
| `STATUS` | Status pill with a colored dot, such as blue for `Open`. |
| `STAGE` | Stage pill with a colored dot, such as green for `Ready`. |
| `REPORTED` | Compact date, such as `Oct 17`. |

Use subdued uppercase column labels and consistent row alignment. Vote controls must be keyboard accessible and expose their selected state and accessible name. At narrow widths, keep the issue identity usable and provide a deliberate responsive table treatment rather than clipping essential content.

### C. Your points chart

The points section contains:

- A `Your points` heading.
- Timeframe filter pills: `Daily`, `Weekly`, `Monthly`, and `Yearly`.
- An `All dates` date-range dropdown.
- A range total, such as `1655 pts in this range`.
- Explanatory subtitle: `Points earned each week, last 8 weeks • 500 pts required, more is welcome`.
- A legend for `500 reached`, `Below 500`, and `Weekly requirement - 500 pts`.

Render the chart as vertical bars with rounded capsule tops and date labels below each bar (for example, `7 Sept`, `14 Sept`, and `19 Oct`). A dashed horizontal line marks the weekly requirement. Inactive bars use muted slate; a bar meeting the target uses vibrant blue. Show the active score label (`1655`) and bonus delta (`+1155`) where appropriate. Keep the chart legible at smaller sizes, with labels and legend wrapping or adapting as necessary.

Timeframe pills are mutually exclusive controls with a visible selected state and accessible pressed state. The date range control must have an accessible name and keyboard-operable menu behavior.

### D. Your agents

Show agents in a rounded section with a `Your agents` heading, count badge (`5`), and a chevron disclosure control. The section can be collapsed and expanded, and the control communicates its state accessibly.

When expanded, show a table with these columns:

| Column | Content and presentation |
| --- | --- |
| `AGENT` | Connection-status bullet, agent name (for example, `Ziki Triager One`), and model tier tag (for example, `Gemini Flash` or `Gemini Pro`). |
| `STATUS` | Connection state, such as `Offline` or `Online`. |
| `CURRENT ACTIVITY` | Activity description, such as `No recent activity`. |
| `LAST SEEN` | Relative time, such as `3 days ago`. |

Use text as well as color to convey connection state. Keep the agent name visually primary and model tier and activity visually secondary.

## 5. Responsive behavior

- Use a mobile-first layout.
- On wide screens, display the metric cards in four columns; progressively reduce columns and stack them on narrow screens.
- Allow header navigation and right-side actions to adapt to available space without making controls difficult to reach.
- Keep tables readable using responsive layout decisions appropriate to their data, such as horizontal scrolling within the table region or a compact row/card presentation. Preserve access to every field.
- Let chart filters, date controls, legends, and labels wrap or reflow without overlap.
- Avoid clipped text, overlapping controls, and page-level horizontal overflow.

## 6. Interaction and accessibility

- Use semantic headings, buttons, links, tables, and disclosure patterns.
- Provide keyboard access, visible focus indicators, and accessible names for all controls.
- Communicate state with appropriate accessibility attributes, including `aria-pressed` for selectable filters or vote controls and `aria-expanded` plus `aria-controls` for the agents disclosure.
- Do not rely on color alone for priority, status, stage, connection state, or chart meaning.
- Give chart information an accessible text equivalent where needed so values and the weekly threshold are understandable without relying only on visual bars.

## 7. Content and sample values

Names, counts, dates, labels, and issue or agent examples in this document define the intended presentation and sample UI content. When connected to live data, retain the same hierarchy and formatting while displaying current values. Format dates and relative times consistently within the interface.

## 8. UX refinement layer

The supplied screenshots establish the current visual direction: a deep navy canvas, blue interactive accents, rounded panels, and a compact developer dashboard. Preserve that recognizable identity while improving scanability, reducing visual repetition, and making every action's purpose clear.

### Page rhythm and hierarchy

- Set a consistent centered content width with responsive side gutters. Keep the header content aligned to the same grid as the dashboard.
- Use a predictable spacing scale between the introduction, metric row, issue list, points chart, and agents panel. Separate sections with whitespace before adding stronger borders or shadows.
- Keep the greeting prominent, but make the primary action easy to find and align it with the heading on wide screens. On small screens, let it fill the available width when that improves reachability.
- Reserve the brightest blue for primary actions, selected states, and meaningful chart data. Use quieter borders and surfaces to keep the page from feeling like a grid of equally prominent boxes.
- Establish consistent panel padding, heading alignment, table row height, and control height across all sections.

### Navigation and actions

- Make the current workspace and active navigation area visually apparent. Use clear hover and focus states for navigation and menu controls.
- Keep the `New issue` action as the page's primary call to action. Give secondary actions such as `View all issues` a quieter treatment.
- Use a consistent icon style and provide tooltips or accessible names for icon-only actions. Do not present a decorative arrow as an actionable control unless it performs a clear action.
- Keep notification count and points visible without allowing their badges to compete with the page title or primary action.

### Metrics

- Make each metric scannable in this order: label, value, then short supporting context. Align the values and baselines across cards.
- Keep supporting badges compact and prevent their text from wrapping into awkward multi-line fragments. Let the full explanation wrap naturally beside or below the badge.
- Only make a card or its action icon interactive when it navigates to a relevant detail view; indicate the click target and give it an accessible name.
- Use color as emphasis rather than decoration. Apply green to positive change and blue to the points total or progress, with neutral supporting text elsewhere.

### Issues table

- Give the issue title the strongest emphasis in its row. Keep issue ID and comment count together as secondary metadata beneath or beside it.
- Use a subtle row hover state and a clear keyboard focus state for interactive rows and vote controls. Do not make the whole row clickable if it contains independent controls without defining their keyboard behavior.
- Keep the vote control visually distinct, comfortably sized for touch, and explicit about whether the current user has voted.
- Use compact, consistent pills for type, priority, status, and stage. Keep labels readable and ensure each state is understandable without color.
- Preserve column alignment and prevent long issue titles from pushing status or date data out of view. On small screens, use a labeled stacked row or allow horizontal scrolling inside the table region with an obvious affordance.
- When the list is empty, show a helpful empty state with a brief explanation and a relevant next action. When loading, use stable skeleton shapes to prevent layout shifts.

### Points chart

- Make the timeframe selection, date range, and total read as one control group, with the chart title and explanatory subtitle kept visually distinct.
- Scale bars and the 500-point threshold from the same data scale. The dashed requirement line must accurately represent 500 relative to the chart's y-axis; do not position it decoratively at an arbitrary height.
- Label the chart's scale or provide concise accessible chart text so the meaning of bar heights and the threshold is clear.
- Show the score and bonus near the active bar without collision. If a bar is too short or too close to an edge, reposition its labels predictably.
- Use a restrained hover/focus highlight to reveal the exact date and points. Ensure equivalent information is available to keyboard and touch users, not only on hover.
- On compact screens, keep timeframe controls usable by allowing horizontal scrolling or wrapping, and simplify date labels only when their meaning remains clear.

### Agents table

- Reduce unused horizontal space by assigning column widths to the content: give the agent identity and current activity room, and keep status and last seen compact.
- Keep the agent name and model tag visually distinct. Make model tags quiet and consistent rather than competing with agent names.
- Use a text label alongside each connection indicator. Avoid implying an agent is active based only on a colored dot.
- Make the disclosure header a full, comfortably sized button with a clear expanded/collapsed state. Preserve the section heading and count in both states.
- On narrow screens, group agent name and model together, then show status, activity, and last-seen information in a compact secondary line or card layout.

## 9. Motion and whimsical details

Motion should make the workspace feel lively, thoughtful, and rewarding while keeping a professional developer-tool tone. Keep animation brief, purposeful, and optional. Whimsy belongs in small moments of feedback, not in continuous movement or decoration that competes with work.

### Motion principles

- Use short transitions for hover, focus, selection, expansion, and value changes, generally in the 140–240 ms range with a gentle ease-out curve.
- Animate only the properties needed for feedback: opacity, transform, color, and small size changes. Avoid large movement, flashing, looping backgrounds, and layout shifts.
- Keep controls responsive immediately; animation must never delay input or make a control's state ambiguous.
- Respect `prefers-reduced-motion`. Disable nonessential movement and replace animated transitions with immediate state changes or subtle opacity changes.
- Do not communicate success, failure, or selection through motion alone. Preserve clear labels, icons, and state styling.

### Suggested microinteractions

- **Metric cards:** On hover or keyboard focus, lift by a few pixels and brighten the border slightly. Keep the effect subtle and omit it on devices without hover.
- **Vote:** On a successful vote, give the chevron a quick upward nudge and the count a brief color/scale emphasis. Do not continuously pulse the vote button.
- **Points chart:** On first entry, bars may rise from the baseline with a short stagger. Animate only when the data or timeframe changes, and keep the transition short. A target-reaching bar may show a tiny one-time sparkle or soft glow; avoid persistent glitter or confetti.
- **Points milestone:** If the user newly crosses the 500-point requirement, show a small, dismissible celebratory accent near the points summary (for example, a brief sparkle and “Weekly goal reached”). Never replay it on every render or page visit for the same milestone.
- **Agents disclosure:** Expand and collapse with a brief opacity/height transition that respects reduced motion and does not hide content from assistive technology while it is visible.
- **Buttons and filters:** Provide clear hover, pressed, selected, and focus feedback with smooth color/border transitions. Use a slight press-in effect for pointer activation only.
- **Loading:** Prefer calm skeleton shimmer only when reduced motion is not requested; otherwise use static skeletons or a small progress indicator.

### Motion accessibility and performance

- Implement reduced-motion behavior using the platform preference, such as CSS `prefers-reduced-motion` or the project's existing motion utilities.
- Avoid animating large shadows, blur, or many chart elements at once when it causes jank. Prefer transform and opacity for movement.
- Keep animation state tied to meaningful events, such as a successful vote, a newly reached milestone, or a user-requested chart filter change.
- Ensure animated content remains understandable if animation is skipped, interrupted, or disabled.

## 10. UX acceptance checklist

- The first screen clearly presents the greeting, primary action, key metrics, and assigned issue without forcing the user to decode decorative styling.
- Related controls are grouped, values and labels align consistently, and secondary information is visually quieter than primary content.
- Tables remain usable at narrow widths, keyboard focus is visible, and touch targets are comfortable.
- The chart threshold matches its scale, and chart values can be understood without relying on color or hover alone.
- Every interactive element has a clear purpose and accessible name/state.
- Motion is brief, tied to user feedback, nonessential, and reduced or removed when reduced motion is requested.
