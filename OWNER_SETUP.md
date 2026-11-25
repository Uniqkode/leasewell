# Owner configuration and launch handover

The websites are complete enough to present and explore the product workflows. They do not publish invented registration, team, customer, throughput, uptime or deployment claims. This file lists the genuine values that activate the remaining business integrations.

## Company, domain, inbox and booking

Edit `src/company-profiles.json`. Use `defaults` for a real parent company shared by all ten brands, or `brands.<slug>` for a product-specific override. Rebuild with `npm run build` after changes.

| Setting | What to enter | Publication control |
| --- | --- | --- |
| `legalName`, `rcNumber`, `registrationEvidence` | The real operating legal company, genuine RC and an evidence reference | Set `registrationVerified: true` only after verification |
| `contactEmail` | A real monitored business mailbox | Set `contactVerified: true`; this also publishes configured phone/address |
| `phone`, `officeAddress` | Actual public business contact details | Require `contactVerified: true` |
| `domain` | The owned hostname, without `https://` or a path | Set `domainVerified: true` after ownership/configuration; drives canonical and sitemap URLs |
| `bookingUrl` | The actual HTTPS appointment link, such as your own Calendly event | Set `bookingVerified: true`; the contact page displays a working booking link |
| `maintainer.bio`, `maintainer.linkedin` | Accurate current responsibilities and the genuine professional profile | No invented experience, employers or qualifications |
| `team` | Actual names, roles, bios, profile/LinkedIn URLs and optional local portrait filename | Each additional person requires `verified: true` |
| `brands.<slug>.market` | Optional `initial` and `next` country arrays and market strategy text | Publish real strategy, not a claim of existing customers or offices |
| `usage` | Actual reporting date, period, evidence source, active organizations, processed count/unit and optional measured median analysis time | Only published when `usage.verified: true` and all reporting fields are valid; otherwise no traction block is rendered |

Blank or unverified values stay unpublished. Do not use generic RC numbers, `YOUR-LINK` booking addresses, imaginary employees or a fabricated `hello@` mailbox to make a page appear complete. The brand names and real public maintainer profile are already used.

## Enquiry workflow

The new contact form collects a workflow, optional public organization name, preferred date/time and enquiry text. It prepares the message for review. With a verified email, the next action opens the visitor’s email application. Otherwise it opens a GitHub issue composer after an explicit public-data consent step. The visitor makes the final submission; the site never falsely confirms delivery or a calendar booking.

The optional local project brief remains available in a separate disclosure. It saves and downloads a planning document; it is not the sales enquiry.

## Product content and prices

- `src/growth-data.mjs`: problem, Why now, segments, distribution, expansion strategy, outcome measures, evaluation methods, compute plan and default value-planner assumptions.
- `src/ai-briefs.mjs`: product descriptions, source-linked prepared cases, pricing/allowances and capacity-planning formulas.
- `src/product-plans.mjs`: sector Azure service roles, integration and operational evaluation milestones.
- `src/brands.mjs`: brand identity, logos’ source parameters and operational register fixtures.

Value-planner numbers are visitor-editable assumptions. Prepared cases are labelled in the review desk. Keep that context when replacing content. Customer counts, measured savings, model accuracy, real cloud usage and uptime should only be published with evidence. No fake 80–95 credit-review score is supplied.

## Live model and Azure deployment

The Node adapter supports Azure OpenAI v1 Responses with a real resource endpoint, compatible model deployment and server credentials. See `server/README.md` and `.env.azure.example`. No API key belongs in the public website.

Each individual product kit includes its own `service/` adapter and `npm run api`, restricted to that product. It also includes an Azure Static Web Apps workflow example and deployment notes under `deployment/`. Static hosting and the Node model service are separate deployments. Model evaluation, sector ingestion and organizational identity remain the roadmap’s actual integration work.

Azure ML, Document Intelligence, Search, Blob, Service Bus, IoT Hub, Entra, Key Vault, Private Link, Monitor/Application Insights and Defender are mapped to specific production jobs. AKS/GPU hosting is an option where evaluated model and serving needs justify it; managed OpenAI inference is not described as a self-owned GPU cluster. Rill explicitly starts from an evaluated CPU-friendly forecast baseline.

## Independent folders and repositories

`sites/<slug>/dist/` is the static site. `sites/<slug>/service/` and `deployment/` form the optional standalone launch kit. Exported folders in `/workspace/Dev/<slug>/` put the website at the repository root and preserve each existing `.git` history. Do not overwrite unrelated local changes or force-push different remote histories.

GitHub previously rejected creating the ten separate remote repositories. Their local commits and remote targets are prepared. Creation/access must exist before those pushes can succeed; the combined public collection remains deployable in the existing repository.
