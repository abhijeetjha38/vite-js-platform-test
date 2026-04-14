# Validation

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
