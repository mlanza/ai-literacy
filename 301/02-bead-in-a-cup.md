# 🧭 A Bead in a Cup

We’re not zooming out right now. We’re zooming in. All the way down to a single cup in the system.

The bead — our unit of work — just dropped in.
Now it’s time to move it forward.

That’s what context engineering is really about: giving the AI what it needs — not to do *everything*, but to do *this next thing*. One step. One contribution. One cup to the next.

Let’s take a concrete case.

## 🎯 Use Case: Build the Final Daily Itinerary

We’re in the middle of planning a trip to Japan. The big decisions are made, key bookings are secured, and the family has already picked out the experiences they’re most excited about.

Our goal now is to build a clear, human-friendly itinerary — one that reflects those commitments, organizes the days sensibly, and includes suggestions for additional activities where time allows.

### Inputs

* 📄 **Confirmed Bookings Summary** — All the purchased tickets and reservations: flights, hotels, and a handful of timed activities.
* 📄 **Experience Bucket List** — A set of interesting activities the family picked earlier in the planning process.
* 🤖 **Activity Formatting Rules** — A simple process artifact describing how each day should be written up (clarity, structure, helpful travel cues).

### Output

* 📄 **Final Daily Itinerary** — A sequenced, structured plan for each day, with confirmed events and optional add-ons.

## 🔍 The Inputs, Up Close

### 📄 Confirmed Bookings Summary

This document captures all locked-in reservations. For this trip, that includes:

* Hotels in Kyoto, Kiso Valley, and Osaka
* Planned excursions for:

  * **Kiyomizu-dera Temple** (Kyoto)
  * **Nakasendo Trail Hike** (Kiso Valley)
  * **Universal Studios** (Osaka)

These weren’t casual adds — they were considered the “rocks” of the trip. High-value experiences that shaped the travel path and defined the itinerary backbone. You’ll find them listed both in the Experience Bucket List *and* in this booking summary. That overlap matters.

### 📄 Experience Bucket List

This came from an earlier phase, where the family explored potential activities near each hotel. Everyone got a say. The list they built includes attractions, food experiences, cultural sites — anything that sparked interest.

Each item comes with **GPS coordinates**.

Now, humans don’t think in lat/long. But machines do. And that matters more than you might think.

By capturing coordinates, you give the AI the spatial information it needs to reason through the geography — grouping nearby activities, identifying natural day plans, and using the hotel locations as hubs for exploring the area. It's how the model learns what’s close enough to combine.

This isn’t decoration. It’s what makes routing, clustering, and prioritizing feasible.

#### 🤖 Aside: Designing for AX

UX is for humans. AX is for AI.

When you enrich your documents with structured, machine-readable cues — GPS coordinates, clean dates, standardized names — you’re improving not the *feel*, but the *function* of the document from an AI’s perspective.

It’s not about writing in JSON. You’re still writing for people.

But you’re also **writing with machines in mind**.

That’s the shift. We’re not the only reader anymore.

Adding small details like coordinates, booking references, or even travel time estimates isn’t overhead. It’s part of **context engineering** — crafting inputs that a machine can actually use to reason through the next step.

The result? Better output, less back-and-forth, and a process that starts to feel like a system.

### 🤖 Activity Formatting Rules

This lightweight guide set the tone for how each day should be written. It covered things like:
*Structure the day chronologically. Use bold headers for key events. Clearly separate fixed bookings from optional add-ons.*

But it wasn’t just about structure — it also carried **human priorities**.

For example, this particular family had accessibility needs. So the formatting rules included a short instruction:
*“Flag each activity with accessibility notes when relevant — stairs, ramps, terrain, etc.”*

That one line shaped the entire output. It ensured the itinerary spoke directly to the family's real-world constraints, without needing to be re-edited afterward.

This is what makes the formatting guide special. It’s a **process artifact**, yes — but also a **human artifact**. It allowed the user to **imprint their priorities** into the process and get results that actually fit their life.

Had that instruction not been captured in the document, the model wouldn’t have known. The output would’ve been “fine” — but not *for them*.

## ⚙️ The Moment of Traction

Let’s zoom in on the moment the bead moved.

