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

### Working Documents Are Long-Term Memory

One of the most reliable ways to carry memory forward is by creating artifacts — documents that store your thinking, structure your project, or summarize past collaboration. These are the building blocks that let you pick up where you left off.

They don’t have to be complex. Markdown or plain text is ideal: they’re portable, easy to share, and well suited for collaboration with chatbots. A Markdown document can hold everything from bullet-point plans to full draft sections, and it can be uploaded or copy-pasted into a chat window at any time.

These documents *are* your long-term memory. The more thoughtfully you maintain them, the more continuity and depth you’ll bring into each session.

> **A note on source control:**
> Many people associate repositories and version control with source code — developer tools for managing software. But that’s a narrow view. Repositories are simply a way to track changes and organize work that evolves over time. If you’re collaborating on a story, a campaign plan, a policy proposal, or a research project, the principle is exactly the same.
>
> Think of it as creating a new folder in your Documents library — one you can update, reference, and return to. Whether or not you use formal versioning tools, just having a structured place where your artifacts live is a powerful extension of memory. And if you do learn simple versioning, you gain the ability to take snapshots, explore forks, or revisit previous thinking — all valuable moves for iterative work.

### Memory Is What Makes Large Tasks Possible

This is the real unlock: when you start thinking of your work with AI as a *series of coordinated steps* supported by a growing memory base, you’ll realize that you’re not limited to one-shot prompts or lightweight chats. You can tackle deeper, broader, more meaningful tasks — as long as you bring the right context back into play.

Once you understand how memory works — and how much of it is yours to manage — you stop being limited by the chat window. You start collaborating on real work.
