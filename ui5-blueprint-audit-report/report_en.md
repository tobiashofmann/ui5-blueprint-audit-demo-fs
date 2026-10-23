# UI5 BlueprintAudit Report

Generated: 2026-10-23T15:04:38.211Z

## Summary

| Project | Type | Errors | Warnings | Status |
|---|---|---|---|---|
| Shop Administration Tool | fs | 7 | 4 | ❌ |

## Shop Administration Tool

Project type: fs

| Rule | Severity | Status | Findings |
|---|---|---|---|
| `xml-views` | error | ✅ | – |
| `controller-matches-view` | error | ❌ | webapp/view/settings/DetailSettings.view.xml: View "webapp/view/settings/DetailSettings.view.xml" should reference a controller named "DetailSettings", but references "sap.ui.demo.toolpageapp.controller.settings.MasterSettings" (expected base name "DetailSettings", got "MasterSettings"). |
| `folder-structure` | error | ✅ | – |
| `odata-metadata-local` | error | ✅ | – |
| `non-odata-json` | error | ✅ | – |
| `no-custom-css` | error | ✅ | – |
| `theme` | error | ✅ | – |
| `namespace` | error | ✅ | – |
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
| `wdi5-tests` | warn | ⚠️ | wdio.conf.js: Missing wdio.conf.js (or .ts) in the project root.<br>package.json: wdio-ui5-service is not a dependency in package.json. |
| `app-icons` | warn | ⚠️ | webapp/manifest.json: sap.ui/icons/icon is not set.<br>webapp/manifest.json: sap.ui/icons/favIcon is not set. |
| `app-version` | warn | ✅ | – |
