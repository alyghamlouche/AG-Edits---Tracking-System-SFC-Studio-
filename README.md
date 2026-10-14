# SFC Studio — Phase 2 Starter

A dark-and-purple Next.js + Supabase project for an editor and client portal.

## Setup

1. Install Node.js 20+.
2. Create a Supabase project, then run `supabase/schema.sql` in its SQL editor.
3. In Supabase Authentication, create your editor account. Copy its UUID. If it was created before the schema, insert a profile manually using the SQL example at the bottom of the schema. Set its profile role to `admin` using the SQL example.
4. Copy `.env.example` to `.env.local`, and replace both placeholders with your project's URL and publishable/anon key. **Never place a Supabase service-role key in this file.**
5. Run `npm install`, then `npm run dev`. Open http://localhost:3000.
6. Create a client record in Supabase SQL editor. Create a client Auth user, then link them to the client record through `client_members`. Client users will only see videos belonging to linked clients.
7. Add videos from the admin `All Videos` screen. Update statuses and links from each video detail page.

## Included

- Email/password sign-in with session refresh middleware
- Server-rendered admin dashboard, videos list, video detail, client list, and Kanban pipeline
- Client-only visibility enforced through Supabase Row Level Security
- Admin video creation, status and link updates
- Client review approval and shared feedback comments
- External Drive/Frame.io links

## Not yet included

- Self-service client invitations, video file hosting, email notifications, AI agents, video preview player, persistent version history, and deployment configuration.
- This is a starter application and **has not been production-tested**. Before onboarding real clients, test role permissions with separate accounts, validate links and inputs, and add rate limiting and operational monitoring.

## Security note

Client access is scoped by membership in the database. The SQL trigger prevents client accounts from modifying video details even though they can approve a video in review. Admin status changes should be validated against your desired workflow before production use.
