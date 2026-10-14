# SFC Studio deployment notes

The original source files and the six subsequently uploaded page files were combined into this project.

## Fixes
- Restored the `db` export in `lib/supabase.ts` as an alias of `supabaseServer`. `workspace.ts` and `actions.ts` both depend on this export.
- Fixed Pipeline `v` implicit-any callbacks by typing the queried video rows and added query error handling.
- Included the updated Dashboard and Clients pages with explicit video/client types.

## Deployment
1. Upload the **contents of this `sfc-studio` directory** to the root of your GitHub repository, preserving the `app`, `lib`, `components`, and `supabase` directories.
2. Configure `NEXT_PUBLIC_SUPABASE_URL` and `NEXT_PUBLIC_SUPABASE_ANON_KEY` in Vercel project environment variables. Use the public anon/publishable key, not a service-role key.
3. Redeploy.
4. If a build fails, share the first complete TypeScript error from the Vercel log.

## Verification limitation
`npm install` could not complete in the preparation environment because access to registry.npmjs.org failed (EAI_AGAIN). Therefore, a complete `npm run build` could not be run here. The fixes are source-level and **the build is not verified**.

## Production readiness
This is a starter, not a production-tested app. Validate authorization and RLS behavior with separate admin and client accounts before onboarding clients.
