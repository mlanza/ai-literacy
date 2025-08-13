# SOPs as a Runtime

## Design the Process, Not Just the Parts

**Show me your process, and I’ll show you your results.**

AI doesn’t just let you divide work into tasks. It lets you **design processes** that would’ve been too costly or complicated before. That’s a shift every team—large or small—should be thinking about.

> *“If you can’t describe what you are doing as a process, you don’t know what you’re doing.”* — W. Edwards Deming

That applies to AI too. If the system isn’t sound—if the specs are vague, or the stages aren’t defined—you’ll get unpredictable results, no matter how capable the AI is. What changes everything is **deliberate process design**, using AI as a teammate at each stage.

Which brings us back to something we've touched throughout: stages and waypoints.

Each stage in a process defines a place where meaningful byproducts should emerge—intermediate outputs that shape the final result. These aren’t throwaway drafts. They’re signals. Snapshots of your thinking. Opportunities to inspect, intervene, or redirect before things veer off course.

A waypoint might be a messy outline, a tone guide, a first-pass summary, or a critique of structure. What matters is that you *materialize the thought*—you make it visible. And once it’s visible, you can act on it.

Waypoints are checkpoints for quality and alignment. Each one is a chance to:

* Shape outcomes intentionally
* Halt missteps before they become entrenched
* Capture your standards as reusable artifacts

This is the hidden value of process: not just throughput, but **thought visibility**. Each stage creates space for waypoints, and each waypoint gives you leverage.

## SOPs Are for Workers

Standard operating procedures—perhaps the most popular kind of **process artifact**—were always designed for people. They're clear, step-by-step guides to help workers produce consistent, reliable outcomes. What’s changed is not the format, but the scope of who counts as a “worker.”

Today, that includes the AI sitting in your chat window.

You don’t need a special AI playbook. The same SOP that guides a new teammate through drafting internal docs can now guide ChatGPT through the same process. Paste it in, give cues, and proceed step by step. The model doesn’t need translation. It needs structure—and SOPs already provide it.

That’s the shift: your SOPs now have **runtime**. They don’t just describe what should happen; they **execute** when you walk the model through them.

And the format still works. The best SOPs don’t name the worker—they name the work. They define what needs to be done, why it matters, and what “good” looks like, without assuming who—or what—is doing it.

This isn’t about writing for bots. It’s about designing systems that any worker—human or virtual—can step into. That’s how you scale not just output, but quality. You’re not building around personalities. You’re building around **outcomes**.

An AI isn’t a sidekick. It’s a seat-filler. And with the right SOP, it can sit down and get to work.

## 🧹 Running the SOP Manually — With a Virtual at the Table

Let’s make this real.

You have a process file called:

> `SOP: Drafting Internal Product Docs`<br>
> (stored at `/Documents/SOPs/drafting-product-docs.md`)<br>

This is your standard operating procedure for creating IT-facing documentation—system overviews, onboarding guides, feature explainers. It’s used by human teammates across multiple departments.

Here’s what it includes:

1. Identify the target audience and their common questions
2. Build a topic outline focused on user workflows
3. Draft section content in plain, direct language
4. Apply tone/style guide and format for readability
5. Spot-check accuracy using examples or config snippets

Now, for your latest doc—an internal guide to the identity platform—you decide to enlist help from ChatGPT.

Not because the SOP says to.
But because **you know how to pilot a chatbot well**.

> **Note:** While the SOP "executes" when stepped through with ChatGPT, it does *not* run autonomously. You are the runtime. In constrained chat environments like this, the model has no memory of prior files or state unless you supply it. You may need to upload files, paste content, or repeat intermediate outputs to carry them forward. The bot can help do the work, but *you have to orchestrate it*.

### 📥 Step 1: Delegating Intelligently

You begin the session by pasting in the SOP:

> 🗣️*Here’s our SOP for drafting product docs. You’re to follow it with me as I build documentation for our identity platform. Wait for my cue before each step. Let me know once you’ve read it.*<br>
> \[uploads SOP]<br>

ChatGPT replies:

> Understood. The SOP has 5 steps. Ready when you are.

You reply:

> 🗣️ Start with Step 1. The audience is new IT hires onboarding this quarter.

### 🛠️ Step 1 Output: Identify the Target Audience

> **Audience Summary:**<br>
> – First 90 days on the job<br>
> – Working through onboarding modules<br>
> – High urgency for role-based access<br> clarity
>
> **Common Questions:**<br>
> – What does this platform manage?<br>
> – Why do I have access to things I didn’t request?<br>
> – How do I change my access?<br>
> – What’s expected of me re: MFA, password changes, etc.?<br>

You review the output and realize something’s missing.

You respond:

> 🗣️ Add: “What happens if I leave a team or project?” That’s often overlooked.

ChatGPT updates the list.

🗓️ Step 1 complete—*and better than it would’ve been alone.*

You move on:

> 🗣️ Let’s do Step 2.

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

### ♻️ Updating the SOP Itself

You prompt:

> 🗣️ Insert this line into Step 1: “Prompt for common confusions around lifecycle events (e.g. team transfers, departures) that affect access.”

ChatGPT returns the updated markdown. You save it to:

> `/Documents/SOPs/drafting-product-docs.md`

No forked process. No separate “AI workflow.”
Just a smarter SOP—ready for any teammate to follow.

## Spec Your Team, Not Just Your Task

That’s the shift. You’re no longer just specifying a task. You’re **specifying a team**.

Each stage of work can be broken out, defined, and refined independently. You can even review their performance in isolation: “How is my structural editor bot doing? Are they skipping steps?” If so, update *that* part of the playbook.

