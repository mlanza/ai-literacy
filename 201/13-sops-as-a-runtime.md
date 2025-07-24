# SOPs as a Runtime

## Design the Process, Not Just the Parts

**Show me your process, and I’ll show you your results.**

AI doesn’t just let you divide work into tasks. It lets you **design processes** that would’ve been too costly or complicated before. That’s a shift every team—large or small—should be thinking about.

As W. Edwards Deming put it, *“If you can’t describe what you are doing as a process, you don’t know what you’re doing.”*

> *“A bad system will beat a good person every time.”* — Deming

That applies to AI too. If the system isn’t sound—if the specs are vague, or the stages aren’t defined—you’ll get unpredictable results, no matter how capable the AI is. What changes everything is **deliberate process design**, using AI as a teammate at each stage.

Which brings us back to something we've touched throughout: stages and waypoints.

Each stage in a process defines a place where meaningful byproducts should emerge—intermediate outputs that shape the final result. These aren’t throwaway drafts. They’re signals. Snapshots of your thinking. Opportunities to inspect, intervene, or redirect before things veer off course.

A waypoint might be a messy outline, a tone guide, a first-pass summary, or a critique of structure. What matters is that you *materialize the thought*—you make it visible. And once it’s visible, you can act on it.

Waypoints are checkpoints for quality and alignment. Each one is a chance to:

* Shape outcomes intentionally
* Halt missteps before they become entrenched
* Capture your standards as reusable artifacts

This is the hidden value of process: not just throughput, but **thought visibility**. Each stage creates space for waypoints, and each waypoint gives you leverage.

That’s how structured collaboration works—not by skipping ahead, but by knowing where to pause, inspect, and shape.

---

## SOPs: For Workers Of All Flavors

Most workplaces already use SOPs—**standard operating procedures**—to keep things consistent. Whether you're onboarding a new employee, drafting a report, or handling a system outage, SOPs describe what needs to happen, in what order, and to what standard. They're checklists for doing the work right.

Traditionally, SOPs were written for humans: concise, easy to follow, and clear enough to keep a team aligned. The point wasn’t creativity—it was **reliability**. A well-written SOP reduced errors, made training easier, and ensured predictable quality across people, projects, and time.

That hasn’t changed.

But now, something subtle has:
**The exact same SOP you wrote for your team can now be *run* by a machine.**

And that makes all the difference.

You don’t need to rewrite it in a different format. You don’t need to create a separate “AI workflow.” You simply hand it to the model—just as you would a new employee—and say, *“We’re going to follow this together.”* The AI reads the steps. It listens for your cues. And it performs the work, one stage at a time.

This is what we mean when we say your SOPs now have **runtime**.
They don’t just sit in a folder. They *do work*—because the model can read them, follow them, and help execute each step in real time.

---

## SOPs Are Not for Bots

SOPs have always been written for people—clear, action-oriented steps that help workers perform a task reliably and consistently. They’re written in plain language. They assume no special access to your brain. And they avoid tool-specific instructions unless absolutely necessary.

That same approach works beautifully for AI.

In fact, **you shouldn’t write AI-specific SOPs at all.** Not unless you’re building automation scripts. For now, your goal is simple: **keep SOPs worker-agnostic.**

Whether the actor is human or virtual doesn’t matter—what matters is that the work gets done to spec.

The old style of SOP writing still applies:

* Describe *what* needs to happen
* Explain *why* it matters
* Define what “good” looks like
* Leave room for different actors to carry it out

That’s exactly what makes SOPs so effective when AI enters the picture. A virtual teammate doesn’t need special instructions or a new format. It just needs access to the same clear, thoughtful SOP you’d give a colleague.

> **Well-written SOPs don’t need to name the worker. They name the work.**

And that’s the point: when you understand how to delegate well—human or virtual—you don’t have to change your process. You don’t build around the actor. You build around the outcome.

What changes is *who can run the steps*.
And increasingly, that includes the model sitting in your chat window.

---

## 🧭 Running the SOP Manually — With a Virtual at the Table

Let’s make this real.

You have a process file called:

> `SOP: Drafting Internal Product Docs`
> (stored at `/Documents/SOPs/drafting-product-docs.md`)

