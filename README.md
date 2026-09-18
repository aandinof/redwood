# Redwood Therapeutics landing page

Static, single-file landing page for redwoodtherapeutics.bio. No build step needed — `index.html` is self-contained.

## Deploy to Render

1. Create a new GitHub repo (e.g. `redwood-landing`), and push this folder's contents to it:

   ```
   git init
   git add .
   git commit -m "Initial landing page"
   git branch -M main
   git remote add origin <your-new-repo-url>
   git push -u origin main
   ```

2. In Render (new account, separate from any work account): **New → Static Site**, connect the repo you just pushed.
3. Render will detect `render.yaml` in this repo and use it automatically (build command: none, publish path: repo root). If it doesn't pick it up, set those two fields manually in the service settings.
4. Once deployed, go to the service's **Settings → Custom Domains** and add:
   - `redwoodtherapeutics.bio`
   - `www.redwoodtherapeutics.bio`
   Render will show you the exact DNS records to add (typically an A/ALIAS record for the apex domain and a CNAME for `www`).
5. At your domain registrar's DNS settings, add the records Render gave you. SSL certificates are issued automatically by Render once DNS propagates (can take a few minutes to a few hours).

## Making future changes

Edit `index.html` (or replace it entirely), commit, and push to `main`. Render auto-redeploys on every push. Past deploys stay available for instant rollback from the Render dashboard if something breaks.
