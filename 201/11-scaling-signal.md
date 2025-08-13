# Scaling Signal

## Compression as a Knob: Framing the Shot With AI

You’ve compressed a photo before. Probably without thinking about it.

You clicked "Export as JPEG," dragged the slider toward "Smaller File Size," and lost a little sharpness. Fuzzy edges. Muted colors. You weren’t just shrinking an image—you were deciding how much of it mattered.

High compression = small file, fast load, fuzzy details.<br>
Low compression = crisp image, heavy file, full fidelity.<br>

You’re used to that tradeoff with pictures. You probably accept it. What you might not realize is: **you’re doing the same thing with words.**

Every time you summarize a meeting, skim a report, or ask ChatGPT to "just give you the gist," you're adjusting a compression slider. You’re deciding how much detail to preserve. You’re asking: *how much of this do I need to see clearly to get the job done?*

Now, take that JPEG slider and tilt it 90 degrees. That’s your camera lens.

That lens is your prompt.

It’s how you decide how much of a book—yes, an entire book—you want to show to ChatGPT. You choose the zoom level. You decide what gets preserved, what gets blurred, and what gets ignored. Just like with image files, there’s no "right" level. Only the right level **for the task at hand**.

But there’s something else pressing on this decision: the size of the AI’s brain at any given moment. Large language models operate in a context window—a fixed amount of memory, measured in tokens. Just like how an image takes up space on a hard drive, your prompt eats up space in the model’s short-term working memory. The more you include, the less room there is for the model’s response. That’s why compression isn’t just stylistic—it’s strategic.

When you use compression, you make space. You make room for clearer answers. You sidestep cut-off replies, shallow reasoning, and lost threads.

Let’s see what that looks like in action.

### Scenario: Building a Behavior Toolkit from Multiple Sources

You’re tasked with creating a lightweight behavioral toolkit for team leads. Something that gives them strategies for coaching new hires, running more effective one-on-ones, and recognizing small signals that might hint at friction or disengagement.

You’ve got three substantial resources on hand:

1. *Atomic Habits* by James Clear — rich with habit-building models.
2. *The Power of Moments* by Chip and Dan Heath — focused on making small experiences meaningful.
3. A 70-page internal document outlining your company’s approach to team norms and psychological safety.

Each one offers something useful—but none of them can be loaded in at full length. Not if you expect ChatGPT to do anything intelligent with them. That’s the constraint: the **context window**. You can’t upload entire books or long guides and expect clarity.

So instead, you compress them. One by one. And you treat each compression as an artifact: a lightweight, structured asset you can reuse later. Think of it as converting a giant raw photo into a clean thumbnail—something the model can work with, quickly and effectively.

#### 📕 Lens 1: *Atomic Habits* Summary Artifact

**Prompt:**
*"Summarize* Atomic Habits *in 300 words. Focus on the key takeaways and practical coaching insights."*

This gives you a compressed view of James Clear’s most important ideas—identity-based habits, the Four Laws, and examples that are perfect for a manager trying to help someone nudge a new behavior into place.

You save this summary as a standalone artifact. Not just for reference—but to upload alongside other summaries later. You’re compressing the asset now so you can synthesize across it later.

#### 📘 Lens 2: *The Power of Moments* Summary Artifact

> 🗣️ *"Summarize* The Power of Moments *in 300 words. Focus on insights that help team leads create more memorable or meaningful experiences."*

You run the exact same pattern here—same prompt shape, different book. The result is another clean, focused summary. It gives you ideas around elevation, insight, pride, and connection. Again, you save it as an artifact.

These two summaries now live as their own files—small enough to feed back into a larger prompt. You’ve dropped the file size. You’ve preserved the signal.

#### 📄 Lens 3: Internal Guide Summary Artifact

> 🗣️ *"From this team norms document, extract only the sections related to psychological safety and early warning signs of misalignment. Summarize them in bullet points with examples where possible."*