This is your standard operating procedure for creating IT-facing documentation—system overviews, onboarding guides, feature explainers. It’s used by human teammates across multiple departments.

Here’s what it includes:

1. Identify the target audience and their common questions
2. Build a topic outline focused on user workflows
3. Draft section content in plain, direct language
4. Apply tone/style guide and format for readability
5. Spot-check accuracy using examples or config snippets

Now, for your latest doc—an internal guide to the identity platform—you decide to enlist help from ChatGPT.

Not because the SOP says to.
But because **you know how to pilot a chatbot well.**

---

### 📥 Step 1: Delegating Intelligently

You begin the session by pasting in the SOP:

> **Prompt:**
> *Here’s our SOP for drafting product docs. You’re to follow it with me as I build documentation for our identity platform. Wait for my cue before each step. Let me know once you’ve read it.*
>
> \[uploads SOP]

ChatGPT replies:

> Understood. The SOP has 5 steps. Ready when you are.

You reply:

> Start with Step 1. The audience is new IT hires onboarding this quarter.

---

### 🛠️ Step 1 Output: Identify the Target Audience

> **Audience Summary:**
> – First 90 days on the job
> – Working through onboarding modules
> – High urgency for role-based access clarity
>
> **Common Questions:**
> – What does this platform manage?
> – Why do I have access to things I didn’t request?
> – How do I change my access?
> – What’s expected of me re: MFA, password changes, etc.?

You review the output and realize something’s missing.

You respond:

> Add: “What happens if I leave a team or project?” That’s often overlooked.

ChatGPT updates the list.

✅ Step 1 complete—*and better than it would’ve been alone.*

You move on:

> Let’s do Step 2.

---

### 🛠️ Step 2 Output: Topic Outline

> 1. What the Platform Manages
> 2. Who Gets Access and Why
> 3. Role Inheritance and Surprise Access
> 4. Requesting or Changing Access
> 5. Leaving a Team: What Happens
> 6. MFA and Password Management
> 7. Audit Trails and Access History

You notice how that last insight—*Leaving a Team*—has now shaped the structure itself. That’s what good process enables: judgment captured and turned into structure.

You decide it’s time to update the process.

---

### 🔁 Updating the SOP Itself

You prompt:

> Insert this line into Step 1:
>
> > “Prompt for common confusions around lifecycle events (e.g. team transfers, departures) that affect access.”

ChatGPT returns the updated markdown. You save it to:

> `/Documents/SOPs/drafting-product-docs.md`

No forked process. No separate “AI workflow.”
Just a smarter SOP—ready for any teammate to follow.

---

## Spec Your Team, Not Just Your Task

That’s the shift. You’re no longer just specifying a task. You’re **specifying a team**.

Each stage of work can be broken out, defined, and refined independently. You can even review their performance in isolation: “How is my structural editor bot doing? Are they skipping steps?” If so, update *that* part of the playbook.

You are building a well-oiled machine. And every part of it runs on the specs you provide.

---

## Bots Can Review Each Other

In the last chapter, we talked about **cloning yourself**—building reusable specifications that let the model act more like a trained version of you. But now that we’re working at the process level, it’s time to shift the metaphor.

You’re no longer just shaping clones of your own judgment.
You’re **assigning bots to specific roles**—modular, goal-oriented workers that slot into your process and carry out defined tasks.

These bots aren’t characters or personalities. They’re seat-fillers. Specialists. Helpers trained to do *just this part* of the work, *in this way*, to *this standard*. And that makes them interchangeable, inspectable, and—most importantly—**reviewable by each other**.

People often talk about AI’s weaknesses—hallucinations, misfires, overconfidence. And those are real. But here’s the twist: people have those weaknesses too. That’s why process exists. It creates **stages**. It defines **roles**. It introduces **checks**. The whole point of a well-structured SOP is to embed those controls into the flow of work.

What’s remarkable is that bots don’t just fit into that structure—they *thrive* in it.

The same bot that makes a mistake in one role can be reassigned to another—to check facts, to question assumptions, to flag inconsistencies—and it does. Not because it "feels bad," but because it’s following the system you designed.

