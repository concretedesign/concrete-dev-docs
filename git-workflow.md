# Git workflow

Use this workflow for creating and managing the git workflow for concrete projects.

- Clone https://github.com/concretedesign/concrete-isomorphic-react (for a SPA) or https://github.com/concretedesign/concrete-metalsmith-boilerplate (for a static site)
- Create branches
 - `development`
 - `staging`
 - `production`
- All work starts in `development`
- Work that is generic and can be used for other projects should be cherry-picked back onto `master`
- Merge `development` work that should be shown to client into `staging` and deployed to staging server
- Fully tested, stable work on `staging` should then be merged into `production` and deployed
