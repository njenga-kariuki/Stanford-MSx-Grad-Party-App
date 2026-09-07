# MSx Finale Shuttle Tracker

An event application built by Njenga Kariuki for the Stanford GSB MSx 2025 graduation celebration. It brings shuttle registration, passenger counts, a coordinator view and music requests into one mobile-friendly interface.

## Implementation

- React and TypeScript interface with Tailwind styling.
- Shuttle selection, registration, guest counts, updates and cancellations.
- Supabase-backed shuttle and registration records, with realtime subscriptions that refresh the views after changes.
- An administrator manifest and a separate DJ request view.

The repository preserves the May 2025 event implementation. The event has concluded; the source is useful for understanding the product and integration work, rather than making a new registration for that event.

## Local setup

Run `npm ci` and provide your own `VITE_SUPABASE_URL` and `VITE_SUPABASE_ANON_KEY` using `.env.example`, then run `npm run dev`. `npm run build` creates a production build.

The client expects `shuttles` and `registrations` tables; the source shows the fields it reads and writes. Database migrations, original event records and hosted configuration are not included. Use a separate project with synthetic registrations when exploring the app.

The Supabase anon key is a client key. Access to the underlying data must be controlled through appropriate database policies; the coordinator view is not protected by a separate login in this version. Reusing this for a new event would require that access-control work and your own database setup.

The original planning brief is retained in [project.md](project.md). Stanford branding identifies the historical event context; this is an independently built application.
