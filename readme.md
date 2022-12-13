# OneSignal Next.js Push Notification Example

    .
    ├── app         # Next.js app to place orders from
    ├── supabase    # Supabase directory containing functions to send push notifications
    └── README.md

- Rename `.env.example` to `.env.local` and add your Supabase URL and Anon Key.
- Run the SQL below to create the `orders` table
- Deploy the `notify` edge function by running `supabase functions deploy notify`

```sql
create table if not exists public.orders (
    id uuid not null primary key default uuid_generate_v4(),
    created_at timestamptz not null default now(),
    user_id uuid not null default auth.uid(),
    price int8 not null
);
```

## Running the app locally

Run the following command to start the Next.js app

```bash
cd app

npm install

npm run dev
```
