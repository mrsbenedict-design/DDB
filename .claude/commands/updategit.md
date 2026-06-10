# /updategit

Perform a full, secure publish of the VitalWealth Consultancy site to GitHub Pages.

## Steps

### 1. Security scan — run BEFORE touching git

Scan every tracked file for secrets, credentials, and sensitive data before anything is staged or pushed.

- Search for patterns that look like passwords, API keys, tokens, or private credentials:
  - `password`, `passwd`, `secret`, `api_key`, `apikey`, `token`, `private_key`, `access_key` (case-insensitive) appearing next to an actual value (not a placeholder like `YOUR_KEY_HERE`)
  - Hardcoded email addresses other than public contact details already present in `index.html`
  - Any `.env` files or files containing `process.env` / `os.environ`
- If anything suspicious is found, **stop and report it to the user** before proceeding. Do not continue until the user confirms it is safe.
- Confirm the `.github/workflows/deploy.yml` workflow does not contain hardcoded secrets (it should use `${{ secrets.* }}` for any sensitive values).

### 2. README — ensure it is complete and up to date

- Read the current `README.md`.
- If it is missing or out of date, regenerate it to accurately reflect the current state of the project (sections, design tokens, tech stack, live URL, local setup instructions).
- The README must include the GitHub Pages live URL once known.

### 3. GitHub Pages workflow — verify it exists and is correct

- Confirm `.github/workflows/deploy.yml` exists and is configured to deploy on push to `main` using the official `actions/deploy-pages` action.
- If the file is missing or broken, recreate it using the standard GitHub Pages static-site workflow (checkout → configure-pages → upload-pages-artifact → deploy-pages).
- Do not add any secrets or tokens directly in the workflow file; use `${{ secrets.* }}` references only if needed.

### 4. Update repo About (description + website)

- Use the GitHub CLI to update the repository description and homepage URL:
  ```
  gh repo edit --description "VitalWealth Consultancy — exercise and financial wellness, in one place." --homepage "https://mrsbenedict-design.github.io/DDB/"
  ```
- If the `gh` CLI is not authenticated, prompt the user to run `gh auth login` and then retry.

### 5. Commit and push

- Run `git status` to see what has changed.
- Stage only the files that belong to the project (`index.html`, `style.css`, `script.js`, `README.md`, `.github/`). Never stage `.env`, credential files, or any file flagged in the security scan.
- Write a concise, descriptive commit message summarising what changed.
- Push to `origin main`.
- After pushing, confirm the GitHub Actions deployment triggered by visiting the Actions tab URL:
  `https://github.com/mrsbenedict-design/DDB/actions`

### 6. Report back

After all steps complete, output a short summary:
- Security scan result (clean / issues found)
- Files committed and pushed
- Live site URL: `https://mrsbenedict-design.github.io/DDB/`
- GitHub Actions URL for the deployment run
