# CloudLaunch — Azure Static Web Apps demo

A ready-to-deploy, plain HTML/CSS/JavaScript website for testing Azure Static Web Apps with GitHub.

## Files
- `index.html` — website
- `staticwebapp.config.json` — basic routing and security headers

## Deploy using Azure Portal
1. Extract this ZIP file.
2. Create a new GitHub repository, for example `azure-static-web-app-demo`.
3. Upload **the contents of this folder** to the repository root. `index.html` must be at the root, not inside an extra nested folder.
4. In Azure Portal, search for **Static Web Apps** and select **Create**.
5. Select your subscription, resource group, name, hosting plan and region.
6. Under Deployment details, choose **GitHub**, authorize GitHub, and select your account, repository and branch (usually `main`).
7. For Build Details, select **Custom** (or the equivalent no-framework option) and set:
   - App location: `/`
   - API location: leave blank
   - Output location: leave blank
8. Review and create the resource. Azure will add a GitHub Actions workflow to your repository.
9. Open the Static Web App's Overview page and visit its generated URL after the deployment finishes successfully.

## If the portal asks for a build preset
Choose **Custom**. This is a plain static site, so no `npm install` or build command is needed.

## Test an update
Edit the heading in `index.html`, commit and push the change to the selected branch. GitHub Actions should run another deployment.

## Troubleshooting
- Check the **Actions** tab in GitHub for deployment logs.
- Confirm `index.html` is at the repository root.
- Confirm the app location is `/` and output location is blank.
- Make sure the workflow uses the branch selected during setup.
