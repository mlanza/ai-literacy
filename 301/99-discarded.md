# Tools Revisited: Beyond the Basics

In the last chapter, we toured the AI's perspective — what it feels like to move through a task, and what it takes to give that AI feet. We saw how an agent turns "let them know I'm running late" into a sequence of real actions, and we explored the trust required as these systems act on our behalf.

But we barely scratched the surface of what tools *are*. The earlier chapter gave you the foundation. This one builds on it. We're going deeper — into the kinds of doors you might not have considered, the economics of building them, and what happens when an AI has more or fewer tools than it needs.

## The Landscape of Tools

A tool is a port — a doorway that lets an AI reach some body of data. That's the core idea. But doors come in different shapes, and it helps to see them all in one place.

**Instrumentation** refers to your device's built-in capabilities — the sensors and signals your computer or phone already has. Your browser is the most familiar example. With permission, it can access your geolocation, camera, microphone, clipboard, Bluetooth, motion sensors. Your phone does this too. Instrumentation gives the AI access to the physical world — where you are, what you see, what you hear, how you're moving.

**Applications** are the programs you use every day — Word, Excel, Outlook, Notion, your CRM, your ticketing system. Each one is a door. Each door leads to a category of data. The app is the means of access, and the data is what's behind the door.

**Files** are the documents, spreadsheets, images, and data you have scattered across your drives. A Word doc, an Excel spreadsheet, a PDF, a CSV, a JSON file, a Python script, a PNG image — these are all files. They're the general containers where people store all kinds of information. You upload one to ChatGPT and it can read, analyze, summarize, answer questions about what's inside.

**Artifacts** are also files, but they're a special kind. They're files *about* how work gets done — not the work product itself, but the guidance that shapes it. An SOP describes the process. A style guide defines the tone and format. An employee handbook explains how the organization operates. A set of examples shows what "good" looks like. These are meta-files — they don't contain the work, they contain the instructions for doing the work.

**Datastores** are where content lives. Everything you've ever created, every record ever saved, every piece of information ever captured — it all lives somewhere. On a local drive. On a server in a data center. In the cloud. Behind an API. The location varies, but the pattern is the same: the data exists in some underlying store, and an app bridges the gap between you and that data. Your CRM queries a database and returns customer records. Your analytics dashboard pulls from a data warehouse and shows trends. Your email client connects to a server and fetches messages. The app is the door. The datastore is what's behind it — often remote, often shared, always there.

## Data vs. Information

This distinction matters more than you might think.

**Data** is raw. It exists. It can be measured, stored, transmitted. But on its own, it doesn't mean anything. A spreadsheet full of numbers is data. A log file is data. A JSON payload is data.

**Information** is data that's been framed with understanding. It's data that's been interpreted, given context, made sense of. It's what you get when someone (or something) takes raw data and explains what it means.

> ⛩️ Data is potential. Information is potential realized. Artifacts are the bridge.

A spreadsheet of numbers is meaningless until someone explains: these are sales figures, these are dates, this column is revenue. The numbers alone don't tell you anything.

For AI, this is crucial. An AI can work with data — read a spreadsheet, parse a file, call an API. But to make that data useful, it needs **context**. It needs to understand what the data represents.

That's what artifacts do. An SOP tells the AI how to interpret a process. A style guide tells the AI what "good" looks like. An employee handbook tells the AI how the organization operates.

When you hand an AI an artifact, you're not just giving it data. You're giving it the ability to *understand* data. You're giving it the bridge from raw information to useful action.

This is why artifacts are among the most powerful tools you can provide. They're not just inputs. They're lenses.

## The Economics of Doors

Here's something worth knowing: **not all tools cost the same to build**.

**Application tools** — the ones that connect AI to systems like calendars, CRMs, file stores, messaging services — are essentially mini-apps. Someone has to write code that connects the AI to the system. That code defines what the AI can do: which doors it can open, what it can read, what it can change. Each one is purpose-built, custom-wired, and needs to be integrated. These cost developer time. They're an investment.

**Everything else** — files, artifacts, SOPs, guides — is different. These don't require code. You don't need a developer to write an employee handbook or create a style guide or document an SOP. These are just documents. They exist already, or you write them the same way you'd write any document. The cost is minimal — just the time to create the content.

> ⛩️ Tools are to AI what apps are to you. But some tools are just documents.

This matters because it changes how you think about equipping an AI. The app-like tools are the expensive ones. They're the ones that require design, development, and integration. The document-based tools — artifacts — are often already there, waiting to be used. Or they cost nothing to create.

Which brings us to **portability**.

