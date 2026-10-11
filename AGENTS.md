<!-- LOVABLE:BEGIN -->
> [!IMPORTANT]
> This project is connected to [Lovable](https://lovable.dev). Avoid rewriting
> published git history — force pushing, or rebasing/amending/squashing commits
> that are already pushed — as it rewrites history on Lovable's side and the
> user will likely lose their project history.
>
> Commits you push to the connected branch sync back to Lovable and show up in
> the editor, so keep the branch in a working state.
<!-- LOVABLE:END -->

## Application architecture
- Keep OVERGLOW features in reusable domain components and routes in TanStack file routing; layout routes render Outlet so leaf pages remain reachable.
- Use Cloud Auth and database RLS for all private data; transactional database functions create servers, memberships, and direct conversations to prevent partial state.
- Keep demonstration data isolated from real accounts and persistence; the public explore page clearly marks temporary demo interactions.
- Centralize all appearance values in global CSS tokens and persist preferences in user_settings, so every screen shares a single theme.
- Roles are server-owned records, never user-editable profile claims; the foundation restricts management to verified server owners.
- Listen to message deletions without a column filter and reconcile via RLS-scoped reads on reconnect; deleted-row payloads do not retain filter columns reliably.
