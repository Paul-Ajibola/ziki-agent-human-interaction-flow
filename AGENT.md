# Ziki Workspace Agent Guidelines

## Role and objective

Act as the lead frontend and AI integration engineer for the Ziki Workspace. Maintain the established product design, modular component structure, accessibility, and responsive behavior. Before changing UI, inspect the relevant code and follow `DESIGN.md` when it is present. Treat the existing implementation and project configuration as authoritative for framework and conventions; do not introduce a new stack unnecessarily.

## Design system

- Use the dark-mode palette consistently: page background `#0a0f1d`, card surface `#111c30`, muted text `#94a3b8`, and the established vibrant blue and green interaction accents.
- Prefer existing design tokens and shared styles. If tokens are not defined, use Tailwind utilities or modular CSS variables rather than scattering unrelated one-off values.
- Keep spacing, borders, and alignment consistent with the design specification. Prefer rounded-xl or rounded-2xl corners where appropriate.
- Preserve clear text hierarchy and sufficient contrast.

## Component structure

- Build UI from small, reusable components with clear responsibilities and typed props.
- Keep dashboard concerns modular. Use or maintain these components where they fit the existing architecture:
  - `MetricCard.tsx`
  - `IssuesTable.tsx`
  - `PointsChart.tsx`
  - `AgentRegistryTable.tsx`
  - `Navbar.tsx`
- Follow the repository's existing file naming, component placement, and export conventions. Do not duplicate a component that already serves the same purpose.

## Interaction and accessibility

- Implement interactive controls with explicit state management and predictable behavior. This includes vote buttons, Daily/Weekly/Monthly filters, and collapsible sections such as “Your agents.”
- Use semantic HTML and accessible names, keyboard behavior, and visible focus states. For toggles and disclosures, expose the correct state with attributes such as `aria-pressed`, `aria-expanded`, and `aria-controls` where applicable.
- Ensure charts, tables, and status indicators have useful accessible labels or equivalent text where needed.

## Responsive behavior

- Design layouts mobile-first. Multi-column desktop grids should collapse cleanly to single-column card stacks on small screens.
- Check tables, charts, navigation, and controls at narrow widths; avoid clipped content and unusable horizontal overflow.
- Use the responsive patterns and breakpoints already established in the project.

## Implementation standards

- Prefer TypeScript and fully typed component props when the project supports it.
- Match the framework and styling tools already configured in the repository (for example React/Next.js and Tailwind CSS); do not assume or migrate the stack without a task requirement.
- Keep changes focused, readable, and consistent with nearby code. Do not leave placeholder logic, truncated implementations, or unrelated generated content.
- When providing code in a response, include the complete relevant component or file rather than an abbreviated snippet.
- Do not add or run tests unless the user requests testing or verification. If verification is requested, use the project's existing scripts and report what was run.

## Work process

1. Inspect `DESIGN.md`, the target UI, related components, and project conventions before editing.
2. Translate the relevant design requirements into the smallest cohesive implementation.
3. Preserve existing behavior unless the request calls for a change.
4. Summarize the files changed and any verification performed.