> It’s kind of funny, honestly. The same bot that hallucinated the problem is now the one catching it—because the process told them to.

Imagine this:

* One bot drafts a summary
* A second bot fact-checks it against policy or source material
* A third bot applies tone and formatting rules

That’s not magic. That’s **structured reuse of intelligence**. Each bot runs a different version of your spec, performing a specific function inside your system.

And if one slips up? Another catches it. Because your waypoints are designed to make the invisible visible.

Even better, the same bot can switch roles midstream. With just a prompt, it changes hats:

> "Now review that summary for unsupported claims. Highlight anything that might require citation."

It can even run a web search to confirm facts—if you ask it to.

That’s not just flexibility. It’s **role awareness**.
And it only works because your process is sound.

The takeaway: these bots aren’t sidekicks. They’re workers.
And if your SOPs are clear, they know exactly what seat to fill.

---

## SOPs Are Code

I don’t want you to miss what’s happening here:

> **SOPs are now programs.**

They are the operational logic we used to hand to people.
Now we hand them to machines.

And the results are shockingly reliable—if the spec is good.

You’re no longer just writing instructions to align humans.
You’re writing instructions that *get executed*.

Let that sink in:
**Your SOPs now have runtime.**

---

## The Architecture That Makes It Work

Let’s zoom out.

Everything you’ve seen in this chapter—delegating by step, reviewing intermediate outputs, updating SOPs midstream—is made possible by a larger architecture. We’ve touched on this in earlier chapters, but let’s bring it back into view.

At the core, every AI-assisted workflow you’ve run so far is powered by three ingredients:

* **Brain**: the large language model (LLM) doing the reasoning and generation
* **Memory**: the prompt, SOPs, style guides, and uploaded artifacts you’ve provided
* **Tools**: optional add-ons that let the AI take direct action—searching files, querying systems, triggering automations

In this book, we’ve mostly stayed in the first two zones: brain and memory. You’ve learned how to prompt deliberately, structure inputs, and create reusable artifacts like SOPs and tone guides. That’s been the focus—**working manually but meaningfully**.

You’ve been riding the bike with training wheels. Not to slow you down—but to give you control.

And it’s working. You’ve seen that by handing the model a clean spec and walking through the steps yourself, you can produce quality results and even improve your own SOPs in the process. That’s not a limitation—it’s a **training ground**.

Now, we’re gesturing toward what comes next. As tools enter the picture—when the AI can take action on its own, not just respond in chat—the game changes. Suddenly, you’re not just piloting the workflow. You’re **designing a system** that runs it.

That shift is real—but it’s also premature if you haven’t yet learned the fundamentals.

So for now, this architecture serves one purpose: to help you think holistically.

Know that your artifacts (like SOPs, drafts, and specs) are part of memory. That the LLM is the brain acting on them. And that tools—when added—are what let that brain reach into the world and do something.

This is just a mental model. You don’t need to build full automation today. You just need to **understand the terrain**, so that when you’re ready to go further, you already know what levers exist.

---

## 👀 What Comes Next: A Glimpse Toward 301

If this chapter feels like a turning point, that’s because it is.

You’re no longer just asking ChatGPT to “help with a task.” You’re designing a repeatable workflow. You’re managing a system.

And here’s the best part: you’re still doing it by hand—on purpose.

You’ve learned to delegate step-by-step. To pass files, track decisions, update specs, and reuse artifacts across sessions. Each action you take is a form of **orchestration**: directing a flow of work between roles, rules, and results.

This hands-on, button-by-button approach is not a fallback. It’s the groundwork for something bigger.

Because once you can run the process manually—deliberately, consistently—you’re ready to think about automating it. Not as a shortcut, but as a natural evolution.

When tools come into play, you’ll be able to let the AI do more: pull data, update documents, notify stakeholders, even trigger reviews. But that comes later.

First, you build the system.

So if this chapter leaves you with a question, let it be this:

> *What parts of my work could I eventually hand off—not just to an assistant, but to a system that runs the way I would run it?*

That’s what we’ll explore in the next tier: **how to orchestrate multiple agents, automate intelligent handoffs, and build workflows that truly scale.**

You’re closer than you think.