You don't want to build app-like tools for a single environment — one version for ChatGPT, another for Claude Code, another for your internal system. That would be inordinately expensive.

The solution is portable tools — tools that work across environments. Like a USB-C cable that plugs into any laptop. Like a thumb drive that works on any computer.

There are two main approaches: **CLIs** and **MCP**.

**CLIs** (Command-Line Interfaces) are programs that run in a terminal. They're useful to both humans and agents. You can type `git push`. An AI can do the same thing. The CLI is a shared language — pilot and copilot both speak it.

> ⛩️ CLIs are simultaneously useful to humans and agents — a shared language for pilot and copilot.

**MCP** (Model Context Protocol) is a standardized way for AI systems to discover and use tools. Think of it like USB — a common interface that lets different devices connect.

CLIs have an edge: they're useful to humans and agents alike. They go everywhere. Every computer has a terminal. They're universal.

## The Leverage Equation

Think about what happens when you give an agent one tool versus ten tools. With one, it can do one thing well. With ten, it can orchestrate across them — decide which tool to use, when, in what sequence.

That's the difference between a handyman and a general contractor. The handyman is useful. The contractor manages the whole job.

This is why ChatGPT feels limited. It has limited tooling. Every time you need something outside its reach, you become the bottleneck. You're the one coordinating across all the places where your data lives.

> ⛩️ The state-of-the-art agentic runtime is exponentially proportionate to the tools you connect.

The powerful agent — the big lever — has direct access to all necessary tools in a single environment. Not an agent that lives inside Word. Not an agent that lives inside Excel. Those agents are like LLMs arriving to furnish a single apartment. Interesting. Helpful. But not transformative.

The agent we want hovers over many tools. It orchestrates across Word and Excel and your ticketing database and your file stores. It sees the whole picture. It can pull data from here, format it there, create something new somewhere else — all in one environment.

That's the lever. That's where orchestration becomes systemic instead of human-mediated.

## What Happens When Tools Are Missing

Here's a perspective worth sitting with: **each job expects a certain number of tools**.

Think back to that Monday morning — the Word doc, the Excel spreadsheet, the email, the Notion page, the ticketing system, the CRM. Apart from any one of them, you couldn't do your job. You'd be incomplete. You'd be limited.

The same is true for AI.

If even one tool is missing from the AI's harness, it's not going to be able to do the work. It's going to explain to you how to do it — like IKEA instructions — and you're going to have to orchestrate. You're going to be the bridge.

> ⛩️ A chatbot without tools gives you homework. A chatbot with tools does the work.

And when a human is kept in the loop for every step, there is no lift. The human will always be a bottleneck. The AI can't carry weight. It can't work while you're not there. It's still driving, even though it's supposed to be flying.

This is the competitive reality. Vendors who learn to harness AI — who build the tools, connect the data, fly the plane — are going to destroy traditional pricing models. They'll deliver more value in less time for less cost. The organization that hasn't utilized lift will still be driving while others are flying — simply because they failed to pull all the tools under a common environment.

The people who learn to pilot agentic runtimes will be the most valuable players in the coming era.

## The Pilot-Copilot Relationship

But here's what the shift actually looks like in practice. It's not about the AI doing *everything* while you sit back and watch. It's about **mutual mentorship**.

The pilot-copilot collaboration doesn't mean the copilot does all the work. What it means is a relationship where, as trust is built, the human can *by choice* step away. More work gets done because of this ongoing mentorship and trust relationship.

You're not just offloading tasks. You're teaching. You're showing the copilot how you like things done. You're building a mental model of your preferences, your standards, your way of working. And the copilot is learning — not just how to do tasks, but how *you* do tasks.

> ⛩️ AI isn't about forcing the human to work harder. It's about recruiting a worker who is fast and who doesn't tire.

This is the key to **working while you're not present** — the same idea behind being a business owner and earning income while you're not running the shop. That's the trade-off. That's the lift.

A chatbot with tools and trust becomes a partner. Someone who can carry the weight when you're not there. Someone who can act on your behalf and represent you well.

That's what flight looks like. Not just faster travel. Not just more efficient movement. It's the ability to be in one place while work gets done in another. It's the ability to scale without adding headcount. It's the ability to leverage your time beyond the hours in a day.

## The View From Above

Let's synthesize what we've added to the foundation.

The earlier chapter gave you the core: tools are doors, apps are portals, tools and data are inseparable. This chapter went further:

- **Instrumentation** adds access to the physical world — location, motion, perception
- **Artifacts** add context — the bridge from raw data to useful information
- **App-like tools cost money** — they're mini-apps requiring developer time; documents don't
- **Portability** ensures your tools work across environments — CLIs over MCP
- **Orchestration** is the lever — the more tools, the more the AI can coordinate
- **Missing tools** create bottlenecks — the IKEA problem
- **Trust** enables the relationship — pilot-copilot mentorship, working while absent

