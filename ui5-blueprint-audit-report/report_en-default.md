# UI5 BlueprintAudit Report

Generated: 2026-10-23T15:03:30.953Z

## Summary

| Project | Type | Errors | Warnings | Status |
|---|---|---|---|---|
| Shop Administration Tool | fs | 12 | 5 | ❌ |

## Shop Administration Tool

Project type: fs

| Rule | Severity | Status | Findings |
|---|---|---|---|
| `typescript` | error | ❌ | tsconfig.json: Missing tsconfig.json in the project root.<br>webapp/Component.js: JavaScript file instead of TypeScript: webapp/Component.js<br>webapp/control/D3Chart.js: JavaScript file instead of TypeScript: webapp/control/D3Chart.js<br>webapp/control/D3ColumnChart.js: JavaScript file instead of TypeScript: webapp/control/D3ColumnChart.js<br>webapp/control/D3ComparisonChart.js: JavaScript file instead of TypeScript: webapp/control/D3ComparisonChart.js<br>webapp/control/D3PieChart.js: JavaScript file instead of TypeScript: webapp/control/D3PieChart.js<br>webapp/controller/App.controller.js: JavaScript file instead of TypeScript: webapp/controller/App.controller.js<br>webapp/controller/BaseController.js: JavaScript file instead of TypeScript: webapp/controller/BaseController.js<br>webapp/controller/Home.controller.js: JavaScript file instead of TypeScript: webapp/controller/Home.controller.js<br>webapp/controller/Statistics.controller.js: JavaScript file instead of TypeScript: webapp/controller/Statistics.controller.js<br>webapp/controller/settings/MasterSettings.controller.js: JavaScript file instead of TypeScript: webapp/controller/settings/MasterSettings.controller.js<br>webapp/model/formatter.js: JavaScript file instead of TypeScript: webapp/model/formatter.js<br>webapp/model/models.js: JavaScript file instead of TypeScript: webapp/model/models.js |
| `xml-views` | error | ✅ | – |
| `controller-matches-view` | error | ❌ | webapp/view/settings/DetailSettings.view.xml: View "webapp/view/settings/DetailSettings.view.xml" should reference a controller named "DetailSettings", but references "sap.ui.demo.toolpageapp.controller.settings.MasterSettings" (expected base name "DetailSettings", got "MasterSettings"). |
| `folder-structure` | error | ✅ | – |
| `no-custom-controls` | error | ❌ | webapp/control/D3Chart.js: Custom control "sap.ui.demo.toolpageapp.control.D3Chart" in webapp/control/D3Chart.js |
| `odata-service` | error | ❌ | webapp/manifest.json: Only 0 OData service(s) found, at least 1 expected. |
| `odata-metadata-local` | error | ✅ | – |
| `non-odata-json` | error | ✅ | – |
| `no-custom-css` | error | ✅ | – |
| `theme` | error | ✅ | – |
| `cache-buster` | error | ❌ | No cache buster task/middleware configured in ui5.yaml, and index.html does not load UI5 via a versioned cache buster URL. |
| `namespace` | error | ❌ | webapp/manifest.json: sap.app/id ("sap.ui.demo.toolpageapp") does not start with "de.itsfullofstars". |
| `consistent-namespace` | error | ✅ | – |
| `fragments-folder` | error | ✅ | – |
| `dialogs-folder` | error | ✅ | – |
| `i18n-used` | error | ✅ | – |
| `i18n-languages` | error | ✅ | – |
| `i18n-fallback` | warn | ✅ | – |
| `device-types` | error | ✅ | – |
| `flex-enabled` | warn | ⚠️ | webapp/manifest.json: sap.ui5/flexEnabled is "undefined", expected "true". |
| `content-densities` | error | ❌ | webapp/manifest.json: sap.ui5/contentDensities/compact is not true.<br>webapp/manifest.json: sap.ui5/contentDensities/cozy is not true. |
| `mockserver-config` | warn | ⚠️ | ui5-mockserver.yaml: Missing ui5-mockserver.yaml in the project root. |
| `framework` | error | ❌ | ui5.yaml: framework.name in ui5.yaml is "OpenUI5", expected "SAPUI5". |
| `ui5-version` | error | ❌ | webapp/manifest.json: sap.ui5/dependencies/minUI5Version ("1.77.0") is below the minimum version "1.152".<br>minUI5Version ("1.77.0") and framework.version ("1.153.0") are not consistent (major.minor). |
| `flp-config` | error | ❌ | webapp/manifest.json: sap.app/crossNavigation/inbounds has no entry with semanticObject and action. |
| `deploy-config` | error | ❌ | ui5-deploy.yaml: Missing ui5-deploy.yaml in the project root. |
| `app-title-description` | error | ❌ | webapp/i18n/i18n.properties: i18n key "appTitle" for sap.app/title is empty or missing.<br>webapp/i18n/i18n.properties: i18n key "appDescription" for sap.app/description is empty or missing. |
| `qunit-opa-tests` | warn | ✅ | – |
| `wdi5-tests` | warn | ⚠️ | wdio.conf.js: Missing wdio.conf.js (or .ts) in the project root.<br>package.json: wdio-ui5-service is not a dependency in package.json. |
| `playwright-tests` | warn | ⚠️ | playwright.config.ts: Missing playwright.config.ts (or .js) in the project root.<br>package.json: @playwright/test is not a dependency in package.json. |
| `app-icons` | warn | ⚠️ | webapp/manifest.json: sap.ui/icons/icon is not set.<br>webapp/manifest.json: sap.ui/icons/favIcon is not set. |
| `app-version` | warn | ✅ | – |
