# Slack-to-Teams migration demonstrations

**[View the website](https://ryanbowie.github.io/slack-to-teams-migration-kit/)**

A documented engineering demonstration of using GitHub Copilot to investigate
Slack applications, build Teams equivalents and check that their business
behaviour is preserved. This is an approach other engineers can reproduce and
adapt, not a commercial product or an official migration service.

The website includes six genuine Slack/Teams screenshot pairs, the migration
workflow, measured worker costs, limitations and an unsuccessful notification
example. All application scenarios and business data are synthetic.

The latest exact-ZIP readiness test is deliberately a mixed result: installation
and 37 packaged regression checks passed; a new dashboard was accepted locally
after two browser-led repairs, while a new policy target exhausted four attempts
without compiling. The final managed cost was **86.057190 AI credits**, including
the failed asset; outside coordination/review and operating costs remain separate.
The prerequisites and compatibility guide explains those adoption limits.

## Documentation

- [Installation readiness, prerequisites and exact-release testing](docs/readiness.md)
- [Six demonstrated migrations](docs/migrations.md)
- [Additional coverage: two accepted migrations and one stopped failure](docs/coverage.md)
- [Fresh three-app portfolio generation and cost breakdown](docs/acceptance.md)

## Publication boundary

This repository publishes **the website and documentation only**. It does not
contain the migration toolkit source, source-app fixtures, generated Teams apps,
toolkit ZIP, private run records, raw screenshots, usage logs, tenant
configuration or credentials. The embedded images are reviewed cropped/redacted
derivatives of genuine client captures.

No MIT licence is being added as part of this documentation publication.
The private toolkit is not being released or licensed here.

Historical live demonstrations, local generation checks and production
acceptance are different scopes. Worker credits exclude outside coordination,
tooling development, live testing, documentation, staff effort and hosting.

## Website updates

The self-contained website is `site/index.html`. GitHub Pages deploys that
directory through `.github/workflows/pages.yml` after relevant changes to
`main`, or when the workflow is manually triggered. Case-study Markdown remains
under `docs/`.

The visual design follows the
[Solution Reviewer reference site](https://ryanbowie.github.io/copilot-studio-powerplatform-solution-reviewer-site/):
its blue-purple headline, lavender controls, neutral dark surfaces,
two-column introduction and numbered screenshot grid. The reference palette is
an explicit override of the page's original theme foundation. Migration
evidence, costs and publication boundaries remain independent of that reference.
