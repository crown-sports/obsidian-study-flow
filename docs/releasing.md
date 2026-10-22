# Release v0.2.0

Distribution: GitHub Release, with three ZIPs and `SHA256SUMS`; this does not submit the plugin to the community directory. The native plugin requires Obsidian 1.13.7+ on desktop. Keep package.json, package-lock.json, manifest.json and versions.json consistent.

PR #5 supplies the native workbench and must merge before PR #6 (text encoding). Retarget #6 to main and rerun its checks after #5 merges. Publish only after both changes are in main, using a previously unused tag. Never replace v0.1.0 or publish an intermediate workbench build.

From the final, clean release checkout, with Node 20+:

```sh
npm ci
npm run check
npm test
npm run package
```

Attach exactly these new files from `dist/`:

- `obsidian-study-flow-plugin-v0.2.0.zip`
- `obsidian-study-flow-example-v0.2.0.zip`
- `obsidian-study-flow-starter-v0.2.0.zip`
- `SHA256SUMS`

Verify each ZIP's CRC and its SHA-256 against the manifest before uploading. Do not upload old ZIPs left in the directory, build-time dependencies, private vault data or third-party plugin binaries. Installation and schema 1/2 upgrade instructions are in the [native guide](native-guide.en.md).
