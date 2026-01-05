# Deploy UI to Github

This is temporary deployment for demo purpose. when only site features require for demoing to users or to give users some handon experience without registering users, we can deploy UI to github and use as a demo site.

## Demo site access

User can access demo site to get experience of available features,
https://rajexcited.github.io/arthasight-ui/

for login, use the email Id ending with `@demo.com` with any password.

For example,  
**emailId:** `user@demo.com`  
**password:** `P@ssword1234`

## Deploy Demo

The demo site will be available for few days after deployment.

### CI Job

Deploy through CI job is preferrable.
Trigger CI job [Deploy Demo UI](actions/workflows/ui-demo-deploy.yml) to deploy UI for demo.

In The input, give appropriate milestone value. only features available through milestone will be accessible in demo site

Allowable values

- **Released Milestone**: the build and deployment will reference the tag.
- **Developing Milestone**: the build and deployment will reference the milestone branch if available
- **Master Milestone**: if developing milestone branch is not available and master has same milestone version, the build and deployment will referece the master branch.

### Local Alternate

If there is a problem with CI job, build with demo file and push dist changes to `gh-pages` branch.
The deployment job will automatically trigger after push on branch.

Commands to run:

```cmd
copy src\\demo\\demo.ts src\\demo\\index.ts
npm run build
gh-pages -d build
```
