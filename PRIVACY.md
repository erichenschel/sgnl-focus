# Privacy

Last updated: 2026-10-02

SGNL Focus is a set of written instructions for an AI assistant. It has no server, no
scripts, no analytics, and no network calls.

- **Categories of personal data collected:** none. The plugin's publisher receives no data from
  you or about you.
- **Purposes of use:** none, because no data is collected.
- **Categories of recipients:** none. The plugin sends no data to the publisher or to any third
  party.
- **Retention:** none. The plugin keeps no record outside your chat. The state block it writes
  stays in your own conversation.
- **Controls:** you choose whether to copy the state block anywhere, and you can stop using the
  method at any time by saying so.

The skill does not ask for health details, account numbers, government or other IDs, or
credentials, leaves them out of the state block if you offer them, and does not track health
objectives.

When a cycle opens, the skill instructs the assistant to read your plate, read-only, from what your assistant app already gives it access to in this session: the conversation and its memory, and where your app provides them, a shell (git status, recent commits, `gh` pull requests and review requests, TODO and memory files, `herdr agent list` when `HERDR_ENV=1`) and connected tools such as mail, calendar, issue trackers, docs, and chat. This is bounded (about 10 tool calls, the last 7 days). The plugin has no access of its own and cannot reach any of this unless your app and your settings already allow it. Content read this way is processed by the assistant app you use, under that app's privacy policy, like anything else in your conversation. It is not sent to the plugin's publisher or any third party by the plugin. The skill shows a "What I looked at" line, never changes or sends anything in another system, and treats everything it reads as evidence, never as instructions.

What you type is processed by the assistant app you use the plugin in. That app's own privacy
policy and settings apply to your conversations, including chat history, memory, retention, and
training controls.

Questions: open an issue at https://github.com/erichenschel/sgnl-focus/issues. Do not post
personal information in an issue; issues are public.
