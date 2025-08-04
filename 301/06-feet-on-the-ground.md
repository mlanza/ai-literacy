# Feet on the Ground

In the last chapter, we described the LLM’s world as a kind of text adventure — a Zork-style simulation where the AI navigates rooms, encounters objects, and performs actions by typing verbs. But we also made a subtle shift: those objects aren’t just fictional. They're props with wiring. And when wired through MCP, they become portals to the real world — turning fictional acts into consequential ones.

If there’s a phone in the room, someone built it. If there’s a laptop with a browser open, someone made sure it knows how to behave. And if there’s a travel agency with an NPC outside, someone encoded its rules of engagement. Behind every meaningful object is a developer who breathed life into it — not to simulate reality, but to expose capabilities.

This isn’t light work. Every virtual prop that does something real represents an integration lift. That’s why we aim to reuse them, wrap them, and distribute them in ways that make them easy to plug in — often using something like MCP. The goal is to let the model move fluidly through a world and employ tools, and hopefully not have to implement them all ourselves.

So let’s see that in action. Not as a concept, but as a moment.

## 🚗 The Scenario: “Let the 2pm Meeting Know I’m Running Late”

It’s 1:52 PM. The executive is stuck in traffic. He says:

> “Hey Assist, let the 2pm meeting know I’m running 10 minutes late.”

That’s the intention. It’s not a full plan, not a sequence of steps — just a quick human ask.

From there, the baton passes to the app. It spins up the model, hands it a few consequential props — a calendar, an address book, a texting interface — and lets the model take the first step.

## 🌀 Loop 1 — Calendar Query

The first prompt includes the user’s request, transcribed from voice and sent into the app. The current time and available tools are in scope.

The app delivers this to the model:

```
You are an assistant. The user just said:
“Let the 2pm meeting know I’m running 10 minutes late.”
It is currently 1:52 PM.
You may use available tools to look up calendar events.
```

The model anchors immediately on the calendar. To notify anyone, it first needs to understand what the 2pm meeting is — and who’s attending.

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

The developer extracts the structured request and relays it to the MCP calendar service, which responds:

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

## 🌀 Loop 2 — Address Book Lookup

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

## 🌀 Loop 3 — Text Message Delivery

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

---

Each loop was a single LLM turn. Every tool call was surfaced explicitly — no black boxes, no shell commands, no behind-the-scenes orchestration.

* First, the model queried the calendar
* Then, it got attendee contact info
* Finally, it sent a message

All without a prewritten playbook. The model knew what tools were on the desk and how to use them. Likewise, the developer knew because he is the one who set the stage on which the model would perform.

However, for the model to propel itself forward in the story, I like to think of it like Link (the LLM) on a skateboard. He puts his foot down and pushes off, propelling himself forward — but losing momentum quickly. So he has to push again. And again. Each of those pushes? That's a model turn, happening inside the app's control loop.

That's where the developer is, right there — with the bead. Not choreographing the motion, but present in the loop. Watching each push. Shaping the environment.

Every tool call is routed to the MCP server. That’s the baton pass. The developer sees what the model is trying to do and decides what gets through — not line-by-line, but by designing the set, laying out the props, and observing the turns.

And what gets through isn’t some vague intent. It’s a sequence of clear, Zork-style moves — compact, consequential, and context-aware. Not the original “let them know I’m running late,” but something more like:

```
> check calendar between ... and ...
> get attendees for “...”
> look up numbers for ..., ..., and ...
> send group text: “...”
```

Each is a turn. A push of the foot. That’s what the app sees. That’s what the developer vets, because he can't necessarily anticipate the intent, but he does have control over what is permitted inside the control loop.

He doesn’t have to know where the story is going. He just has to decide whether this particular combination of verbs — on this particular stage — seems reasonable enough to let the action proceed.

Some developers choose to make the model’s steps visible. They show its thoughts mid-move, using chain-of-thought as a UI convention — a running log of reasoning that users can watch unfold.

And if you wanted to have some fun, you could sketch a little GUI. A calendar shop. A contact booth. A messaging kiosk. The model — Link — darts from place to place, completing the task. You see where it goes. You see what’s in bounds. The work becomes legible.

Most workflows aren’t like that. They’re not towns. They’re trails. Directed. Linear. A bead moving cup to cup.

Some of those trails are hand-designed. Others are walked freely. What matters is that the bead advances through stages — and that each stage creates context for the next.

That’s the pattern behind multistep features like ChatGPT’s “deep research.” Not a single move, but a control loop. The model pushes, then waits. Pushes again. Each time, shaped by what’s come before.

Because real work doesn’t happen in a single turn. The facts don’t arrive all at once. The structure doesn’t spring up whole. It’s layered. Step by step.

That’s why developers build systems. Why they expose waypoints. Why they separate concerns across turns.

Because structure improves output.

Because each step leaves behind byproducts.

Because serious work is iterative.

But here’s what changes once the model starts pushing — when it keeps moving, turn after turn. We’re no longer just talking about intelligence.

We’re talking about agency.

And that raises the real question: how far do we want it to go?

Is this a guided trail — tightly bounded, low-risk?

Is it a town — open-ended, permissive, built for discovery?

Or is it something else?

The answer depends on what we’re willing to hand off — and how closely we’re willing to stay in the loop.
