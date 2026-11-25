# Leasewell deployment

The independent export has its homepage at the repository root. Deploy to Azure Static Web Apps: connect the GitHub repository, select a custom/static build, and use the repository root as the app location with no build output directory. Azure can create the workflow, or use the supplied example after creating the actual resource. Store its deployment token in the repository secret `AZURE_STATIC_WEB_APPS_API_TOKEN`.

Copy `deployment/azure-static-web-apps.yml.example` to `.github/workflows/azure-static-web-apps.yml` only after configuring the resource and secret. Do not commit actual keys. The supplied workflow skips a framework build and uploads the standalone files.

Add a custom domain you actually own through the Azure resource’s domain setup and DNS verification. The root sitemap and canonical URLs come from the verified domain in the complete authoring repository’s `src/company-profiles.json`; update them when moving the exported website to another origin.

The optional Node AI service is separate from static hosting. Configure the server environment using `.env.azure.example` and run `npm run api`. It supports only Leasewell evidence requests. It does not load an .env file automatically. Deploy it on an appropriate Node host with HTTPS, explicit allowed origins and a service access token before connecting the website to it. Production tenant authentication and sector ingestion remain separate milestones.

The static Azure header configuration applies when deployed to Azure Static Web Apps. It does not change GitHub Pages response headers or establish uptime, a live Azure deployment or a security certification.