You are building a well-oiled machine. And every part of it runs on the specs you provide.

## Multiple Hats, Fewer Blind Spots

In the last chapter, we talked about **cloning yourself**—building reusable specifications that let the model act more like a trained version of you. But now that we’re working at the process level, it’s time to shift the metaphor.

You’re no longer just shaping clones of your own judgment.
You’re **assigning bots to specific roles**—modular, goal-oriented workers that slot into your process and carry out defined tasks.

These bots aren’t characters or personalities. They’re seat-fillers. Specialists. Helpers trained to do *just this part* of the work, *in this way*, to *this standard*. And that makes them interchangeable, inspectable, and—most importantly—**reviewable by each other**.

People often talk about AI’s weaknesses—hallucinations, misfires, overconfidence. And those are real. But here’s the twist: people have those weaknesses too. That’s why process exists. It creates **stages**. It defines **roles**. It introduces **checks**. The whole point of a well-structured SOP is to embed those controls into the flow of work.

What’s remarkable is that bots don’t just fit into that structure—they *thrive* in it.

The same bot that makes a mistake in one role can be reassigned to another—to check facts, to question assumptions, to flag inconsistencies—and it does. Not because it “feels bad,” but because it’s following the system you designed.

Imagine this:

* One bot drafts a summary
* A second bot fact-checks it against policy or source material
* A third bot applies tone and formatting rules

That’s not magic. That’s **structured reuse of intelligence**. Each bot runs a different version of your spec, performing a specific function inside your system.

And if one slips up? Another catches it. Because your waypoints are designed to make the invisible visible.

Even better, the same bot can switch roles midstream. With just a prompt, it changes hats:

> 🗣️ "Now review that summary for unsupported claims. Highlight anything that might require citation."

It can even run a web search to confirm facts—if you ask it to.

That’s not just flexibility. It’s **role awareness**.

And it only works because your process is sound.

> *“A bad system will beat a good person every time.”* — W. Edwards Deming

That’s the point. The fix didn’t come from talent or intuition—it came from process.

Ironic that the same bot that made the error in a **different seat**—a different role, a different spec—caught it?

Maybe.  But the leverage of systems is not that they’re perfect.  It’s that they make recovery routine.

## SOPs Are Code

I don’t want you to miss what’s happening here:

> **SOPs are now programs.**

They are the operational logic we used to hand to people.
Now we hand them to machines.

And the results are shockingly reliable—if the spec is good.

You’re no longer just writing instructions to align humans.
You’re writing instructions that *get executed*.

That’s what makes this moment different: the same SOP that once trained a junior teammate can now run an AI worker in the loop. Your documents don’t just describe—they *do*.

You’ve crossed a line: from writing about work to actually running it.
And that opens the door to something bigger.

## 💻 Repeatability Before Systemization

An SOP isn’t just a checklist. It’s a *design space*—where you shape and test the logic of your process before locking anything in.

And before that design becomes a system, it needs to be **repeated**.

Why? Two big reasons.

First: **understanding**.<br>
You can’t automate what you don’t fully grasp. Running the SOP manually forces you to clarify every step, outcome, and dependency. It exposes the seams. It teaches you what “good” really looks like—so you don’t end up encoding confusion into the system itself.

Second: **adaptability**.<br>
SOPs are malleable. Systems are not. Once you start plugging in tools, triggers, or agents, you’re locking in choices—some of which you haven’t fully tested yet. Systemization is just SOPs with machines plugged in. And if you do it too early, you risk freezing flaws into place.

That’s why we don’t rush. We repeat.

Every pass through the SOP—by hand, with AI in the loop—is a test run that sharpens your process and prepares it for scale.

## 🧪 From One Run to Many

If you’ve made it this far, you’re already running experiments—using a chatbot to walk through a process, step by step. That’s not trivial. That’s a rehearsal. It’s a real-world loop, with real byproducts, that gives you something to improve next time.

And that’s the seed of something bigger.

Not a system yet. But a pattern. A rhythm.
One you can repeat. One that reveals friction. One that gets better with every pass.

You’re not automating yet—but you are **making things visible**. And that’s how process becomes design.

## 💡 What Makes a Process Worth Keeping?

Not every process needs to be formalized. But some will **prove themselves** through use.

The signs:

* You’ve run it more than once
* Each run leaves behind a set of useful artifacts
* You’ve refined how it works—tweaked prompts, added checks, clarified steps
* Others could benefit from using it too

That’s when it’s worth turning the corner. From “something I do” to “something we can run.” From ad hoc to asset.

## 🪑 A Chatbot Is a Seat at the Table

You don’t need a full orchestration engine or a scriptable bot framework to get started. If you can describe a process, and if it leaves visible traces behind, you can walk a chatbot through it.

That might look like:

* Generating a first-pass outline for a guide
* Reviewing that outline for tone or structure
* Reworking it after feedback
* Turning those changes into a reusable prompt or SOP

Each of those steps? Repeatable. Reviewable. Learnable.

The chatbot doesn’t remember—but you do.
And every time you loop through, the process gets sharper.

## 🧭 The Next Threshold

Don’t think about automation yet.
Don’t reach for agents.
Don’t systemize what you haven’t lived through.

But do notice what’s working.

Do notice what leaves behind structure.

Do notice what feels like it could be **run again**.

That’s the threshold that matters: when something becomes steady enough to hold its shape.
That’s when systemization becomes a real option—not a buzzword, but a next step.

For now?
Just get good at running things through.

You’ve already got a chatbot.
You’ve already got a want.
And you’ve already got a process—at least the beginnings of one.

That’s enough to begin.
