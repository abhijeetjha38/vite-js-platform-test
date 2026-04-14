

Here is the DESIGN.md content based on the locked design decisions:

# DESIGN.md

## Framework & Tooling
- Use Next.js in static export mode (`next export`). Do NOT use SSR, API routes, or serverless functions.
- Use Tailwind CSS for all styling. Do NOT use inline styles or separate CSS files for component styling.
- Use shadcn/ui (Radix UI primitives) as the component library. Copy components into `components/ui/`.
- All pages must be statically generated at build time. Handle any data fetching client-side only.

## Color Palette
- Primary: Teal `teal-600` (#0d9488) — use for CTAs, links, active/focus states, primary buttons.
- Primary hover: `teal-700` (#0f766e).
- Primary emphasis: `teal-800` (#115e59) — use for dark headings on teal backgrounds or strong emphasis.
- Primary subtle: `teal-100` (#ccfbf1) — use for highlight backgrounds, badges, selected row states.
- Primary ghost: `teal-50` (#f0fdfa) — use for hover backgrounds on ghost buttons or table rows.
- Neutral text: `slate-900` (#0f172a) for headings, `slate-700` (#334155) for body, `slate-500` (#64748b) for muted/secondary text.
- Neutral borders: `slate-200` (#e2e8f0). Neutral surface: `white` (#ffffff). Page background: `slate-50` (#f8fafc).
- Error: `red-600` (#dc2626). Warning: `yellow-500` (#eab308). Success: `green-600` (#16a34a).
- Do NOT create custom colors outside this palette. Use Tailwind's teal and slate scales exclusively.

## Typography
- Font family: "Source Sans Pro" from Google Fonts. Load weights 400, 600, 700.
- Set in Tailwind config: `fontFamily: { sans: ['"Source Sans Pro"', 'sans-serif'] }`.
- Headings: `font-semibold` or `font-bold`. Use `text-slate-900`.
- Body text: `font-normal` (400). Use `text-slate-700`.
- Muted/secondary text: `text-slate-500`.
- Use monospace (`font-mono`) only for code snippets or raw data values.
- Do NOT use font weights other than 400, 600, 700.

## Spacing & Layout
- Use Tailwind's default spacing scale (4px base unit: 1=4px, 2=8px, 3=12px, 4=16px, 6=24px, 8=32px).
- Common patterns: `p-4`, `px-6`, `py-3`, `gap-4`, `space-y-4`, `mb-6`.
- Page container: `max-w-7xl mx-auto px-4 sm:px-6 lg:px-8`.
- Maintain generous whitespace. Separate major sections with `py-8` or `py-12`.
- Do NOT use arbitrary spacing values (e.g., `p-[13px]`) unless absolutely unavoidable.

## Components (shadcn/ui)
- Use shadcn/ui `Button`, `Card`, `Input`, `Dialog`, `Table`, `Badge`, `DropdownMenu`, and other primitives.
- Primary button: `bg-teal-600 hover:bg-teal-700 text-white`.
- Secondary/outline button: `border-slate-200 text-slate-700 hover:bg-slate-50`.
- Ghost button: `hover:bg-teal-50 text-teal-600`.
- Cards: `bg-white border border-slate-200 rounded-lg shadow-sm`. Do NOT use heavy drop shadows.
- Border radius: use `rounded-md` (6px) for buttons/inputs, `rounded-lg` (8px) for cards/dialogs.
- Transitions: `transition-colors duration-150` on all interactive elements.
- Configure shadcn/ui theme CSS variables to map to the teal/slate palette defined above.

## Visual Rules
- Shadows: use only `shadow-sm` or `shadow` (Tailwind defaults). Do NOT use `shadow-lg`, `shadow-xl`, or custom box-shadows.
- Borders: 1px `border-slate-200` for separation. Do NOT use thick or colored borders except for focus rings.
- Focus rings: `focus-visible:ring-2 focus-visible:ring-teal-600 focus-visible:ring-offset-2`.
- Maintain WCAG AA contrast ratios on all text. Test teal-600 on white (passes AA for large text; use teal-800 for small text if needed).
- Responsive: design mobile-first. Use `sm:`, `md:`, `lg:` breakpoints progressively.

## Do NOTs
- Do NOT use SSR, API routes, `getServerSideProps`, or any server-only features.
- Do NOT install additional CSS frameworks (Bootstrap, Chakra, MUI, etc.).
- Do NOT use inline `style={}` attributes.
- Do NOT create one-off color values or arbitrary Tailwind values.
- Do NOT use heavy shadows, gradients, or decorative flourishes — keep it corporate and clean.
- Do NOT skip semantic HTML (`<main>`, `<nav>`, `<section>`, `<article>`).

Now I'll write this to the DESIGN.md file: