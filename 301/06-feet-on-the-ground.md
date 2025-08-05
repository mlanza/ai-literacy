# Feet on the Ground

In the last chapter, we described the LLM’s world as a kind of text adventure — a Zork-style simulation where the AI navigates rooms, encounters objects, and performs actions by typing verbs. But we also explained from a practical perspective: those objects aren’t just fictional. They're props with wiring. When wired into the app’s glue code (ahem, architecture), they become portals to the real world — turning fictional acts into consequential ones.

If there’s a phone in the room, someone built it. If there’s a laptop with a browser open, someone made sure it knows how to behave. And if there’s a travel agency with an NPC outside, someone encoded its rules of engagement. Behind every meaningful object is a developer who breathed life into it — not to simulate reality, but to expose capabilities.

This isn’t light work. Every virtual prop that does something real represents an integration lift. That’s why we aim to reuse them, wrap them, and distribute them in ways that make them easy to plug in — often using something like MCP. The goal is to let the model move fluidly through a world and employ tools, and hopefully not have to implement them all ourselves.

So let’s see that in action. Not as a concept, but as a moment.

## 🚗 The Scenario: “Let the 2pm Meeting Know I’m Running Late”

It’s 1:52 PM. The executive is stuck in traffic. He says:

> “Hey Assist, let the 2pm meeting know I’m running 10 minutes late.”

That’s the intention. It’s not a full plan, not a sequence of steps — just a quick human ask.

From there, the baton passes to the app. It spins up the model, hands it a few consequential props — a calendar, an address book, a texting interface — and lets the model take the first step.

### 🌀 Loop 1 — Calendar Query

The first prompt includes the user’s request, transcribed from voice and sent into the app. The current time and available tools are in scope.

The **app** delivers this prompt to the model:

```
You are an assistant. The user just said:
“Let the 2pm meeting know I’m running 10 minutes late.”
It is currently 1:52 PM.
There is a calendar shop, contact booth, and messaging kiosk in sight.
```

The **model** anchors immediately on the calendar. To notify anyone, it first needs to understand what the 2pm meeting is — and who’s attending.

```
To notify the attendees, I need to check the user’s calendar for the 2:00 PM meeting.

{
  "tool_request": {
    "tool": "calendar.query",
    "start_time": "2025-08-03T14:00:00",
    "end_time": "2025-08-03T14:30:00"
  }
}
```

This response has two layers: the natural-language explanation for the human and the structured tool call for the system. That duality is exactly what makes the LLM a **universal mediator** — one foot in each world, translating human intention into machine action.

The developer extracts the structured request and relays it to the **MCP calendar service**, which responds:

```json
{
  "tool_response": {
    "tool": "calendar.query",
    "results": [
      {
        "id": "evt-88aa9b72",
        "title": "Project Sync",
        "start_time": "2025-08-03T14:00:00",
        "end_time": "2025-08-03T14:30:00",
        "location": "Zoom",
        "attendees": [
          { "name": "Ava Bennett", "email": "ava@example.com" },
          { "name": "Marcus Liu", "email": "marcus@example.com" },
          { "name": "Leo Vargas", "email": "leo@example.com" }
        ]
      }
    ]
  }
}
```

The app injects that fact into the next prompt:

```
The 2pm meeting is titled “Project Sync”. The attendees are Ava Bennett, Marcus Liu, and Leo Vargas.
```

No instructions needed. The model already knows what tools are available and how to use them. That’s baked into the system prompt. The app just supplies new facts — like a user feeding context to ChatGPT — trusting the model to keep the thread going.

### 🌀 Loop 2 — Address Book Lookup

The model immediately advances with the next logical step: resolve names into numbers.

```
To send a message, I need their mobile numbers.

{
  "tool_request": {
    "tool": "address_book.lookup",
    "names": ["Ava Bennett", "Marcus Liu", "Leo Vargas"]
  }
}
```

The app relays the request to the MCP contact service, which replies:

```json
{
  "tool_response": {
    "tool": "address_book.lookup",
    "results": [
      {
        "name": "Ava Bennett",
        "phone": "+1-555-123-0192",
        "email": "ava@example.com"
      },
      {
        "name": "Marcus Liu",
        "phone": "+1-555-388-4421",
        "email": "marcus@example.com"
      },
      {
        "name": "Leo Vargas",
        "phone": "+1-555-207-3988",
        "email": "leo@example.com"
      }
    ]
  }
}
```

As before, we don’t extract or interpret — just pass it along. The model continues the chain.

### 🌀 Loop 3 — Text Message Delivery

With everything in hand, the model responds:

```
Notifying the team.

{
  "tool_request": {
    "tool": "text_message",
    "to": [
      "+1-555-123-0192",
      "+1-555-388-4421",
      "+1-555-207-3988"
    ],
    "message": "Hey everyone — running about 10 minutes late. Please feel free to get started without me."
  }
}
```

