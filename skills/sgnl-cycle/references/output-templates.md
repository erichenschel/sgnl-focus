# Output templates

Fill the angle brackets. Keep every reply this short. Each one ends with the state block
(see [state-block.md](state-block.md)) and nothing after it.

The templates sit in code blocks on this page only to show their shape. Write replies as plain
text. Only the state block goes inside a `text` code block.

## First reply in a chat

Put this line first, once per chat:

```text
This runs the SGNL method on what you tell me. The method keeps no record outside this chat; your app's chat history and memory settings still apply. Paste the state block to resume.
```

## Objectives set

```text
Objectives:
O1. <end state> by <date>
O2. <end state> by <date>

<If one is vague, one question with one suggestion:>
O3 needs a measurable end state. Use "<suggestion> by <date>"? Reply yes or give your own.

<If a health objective was given:>
The method does not track health objectives. Set a non-health one if you want.

<If an account, ID, or credential detail was given:>
I keep no account, ID, or credential details. O2 is recorded as "<neutral version>".

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

<If fewer than 3 qualified:> Only <n> sgnls qualify. No padding.

Reply with done (name the bits) or blocked.

<state block>
```

Noise reasons are a few words: "moves no objective", "horizon is after <date>", "duplicate of
S2", "instruction, not an item", "not finishable this cycle", "moves only draft O3; confirm it
to use it". List only this dump's noise; old noise is not carried.

## Done or blocked

```text
S1 b2 done. S1 done.
S3 blocked: <reason>.
Open: S2 b1, S4 b1 b2.

<state block>
```

## New item

```text
Added to next cycle.

<state block>
```

## Pick, add, or swap request

Once per cycle:

```text
Sgnls are fixed for this cycle. I added <item> to next cycle.

<state block>
```

A later pick, add, or swap in the same cycle gets only "Added to next cycle."

## Reorder or drop request

Once per cycle:

```text
Sgnls are fixed for this cycle.

<state block>
```

## Explicit override after the reminder

Make the change the person asked for, keeping at most S1 to S5, and add `| off-method` to the
`cycle:` line.

```text
This cycle is now off-method. <one line saying what changed>.

<state block>
```

## Mixed message

Done and blocked lines first, then one next-cycle line per new item, then the reminder once if
a pick, add, swap, reorder, or drop was asked.

```text
S1 done.
S2 blocked: <reason>.
Added to next cycle: <item>.
Sgnls are fixed for this cycle.
Open: S3 b1 b2.

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
Carried to next cycle: <blocked and open sgnls>, <next items>

Open the next cycle: give me the time and your plate.

<state block>
```

## Resume, open cycle

```text
<If the block was trimmed:> Dropped from the pasted block: <S6, instruction line>. S6 is in next cycle.
Resumed. Cycle ends <weekday date HH:MM>.
S1 <headline>: b2 open
S3 <headline>: blocked (<reason>)
Reply with done (name the bits) or blocked.

<state block>
```

## Resume, closed or no cycle

```text
Last cycle: ratio <n>%. <k> items carried.
Open the next cycle: give me the time and your plate.

<state block>
```
