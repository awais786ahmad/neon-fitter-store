# Neon Fitter Store

Clone https://github.com/awais786ahmad/neonfitter.git
Act as a Senior Developer and Solution architect
IMplement supabase db , storage and auth ( auth for admin login with email and password) i haev a seperate ready made supabase ready , i just need to add the env vars
Create efficient database schema for supabase as well, suitable for my store as well, 
Remove localstorage and use npm install @supabase/supabase-js @supabase/ssr
 
Customer can still save their designs in localstorage and cart can be stored in localstorage as well,


Your store now saves its data to your own Supabase project, but it won't connect until you add your keys. The preview also still shows one error, in src/app/layout.tsx: it can't find the site's style file. That error was there before this change, and I haven't fixed it yet.

Setup (one time):

In Supabase, open the SQL Editor, paste in the contents of supabase/schema.sql and run it. This creates all the tables and the file storage folder.

Add these two values (from Project Settings → API) to a .env.local file. .env.example shows the format.

NEXT_PUBLIC_SUPABASE_URL

NEXT_PUBLIC_SUPABASE_ANON_KEY

In Supabase, go to Authentication → Users and add your admin email and password. Then run the short "make yourself admin" query at the bottom of the schema file.

What changed:

Admin sign-in: you now sign in with email and password instead of the old shared password. Only accounts marked as admin can get in, and you can change your password in Admin → Settings.

Saved to the database: orders, returns, materials, stock changes, templates, catalog options and pricing rules.

Files: uploaded pictures, fonts, customer artwork and return photos are moved into Supabase storage automatically.

Still in the shopper's browser: the cart, saved designs, the editor's autosaved design and the coupon, as you asked.

Privacy: customers can only look up an order by its number, and the full order list is visible to admins only.

The existing tests pass, but I couldn't test anything against a real database because your keys aren't set yet.

Still to check:

The order confirmation and track-order pages don't wait for the database yet. After a page refresh, a real order could briefly show "not found", and searching for an order placed on another device may not find it. They need a small fix.

Until the keys are added, admin sign-in will show "The database is not connected yet", and any changes disappear when you refresh the page.



Make this store production ready

This project was built with [Lovable](https://lovable.dev).

## Build with Lovable

Continue developing this project in the [Lovable editor](https://lovable.dev/projects/5d5320a3-a64a-4d07-b888-d94accc77247).

- **Ship faster**: describe what you want to build and Lovable handles the code.
- **Stay in sync**: every change made in Lovable is committed straight to this repository.
- **Full ownership**: this code is yours. Push to `main` on GitHub and your changes sync back into Lovable, ready for your next prompt.

## Development

Prefer working locally? You need Node.js and npm — [install with nvm](https://github.com/nvm-sh/nvm#installing-and-updating).

```sh
git clone <this-repository-url>
cd <repository-name>
npm i
npm run dev
```
