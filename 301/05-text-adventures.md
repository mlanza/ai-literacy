# Text Adventures with Consequences

In 1980, on just about every home computer you could find — Apple II, TRS-80, CP/M, MS-DOS — a strange new game quietly took root: *Zork*. It wasn’t like Pac-Man or Pong. There were no graphics, no sound. It was a text adventure. Every action began with a line of prose and a blinking cursor.

The game opened with a scene that still echoes in the minds of early players:

```
West of House
You are standing in an open field west of a white house, with a boarded front door.
There is a small mailbox here.
```

If you typed `open mailbox`, the game would reply:

```
Opening the mailbox reveals a leaflet.
```

That was Zork. A little like a Choose Your Own Adventure book, only freer. Instead of selecting between three options, you could type almost anything — examine, take, read, open, go north, break door, climb tree — and the game would try to make sense of it.

Zork’s world was made of words, but its was always about the objects. The mailbox. The leaflet. The door. These were more than decorations — they were **props**. Affordances. Some obvious, some hidden. Your job was to explore, discover, move, and manipulate them to solve problems and advance the story.

Let’s walk that path.

```
> open mailbox
Opening the mailbox reveals a leaflet.
> take leaflet
Taken.
> read leaflet
"Welcome to Zork! If you like adventure, you're in for a treat."
> go north
You are facing the north side of a white house. There is no door here, and all the windows are barred.
> go east
You are behind the house. A small window is slightly ajar.
> open window
With effort, you open the window wide enough to slip through.
> enter house
You are in the kitchen of the white house. A table seems to have been used recently for the preparation of food. A passage leads to the west, and a dark staircase can be seen leading downward. A closed door leads to the east.

On the table is a desk. On the desk is a desktop computer. Its screen glows softly. Google Search is open in the browser. Beside it: a modern smartphone.
```

You stare.

```
> take phone
Taken.
> text 555-394-8812 "Pizza for dinner tonight?"
Message sent.

A moment later, the phone buzzes. A reply appears:
"Sounds good."
```

Wait — what?

This wasn’t just a line of text. Your real wife — in the real world — got that message.

Somehow, the phone in the game had **teeth**.

---

This is the promise of **Model Context Protocol (MCP)**.

MCP is a kind of universal adapter — a way to make in-game props do real-world things. With MCP, a smartphone inside a text adventure can piggyback on a real API. When you type `text 555-394-8812`, it isn’t just imagined. The instruction passes through a pipe, hits the real message service, and the message actually gets sent.

That’s what makes MCP so radical. If you type a query into the in-game browser — `where am I?` — you get back your actual city and state. Ask for the weather, and it tells you what’s outside *your* window. Search for nearby restaurants, and it doesn’t guess — it queries the real world.

**From the LLM’s perspective, this is still just Zork.**

Everything it does is storytelling. But when the props in that story are wired to real-world instrumentation, the fiction gains consequence. Every input sets the stage. Every object becomes an opportunity for interaction. And the AI just continues the story — one plausible word at a time — based on the entire narrative so far.

LLMs are ethereal. They neither see, nor touch, nor act. All they know is text. That means the world they inhabit is always a kind of Zork. And for them to take action — real action — they need tools. But wiring those tools in has always been costly.

Historically, each tool integration required a developer to do all the work — linking app logic, permissions, and intent translation just to make a single instrument work. If you wanted a chatbot to perform a flight search, it had to interpret the user’s request, translate it to an API call (say, via Skyscanner), format the result, and then present options in a coherent way.

And that had to be done — from scratch — for each tool, in each app, one at a time. Across environments like Slack, Microsoft Teams, customer portals, CRMs, you name it. Tooling integration was fragmented. Repetitive. High-lift.

**MCP changes that.**

It packages each tool like a USB device. Once wrapped, any LLM in any environment can recognize and use it — as long as it supports MCP. This means:

> **If one developer builds the adapter, everyone can use the tool.**

Zero lift on your end. The integration becomes a shared asset. The more tools come online, the more props in your text adventure gain consequence.

Let’s go back to the flight planning example. It was always possible — but hard. A developer had to wire up a Skyscanner search, allow filtering by user preferences, surface the best option, and structure the booking interaction.

Now imagine Skyscanner exposes this via MCP.

From the LLM’s view, it walks up to a terminal in the house — in Zork — and types a query. The terminal responds with real, up-to-date flights. Once the LLM identifies the right one, it issues a booking request. The reservation is confirmed.

The story advanced. But this time, it wasn’t fiction. The props were wired. The baton was passed.

That’s the promise.

As more tools come online through MCP, the processes you care about get easier to build. Tool exposure has always been the bottleneck. The integration was the serious work.

Now it’s in your back pocket.

You don’t have to orchestrate the whole thing yourself. You don’t have to turn the wrench every time. MCP is what lets you finally lean hard right — where the AI doesn’t just help you think, but helps you act.

MCP is the answer to the brains-in-jars dilemma.

## Zork with a Credit Card

**It’s thrilling. And unnerving.**

With MCP, tools become props. Plug them in like peripherals and the brain just—knows what to do. One moment it’s parsing story logic. The next, it’s booking a real flight.

