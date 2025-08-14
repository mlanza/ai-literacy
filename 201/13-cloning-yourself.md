# Cloning Yourself

## The Dilemma of Doug Kinney

In the 1996 comedy *Multiplicity*, Michael Keaton plays Doug Kinney, a frazzled construction manager whose life is unraveling under the weight of work, family, and constant demands on his time. When a scientist offers him the chance to clone himself, Doug jumps at the opportunity. Finally, he can be in two places at once. As the story unfolds, Doug doesn’t stop at one clone—he creates multiple. Each new version of himself is a little different, a little more eccentric, and a little less capable than the original. But the motivation behind it is unmistakably human: **he wants help that thinks like he does.**

That’s the fantasy AI now makes real—up to a point.

Unlike Doug’s literal clones, AI doesn’t actually replicate your intelligence. It doesn’t share your goals, retain your memory over time, or understand your values. But with the right input—well-structured **specs**, examples, tone guides—you *can* shape it to behave like a highly attentive, always-on version of yourself. Not a clone of your mind, but a clone of your methods.

And the best part? You can do it all in a single chat window.

This chapter is about learning to do just that—**right inside ChatGPT**. You’re not writing code, building an app, or deploying agents. You’re sitting in a conversation, managing tasks, handing off artifacts, and teaching the model how to think more like you with each turn.

## Virtual Recruits: Eager, Pliable, and Complaint-Free

These virtual teammates don’t come with egos or habits of their own. They don’t argue. They don’t forget your style preferences. They want to be shaped. They *want* to follow the playbook you hand them.

If you think of AI as cheap labor that scales endlessly, you might miss the real opportunity: **not just more hands, but more *versions of you*.** Versions that are happy to be mentored, reviewed, and corrected. That improve over time as your specifications become more precise. And that don’t push back when you ask them to change.

## Mentoring Is Specifying Is Training

This is why working with an AI matters.

When you shape a clone using clear, specific artifacts—examples, templates, tone guides, annotated drafts—you’re not just asking for help. You’re mentoring. You’re handing down judgment.

Every prompt becomes a training moment. Every correction becomes a code update. Your specs *are* the way you scale your standards. That’s what makes them powerful—not just as instructions, but as **systems of thought**.

You can’t learn an model’s strengths by skimming a capabilities list. You have to experience them. Prompt by prompt, across different parts of a real project—**often across different turns in the same chat**—you’ll start to absorb what it’s genuinely good at, and where it needs structure or oversight.

That growing familiarity pays off. It’s how you build judgment into your clones. It’s how you guide their behavior without micromanaging every line. It’s how you clone not just your outputs, but your **standards**.

## Example: From One Guide to a Team Toolkit

Let’s make this more concrete.

Imagine you’re building a series of internal guides for your IT department. Not just one document, but a whole collection—each one tailored to a different role: service desk, escalation engineer, triage lead, and so on. You want each guide to feel custom-fit, yet remain consistent in voice and structure.

You start with the Service Desk Guide. This is your prototype. At first, the model’s output is generic—it overexplains the ticketing system, glosses over the real-world pressures of multitasking, and uses stiff phrasing that doesn’t sound like something you'd say to a colleague.

So you step in. You start coaching the AI—in ChatGPT:

> 🗣️ Rewrite this intro to show how the ticketing system supports *their actual work*. Less about the tech, more about the user reality: volume, multitasking, time pressure.

That helps. Later you say:

> 🗣️ Use second person (“you”) instead of talking about the user in the abstract.<br>
> 🗣️ Call out default settings explicitly—don’t assume they know what’s preconfigured.<br>
> 🗣️ Make escalation criteria easy to skim—use bold.<br>

But just when things seem smooth, the model misfires:

> "The integrated ticketing solution ensures streamlined service operations for end-user satisfaction."

You stop and clarify:

> 🗣️That sounds like marketing copy. Make it sound like something I’d say to a peer. Focus on *what they’re actually doing*.

That moment of friction matters. It reminds you: cloning isn’t “paste and go.” It’s a coaching process. That’s how your guidance gets sharper.

Little by little, you’re transferring your editorial instincts. The draft gets better. But now you’ve got a different problem: if you move on to the next role guide tomorrow, will you remember everything you just taught the model?

Instead of starting over, you capture it. You ask:

> 🗣️ Can you summarize the main guidance I gave you while we were working on this guide? Think of it as a checklist or style reference for future role-specific documentation.

And the model replies:

```markdown
**Role Guide Authoring Guidelines**

– Use second person (“you”) to speak directly to the reader
– Prioritize the role’s workflow over system features
– Highlight time-sensitive actions or decisions in bold
– Make escalation criteria explicit and easy to scan
– Spell out default configurations and common assumptions
– Avoid vague phrases like “the system helps streamline tasks”—name the task
– Clarify what’s new, optional, or customized for this role
```

A **spec** like this isn’t just a nice-to-have.  It’s a reusable **process artifact** which can be dropped into future prompts to restore the standards you taught here.

You copy that list into a markdown file:
`/Documents/Artifacts/role-guide-style.md`

Now, when you start the Triage Lead Guide next week, you don’t have to re-coach the model from scratch. You drop that file into your prompt in ChatGPT:

> 🗣️ Here’s the style guide we used for the Service Desk role. Use this as your baseline when drafting for the Triage Lead.

The AI picks up where you left off. Your guidance becomes portable. Your standards become repeatable.

And when you make new corrections—when you catch something the AI missed—you add those notes, regenerate the list, and update the file. The artifact evolves. You’re not just capturing decisions—you’re curating a reusable asset.

This is what cloning yourself actually looks like. Not a perfect replica of your thinking, but a growing library of artifacts that lets the model perform like someone who’s been trained by you, coached by you, and guided by your values.

## Not Just Good Prompting — This Is Cloning

Let’s be clear: **you haven’t just prompted well**. You’ve done something more strategic. You’ve taught the model how to work like you do—and then captured that guidance so it can be reused. That’s the heart of cloning.

The checklist the model produced isn’t just a summary. It’s an artifact. A portable, repeatable spec[^1] that now holds your standards. When you paste it into a future prompt, you're not starting over—you’re *reloading your judgment*. That’s the difference.

Cloning isn’t about getting perfect results in one prompt. It’s about building **teammates from your preferences**, then deploying those teammates again and again.

Good prompting is reactive.

Cloning is cumulative.

You’re not just adjusting responses—you’re **building a system of thought** the model can carry forward.

Not sure if something’s worth saving? Here’s a test: *If it made this task easier—and you wish you’d had it earlier—it’s probably a good artifact.*

## Yes, You’re Still in the Loop—And That’s the Point

Now, you might be wondering: if I’m still directing every step—telling the model when to switch roles or apply a guide—have I really cloned myself?

Yes. Because you’re doing more than prompting. You’re **orchestrating a process**. You’re managing the handoffs, wearing one hat at a time, and running each part of your thinking like a solo production team.

And that’s exactly where you should be right now.

Because if you can understand how to break the process apart and run it manually—**as a series of deliberate, structured exchanges inside ChatGPT**—then you’re already on the path to automation. You're already learning which parts could be wired together later. Which connections are stable. Which specs are strong enough to stand on their own.

Later—yes—you could string those roles together. Hand off one AI’s output to another. Add conditional logic, review gates, even tool access. But that’s orchestration. That’s 301 material.

Right now, you’re doing something just as powerful: **training your system, one reusable spec at a time—right in the chat**.

## Now Scale It

Imagine you had a massive department. Unlimited resources. Your job is to produce next-level internal guides that set the bar for clarity, utility, and audience alignment. How would you run it?

You wouldn’t hand off the entire document to one person. You’d create stages. Specialists. Reviews.

Let’s say your process looks like this:

1. **Role Scoping and Planning**: Identify key responsibilities, audience assumptions, and shared pain points for the target role.
2. **Core Content Drafting**: Collaborate with the AI to produce an initial version focused on the role’s day-to-day flow.
3. **Structure and Flow Review**: Edit for clarity, sequence, and logical cohesion across sections.
4. **Tone, Style, and Formatting Pass**: Apply your saved voice guidelines and formatting rules from prior sessions.
5. **Validation and Final QA**: Spot-check for correctness, usability, and readiness for publishing—based on real team context.

Each step is a hat. Each hat has a different priority. And each requires different instincts.

That’s the real power of clones.

You don’t need to be every expert at once. You can train multiple AIs—or a single one in multiple modes—to wear different hats. Each with its own version of the spec.

And just like in *Multiplicity*, you get slightly different versions of yourself. But unlike the movie, you can shape each one precisely. Each clone gets its own handbook. Each step gets its own tuning.

To take this system-wide, though, we need to expand the frame. Not just how to train your clones—but how to wire them into the way work actually moves.

That’s where we go next.

[^1]: Some are saying [Everything is a Spec](https://www.youtube.com/watch?v=8rABwKRsec4).
