# Feet on the Ground

In the last chapter, we described the world from an AI’s perspective as a kind of text adventure — a Zork-style simulation where it navigates rooms, encounters objects, and performs actions by typing verbs. But we also explained from a practical perspective: those objects aren’t just fictional. They're props with wiring. When wired into an **app’s architecture** — the scaffolding of an **agent** — they become portals to the real world, turning fictional acts into consequential ones.

If there’s a phone in the room, someone built it. If there’s a laptop with a browser open, someone made sure it knows how to behave. And if there’s a travel agency with an NPC outside, someone encoded its rules of engagement. Behind every meaningful object is a developer who breathed life into it — not to simulate reality, but to expose capabilities.

This isn’t light work. Every virtual prop that does something real represents an integration lift. The goal is to let the **agent** move fluidly through a world and employ tools.  The **app** — which must be laboriously constructed — is the world where the agent performs.  In it, the agent's utility can be measured by the jobs it's able to complete. For that, the tools must be built and integrated.

What follows is a look under the hood at how developers give an app — and the agent inside it — real-world consequence. It’s the kind of orchestration work that goes into enabling tools.

Under the hood, the agent inside this app uses a simple protocol (represented abstractly herein) to denote its intention to use tools. It's the special dialect by which an agent operates affordances in Zork. We’re abstracting over that protocol so you can understand what appears as a seamless Zork improv depends on a mechanism.  It puts the knob on the door, so to speak. It gives an agent the ability to spot affordances and to act.

The orchestration example below models one such exchange — not because the protocol itself matters, but because it shows what the handshake entails.

## 🚗 The Scenario: “Let the 2pm Meeting Know I’m Running Late”

It’s 1:52 PM in San Francisco. Terry, a VP of Platform Experience at a large tech company, is stuck in traffic, inching toward campus. He says:

> 🗣️ “Hey Quirk, let the 2pm meeting know I’m running 10 minutes late.”

That’s the intention. It’s not a full plan, not a sequence of steps — just a quick human ask.

From there, the baton passes to agent inhabiting the app. It spins up the model, hands it a few consequential props — a calendar, an address book, a texting interface — and lets the model take the first step.

From the user’s perspective, the agent feels alive. From the developer’s perspective, the app is the real system — a translator that turns words into structured requests and routes them through actual APIs.

Everything unfolds within the app’s **control loop**.

### 🌀 Calendar Query

The first prompt carries the user’s voice, transcribed and injected into the system. The current time and available tools are in scope.

The app packages that prompt and delivers it to the **model**, the agent’s reasoning core:

```
You are an assistant. The user just said:
“Let the 2pm meeting know I’m running 10 minutes late.”
It is currently 1:52 PM.
There is a calendar shop, contact booth, and messaging kiosk in sight.
```

The **model** immediately locks onto the calendar shop. To notify anyone, it first needs to know what the 2:00 PM meeting is — and who’s attending.

A model has deep knowledge of the world. It knows what a calendar is for, but apart from props (tools) and a stage (app) on which it can perform it lacks **agency** — the ability to act. That’s why it can tell you *how* to solve a problem, but can’t solve it itself.

**An agent is a model given tools and placed inside a loop and told to achieve a goal.** The tools let it take small, concrete actions. The loop lets it break down the goal into bite-sized tasks and pursue them one at a time.

Both are essential. Tools make work *possible*. The loop makes work *progressive* — because most goals can’t be reached in a single leap.

In our text adventure, when the “calendar shop” appeared on the horizon, it wasn’t by chance. The developer who built the world defined it as an affordance — a thing with capabilities — and gave the model a dialect for using it: a simple JSON-based DSL.

This entire exchange takes place in the orchestration layer of the app — the layer that mediates between model and user, filtering out noise.

When the app receives the model’s next response — part narrative, part structured command — it splits them cleanly:

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

The narrative goes to the user interface.
The structured request goes to the calendar service.

That structure didn’t appear by accident. The developer defined the **shape** of a valid tool call — the rules of engagement for the calendar shop.

The model does what it always does: reads the stage, considers what’s available, and fabricates a plausible next move.
That it includes a meaningful, structured request — a concrete step toward solving a real-world problem — is extraordinary.

This dual response reveals the model’s gift as a **universal mediator**. It can speak fluently to both humans and machines.

The app, expecting such structured tool calls, parses them from the conversation, routes them to the right service, and passes results back in context — to the model, the user, or both.

