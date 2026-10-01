# SGNL

![SGNL icon](assets/icon.png)

SGNL is a skills-only plugin with one skill, `sgnl-cycle`. It runs the SGNL method inside one
conversation. It is a method you run on yourself: the assistant works only from what you tell it.
It cannot see your calendar, inbox, code, or files.

## What it does

1. **Objectives, once.** You set 1 to 3 objectives. Each one gets a date and a measurable end
   state. A vague objective gets one follow-up question.
2. **Open a cycle.** You give the time and an unsorted dump of everything on your plate. The skill
   scores each item against your objectives and returns 3 to 5 sgnls, the items that move an
   objective inside its horizon. Each sgnl has 1 to 5 bits (do, expect). Everything else is noise,
   listed once with a reason. The cycle ends 18 hours after it opens.
3. **During the cycle.** You report done (naming bits) or blocked. New items wait for the next
   cycle. The sgnls do not change mid-cycle.
4. **Close.** You give hours per sgnl and awake hours. The skill returns a ratio (sgnl hours over
   awake hours; target 80, floor 50), a recap, and carries blocked sgnls and noise forward.

Every reply ends with a short state block. Paste it into a new chat to resume.

## Data

The plugin has no server, no scripts, no hooks, and no MCP servers. It stores nothing and sends
nothing anywhere. It is a set of written instructions. The only record of your cycle is the state
block in your own conversation. The skill does not ask for health details, account numbers, IDs,
or credentials, and it leaves them out of the state block if you offer them. Your assistant
platform's own privacy policy covers your conversation. See [PRIVACY.md](PRIVACY.md).

## Install

### Claude Code

```bash
claude plugin marketplace add erichenschel/sgnl-plugin
claude plugin install sgnl@sgnl-plugin
```

### Claude apps (web and desktop)

1. Zip this folder: `zip -r sgnl.zip . -x '.git/*' 'evals/results/*'`
2. In Claude, open Customize > Plugins > Upload plugin and choose `sgnl.zip`.

Plugins in the Claude apps need a paid plan.

### ChatGPT desktop app (local testing)

1. Copy this folder to `~/plugins/sgnl`.
2. Create `~/.agents/plugins/marketplace.json`:

```json
{
  "name": "local-sgnl",
  "plugins": [
    {
      "name": "sgnl",
      "source": { "source": "local", "path": "./plugins/sgnl" },
      "policy": { "installation": "AVAILABLE", "authentication": "ON_INSTALL" },
      "category": "Productivity"
    }
  ]
}
```

3. Restart the ChatGPT desktop app, open the Plugins Directory, choose the `local-sgnl` source,
   install SGNL, and start a new chat.

## Starter prompts

- Set my objectives. I will say what I want true and by when. Make each one measurable.
- Open an 18-hour cycle. Here is everything on my plate, unsorted. Give me my sgnls and bits.
- Close this cycle. Done: the first two sgnls. Blocked: the third. Give me the recap and ratio.

## Files

- `skills/sgnl-cycle/SKILL.md`: the method.
- `skills/sgnl-cycle/references/`: the state block format, reply templates, and a worked example.
- `evals/`: test cases for `claude plugin eval`.

## Support

Open an issue at https://github.com/erichenschel/sgnl-plugin/issues. See [SUPPORT.md](SUPPORT.md).

## License

MIT. See [LICENSE](LICENSE). Use is subject to [TERMS.md](TERMS.md).
