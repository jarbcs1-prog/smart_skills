# Deployment reference

## GitHub Pages deployment (Stage 8)

Deploy a product landing page to GitHub Pages using the user's GitHub PAT.

### Procedure

1. **Clone the repo** (or reuse an existing repo). Use `gh auth status` to verify the PAT is active.
2. **Add the landing page** (`index.html`) to the repo root or a deploy folder.
3. **Commit and push**: `git add -A && git commit -m "Add landing page" && git push -u origin main`
4. **Enable GitHub Pages** via API:
   ```bash
   curl -s -X PUT \
     -H "Authorization: token <PAT>" \
     -H "Accept: application/vnd.github+json" \
     -H "Content-Type: application/json" \
     https://api.github.com/repos/<owner>/<repo>/pages \
     -d '{"source":{"branch":"main","path":"/"}}'
   ```
- **GitHub Pages API returns 404 for some repos** even when the same API works for others. This is a known inconsistency — if the API returns 404, flag to the user and suggest manual enablement (Settings → Pages).

### Pitfalls

- **Email privacy restriction (GH007)**: GitHub rejects pushes when the commit email is not public. Fix: use a public email in git config or amend the commit with `git commit --amend --no-edit` (force push required) and confirm with the user before force-pushing.
- **GitHub Pages API returns 404 for some repos** even when the same API works for others. If the API returns 404, flag to the user and suggest manual enablement (Settings → Pages).
- **GitHub Pages rebuild delay**: After enabling Pages, the site may return 404 for several minutes while the build runs. Wait 30-60 seconds and re-check before declaring the deployment failed.
- **Token scope**: The PAT must have `repo` scope (or `pages` permission) for the Pages API to work. Verify with `gh auth token` and check the token's scopes.
- **No Twitter/Reddit/Discord**: Per the user's platform constraints, do not set up accounts or campaigns on these platforms. Use GitHub Pages, email and any already approved Facebook Ads budget.