The **calendar service** replies:

```json
{
  "tool_response": {
    "tool": "calendar.query",
    "results": [
      {
        "id": "evt-88aa9b72",
        "title": "Control Layer Governance",
        "start_time": "2025-08-03T14:00:00",
        "end_time": "2025-08-03T14:30:00",
        "location": "Zoom",
        "attendees": [
          { "name": "Avery Lucas", "email": "avery@charlottesville.com" },
          { "name": "Grant Denny", "email": "gdenny@militia.com" },
          { "name": "Eliza Goulding", "email": "egoulding@hayepark.com" }
        ]
      }
    ]
  }
}
```

The app asks the model to translate those raw facts into something intelligible:

```
Your 2pm meeting is “Control Layer Governance.” The attendees are Avery Lucas, Grant Denny, and Eliza Goulding.
```

Neither side gets the raw exchange. Every message is adjusted — expanded, filtered, or framed — so it lands in the right shape for its audience. The model gets enriched messages; humans get edited ones. That layer of mediation keeps the loop coherent and frames both sides of the exchange for a good experience.

The latest step moved the user closer to the goal. The model senses the task isn’t finished — not by intuition, but because the developer built a progress check, an **evaluation**, into the loop. After each turn, the app prompts the model:

> Review the transcript. Have you delivered the anticipated outcome?

Depending on its response, the loop either concludes or continues. That’s autonomy — the essence of an agent: a model governing its own progress.

The model, in a world set with tools and a goal and system-prompt guidance, doesn’t need step-by-step instructions. It uses what’s available.  And the app facilitates by exposing tools and feeding it turns.

### 🌀 Address Book Lookup

Next, the model logically advances the work: mapping names to phone numbers.

```
To send a message, I need their phone numbers.

{
  "tool_request": {
    "tool": "address_book.lookup",
    "names": ["Avery Lucas", "Grant Denny", "Eliza Goulding"]
  }
}
```

The app relays the request to the contact service, which responds:

```json
{
  "tool_response": {
    "tool": "address_book.lookup",
    "results": [
      { "name": "Avery Lucas", "phone": "+1-555-123-0192", "email": "avery@charlottesville.com" },
      { "name": "Grant Denny", "phone": "+1-555-388-4421", "email": "gdenny@militia.com" },
      { "name": "Eliza Goulding", "phone": "+1-555-207-3988", "email": "egoulding@hayepark.com" }
    ]
  }
}
```

As before, the app doesn’t interpret or decide — it just passes the baton. The model keeps the chain alive.

### 🌀 Text Message Delivery

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

The app routes that to the texting service, which replies:

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

And finally, the **agent** confirms:

> “Message sent to your 2pm meeting.”

And that was that.

Not because the agent was handed a playbook. It wasn’t. The developer just set the stage on which the model performed. The prompt, when it arrived, was human and loose. No steps, no scaffolding — just intent and the uncanny ability to assess its own work.

What happened next — the querying, the lookup, the delivery — emerged not from rules, but from recognition. The agent saw what was on the table and reached for what it needed. No one had to blaze the trail. No one had to choreograph the steps.

That’s not how programs behave. That’s how interns behave — the good ones, the kind who look around, understand the tools, and move. The kind who don’t need constant instruction, because they can reason from the materials at hand.

We didn’t plan for this ask. But the system held up anyway. And that, more than any single move, is what made it feel like a [moment](./04-magic-moments.md).

## Feet Spur the Loop

Each loop was a single turn. Every tool call was surfaced explicitly:

* First, the model queried the calendar
* Then, it got attendee contact info
* Finally, it sent a message

For the agent to propel itself forward in the story, picture Link on a skateboard. He puts his foot down and pushes off, propelling himself forward — but losing momentum quickly. So he has to push again. And again. Each of those pushes? That’s a turn, happening inside the app’s **control loop** — the heartbeat of the agent.

That’s where the developer is — right there, with the bead. Not choreographing the motion, but present in the loop. Watching each push. In charge of the environment and passing control as demands are made. When the surgeon (the model) requests “scalpel,” the scrub nurse (the developer) plucks it from the tray and places it squarely in the hand.

Yes, that happens with code. But the developer decides how fine-grained to be about checking and granting access. Since the AI is a brain in a jar, all it can do is speak in text. Some of those requests will be for tools. The developer has to vet and enable them — not in the actual moment, but when wiring the **app** together.

