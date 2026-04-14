# Implementation Approach

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
