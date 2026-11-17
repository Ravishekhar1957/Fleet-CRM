# Fleet CRM

Fleet CRM is being prepared for Supabase-backed development. This repository currently has no application framework configured, so the setup below is framework-agnostic.

## Supabase local development

1. Install the [Supabase CLI](https://supabase.com/docs/guides/cli) and Docker.
2. From the repository root, start the local Supabase services:

   ```sh
   supabase start
   ```

3. Copy `.env.example` to `.env.local` and fill in the values for your application. For local development, the CLI prints the local API URL and keys when `supabase start` completes.
4. Add the Supabase client SDK and environment-variable loading appropriate for your chosen application framework.

Useful commands:

```sh
supabase status
supabase stop
supabase migration new <migration_name>
```

The Supabase CLI configuration lives in `supabase/config.toml`; database migrations belong in `supabase/migrations/`.

## Credentials

Never commit `.env.local`, service-role keys, or other secrets. Use the public/anon key only in client-side code; keep the service-role key exclusively on trusted server-side code. For deployed environments, configure secrets through the hosting provider rather than committing them to this repository.