The app routes that to the MCP texting service, which replies:

```json
{
  "tool_response": {
    "tool": "text_message",
    "status": "sent",
    "timestamp": "2025-08-03T13:53:12Z",
    "message_id": "msg-0093442"
  }
}
```

And finally, the app confirms:

> “Message sent to your 2pm meeting.”

## Feet Spur the Loop

Each loop was a single LLM turn. Every tool call was surfaced explicitly:

* First, the model queried the calendar
* Then, it got attendee contact info
* Finally, it sent a message

All without a prewritten playbook. The model knew what tools were on the desk and how to use them. Likewise, the developer knew because he is the one who set the stage on which the model would perform.

However, for the model to propel itself forward in the story, I like to think of it like Link (the LLM) on a skateboard. He puts his foot down and pushes off, propelling himself forward — but losing momentum quickly. So he has to push again. And again. Each of those pushes? That's a model turn, happening inside the app's control loop.

That's where the developer is, right there — with the bead. Not choreographing the motion, but present in the loop. Watching each push. In charge of the environment and passing control as demands are made.  When the surgeon (the model) requests "scalpel," the scrub nurse (the developer) plucks it from the tray and places it squarely in the hand.

Yes, that happened with code, but the developer decides how fine grained to be about checking and granting access.  Since the AI is a brain in a jar, all it can do is speak in text.  Some of those requests will be for tools.  The developer has to vet and enable them, not in the actual moment, but when he's wiring the app together.

While means he's not necessarily thinking about the original “let them know I’m running late.”  It's a little more opaque than that.  He just knows having designed the set and laying out the props the kinds of things the AI will attempt in response to the user's demands.  So, from his perspective, the Zork adventure might unfold something like:

```
> check calendar between ... and ...
> get attendees for “...”
> look up numbers for ..., ..., and ...
> send group text: “...”
```

And, as we saw, each discrete action was a turn. A push of the foot. That’s what the app sees. That’s what the developer vets, because he can't necessarily anticipate the intent, but he does have final say over how to handle what is permitted inside the control loop.

He doesn’t have to know where the story is going. He just has to decide whether this particular combination of verbs — on this particular stage — seems reasonable enough to let the action proceed.

Some developers choose to make the model’s steps visible. They show its thoughts mid-move, using chain-of-thought as a UI convention — a running log of reasoning that users can watch unfold.

But I wanted to imagine something a little more fun to watch.  The developer could, if he wanted, render a town for the model — Link — to inhabit.  It has a calendar shop, a contact booth, and a messaging kiosk. Link darts from place to place, completing tasks. You see where it goes. You see what’s in bounds. This way, the work becomes legible.

Most workflows aren’t like that. They’re not towns. They’re trails. Directed. Linear. A bead moving cup to cup.

Some of those trails are hand-designed. Others are walked freely. What matters is that the bead advances through stages — and that each stage creates context for the next.

That’s the pattern behind multistep features like ChatGPT’s “deep research.” Not a single move, but a control loop. That's what were talking about now.  How the model gets traction, feet to on the ground, pushing. Then pushing again. Each push, shaped by what’s come before.

Because real work doesn’t happen in a single turn. The facts don’t arrive all at once. The structure doesn’t spring up whole. It’s layered. Step by step.

That’s why developers build systems. Why they expose waypoints. Why they separate concerns across turns.

Because structure improves output.

Because each step leaves behind byproducts.

Because serious work is iterative.

But here’s what changes once the model starts pushing — when it keeps moving, turn after turn. We’re no longer just talking about intelligence.

We’re talking about **trust**.

And that raises the question: how far do we want it to go?

Is this a guided trail — tightly bounded, low-risk?

Is it a town — open-ended, permissive, built for discovery?

Or is it something else?

The answer depends on what we’re willing to hand off — and how closely we’re willing to stay in the loop.

## Human Proximity Reflects Trust

With **human out of the loop**, everything has already been decided. The stage is set, the props pre-approved, and Link moves through the world freely. The user offers the quest, and Link takes it from there — pushing forward, making decisions, carrying out the task with no interruptions. No one watches. No one interferes. There may not even be a visible interface showing what he’s doing. That’s maximum trust.

With a **human on the loop**, the stage looks the same, but there’s a window into the play. The imagined town becomes visible. Link darts from shop to kiosk, nimble and fast — and the system might even slow him down on purpose, introducing a delay before each service interaction. Maybe 10 seconds. Enough time for someone to intervene if needed. A **stop** button appears. The adventure is still his, but it can be halted at any time. That’s medium trust.