This wasn’t a vibe check. It wasn’t magic. It was a **command** — supported by real data.

The prompt that drove things forward:

> “Use these three documents — the Confirmed Bookings Summary, the Experience Bucket List, and the Activity Formatting Rules — to generate a final daily itinerary for the Japan trip, formatted as requested.”

That’s the bead moving from one cup to the next.

A single, explicit ask.

With all the materials needed to fulfill it.

Let’s break it down:

1. 📄 **Confirmed Bookings Summary** — a **product artifact** listing what’s locked in.
2. 📄 **Experience Bucket List** — a **product artifact** listing what’s desired.
3. 🤖 **Activity Formatting Rules** — a **process artifact** describing how the result should be shaped.

Together, these formed the full context. Not in the model’s memory. Not implied in conversation.

**Visible. Present. Supplied.**

The result? A clear, structured daily itinerary.

Confirmed events anchored the days. Optional activities clustered by proximity. Accessibility needs respected. Formatting consistent.

None of that was guessed. It was derived — from the prompt and the payload.

From data in the cup.

That’s the bead-in-a-cup metaphor, made real.

Incidentally, this is also what a **function** in a computer program looks like in practice:

* The prompt is the function signature.
* The artifacts are the parameters.
* The output is (or can be) deterministic, shaped by inputs alone.

This is **context engineering** at its core.

You’re not “asking ChatGPT to help.”

You’re designing a system moment — a reproducible unit of AI labor, shaped by structure and scope.

You’re building a world the model can see — then asking it to take the next step.

That’s how you move the bead.

That’s the real work.

And now you’ve seen it land.

## 🧱 The Artifacts Are the Infrastructure

This prompt didn’t work in a vacuum. It worked because earlier steps produced **artifacts**.

* A checklist of experiences
* A structured booking summary
* A shared format for writing things down

These aren’t fancy. They’re markdown files, tables, bullet lists — whatever captured the state of the work.

But that’s the point.

They made the prompt possible.

They *enabled* the AI to perform real labor.

That’s what most people miss.

They want the chatbot to “plan their trip” — but without the scaffolding, the model is guessing in the dark. The groundwork has to be there.

And once it is? You’re not asking it to plan the whole trip.

You’re asking it to move the bead.

## Meeting the Fork

Back in the *Reifying Process* chapter, we talked about the spectrum.

* **Lean left** and you steer the conversation, one volley at a time
* **Lean right** and the system carries the memory, the baton, the state

In this case, we leaned right — we passed in artifacts, gave it everything at once.

But we could’ve leaned left. You could have had a long chat, describing your hotels, your must-do activities, your preferences. As long as those ideas were exposed — in conversation, not just in your head — the model could’ve done the same thing.

That’s what “context” means. It doesn’t matter whether it lives in a file or in a transcript. It just needs to exist — and be accessible when it’s needed.

## 🧠 Brain, Memory, Tools — Now Complete

For decades, we’ve had **tools**.

We’ve had **memory** — databases, forms, files.

What we lacked was the **brain**.

Now we have one.

And when we let that brain operate in a system that exposes the work — through structured memory, repeatable artifacts, and prompts shaped by purpose — it can help us actually get things done.

The AI doesn’t have arms. It can’t move the bead on its own.

But it can tell you what to do next. It can write the next artifact.

It can surface the options. Propose a plan. Spot a conflict.

If — and only if — the inputs are there.

## 🧠 That’s Context Engineering

It’s not magic. It’s not command-only.

It’s **prompt + artifact** — the instruction *and* the materials.

It’s recognizing that AI can’t pull from your mind — it can only work with what’s in view.

Context engineering is how we decide *what* to show it, and *how*.

The more visible your process becomes, the more useful your AI gets.

That’s the handoff.

That’s how you move the bead.

## 👀 What’s Next

So far, we’ve assumed you’re still holding the wrench.

Still the one pasting files, managing context, pulling the strings.

But that’s starting to change.

You’re about to meet tools — and agents — that can do more of that *for you*.

Because once you’ve built artifacts, you can start building handoffs.

And that’s how you shift from chatbot to teammate.

We’re not all the way there yet.

But the infrastructure is coming.

And now, you know what and how to feed it.
