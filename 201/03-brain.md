# Brain 🧠

At the heart of every chatbot is the model. This is the brain. It doesn’t store memories. It doesn’t update with time. It doesn’t know who you are or what you’re trying to do. It simply responds to the input it receives, based on patterns it learned during training.

That’s important to understand: **the model is stateless**. Each time you interact with it, it has no idea what came before — unless that information is included in the payload. From its point of view, every request is a one-time job. No history, no assumptions. Just a single, isolated input stream.

And that stream — the **payload** — is everything.

You may think you’re just sending a sentence when you press Enter, but in reality, the app around the model (like ChatGPT) is assembling much more: your recent conversation, your past clarifications, even relevant documents or tools you’ve activated. That full bundle is handed to the model as one long string of text. It’s that bundle — not the interface, not the chat history — that the model actually sees.

This is why the *quality* of the payload matters. It’s the sole input the model uses to generate its response. If key context is missing, the model won’t “know” to ask. If the prompt is vague, the answer will be vague. The model doesn’t intuit your needs — it computes based on what’s there.

Now, there are two common ways to arrive at a strong payload:

* **All at once** – You carefully think through the task, draft a clear prompt, include relevant details, and attach supporting information up front. It’s a one-shot approach, requiring deliberate forethought — and when done well, it works beautifully.
* **Iteratively** – You start with a rough question, then refine. You adjust your wording, clarify your needs, add examples or constraints across several turns. Each round, the app updates the payload to include your latest thinking, until you land on the version that works.

Both paths lead to the same place: a payload that gives the model what it needs to deliver a useful response. Whether you arrive there through careful planning or trial and error doesn’t matter. What matters is that the final volley — the one that reaches the model — is clear, complete, and well-structured.

That’s how the brain does its best work.

As a user, your job is to recognize that the model isn’t “having a conversation” in the way you are. It’s processing an input — one that you, with the help of the app, are responsible for shaping. And the better that input, the better the output.

In the next section, we’ll turn our attention to the memory — not the model’s, but the app’s — and how it scaffolds each conversation to help you build better payloads without starting over every time.
