# Shop Administration Tool (UI5 Demo App)

This project is a SAPUI5/OpenUI5 demo application (the "Toolpage App") and also serves here as an
example project showing how to audit a UI5 Freestyle project with
[`@abap/ui5-blueprint-audit`](https://github.com/tobiashofmann/UI5-BlueprintAudit).

`ui5-blueprint-audit` is a CLI tool that checks a UI5 project's structure, manifest, and
configuration against guidelines (it complements ESLint and `@ui5/linter`, rather than replacing
them).

## Prerequisites

- Node.js (for `npx`/`npm`)
- A project type must be known: `fs` (Freestyle), `fe` (Fiori Elements), or `lib` (Library).
  This project is a Freestyle project (`fs`) — recognizable from `webapp/manifest.json` having
  `"type": "application"` and hand-written views/controllers under `webapp/view` and
  `webapp/controller`.

## Installation

The tool is installed as a dev dependency:

```bash
npm install --save-dev @abap/ui5-blueprint-audit
```

## Audit with default values

Without a custom configuration file, the tool checks the project against the catalog's default
rules. The project type must still be passed via `--type`:

```bash
npx ui5-blueprint-audit --type fs
```

Optionally, this can also be set up as an npm script in `package.json`:

```json
{
  "scripts": {
    "audit": "ui5-blueprint-audit --type fs"
  }
}
```

```bash
npm run audit
```

Useful options:

- `--lang de,en,pt-BR` – output languages for the reports (default: `de,en`)
- `--out <dir>` – target folder for the reports (default: `ui5-blueprint-audit-report/`)
- `--help` – shows all available options

The tool exits with code `1` as soon as at least one finding with severity `error` exists. Pure
`warn` findings alone don't cause a failing exit code — useful for CI pipelines that should only
fail on real errors.

## Audit with a custom configuration file

For project-specific adjustments, place a file named `ui5-blueprint-audit.yaml` in the project
root. It only overrides the settings explicitly specified — everything else stays at its default.

This project already ships a complete example configuration at
[`ui5-blueprint-audit.yaml`](ui5-blueprint-audit.yaml). It contains all 33 rules from the catalog
with their default severity and all available parameters — as a template to copy and adapt. Key
settings from it:

```yaml
projectType: fs
languages: [de, en]

rules:
  namespace:
    - error
    - value: sap.ui.demo.toolpageapp   # must match manifest.json

  theme:
    - error
    - themes: [sap_horizon]

  ui5-version:
    - error
    - min: "1.152"
```

Once the file exists, running the tool is as simple as:

```bash
npx ui5-blueprint-audit
```

(the project type can then come from the file; `--type` still overrides the file if given).

Examples of typical adjustments in `ui5-blueprint-audit.yaml`:

- Disable a rule: `no-custom-controls: off`
- Tighten/loosen a rule: `cache-buster: error` instead of `off`
- Adjust parameters, e.g. allowed themes:

  ```yaml
  theme:
    - error
    - themes: [sap_horizon, sap_horizon_dark]
  ```

- Restrict report languages: `languages: [en]`

## Reports

Results are written to `ui5-blueprint-audit-report/` by default:

- `report_<locale>.md` – one Markdown report per active language (e.g. `report_de.md`, `report_en.md`)
- `report.xml` – JUnit format (always in English), one testcase per rule, one testsuite per project
- `report.html` – a single HTML file with all active languages and a language switcher

## Sampel reports

File [report_en-default.md](ui5-blueprint-audit-report/report_en-default.md) shows the result when using the default configuration. No namespace configured, typescript expected, custom control used, etc.

File [report_en.md](ui5-blueprint-audit-report/report_en.md) shows the result when using a custom configuration:
- JavaScript
- Custom control allowed
- No OData service
- No Cachebuster
- ...

## Checking multiple projects / subfolders

```bash
# A single project at a given path (must contain webapp/manifest.json)
npx ui5-blueprint-audit path/to/my-app --type fs

# Every direct subfolder is checked as its own project
npx ui5-blueprint-audit projects/ --type fs
```

## Further information

For the full rule reference, the plugin mechanism, and more details, see
[UI5-BlueprintAudit on GitHub](https://github.com/tobiashofmann/UI5-BlueprintAudit).
