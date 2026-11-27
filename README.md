# Hostel Manager — Android online starter

This is a **starter source project**, not a published APK yet. It uses Expo (Android) + Supabase (online database/auth).

## Included
- Green-themed Android app shell and phone/password sign-in.
- Supabase database schema for profiles, month ledgers, meals, expenses, deposits and manager history.
- Row Level Security policies and an Edge Function for manager/owner-created member accounts.
- Monthly ledgers are independent: each month starts with no carried-forward member dues or cash balance.
- Meal self-service policy has the 09:30 local cutoff; manager/owner override is allowed while the month is running.

## Required setup
1. Create a Supabase project.
2. In Supabase SQL Editor, run `supabase/schema.sql`.
3. Configure Supabase Auth phone sign-in and an SMS provider. Phone/password sign-in requires phone auth enabled.
4. Create the first Owner auth user securely in Supabase Dashboard, then insert their matching profile row with role `owner` (never put service-role keys in the app).
5. Deploy `supabase/functions/create-member` with Supabase CLI and set its server secrets.
6. Copy `.env.example` to `.env` and fill the project URL and anon key.
7. Install dependencies with `npm install`, then run `npx expo start`.
8. For an Android APK, configure EAS Build and run `eas build -p android --profile preview` after installing/configuring EAS CLI.

## Important before real hostel use
This starter still needs full CRUD screens (member creation UI, meal calendar, expense/deposit forms, month close/reopen UI), server-side transactional accounting, tests, backup policy and security review. The schema is a foundation and must be reviewed before production use. Do not use real member financial records until those steps are complete.
