# Feet on the Ground

In the last chapter, we described the world from an AI’s perspective as a kind of text adventure — a Zork-style simulation where it navigates rooms, encounters objects, and performs actions by typing verbs. But we also explained from a practical perspective: those objects aren’t just fictional. They're props with wiring. When wired into an **app’s architecture** — the scaffolding of an **agent** — they become portals to the real world, turning fictional acts into consequential ones.

If there’s a phone in the room, someone built it. If there’s a laptop with a browser open, someone made sure it knows how to behave. And if there’s a travel agency with an NPC outside, someone encoded its rules of engagement. Behind every meaningful object is a developer who breathed life into it — not to simulate reality, but to expose capabilities.

This isn’t light work. Every virtual prop that does something real represents an integration lift. The goal is to let the **agent** move fluidly through a world and employ tools.  The **app** — which must be laboriously constructed — is the world where the agent performs.  In it, the agent's utility can be measured by the jobs it's able to complete. For that, the tools must be built and integrated.

What follows is a look under the hood at how developers give an app — and the agent inside it — real-world consequence. It’s the kind of orchestration work that goes into enabling tools.

Under the hood, the agent inside this app uses a simple protocol (represented abstractly herein) to denote its intention to use tools. Think of it as the dialect by which the agent operates affordances in Zork. We’re abstracting over that protocol so you can understand what appears as a seamless Zork improv depends on a mechanism.  It puts the knob on the door, so to speak. It gives an agent the ability to spot affordances and to act.

The orchestration example below models one such exchange — not because the protocol itself matters, but because it shows what the handshake entails.

## 🚗 The Scenario: “Let the 2pm Meeting Know I’m Running Late”

It’s 1:52 PM in San Francisco. Terry, a VP of Platform Experience at a large tech company, is stuck in traffic, inching toward campus. He says:

> 🗣️ “Hey Quirk, let the 2pm meeting know I’m running 10 minutes late.”

That’s the intention. It’s not a full plan, not a sequence of steps — just a quick human ask.

From there, the baton passes to agent inhabiting the app. It spins up the model, hands it a few consequential props — a calendar, an address book, a texting interface — and lets the model take the first step.

From the user’s perspective, the agent feels alive. From the developer’s perspective, the app is the real system — a translator that turns words into structured requests and routes them through actual APIs.

Everything unfolds within the app’s control loop.

> ⛩️ The **loop** is the crucial foundation for agency. It's what makes tool use possible.

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

A model has deep knowledge of the world. It knows what a calendar is for, but apart from props (tools) and a stage (app) on which it can perform it lacks **agency** — the ability to act. That’s why it can tell you *how* to solve a problem, but can’t solve it itself.  But when you drop a model into a loop and give it tools and goal, that's a recipe for magic.

> ⛩️ An **agent** is a model placed inside a loop and handed tools and a goal.

Tools permit the model to take small, concrete actions. The loop lets it break the goal into bite-sized tasks and pursue them one at a time.

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

This dual response reveals the model’s gift as a **universal mediator**, a true-to-life C-3P0. It can speak fluently to both humans and machines.

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

The latest step moved the user closer to the goal. The model senses the task isn’t finished — not by intuition, but because the developer built a progress check, an **evaluation**, into the loop. This is essential for tracking the goal. After each turn, the app prompts the model:

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

We didn’t plan for this ask. But the system held up anyway. The loop enabled it. And the fact it reached its goal without step-by-step guidance is what made it a [magic moment](./04-magic-moments.md).

## Feet Spur the Loop

Each loop was a single turn. Every tool call was surfaced explicitly:

* First, the model queried the calendar
* Then, it got attendee contact info
* Finally, it sent a message

For the agent to propel itself forward in the story, picture Link on a skateboard. He puts his foot down and pushes off, propelling himself forward — but losing momentum quickly. So he has to push again. And again. Each of those pushes? That’s a turn, happening inside the app’s control **loop** — the heartbeat of the agent.

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

## Wiring Up v. Plugging In

When the surgeon calls for "scalpel," the scrub nurse plucks it from the tray and places it squarely in the hand. That handover isn't magic. It was designed. Someone had to decide what instruments would be on the tray, what each one does, and how to hand it over. That's the developer's job — not in the moment, but in the building.

Every tool the agent uses represents a bridge the developer had to construct: code that translates the model's intent into an actual API call, code that shapes the response into something the model can reason about, code that vets permissions and handles errors. This is the **orchestration layer** — the backstage where the agent's world comes alive. The props from our text adventure? They're not just scenery. They're the "fictional props with teeth" we mentioned earlier — and someone has to give them those teeth.

That means writing code for each one. Every new tool requires the same heavy lift: define the shape of a valid request, wire in the actual service, handle the response, feed it back to the model. It's work. Important, necessary work — but repetitive.

Here's the thing: there's a better way. The abstract protocol we used in the exchange above? That's essentially what **MCP (Model Context Protocol)** is. It exists because the industry hit the same wall we just walked through. Instead of building every tool into every app — calendar, contacts, messaging, and so on — it made sense to standardize. To make tools modular. To make them into what are effectively USB drives: build them once, plug them in, reuse them everywhere.

It's the pivot from **wiring up** to **plugging in**.

Wiring up means baking each tool directly into your app — custom code for every integration, bespoke connections that live and die with that application. Plugging in means building a generic scaffold that speaks the protocol. You adapt your app to support MCP once, and then any tool that speaks MCP can be plugged in. The effort becomes portable. The shop that builds the tool can use it — but so can anyone else. These tools become commodities, ready to deploy.

So the developer doesn't wire up each individual tool. He wires up a scaffolding that supports an entire category of tools. He builds the port. The tools are the devices.

This idea — reuse through modularity — shows up in other forms too. The principle is the same: rather than custom-orchestrating every capability, have apps support plug-in components. It's not that wiring is wrong. If there's an app, there's a loop. It wants a tool.  The integration lift is necessary. But how it get there is a choice. It can be wired up individually — building all the code that makes it come alive — or it can be authored as a pluggable component that lets the protocol do the heavy lifting.

One builds a feature. The other builds a platform.

## Agency Is a Path, Autonomy a Town

To give a model “feet on the ground” is to let it act, not just reason.

It means giving it **agency** — the ability to push forward, to keep momentum, to lift the bead and drop it in the next cup. The goal is already known. The direction is clear. The work unfolds across turns.

That was the 2 pm message — the “let them know I’m late” ask. The bead was placed. The trail was laid. The model moved forward step by step.

Agency makes that possible.

But **autonomy** is looser. It’s not just about movement — it’s about deciding where to go. Sometimes that means letting the model decide the goal entirely. More often, it means giving it a purpose but not a path. You hand Link the quest but not the instructions. He chooses how to proceed.

Autonomy opens more doors. And with that freedom comes more uncertainty. Risks.

Risks are a topic to be covered later. In the meantime, let’s correct a former generalization about models.

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
