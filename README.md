# See https://help.github.com/articles/ignoring-files/ for more about ignoring files.
# dependencies
/node_modules
/.pnp
.pnp.js
# testing
/coverage
# next.js
/.next/
/out/
# production
/build
# misc
.DS_Store
*.pem
tsconfig.tsbuildinfo
# debug
npm-debug.log*
yarn-debug.log*
yarn-error.log*
# local env files
.env.local
.env.development.local
.env.test.local
.env.production.local
# vercel
.vercel

# external fonts
public/fonts/**/Optimistic_*.woff2

# rss
public/rss.xml
  5 changes: 3 additions & 2 deletions5  
package.json
@@ -15,11 +15,12 @@
    "prettier:diff": "yarn nit:source",
    "lint-heading-ids": "node scripts/headingIdLinter.js",
    "fix-headings": "node scripts/headingIdLinter.js --fix",
    "ci-check": "npm-run-all prettier:diff --parallel lint tsc lint-heading-ids",
    "ci-check": "npm-run-all prettier:diff --parallel lint tsc lint-heading-ids rss",
    "tsc": "tsc --noEmit",
    "start": "next start",
    "postinstall": "patch-package && (is-ci || husky install .husky)",
    "check-all": "npm-run-all prettier lint:fix tsc"
    "check-all": "npm-run-all prettier lint:fix tsc rss",
    "rss": "node scripts/generateRss.js"
  },
  "dependencies": {
    "@codesand