The runway exists. The plane is ready. What was missing was understanding what tools are — and now you know more than before.

The question isn't whether AI is useful. The question is which doors you've opened — and which ones you're still locking.

---

## Discarded

### From Driving to Flying

Now let's change the lens.

You've been driving your whole life. Typing. Clicking. Moving the bead yourself, cup to cup. A person at their keyboard, cranking through the work, at human speed.

That's driving.

You can still use AI. An agent bound up in The Inkwell (Word) — helpful in that shop, useful for writing — that's still driving. A better car, maybe. Faster. More comfortable. But you're still on the road.

An agent in The Ledger Hall (Excel) does calculations. An agent in your email sorts messages. Each one is brilliant at what it does, within its borders. But each one is still driving. Still constrained. Still limited to what fits inside that one shop.

ChatGPT is useful. It mustn't be dismissed. But a chatbot of any kind is a minor lever. It's a tool that still requires too much orchestration. If you're putting the IKEA shelves together, the assembly is still on you.

What turns driving into flying is something different. It's when the agent can coordinate across *all* the capabilities needed to complete the job end to end. Not just one shop. Not just Word or Excel or email. All of them. The whole scope. The agent decides what tools it needs, in what order, and goes and gets them. That's the difference. That's when the human can step out of the loop.

Now imagine you've switched vehicles. You've left the car behind and climbed into a private jet parked at the airport behind your house. You could still drive — the car is right there, in the driveway, waiting. But you're in the plane now on the runway.

You can drive the plane, taxi it along slowly both hands on the yoke same as if it were a steering wheel. You can refuse to lift off.

But why do that? That's what happens when you use AI without the full kingdom. You have the power of the plane, but you're still driving on the ground. You're still orchestrating. Moving the bead. It makes you the bottleneck.

But if you give someone an **agentic runtime** — that human can step out of the loop. That's when the plane lifts. That's when the jet takes off and the car in the driveway becomes irrelevant.

> ⛩️ The agentic runtime is the plane. The tools are the engine. Together, they lift.

---

### Additional Pulled Quotes (Original)

> ⛩️ The organizations who learn to fly will operate at a cost structure that makes traditional delivery look like hand-crafting.

> ⛩️ You can get everywhere by driving the car. It works. But it's almost comical when everyone else has a private jet.

> ⛩️ The runway is already built. The planes already exist. What you need are the pilots. And the infrastructure that lets them fly.

> ⛩️ The organizations who thought to build airports and train pilots 2 years ago will be the ones landing planes while the rest of us are still driving.

> ⛩️ The lever requires tools. The tools require safety. The safety requires infrastructure. And all of it requires starting before the urgency is undeniable.



---

## Watching The Show

Some developers choose to make the model's steps visible. They show its thoughts mid-move, using chain-of-thought as a UI convention — a running log of reasoning that users can watch unfold.

But I wanted to imagine something a little more fun to watch. The developer could, if he wanted, render a town for the model — Link — to inhabit. It has a calendar shop, a contact booth, and a messaging kiosk. Link darts from place to place, completing tasks. You see where it goes. You see what's in bounds. This way, the work becomes legible.

Most workflows aren't like that. They're not towns. They're trails. Directed. Linear. A bead moving cup to cup.

Some of those trails are hand-designed. Others are walked freely. What matters is that the bead advances through stages — and that each stage creates context for the next. That's what we're talking about now. How the model gets traction, feet on the ground, pushing. Then pushing again. Each push, shaped by what's come before.

Because real work doesn't happen in a single turn. The facts don't arrive all at once. The structure doesn't spring up whole. It's layered. Step by step.

That's why developers build systems. Why they expose waypoints. Why they separate concerns across turns.

Because structure improves output. Because each step leaves behind byproducts. Because serious work is iterative.

But here's what changes once the model starts pushing — when it keeps moving, turn after turn. We're no longer just talking about intelligence.

We're talking about **trust**.

And that raises the question: how far do we want it to go?

Is this a guided trail — tightly bounded, low-risk?

Is it a town — open-ended, permissive, built for discovery?

Or is it something else?

The answer depends on what we're willing to hand off — and how much we want to be kept in the loop.

## Proximity Reflects Trust

With **human out of the loop**, everything has already been decided. The stage is set, the props pre-approved, and Link moves through the world freely. The user offers the quest, and Link takes it from there — pushing forward, making decisions, carrying out the task with no interruptions. No one watches. No one interferes. There may not even be a visible interface showing what he's doing. That's maximum trust.