You don’t need the whole 70-page policy doc. You need the pieces that will help a manager spot when a new hire is silently struggling. This prompt gives you exactly that—tight bullet points, targeted insights, no fluff. You compress selectively.

#### 🎛️ Putting It Together: Context Engineering in Action

You upload all three artifacts—your summary of *Atomic Habits*, your summary of *The Power of Moments*, and your curated notes from the internal guide.

Then you ask:

> 🗣️ *"Based on these three documents, what are five concrete practices a team lead could use in their first 30 days to build trust, encourage productive habits, and create meaningful early experiences for a new hire? Keep the advice actionable and tie each practice back to its source."*

This is where it all pays off.

You’re not just prompting anymore—you’re **engineering the context**. You’ve fed the model just enough compressed insight to reason across multiple sources. The summaries made that possible. You didn’t try to cram in three books and a policy manual. You respected the limits—and used them as design constraints.

Now the model returns with five targeted, thoughtful, traceable recommendations—each one backed by a different source, but all shaped into something usable.

But let’s be clear—this isn’t just a clever workaround. It’s a skill you’ll need whenever you bump up against the limits of a model’s memory. Different models have different context windows. Some can handle a few thousand tokens. Others can hold a few hundred thousand. As models evolve, those ceilings will rise—and the need to compress may shift.

**But the principle remains.**

Compression isn’t just about fitting inside today’s limits. It’s about learning how to shape meaning. It’s how you make the signal fit the channel. When you can’t hand over everything, you decide what to preserve. What gets blurred. What gets dropped.

That’s not a compromise—that’s craft.

### 🧭 Another Use Case: Designing for Better Defaults

> 🗣️ *"Extract all mentions of environment design from* Atomic Habits. *Summarize how surroundings—digital or physical—can be shaped to encourage better behavior. Include examples, and focus on practical applications relevant to workplace settings."*

Your department didn’t expect it—but you got a surprise surplus budget this quarter. Not enough to renovate the building, but enough to do something meaningful. The directive from above is clear: **invest in your people.** Specifically, find ways to improve the working environment and promote healthier habits across the team.

That could mean ergonomic upgrades. Or smarter defaults in your onboarding kits. Or changes to the shared calendar and team norms. But which ones will actually *stick*?

You remember *Atomic Habits* has a whole section on **environment design**—the idea that our surroundings silently nudge our behavior. But the book’s 250 pages long, and you don’t need another summary of the Four Laws. You need one specific thread, clearly pulled and cleanly laid out.

So you aim your camera.

You send the prompt above to ChatGPT, and what you get back is a **compressed asset** focused entirely on one lens: how environment shapes behavior. It gathers examples like:

* Putting a bowl of fruit on the counter so you eat better
* Designing your home to separate “work zones” and “rest zones”
* Making good habits obvious and frictionless by changing the cues around you

It also echoes a deeper idea: **you don’t have to rely on willpower if you fix the defaults**.

That becomes your foundation.

You use that compressed artifact as the raw material for a second prompt:

> 🗣️ *"Given these environment design principles, what are five low-cost, high-impact changes we could make in an office setting to encourage healthier work habits? Focus on defaults—calendar changes, layout tweaks, visual cues, etc."*

Now the model can actually reason. You’ve cut away the noise and handed it only the pieces that matter. The camera’s in focus, the shot is framed, and the output feels relevant and actionable.

## 🧠 Wrapping It Up: Compression Is Craft

In both scenarios—building a behavior toolkit from multiple sources, and sharpening one idea from a single book—you used the same move: compression with intent.

You didn’t shrink the whole book. You didn’t drop in vague prompts and hope for the best. You aimed your lens at what mattered, trimmed the chaff, and gave the AI exactly what it needed to help.

That’s context engineering. That’s compression as strategy.

You’re not shrinking meaning. You’re focusing it.

You’re not losing signal. You’re sharpening it.

You’re not working around the AI—you’re working with it.

And that’s the point.

You’re holding the camera.

You decide what comes into frame.