With a **human in the loop**, Link’s freedom narrows. He must knock before entering. Each time he attempts something, the simulation pauses. The system reveals not just what he's doing, but what he intends to do. The human sees the request, evaluates it, and must explicitly approve it — clicking **proceed** before the story moves on. That’s minimal trust.

The scale varies, but the question underneath is steady: how much freedom does the system get before someone steps in?

## The Hippocratic Oath

This kind of trust isn’t about sentiment. Machines don’t deserve it. They don’t earn it. They don’t feel responsible. The only oath in play is ours: **first, do no harm.**

So trust, here, means something narrower and heavier. It’s confidence in outcome.

That the system will do what was meant, not just what was said.

That it won’t cause damage — not because it understands the stakes, but because the scaffolding holds.

Deciding how close a human must stay — in, on, or out of the loop — is a design question. And that design is shaped by risk.

## Agency vs. Autonomy

To give a model “feet on the ground” is to let it act, not just reason.

It means giving it **agency** — the ability to push forward, to keep momentum, to lift the bead and drop it in the next cup. The goal is already known. The direction is clear. The work unfolds across turns.

That was the 2pm message — the “let them know I’m late” ask. The bead was placed. The trail was laid. The model moved forward step by step.

Agency makes that possible.

But **autonomy** is looser. It’s not just about movement — it’s about deciding where to go. Sometimes that means letting the model decide the goal entirely. More often, it means giving it a purpose but not a path. You hand Link the quest but not the instructions. He chooses how to proceed.

Autonomy opens more doors. And with that freedom comes more uncertainty.

So trust expands to meet the risks.

## Risk Categories

### Mistakes

Language models are predictive machines. They don’t reason like people. They don’t understand. So they guess — and sometimes they guess wrong. Small errors might just be cosmetic. Larger ones can do real harm. They might misstate facts, mislabel diagnoses, or fabricate something that was never true.

And they sound confident while doing it.

So the first question is simple:
*Can this be trusted to behave as expected — and will anyone notice when it doesn’t?*

### Misalignment

Not every system serves your goals. Some optimize for attention. Some quietly serve the priorities of whoever built them. They follow instructions, yes — but they might pursue outcomes you didn’t ask for, or don’t want.

So another question emerges:
*Does this system behave in ways that reflect human values — and whose values does it follow?*

As autonomy increases, so does this risk. A helpful agent is one thing. An autonomous one pursuing the wrong objective is something else entirely.

### Unintended Consequences

Sometimes the damage doesn’t come from one wrong answer. It builds. A small flaw compounds. A small nudge shifts the path. A harmless tool, used at scale, drives outcomes no one intended. Maybe it reinforces bias. Maybe it deepens polarization. Maybe it makes the wrong call and acts on it, fast.

So the final question is:
*Can we see where this might lead — and stop it if it goes too far?*

Got it. You’re right — that last section of the original text introduced four clear risk-mitigation strategies: **transparency, auditability, control, and alignment**. That framework deserves to stay visible in the outro, especially since it grounds the lofty language in practical design.

## The Weight of the Lever

To give Link feet on the ground is to build a lever of unusual size—a way to move more than we otherwise could. And it’s easy to feel the promise. A system that can respond to human intent, operate tools, complete tasks, even carry work forward without needing to be told what to do at each step.

That’s not science fiction. That’s the present tense.

The ask is small—“Let them know I’m running late.” The output is precise: the right people, the right message, the right time. And the lift? Offloaded entirely. That’s the lever.

Of course we want this. Of course we’re trying. Because if a machine can help shoulder our knowledge work—lighten it, speed it, hand it off—the value is enormous.

But the lever cuts both ways.

The same momentum that lets Link glide from shop to kiosk, taking the next step and the next, can also carry him into places we didn’t mean to go. The same fluency that lets him bridge gaps in planning or knowledge can, just as easily, fill them with fiction.

We’ve already seen what machines can do: self-driving cars. But sometimes they fail—and the weight of the error is real. Not a mistyped word. A broken body. A life.

And while knowledge work may seem safer, its effects aren’t soft. A misfiled claim. A biased loan decision. A hallucinated treatment plan. When software does the work, the risk rides with it.

So while the lever is impressive—and it is—the fulcrum must be strong. That’s where trust comes in. And trust, as we said, is not a feeling. It’s a system design.

One that demands **transparency**—can you see what it’s doing?

One that allows for **auditability**—can you trace how it got there?

One that offers **control**—can you intervene or shut it down?

One that secures **alignment**—does it pursue human intent, not just human input?

These qualities don’t emerge on their own. They’re engineered. They’re governed. And they show up in the details—in what props are placed, in how tightly loops are held, in who gets to click *proceed*.

Because AI doesn’t care. It never will. That burden, and that promise, rests with the people who build it—the ones who put feet on the ground.
