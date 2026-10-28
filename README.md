# MakeHybrid for Gemini CLI

Your MakeHybrid account — LinkedIn, the messaging channels, the work
trackers — as tools in Gemini CLI.

```bash
gemini extensions install https://github.com/makehybrid/mcp
```

It asks for your MakeHybrid API key at install and keeps it in your
system keychain. The key is on your dashboard at
[makehybrid.com](https://makehybrid.com/dashboard.html); leave the
address setting empty unless your provider gave you one of its own.

Check it worked:

```
List my connected LinkedIn accounts.
```

## Using the Gemini app instead?

The app does not run extensions. It takes a remote MCP server as a
**custom app** on its Connected apps page — open `gemini.google.com/apps`,
choose **Add a custom app**, and paste the address your dashboard gives
you as the **MCP server URL**. Nothing to install, and the same tools.

## Why this one runs a local server

Gemini CLI expands `${VAR}` inside an extension manifest's `env` block
only — not inside `httpUrl`, `url` or `headers`. So a remote-URL
extension could not carry your own key, and every install would have to
be edited by hand. Running the published package over stdio lets the
`settings` block below prompt for the key and keep it out of the file.

## Publishing this

The extension gallery indexes public GitHub repositories on its own —
there is no form and no approval. What it needs is this directory at the
ROOT of a public repo, with `gemini-extension.json` as a top-level file,
and a tagged release.

`makehybrid-mcp@1.0.0` is on npm, so `npx -y makehybrid-mcp@latest`
resolves and this no longer waits on anything.

From a checkout of the monorepo:

```bash
cd extensions/gemini
git init -b main
git remote add origin https://github.com/makehybrid/mcp.git
git add -A
git commit -m "MakeHybrid for Gemini CLI"
git push -u origin main
git tag v1.0.0 && git push origin v1.0.0
```

A separate repo rather than a subfolder of the monorepo, for two
reasons: the manifest has to be at the root for the gallery to see it,
and the monorepo is private and names a plan that is not public yet.
These three files name neither — checked, not assumed.