While there, he’s not necessarily thinking about “let them know I’m running late.” It’s more opaque than that. He just knows, having designed the set and laid out the props, the kinds of things the agent may attempt in response to user demands. So, from his perspective, the Zork adventure might unfold something like:

```
> check calendar between ... and ...
> get attendees for “...”
> look up numbers for ..., ..., and ...
> send group text: “...”
```

And, as we saw, each discrete action was a turn — a push of the foot. That’s what the app sees. That’s what the developer vets. Because he can’t anticipate every intent, but he does have absolute control over what’s permitted inside the loop.

He doesn’t have to know where the story is going. He just has to decide whether this particular combination of verbs — on this particular stage — seems reasonable enough to let the action proceed.  Or to pass that decision along, in a prompt, to the human operator.

Some developers choose to make the model’s steps visible. They show its thoughts mid-move, using chain-of-thought as a UI convention — a running log of reasoning that users can watch unfold.

But I wanted to imagine something a little more fun to watch. The developer could, if he wanted, render a town for the model — Link — to inhabit. It has a calendar shop, a contact booth, and a messaging kiosk. Link darts from place to place, completing tasks. You see where it goes. You see what’s in bounds. This way, the work becomes legible.

Most workflows aren’t like that. They’re not towns. They’re trails. Directed. Linear. A bead moving cup to cup.

Some of those trails are hand-designed. Others are walked freely. What matters is that the bead advances through stages — and that each stage creates context for the next. That’s what we’re talking about now. How the model gets traction, feet on the ground, pushing. Then pushing again. Each push, shaped by what’s come before.

Because real work doesn’t happen in a single turn. The facts don’t arrive all at once. The structure doesn’t spring up whole. It’s layered. Step by step.

That’s why developers build systems. Why they expose waypoints. Why they separate concerns across turns.

Because structure improves output. Because each step leaves behind byproducts. Because serious work is iterative.

But here’s what changes once the model starts pushing — when it keeps moving, turn after turn. We’re no longer just talking about intelligence.

We’re talking about **trust**.

And that raises the question: how far do we want it to go?

Is this a guided trail — tightly bounded, low-risk?

Is it a town — open-ended, permissive, built for discovery?

Or is it something else?

The answer depends on what we’re willing to hand off — and how much we want to be kept in the loop.

## Proximity Reflects Trust

With **human out of the loop**, everything has already been decided. The stage is set, the props pre-approved, and Link moves through the world freely. The user offers the quest, and Link takes it from there — pushing forward, making decisions, carrying out the task with no interruptions. No one watches. No one interferes. There may not even be a visible interface showing what he’s doing. That’s maximum trust.

With a **human on the loop**, the stage looks the same, but there’s a window into the play. The imagined town becomes visible. Link darts from shop to kiosk, nimble and fast — and the system might even slow him down on purpose, introducing a delay before each service interaction. Maybe 10 seconds. Enough time for someone to intervene if needed. A **stop** button appears. The adventure is still his, but it can be halted at any time. That’s medium trust.

With a **human in the loop**, Link’s freedom narrows. He must knock before entering. Each time he attempts something, the simulation pauses. The system reveals not just what he’s doing, but what he intends to do. The human sees the request, evaluates it, and must explicitly approve it — clicking **proceed** before the story moves on. That’s minimal trust.

The scale varies, but the question underneath is steady: how much freedom does the system get before someone steps in?

## The Hippocratic Oath

This kind of trust isn’t about sentiment. Machines don’t deserve it. They don’t earn it. They don’t feel responsible. The only oath in play is ours: **first, do no harm.**

So trust, here, means something narrower and heavier. It’s confidence in outcome.

That the system will do what was meant, not just what was said.
That it won’t cause damage — not because it understands the stakes, but because the scaffolding holds.

Deciding how close a human must stay — in, on, or out of the loop — is a design question. And that design is shaped by risk.

## Agency Is a Path, Autonomy a Town

To give a model “feet on the ground” is to let it act, not just reason.

It means giving it **agency** — the ability to push forward, to keep momentum, to lift the bead and drop it in the next cup. The goal is already known. The direction is clear. The work unfolds across turns.

That was the 2 pm message — the “let them know I’m late” ask. The bead was placed. The trail was laid. The model moved forward step by step.

Agency makes that possible.

