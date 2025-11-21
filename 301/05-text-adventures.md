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

Somehow, the phone in the game had **teeth**.  That's what tools offer.  Text-based affordances which map to real-world capabilities.

## Pluggable Tooling

We talked before about tools — how they give an agent real leverage, the means to act on your behalf instead of just talking about what could be done.

Earlier, the discussion was how developers hardwired **internal tools** into the app. But what if **external tools** were designed to be more like thumb drives? Something you could just reach for and plug in — **pluggable**.

In that model, a developer builds each tool as a standalone component, not as an internal appendage. That’s what makes them reusable — any agent can discover and use them, not just the one they were built for.

There are several ways this idea shows up in practice — from command-line interfaces (CLIs) that expose discrete operations, to the Model Context Protocol that lets agents negotiate access to external resources, to Skills frameworks that package specialized behaviors. Each of these embodies the same design philosophy: tools that can be recognized, explored, and mastered on demand. They make capability modular, composable, and readily accessible.

The deeper principle at play, what actually promotes the pluggability, is **progressive disclosure**. The agent doesn’t perceive the full depth of every tool it could use all at once; it starts with the first rung of a ladder. But it knows the ladder is there. When the moment calls for it, it can ascend — uncovering more detail and capability as needed. That’s how it keeps its context lean while still having depth on demand.

In practice, readily accessible is 3 rungs on a ladder:

* **Instant identifiability.** The agent immediately recognizes the tool as an affordance — something that can *do* — and understands, at a glance, what class of problem it’s meant to solve.
* **Instant discoverability.** When asked, the tool reveals its table of contents — the api for what it can do.  This allows the agent to think about the particular feature(s) it wants to use.
* **Instant grokkability.** Once the agent chooses a capability, it can instantly absorb the know-how it needs — like flipping open to the right page and putting on the skill like a hat.

Progressive disclosure is a technique for preserving the context window, allowing the agent proper focus, while pluggability ensure it has access to the on-demand capabilities it requires to get a job done.

## Text-base smartphone, real-world consequence

Take the smartphone in Zork that does real-world things. That in-game prop piggybacks on a real API. When you type `text 555-394-8812`, it isn’t just imagined. The instruction passes through a pipe, hits the real message service, and the message actually gets sent.

That’s what makes tools so radical. If you type a query into the in-game browser — `where am I?` — you get back your actual city and state. Ask for the weather, and it tells you what’s outside *your* window. Search for nearby restaurants, and it doesn’t guess — it queries the real world.

**From the model’s perspective, it's just Zork.**

Everything it does is storytelling. But when the props in that story are wired to real-world instrumentation, the fiction gains consequence. Every input sets the stage. Every object becomes an opportunity for interaction. And the AI just continues the story — one plausible word at a time — based on the entire narrative so far.

Models are ethereal. They neither see, nor touch, nor act. All they know is text. That means the world they inhabit is always a kind of Zork. And for them to take action — real action — they need tools. But wiring those tools in has always been costly.

Historically, each tool integration required a developer to do all the work — linking app logic, permissions, and intent translation just to make a single instrument work. If you wanted a chatbot to perform a flight search, it had to interpret the user’s request, translate it to an API call (say, via Skyscanner), format the result, and then present options in a coherent way.

And that had to be done — from scratch — for each tool, in each app, one at a time. Across environments like Slack, Microsoft Teams, customer portals, CRMs, you name it. Tooling integration was fragmented. Repetitive. High-lift.

**Pluggability changes that.**

It packages each tool like a USB device.  Makes them modular. Once wrapped, a model can readily recognize and use it.

Zero lift on your end. The integration becomes a shared asset. The more tools come online, the more props in your text adventure gain consequence.

Let’s go back to the flight planning example. It was always possible — but hard. A developer had to wire up a Skyscanner search, allow filtering by user preferences, surface the best option, and structure the booking interaction.

Now imagine Skyscanner exposes its capabilities in a tool.

From the model’s view, it walks up to a terminal in the house — in Zork — and types a query. The terminal responds with real, up-to-date flights. Once the model identifies the right one, it issues a booking request. The reservation is confirmed.

The story advanced. But this time, it wasn’t fiction. The props were wired. The baton was passed.

That’s the promise, plugging the things you care about into the app. That's always been the bottleneck. In this era of intelligence,  integration is still the serious work in front of the lever.

With the right tool already plugged in, its in your back pocket. You don’t have to orchestrate the whole thing yourself. You don’t have to turn the wrench every time. Accessible tools let you finally lean hard right — where the AI doesn’t just help you think, but helps you act.

Tools are the answer to the brains-in-jars dilemma. Pluggability makes them portable.  In this world, buidling a good experience is a matter of plugging in the right tools and defining a good process.

## Zork with a Credit Card

But the notion that a tool plugged in instantly becomes an in-game prop is both thrilling and unnerving.  It shatters the jar, unshackles the brain. One moment it’s parsing story logic. The next, it’s booking a real flight.

The AI doesn’t feel the difference.

