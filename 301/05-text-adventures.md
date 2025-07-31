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

Zork’s world was made of words, but its objects felt real. The mailbox. The leaflet. The door. These were more than decorations — they were **props**. Affordances. Some obvious, some hidden. Your job was to explore, discover, move, and manipulate them to solve problems and advance the story.

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

That’s what makes MCP so radical. If you type a query into the in-game browser — `where am I?` — you might get back your actual city and state. Ask for the weather, and it tells you what’s outside *your* window. Search for nearby restaurants, and it doesn’t guess — it queries the real world.

**From the LLM’s perspective, this is still just Zork.**

Everything it does is storytelling. But when the props in that story are wired to real-world instrumentation, the fiction gains consequence. Every input sets the stage. Every object becomes an opportunity for interaction. And the AI just continues the story — one plausible word at a time — based on the entire narrative so far.

As discussed in earlier chapters, LLMs are brains in jars. They don’t see, touch, or act. All they know is text. That means the world they inhabit is always a kind of Zork. And for them to take action — real action — they need tools. But wiring those tools in has always been costly.

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

As more tools come online through MCP, the processes you care about get easier to build. Tool exposure has always been the bottleneck. Implementing the integration is 90% of the work.

Now it’s in your back pocket.

You don’t have to orchestrate the whole thing yourself. You don’t have to turn the wrench every time. MCP is what lets you finally lean hard right — where the AI doesn’t just help you think, but helps you act.
