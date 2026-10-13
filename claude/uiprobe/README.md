# Uiprobe plugin for Claude Code

[Uiprobe](https://www.uiprobe.io) automatically detects spacing, typography, color, and layout differences between your Figma design and live website. This plugin connects Claude Code to Uiprobe, so Claude can compare a page with its design and fix the differences in your code.

## Install

```
/plugin marketplace add uiprobe/claude-plugin
/plugin install uiprobe@uiprobe
```

To sign in, run `/mcp`, choose `uiprobe` and sign in with Figma in the browser window that opens.

If you've already added Uiprobe as a connector in claude.ai, Claude Code may show its tools twice. Keep one of the two.

## What it adds

The plugin adds the Uiprobe MCP server at `https://app.uiprobe.io/mcp` and four skills. With the MCP server, Claude can:

- **Run a probe** from a Figma frame URL and a webpage URL, and get every difference in text, fonts, colors, sizes, spacing and layout.
- **Rerun a probe** after changing the page to see what's left.
- **List your probes** and read their findings.
- **Look at a finding** as crops of the design and the page.
- **Dismiss findings** you say are intentional, after asking you, so nobody on the probe sees them again, and restore them whenever you want.

The skills turn those tools into workflows. Ask for one in your own words, or call it by name:

- **`uiprobe:match-design`**: make a page match its Figma design. Claude probes the page, fixes the findings in your code, and reruns the probe until the page matches.
- **`uiprobe:design-qa-summary`**: summarise a probe's findings into something you can paste for a designer, developer or PM, with images of a few of them. It only reads, and never starts a run.
- **`uiprobe:triage-findings`**: go through a probe's findings with Claude, decide what to fix and what is intentional, and dismiss the intentional ones after you confirm.
- **`uiprobe:pr-design-check`**: before a pull request, probe the pages your branch changed against their Figma frames, after you agree to the number of runs, and get a note for the pull request description. It doesn't change code.

The plugin contains no code that runs on your machine.

## What it sends

- **To Uiprobe:** the Figma frame URL and webpage URL of each probe you run, and the ids of probes and findings you ask about. Uiprobe reads the Figma frame through Figma's API with your Figma sign-in, and captures the webpage from its own servers, so the page must be publicly reachable. For a page on localhost, Claude can open a temporary tunnel to it.
- **Sign-in:** you sign in with Figma through Uiprobe's sign-in page. Claude Code keeps the resulting token.

Uiprobe's [privacy policy](https://www.uiprobe.io/legal/privacy) and [terms](https://www.uiprobe.io/legal/terms) apply.

## Updates

Run `/plugin marketplace update uiprobe` to get the latest version.

## Support

This repository is a published copy of the plugin and doesn't accept issues or pull requests. For help, go to https://www.uiprobe.io/help/support.

## License

MIT, see [LICENSE](https://github.com/uiprobe/claude-plugin/blob/main/LICENSE).