With a **human on the loop**, the stage looks the same, but there's a window into the play. The imagined town becomes visible. Link darts from shop to kiosk, nimble and fast — and the system might even slow him down on purpose, introducing a delay before each service interaction. Maybe 10 seconds. Enough time for someone to intervene if needed. A **stop** button appears. The adventure is still his, but it can be halted at any time. That's medium trust.

With a **human in the loop**, Link's freedom narrows. He must knock before entering. Each time he attempts something, the simulation pauses. The system reveals not just what he's doing, but what he intends to do. The human sees the request, evaluates it, and must explicitly approve it — clicking **proceed** before the story moves on. That's minimal trust.

The scale varies, but the question underneath is steady: how much freedom does the system get before someone steps in?

## The Hippocratic Oath

This kind of trust isn't about sentiment. Machines don't deserve it. They don't earn it. They don't feel responsible. The only oath in play is ours: **first, do no harm.**

So trust, here, means something narrower and heavier. It's confidence in outcome.

That the system will do what was meant, not just what was said.
That it won't cause damage — not because it understands the stakes, but because the scaffolding holds.

Deciding how close a human must stay — in, on, or out of the loop — is a design question. And that design is shaped by risk.

---

## Risk Categories

### Mistakes

Language models are predictive machines. They don't reason like people. They don't understand. So they guess — and sometimes they guess wrong. Small errors might just be cosmetic. Larger ones can do real harm. They might misstate facts, mislabel diagnoses, or fabricate something that was never true.

And they sound confident while doing it.

So the first question is simple:
*Can this be trusted to behave as expected — and will anyone notice when it doesn't?*

### Misalignment

Not every system serves your goals. Some optimize for attention. Some quietly serve the priorities of whoever built them. They follow instructions, yes — but they might pursue outcomes you didn't ask for, or don't want.

So another question emerges:
*Does this system behave in ways that reflect human values — and whose values does it follow?*

As autonomy increases, so does this risk. A helpful agent is one thing. An autonomous one pursuing the wrong objective is something else entirely.

### Unintended Consequences

Sometimes the damage doesn't come from one wrong answer. It builds. A small flaw compounds. A small nudge shifts the path. A harmless tool, used at scale, drives outcomes no one intended. Maybe it reinforces bias. Maybe it deepens polarization. Maybe it makes the wrong call and acts on it, fast.

So the final question is:
*Can we see where this might lead — and stop it if it goes too far?*

## The Weight of the Lever

To give Link feet on the ground is to build a lever of unusual size — a way to move more than we otherwise could. And it's easy to feel the promise. A system that can respond to human intent, operate tools, complete tasks, even carry work forward without needing to be told what to do at each step.

That's not science fiction. That's the present tense.

The ask is small — "Let them know I'm running late."
The output is precise: the right people, the right message, the right time.
And the lift? Offloaded entirely.
That's the lever.

Of course we want this. Of course we're trying. Because if a machine can help shoulder our knowledge work — lighten it, speed it, hand it off — the value is enormous.

But the lever cuts both ways.

The same momentum that lets Link glide from shop to kiosk, taking the next step and the next, can also carry him into places we didn't mean to go. The same fluency that lets him bridge gaps in planning or knowledge can, just as easily, fill them with fiction.

We've already seen what machines can do: self-driving cars. But sometimes they fail — and the weight of the error is real. Not a mistyped word. A broken body. A life.

And while knowledge work may seem safer, its effects aren't soft. A misfiled claim. A biased loan decision. A hallucinated treatment plan. When software does the work, the risk rides with it.

So while the lever is impressive — and it is — the fulcrum must be strong. That's where trust comes in. And trust, as we said, is not a feeling. It's a system design.

One that demands **transparency** — can you see what it's doing?

One that allows for **auditability** — can you trace how it got there?

One that offers **control** — can you intervene or shut it down?

One that secures **alignment** — does it pursue human intent, not just human input?

These qualities don't emerge on their own. They're engineered. They're governed. And they show up in the details — in what props are placed, in how tightly loops are held, in who gets to click *proceed*.

Because AI doesn't care. It never will. That burden, and that promise, rests with the people who build it — the ones who put feet on the ground.

---

**CLIs** (Command-Line Interfaces) and **MCP** (Model Context Protocol) services are to Link what an app is to a human. They're the programs an agent uses to gain a capability. Where a human might use a graphical app (like Word) an agent prefers ones that speak in plain text — its native tongue — and can act on a wide range of commands. While people don't use MCP services directly, they can and do use CLIs.
