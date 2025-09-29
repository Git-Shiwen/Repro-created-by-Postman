# Postman + Newman CI Starter

This repo contains a ready-to-run Postman collection and GitHub Actions workflow.

## Files
- `reqres-collection.json` — Sample collection (uses https://reqres.in)
- `reqres-env.json` — Environment with variables
- `.github/workflows/api-tests.yml` — CI pipeline

## Local run
```bash
# If npm isn't recognized on Windows, reopen your terminal after Node install or use npx:
npx --yes newman run reqres-collection.json -e reqres-env.json -r cli,htmlextra,junitfull   --reporter-htmlextra-export reports/newman.html   --reporter-junitfull-export reports/junit.xml
```

## GitHub Actions
1. Create a new GitHub repo and push these files.
2. Go to **Actions** tab to see the pipeline run on every push / PR.
3. Download `newman.html` artifact for a visual report; see **Summary** for JUnit results.