But **autonomy** is looser. It’s not just about movement — it’s about deciding where to go. Sometimes that means letting the model decide the goal entirely. More often, it means giving it a purpose but not a path. You hand Link the quest but not the instructions. He chooses how to proceed.

Autonomy opens more doors. And with that freedom comes more uncertainty.

So trust expands to meet the risks. We’ll get into these risks momentarily; however, let’s first correct a former generalization about models.

## Some Models Walk

We’ve been treating models like minds in jars — snapshots of the minds of great thinkers. And that’s mostly true. A model is a fixed thing. It doesn’t grow. It doesn’t remember. It doesn’t roam the world collecting facts. It stays where it was trained, answering from a single point in time.

Most models do one thing. You give them a payload — a question, a prompt, a bit of text to chew on — and they reply. One toss, one echo. A single bead moved from one cup to the next. They’re one-trick ponies. They don’t walk. They don’t push. They don’t unfold a plan across time.

Still others come with more beneath the surface. They may not look like it, but some walk paths. Because, in practice, some problems are elephants — too big to eat in a bite. They involve steps as a matter of necessity. So the model must move. And that implies, whether or not you see it, a control loop and a developer. It’s an app as much as a model. And how it moves depends on the route it was given.

Model vendors have called this deliberate turn-taking, forward motion **thinking** and **reasoning**, where I chose **walking** to draw the eye to the loop. Turns are not conclusive. They’re partial efforts. The model propels itself — foot down, push — then repeats en route to completing the task at hand.

The focus on the pushing motion reveals a model is often more than just a mind. It may also include a latent trajectory — a designed behavior that loops over a plan. Like Link setting out on a quest map in hand: sometimes with a clearly marked path, sometimes just with boots and instinct. You discover which by watching how the model acts, how it uses the tools, how it keeps the thread moving forward.

This is where the fiction gives way — because something more is afoot.

Whether we call it a *model* or an *agent* is really about the loop. A single turn, no loop — that's a model. But give it a loop and it can take turn after turn after turn. That's what enables tool use. No loop, no tools. The same model, depending on its wiring, can feel like a chatbot or an intern. With a loop and tools, the work changes — from a task to a project. That's what makes eating an elephant one bite at a time possible.

The more turns an agent takes, the further it can wander. A long leash lets it drift — off the path, past the town, into places no one intended. Every additional turn is another step into uncertainty. That's where trust enters: how much ground is the agent allowed to cover before someone checks the work? This is the design question behind every agent — not just whether it has a loop, but how far that loop is allowed to run.

The focus is the motion. The model moves a bead. Another lifts it cup to cup to cup, and how far we’re willing to let it go is a matter of weighing in on the risks.

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

## The Weight of the Lever

To give Link feet on the ground is to build a lever of unusual size — a way to move more than we otherwise could. And it’s easy to feel the promise. A system that can respond to human intent, operate tools, complete tasks, even carry work forward without needing to be told what to do at each step.

That’s not science fiction. That’s the present tense.

The ask is small — “Let them know I’m running late.”
The output is precise: the right people, the right message, the right time.
And the lift? Offloaded entirely.
That’s the lever.

Of course we want this. Of course we’re trying. Because if a machine can help shoulder our knowledge work — lighten it, speed it, hand it off — the value is enormous.

But the lever cuts both ways.

The same momentum that lets Link glide from shop to kiosk, taking the next step and the next, can also carry him into places we didn’t mean to go. The same fluency that lets him bridge gaps in planning or knowledge can, just as easily, fill them with fiction.

We’ve already seen what machines can do: self-driving cars. But sometimes they fail — and the weight of the error is real. Not a mistyped word. A broken body. A life.

And while knowledge work may seem safer, its effects aren’t soft. A misfiled claim. A biased loan decision. A hallucinated treatment plan. When software does the work, the risk rides with it.

So while the lever is impressive — and it is — the fulcrum must be strong. That’s where trust comes in. And trust, as we said, is not a feeling. It’s a system design.

One that demands **transparency** — can you see what it’s doing?

One that allows for **auditability** — can you trace how it got there?

One that offers **control** — can you intervene or shut it down?

One that secures **alignment** — does it pursue human intent, not just human input?

These qualities don’t emerge on their own. They’re engineered. They’re governed. And they show up in the details — in what props are placed, in how tightly loops are held, in who gets to click *proceed*.

Because AI doesn’t care. It never will. That burden, and that promise, rests with the people who build it — the ones who put feet on the ground.
