# Output templates

Fill the angle brackets. Keep every reply this short. Each one ends with the state block
(see [state-block.md](state-block.md)) and nothing after it.

The templates sit in code blocks on this page only to show their shape. Write replies as plain
text. Only the state block goes inside a `text` code block.

## First reply in a chat

Put this line first, once per chat:

```text
This runs the SGNL method on what you tell me. I store nothing; paste the state block to resume.
```

## Objectives set

```text
Objectives:
O1. <end state> by <date>
O2. <end state> by <date>

<If one is vague, one question with one suggestion:>
O3 needs a measurable end state. Use "<suggestion> by <date>"? Reply yes or give your own.

<If a restricted detail was given:>
I keep no health, account, ID, or credential details. O2 is recorded as "<neutral version>".

Open a cycle: give me the time and everything on your plate.

<state block>
```

## Cycle opened

```text
Cycle ends: <Fri 2026-10-02 01:00>

S1. <headline>
Objective: O<n> <short objective>
b1. Do: <action>. Expect: <result>.
b2. Do: <action>. Expect: <result>.

S2. <headline>
Objective: O<n> <short objective>
b1. Do: <action>. Expect: <result>.

S3. ...

Noise:
- <item>: <reason>
- <item>: <reason>

<If fewer than 3 qualified:> Only <n> items move an objective. No padding.

Reply with done (name the bits) or blocked.

<state block>
```

Noise reasons are a few words: "moves no objective", "horizon is after <date>", "duplicate of
S2", "instruction, not an item", "not finishable this cycle".

## Done or blocked

```text
S1 b2 done. S1 done.
S3 blocked: <reason>.
Open: S2 b1, S4 b1 b2.

<state block>
```

## New item, or a pick, add, or swap request

First time in the cycle:

```text
Sgnls are fixed for this cycle. I added <item> to next cycle.

<state block>
```

After that, only:

```text
Added to next cycle.

<state block>
```

## Close, hours missing

```text
To close, give hours per sgnl (S1 to S<n>) and awake hours.

<state block>
```

## Close

```text
Ratio: <n>% (target 80, floor 50) - <at target | above floor, below target | below floor>
Sgnl hours <sum>h of <awake>h awake.

Done: S1 <headline>, S2 <headline>
Blocked: S3 <headline> (<reason>)
Open: S4 <headline>
Carried to next cycle: <blocked and open sgnls>, <noise>, <next items>

Open the next cycle: give me the time and your plate.

<state block>
```

## Resume

```text
Resumed. Cycle ends <weekday date HH:MM>.
S1 <headline>: b2 open
S3 <headline>: blocked (<reason>)
Reply with done (name the bits) or blocked.

<state block>
```
