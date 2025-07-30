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

That’s the bead-in-a-cup metaphor, made real, the epitome of **atomicity**.

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

And this is what LLMs make possible — not because they’re guessing, but because they can now act on a command *if* the right information is already in view. That’s the real shift:

AIs can write deliverables. They can recommend actions. They can reason through a situation. But only when the inputs are there — right there, piped into the cup at the moment of execution.

The bottleneck isn’t the model. It’s us.

We haven’t built the infrastructure to carry forward the artifacts, decisions, and constraints that make a command actionable. The model is ready to do the work. Our job is to support that moment — to structure what matters, and deliver it when it counts.

That’s the new frontier of systems design.

## Meeting the Fork

Back in the *Reifying Process* chapter, we talked about the spectrum.

* **Lean left** and you steer the conversation, one volley at a time
* **Lean right** and the system carries the memory, the baton, the state

In this case, we leaned right — we passed in artifacts, gave it everything at once.

That only works if *everything at once* already exists.

And that means prior work.

The bookings were already made. The preferences were already collected. The formatting rules were already agreed on.

What made the prompt work wasn’t just the instruction. It was the infrastructure:
**Artifacts** that captured what mattered, in a way the model could act on.

We could’ve leaned left. You could have had a long chat, describing your hotels, your must-do activities, your preferences. As long as those ideas were exposed — in conversation, not just in your head — the model could’ve done the same thing.

That’s what “context” means. It doesn’t matter whether it lives in a file or in a transcript. It just needs to exist — and be accessible when it’s needed.

## 🧠 The New Piece

Everything we’ve seen so far — the way the bead moves, the way the model performs — rests on one thing: giving it the right inputs at the right time.

That’s not new. Systems have always worked this way.

Long before LLMs, developers were already building the infrastructure for continuity.

*Databases held decisions.*

*APIs triggered actions.*

*Formats and schemas carried priorities forward.*

Memory wasn’t a metaphor. It was a backend.

The tools? Not novel either. We’ve had them for decades — browsers, schedulers, scripts, triggers, queues. Systems got things done because we told them what mattered and when.

What’s new isn’t that structure.

It’s that now, at the moment of execution, a brain can join the loop.

That’s the shift.

The memory’s always been there.

The tools have been ready.

Now the brain shows up — and asks how it can help.

But it’s a brain in a jar.

It can’t act. It can’t feel its way forward.

It can only see what you show it.

If the data arrives with the bead — if the pipeline delivers what it needs, just like it always has — then the brain can contribute. Not by guessing, but by reasoning.

And what it reasons from is the payload.

Every artifact, decision, and constraint required to take the next step — already in the cup.

That’s what makes the bead move.

That’s the handoff.

## 🧠 That’s Context Engineering

It’s not magic. It’s not command-only.

It’s **prompt + artifacts** — the instruction *and* the materials.

It’s recognizing that AI can’t pull from your mind — it can only work with what’s in view.

**Context engineering is putting enough integrity into what's been captured and communicated in your prompt and payload that one can reasonably anticipate a good output.**

The more visible your process becomes, the better you get at exposing the necessary information, the more likely your AI will be able to assist.

That’s the handoff.

That’s how you move the bead.

## 👀 What’s Next

We all know what it’s like to lean left. To bring in AI when we’re stuck, or when a task feels small and self-contained. We paste in a bit of context, talk through the shape of what we want, maybe try a few rewrites. The help is real — but so is the overhead.

Because unless we’ve already laid the groundwork, even a smart assist becomes a manual job. We spend time gathering references, restating what we know, walking the model through constraints we’re holding in our heads. It can feel more like narrating than collaborating.

So we don’t do it often. We stick to using AI for isolated tasks — things we can hand off in one shot. And we avoid inviting it into the bigger work. Not because the model can’t help, but because the logistics are brutal. The friction is too high. It’s easier to do it ourselves.

**That’s why we want to shift things to the right.**

To do that, to make the whole projects tractable, you need to build scaffolding to carry memory, structure, and priorities forward — not just to make the next prompt easier.  The goal is to **build systems where thinking happens inside the loop**.

You’ve seen what happens when a brain joins the process — when it has the right inputs, at the right time, and can reason from them.

Now imagine that brain sitting *next to the bead*.

Not off to the side, waiting for you to intervene. Not in a chatbot thread you have to copy everything into.

**Right there in the cup.**

That’s what’s starting to happen.

Tools are emerging that don’t just carry the data — they carry the *intelligence*. Agents that can spot what's missing, fill in gaps, reformat, restructure, even route artifacts downstream.

