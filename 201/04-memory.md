# Memory 💽

If the model is the brain, then memory is the surrounding context that helps the brain do its job. But it’s important to be clear about what memory *is* — and what it isn’t.

The LLM itself doesn’t have memory. It doesn’t remember your name, your previous session, or what you asked it last week. Each time you interact with it, it starts fresh — a new, stateless moment. But what makes it feel conversational is the **scaffolding provided by the app**. That scaffolding stitches together your recent messages, the model’s past responses, and anything else the interface decides to include in the prompt. From your perspective, it feels like a chat. But under the hood, it’s just building a longer and longer payload.

That’s one kind of memory — **temporary, automatic, app-provided memory**. It holds just long enough to support a single turn. Think of it as the app’s clipboard.

But for anything more ambitious — a multi-step process, a longer project, a goal that spans more than one session — you’ll need more than a clipboard. You’ll need working memory you can carry forward yourself.

This is where **you**, the pilot of the suit, come in.

### Memory as Work Context

In the context of AI collaboration, memory refers to all the surrounding information that shapes the AI’s ability to respond well. This includes:

* The current conversation thread
* Uploaded files and documents
* Reference material (e.g., project goals, tone guides, outlines)
* Your evolving work artifacts — the drafts, notes, diagrams, summaries, or plans you and the AI build together

All of these are forms of memory — **not inside the model, but around it** — and they’re essential to meaningful work.

If you’re writing a book, your memory might include:

* A book-level outline
* Individual chapter plans
* A document describing your voice and tone
* Notes from brainstorming sessions
* A working draft
* A list of source material or footnotes

The model can’t “remember” any of these unless you **explicitly include them** in your current payload — either by uploading them, pasting them in, or summarizing and referencing them. That’s **user-provided memory**, and managing it well is key to scaling your work with AI.

### Conversations as Lightweight Memory

Even a simple chat thread functions as a kind of memory — just a fragile, temporary one. As long as the thread is short enough, the app can include the full conversation in each prompt it sends to the model. That’s why it *feels* like the chatbot remembers what you said five turns ago. But once that thread gets too long, or too complex, the model starts losing access to earlier parts. It simply can’t fit everything at once.

That’s why **intentional memory packaging** becomes more important the longer your task runs.

### Documents as Long-term Memory

One of the most reliable ways to carry memory forward is by creating artifacts — documents that store your thinking, structure your project, or summarize past collaboration. These are the building blocks that let you pick up where you left off.

They don’t have to be complex. Markdown or plain text is ideal: they’re portable, easy to share, and well suited for collaboration with chatbots. A Markdown document can hold everything from bullet-point plans to full draft sections, and it can be uploaded or copy-pasted into a chat window at any time.

These documents *are* your long-term memory. The more thoughtfully you maintain them, the more continuity and depth you’ll bring into each session.

### Memory Makes Large Tasks Possible

When you recognize your work with AI is a *series of coordinated steps* supported by a growing memory base, you’ll realize that you’re not limited to one-shot prompts or lightweight chats. You can tackle deeper, broader, more meaningful tasks — as long as you bring the right context back into play.

Once you understand how memory works — and how much of it is yours to manage — you stop being limited by the chat window. You start collaborating on real work.

---

### Versioning Reflects Iteration

If you’re already thinking in terms of capturing artifacts and building continuity, you’re halfway to a powerful habit: versioning. Once your work starts to stretch across multiple sessions and revisions, it’s natural to want a way to preserve history, compare drafts, or experiment without losing your place. That’s what versioning offers.

At its core, versioning is about saving your progress in a structured way. It gives you the ability to roll back to earlier drafts, explore new directions safely, and track how your thinking evolves over time.

**Version control systems** like Git (backed by Github for remote safekeeping) give you fine-grained tools for this kind of work — snapshots, branches, diffs, merges. These are staples in software development, but the underlying concept applies just as well to a policy document, a campaign plan, or a collaborative draft.

Even simpler tools like **SharePoint or OneDrive** provide automatic version history. They won’t show you line-by-line diffs or support branching, but they still let you recover previous versions or compare changes over time. Think of them as *lightweight versioning systems* — good enough for everyday needs.

If you’re iterating, revising, or collaborating — and especially if the outcome matters — versioning is worth being aware of. You don’t have to adopt formal tools to benefit from the mindset. Even just saving dated copies or keeping a changelog in a document can go a long way.

You don’t need to start with versioning. But if you find yourself wanting a clearer trail behind you, it’s a sign you’re already doing work that deserves it.
