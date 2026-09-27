# Amin Plugins

A Git-backed plugin marketplace containing MRI Interpreter.

MRI Interpreter helps radiologists draft follow-up MRI and CT reports from a prior
report and clinician-supplied current findings. It is a documentation aid; the
radiologist reviews and signs the final report.

## Repository layout

```text
.agents/
└── plugins/
    └── marketplace.json
plugins/
└── mri-interpreter/
    ├── plugin.json
    ├── .codex-plugin/
    │   └── plugin.json
    └── skills/
        └── mri-interpreter/
            └── SKILL.md
```

The root `plugin.json` is the portable manifest. `.codex-plugin/plugin.json`
provides Codex compatibility metadata. Keep the name, version, and description
consistent between them. The original skill text lives in the nested `skills/`
directory unchanged. No MCP server is required.

## Add the marketplace

To test this checkout locally, run from the repository root:

```sh
codex plugin marketplace add .
```

After committing and pushing this structure to GitHub, others can add it with:

```sh
codex plugin marketplace add amintorabi88/MRI_Interpreter_skill
```

Open the Plugins directory, select **Amin Plugins**, and install **MRI Interpreter**.
Adding this Git marketplace does not publish the plugin in the public directory.

## Add another plugin

Create `plugins/<plugin-name>/plugin.json` and its `skills/` directory, then append
an entry to `.agents/plugins/marketplace.json`. Source paths resolve from the
repository root, for example `./plugins/<plugin-name>`.

See [OpenAI's plugin packaging documentation](https://developers.openai.com/plugins/build/plugins).