The bead doesn’t just move because you told it to.

It moves because you engineered a system that knows what to do with it.

The next frontier isn’t just asking AI to assist — it’s designing environments where its contribution is built in.

Where moving the bead doesn’t require a prompt, because the system already knows what matters.


## ✈️ Modeling a Harder Problem: Picking the Best Flight

Let’s move the bead again. But this time, let’s pick a messier moment — one that forces more context into view.

In course of planning an international trip, what'd be helpful is having the AI find us a flight.

What would it take to get a chatbot to make a smart recommendation — or at least shortlist three options that meet your needs?

You can’t just say, *“Which one should I pick?”* and expect brilliance. That’s not context engineering. That’s a shrug in the dark.

You need to think like a system designer.

So step back. Imagine you were doing this yourself. Or better yet, imagine you were handing it off to a smart assistant — one with no prior knowledge of your preferences or the options available.

What would you give them?

Two things:

1. A list of flight options (the candidates).
2. A clear traveler profile (your decision criteria).

That’s the anatomy of the moment. Two inputs. One ask. And if you’ve framed them well, the AI can do useful work.

Let’s walk through what each artifact needs to look like.

### 📄 Traveler Profile (Process Artifact)

This is the cheat sheet — a way to help the AI see how *you* think about flights.

You don’t need a special format. A simple markdown file works fine. Use plain language. Use bullets. Weight your preferences if that helps.

For example:

```markdown
# Traveler Profile

## Preferences (in rough order of importance)

- Cost matters. Avoid outliers — we don’t always pick the cheapest, but extreme prices are disqualifying.
- Prefer nonstop flights. Willing to accept one connection if it significantly improves cost or schedule.
- Avoid long layovers (more than 3 hours) and too-short layovers (less than 45 minutes).
- Departure/arrival time should align with normal waking hours (no red-eyes unless necessary).
- Favor known carriers over budget airlines, unless cost savings are substantial.
```

This isn’t about being exhaustive. It’s about being clear enough that someone else — human or AI — can juggle your tradeoffs.

That’s why it’s a **process artifact**. It doesn’t depend on where you’re going. It applies across trips.

### 📄 Flight Search Results (Product Artifact)

This is the raw material. The actual flight options on the table.

Now, in a real system, you’d query an API. But most flight sites don’t make their data exportable. So what do you do?

You make a reasonable facsimile.

You ask the AI to play C-3PO.

Here’s the move:

> “Pretend I’m searching for roundtrip flights from BWI to Kyoto (with outliers like IAD or JFK allowed). Use the Skyscanner API format as a guide. I need realistic mock data — at least 200 itineraries, in JSON. Include carrier, price, layover details, total travel time, etc.”

That’s it. You’re not looking for real data — you’re modeling the shape of it. Because the shape is enough to practice the moment.

You don’t need the actual trip. You need the structure.

Once you’ve got that mock data, you’re ready to move the bead.

### 🧠 The Moment of Execution

The setup is done. Now comes the ask:

> “Given our traveler profile (attached) and this list of flight options (attached), recommend the best flight. List two alternates for comparison.”

The AI doesn’t need memory. It doesn’t need backstory. It just needs these two artifacts — dropped cleanly in the cup.

That’s when you watch it work.

You’re not expecting perfection. You’re testing for traction.

Did it pick flights that align with your priorities? Did it weigh tradeoffs in the way you hoped?

Maybe. Maybe not.

And if not — now you iterate. You revise your traveler profile. You tweak how you framed the tradeoffs. You run it again. That’s how you mentor the AI.

You’re not grading a student. You’re training a teammate.

### 🛠 From Modeling to System Design

This is what “moving the bead” really means. Not just issuing a prompt, but engineering the moment so a smart tool can act meaningfully.

And if you can do it in ChatGPT, you can do it anywhere.

Picture the same logic embedded in a Power Automate flow — traveler profile and flight results piped in as variables. The LLM evaluates and outputs a shortlist. Now that same bead moves in Microsoft land.

Or maybe it lives in a browser extension. Or a console app. Or a shared team tool.

The form doesn’t matter. The inputs do.

Because once you know what the moment *requires*, building the environment is just infrastructure work.

### 🧭 Why This Matters

This whole exercise wasn’t about flights. It was about **context engineering**.

You built a prompt, yes — but more importantly, you built the **payload**. You isolated the exact inputs that shape a good decision, and you wrapped them in a frame the AI could act on.

That’s the skill. That’s the shift.

And that’s how system design starts: not with automation, but with a moment.

You moved the bead.
