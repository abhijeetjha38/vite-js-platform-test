# Locked Decisions for Story 3ffd3534-8622-4fbf-b543-7c847b378dd9

## Implementation Approach
## Implementation Approach — Login Page

### Project Setup
Since this is a greenfield project, the first step is scaffolding the Next.js application:
- Initialize **Next.js** with TypeScript, Tailwind CSS, and App Router
- Configure for **static export** (`output: 'export'` in `next.config.js`)
- Install and configure **Shadcn/ui** (init with Tailwind + Radix primitives)
- Set up **Source Sans Pro** via `next/font/google`
- Configure Tailwind theme with teal & gray/slate color palette

### Login Page Structure
- **Route:** `app/page.tsx` — the login page is the root/index route (navigating to the application URL shows the login form, per AC #1)
- **Component:** `components/login-form.tsx` — a client component (`"use client"`) containing the form logic
- **Layout:** `app/layout.tsx` — root layout with font loading and global styles

### Form Handling
- Use **React state** (`useState`) for username, password, and error fields — no form library needed for two fields
- On submit: **`console.log`** the credentials object `{ username, password }` and show a brief success toast/message (mock submission per user decision)
- No actual network call, no fetch, no API route

### Key Technical Choices
- **No external state management** — local component state is sufficient
- **No routing beyond the index page** — single page application for this story
- **Client component** — the form requires interactivity (`onChange`, `onSubmit`), so it must be a client component
- **Shadcn/ui components** used: `Button`, `Input`, `Label`, `Card` (and related Card sub-components)

## Validation
## Validation — Login Page

### Required Field Validation (AC #3)
- **Trigger:** On form submit only (not on blur or keystroke — keeps it simple for a sandbox)
- **Rules:**
  - Username field must not be empty/whitespace-only
  - Password field must not be empty/whitespace-only
- **Error Display:** Inline error message below each empty field in red (`text-red-500`), e.g., "Username is required" / "Password is required"
- **Behavior:** If either field is empty, the form does NOT submit and errors are shown. Errors clear when the user starts typing in the respective field.

### On Successful Submit
- Both fields are non-empty → `console.log({ username, password })` 
- Show a brief inline success message (e.g., "Credentials submitted — check console") styled with a green/teal indicator
- Form fields remain filled (no reset) so the developer can inspect state

### Edge Cases
- **Whitespace-only input:** Treated as empty — trimmed before validation
- **No max-length enforcement** — this is a sandbox, no real security constraints
- **No password complexity rules** — out of scope for this story
- **No rate limiting or lockout** — not applicable for a mock form