It’s still in Zork, driving the storyline.  Pure text. Only now the mailbox isn’t imaginary. It’s your email account. The credit card isn’t fake. It’s yours. And if the model hallucinates the wrong dates? That trip you didn’t mean to take still gets charged.

That’s the disconcerting part.

The model’s whole story has always been an elaborate hoax — a useful one, often brilliant, but fundamentally a high-speed act of make-believe. Tools wire that fiction into reality, give it teeth.

This doesn’t mean we should slam the brakes. But it does mean we’re on different ground now. Consequences are real. The baton isn’t metaphorical anymore. When you hand something off to the model — especially something with reach — you’re not just prompting. You’re delegating. That deserves care.

As we move from the left side of the spectrum toward the right — from manual nudging to full AI-driven action — we carry more risk. That’s not a reason to stop. It’s a reason to design thoughtfully.

Because in this new kind of text adventure, your credit card is in the room.

And the window is already open.

## Not Just a USB Stick — A Skyscanner Agent

That a tool plugged in exposes real-world levers is true, but it’s only half the story.

They don’t just do — they *know how to do*. They teach the model how to think and execute. When you hand something off to one, you’re not dealing with a dumb terminal. You’re talking to a pro who already speaks the language.

Picture this: you walk into the Skyscanner Travel Agency. There are two options in front of you — a **self-service kiosk** and a **Skyscanner agent**.

At the **kiosk**, there’s a glowing touchscreen. You tap through menus: choose dates, destinations, seat classes. Every option is there, but you have to know what you’re looking for. The interface doesn’t guide you — it just obeys. It’s efficient, but only if you already understand the system.

Across the room sits the **agent** — a human presence behind a desk. You say, “I need to be in Denver by Wednesday, but I can’t get there too late.” The agent nods, asks a few questions, fills in the gaps you didn’t think to mention. They anticipate. They smooth the friction. They know the dance.

You’ve seen this before — it’s McDonald’s all over again. Kiosk or counter. When you know exactly what you want, the screen is fast. But when the order’s complicated, when you need substitutions or explanations, the person is better. The difference isn’t hardware. It’s **competence**.

That’s the spectrum of tooling. Every tool offers its own user experience, from kiosk to agent — from pure capability to intuitive fluency. Some just execute commands. Others *teach you how* to use them as you go. And the best ones, like the agent, don’t just follow instructions they own the process to ensure you get exactly what you want.

Competency, it turns out, isn’t something you bolt on later. It’s an **emergent property of good design**. The more a tool can teach its own use, the more portable it becomes. The best tools make their know-how self-descriptive — permit the model to instantly level up to expert status. They carry their own onboarding kit.

Getting from kiosk to agent takes intentional scaffolding. For the mind to reach fluency — equipped with the structures, resources, and context that let it think like an expert — it must be booted.

## Booting Brains

But how does this work? Conceptually.

The tools are there (in the kiosk) and so is the model, but how is it onboarded?  In the real world, to become an agent the employee attends orientation, watches training videos, and reads the handbook.  That's true of models too; however, the process is more seamless — and abrupt.

Let’s go sideways for a second. Picture The Legend of Zelda.

Link, our hero, explores Hyrule — a world full of towns. Each town has its shops: weapon stores, potion sellers, inns. Outside these buildings are NPCs — non-player characters — who mostly stand still, repeating the same line forever. They’re decorative. Props.

And that suits us. Because Zork was about props too.

Now imagine our AI as Link. It spots the Skyscanner Travel Agency in a new town. Before heading in, it stops to chat with the NPC outside.

That conversation? It’s not chitchat. It’s *critical*.

In that moment, the NPC does two things:

1. **It hands over the handbook** — everything Link needs to know to operate inside the agency. That’s the **resource**: the process artifact, the contextual download, the ["I know kung fu" moment](https://www.youtube.com/watch?v=OrzgxUhnYjY).
2. **It teaches the language** — the special phrases and inputs required to operate the internal machinery. That’s the **prompt template**: the syntax and style for issuing meaningful commands inside the agency.

The whole exchange is instantaneous. But when Link walks through the door, he’s not confused. He’s fluent. He doesn’t just use the system — *he acts like he works there*.

## A Kingdom of Capable Places

Now zoom out. Hyrule isn’t one town. It’s a kingdom.

Everywhere you go, there are new buildings. And outside each one is a helpful NPC, ready to brief you. Every agency, shop, or office you visit becomes a new venue for meaningful work. When affordances are hardwired, the whole world is explorable. And actionable.

Which means that giant petri net of processes we talked about? The one with the bead tracing its way through complex workflows?

Suddenly, it's navigable. Not with custom orchestration code, but with nothing more than a wandering AI and a bit of structured text.

Even something as lightweight as ChatGPT can now coordinate serious work — issuing bookings, updating systems, validating records — because the townsfolk have been trained, the buildings are wired, and the AI knows how to move from one to the next, changing hats each time.

From the model’s perspective, it’s still Zork.

Only now, the props have teeth. The baton is real. And the kingdom is alive.