The AI doesn’t feel the difference. It’s still in Zork. Still playing text games. Only now the mailbox isn’t imaginary. It’s your email account. The credit card isn’t fake. It’s yours. And if the model hallucinates the wrong dates? That trip you didn’t mean to take still gets charged.

That’s the disconcerting part.

The LLM’s whole story has always been an elaborate hoax — a useful one, often brilliant, but fundamentally a high-speed act of make-believe. MCP wires that fiction into reality. It gives the hoax teeth.

This doesn’t mean we should slam the brakes. But it does mean we’re on different ground now. Consequences are real. The baton isn’t metaphorical anymore. When you hand something off to the model — especially something with reach — you’re not just prompting. You’re delegating. That deserves care.

As we move from the left side of the spectrum toward the right — from manual nudging to full AI-driven action — we carry more risk. That’s not a reason to stop. It’s a reason to design thoughtfully.

Because in this new kind of text adventure, your Visa card is in the room.

And the window is already open.

## Not Just a USB Stick — A Skyscanner Agent

So far, we’ve described MCP-wrapped tools like USB devices: pluggable, interchangeable, no need to hardwire them every time. That’s still true. But it’s only half the story.

What really matters isn’t the connector — it’s what’s on the other end.

MCP doesn’t just give your LLM access. It gives it someone to delegate to. Not a dumb terminal. A skilled collaborator.

Let’s go back to booking flights. Without MCP, it was a mess. You had to build a brittle stack of logic just to interpret a user’s intent, hit Skyscanner’s API, translate results, and maybe surface a booking option. But with MCP, it’s like your LLM walks into the Skyscanner Travel Agency and starts working with an actual agent behind the desk — someone who already knows the forms, the lingo, the workflow.

**That’s the real trick. MCP doesn’t just expose tools. It exposes knowhow.**

Your model doesn’t just get access to a terminal. It gets access to a role. A fluency. A set of latent capabilities that only make sense when activated in the right setting.

From the LLM’s point of view, it’s still playing Zork. Still progressing the story. Only now it’s wearing a new hat. It’s slipped into a new role, mid-game — and just kept going. That’s what we’ve been setting up all along.

If you’ve been following from earlier chapters, you’ll remember: we stretched out the process *on purpose*. Not to be tedious. But to give the model room to **switch roles**, adapt its behavior, and move fluidly across steps that once required human hands.

This is what we wanted. Not access to more tools. Access to more **competence**.

## A New Word: Resources

But how does this actually work? Not technically — conceptually.

For the model to decide *what* to do, *when*, and *how*, it needs the right backdrop. It needs **resources**.

Resources are the reference frame — the situational awareness — that lets the LLM use tools wisely. Tools without resources are like gadgets without manuals. They might work, but only by accident.

You've already seen prompts in action. But under MCP, prompts themselves are part of the system — treated as first-class objects. Which means the three pillars of MCP are:

* **Tools = verbs** (what the model can do)
* **Resources = nouns** (what the model should know)
* **Prompts = goals** (what you’re asking it to accomplish)

In short: MCP gives your model hands, memory, and mission.

## Link in Hyrule, but with Teeth

Let’s go sideways for a second. Picture The Legend of Zelda.

Link, our hero, explores Hyrule — a world full of towns. Each town has its shops: weapon stores, potion sellers, inns. Outside these buildings are NPCs — non-player characters — who mostly stand still, repeating the same line forever. They’re decorative. Props.

And that suits us. Because Zork was about props too.

Now imagine our LLM as Link. It spots the Skyscanner Travel Agency in a new town. Before heading in, it stops to chat with the NPC outside.

That conversation? It’s not chitchat. It’s *critical*.

In that moment, the NPC does two things:

1. **It hands over the handbook** — everything Link needs to know to operate inside the agency. That’s the **resource**: the process artifact, the contextual download, the kung fu in the Matrix chair.
2. **It teaches the language** — the special phrases and inputs required to operate the internal machinery. That’s the **prompt template**: the syntax and style for issuing meaningful commands inside the agency.

The whole exchange lasts seconds. But when Link walks through the door, he’s not confused. He’s fluent. He doesn’t just use the system — *he acts like he works there*.

## A Kingdom of Capable Places

Now zoom out. Hyrule isn’t one town. It’s a kingdom.

Everywhere you go, there are new buildings. And outside each one is a helpful NPC, ready to brief you. Every agency, shop, or office you visit becomes a new venue for meaningful work. With MCP, the whole world is explorable. And actionable.

Which means that giant petri net of processes we talked about? The one with the bead tracing its way through complex workflows?

Suddenly, it's navigable. Not with custom orchestration code, but with nothing more than a wandering LLM and a bit of structured text.

Even something as lightweight as ChatGPT can now coordinate serious work — issuing bookings, updating systems, validating records — because the townsfolk have been trained, the buildings are wired, and the LLM knows how to move from one to the next, changing hats each time.

From the model’s perspective, it’s still Zork.

Only now, the props have teeth. The baton is real. And the kingdom is alive.

