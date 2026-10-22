# Release v0.2.1

This documentation/example patch adds the first-result checklist to the native
example ZIP and aligns download guidance. It does not change the learning engine
or record schema. Keep v0.2.0 assets unchanged and create a new v0.2.1 release.
Existing users replace plugin files while retaining `data.json`; no extra legacy
migration is required.

Distribution: GitHub Release, with three ZIPs and `SHA256SUMS`; this does not submit the plugin to the community directory. The native plugin requires Obsidian 1.13.7+ on desktop. Keep package.json, package-lock.json, manifest.json and versions.json consistent.

The v0.2.0 release already combined PR #5 (native workbench) and PR #6 (text encoding). For v0.2.1, merge the documentation/package-metadata patch, wait for the exact main commit to pass CI, and build that clean commit. Use a new tag and preserve all earlier release assets.

From the final, clean release checkout, with Node 20+:

```sh
npm ci
npm run check
npm test
npm run package
```

Attach exactly these new files from `dist/`:

- `obsidian-study-flow-plugin-v0.2.1.zip`
- `obsidian-study-flow-example-v0.2.1.zip`
- `obsidian-study-flow-starter-v0.2.1.zip`
- `SHA256SUMS`

Verify each ZIP's CRC and its SHA-256 against the manifest before uploading. Do not upload old ZIPs left in the directory, build-time dependencies, private vault data or third-party plugin binaries. Installation and schema 1/2 upgrade instructions are in the [native guide](native-guide.en.md).
