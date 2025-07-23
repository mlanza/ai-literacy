# So Why Isn’t ChatGPT Predictable?

Here’s where things get interesting.

You can attempt to have the same conversation with ChatGPT, but it'll surprise you. It won’t answer the same prompt the same way. Its uncanny ability to respond differently to the same prompt is engineered.

In a deterministic world, when prompted “Write a greeting for a welcome email,” it responds:

> Welcome to our service. We’re excited to have you on board.

every single time. Same input, same output. Guaranteed.

In a nondeterministic world, there are no guarantees. You might get any of:

> *Hey there—welcome aboard! We're thrilled you're here.*

> *So glad you joined us! Let’s make something great together.*

> *Welcome! You're officially one of us now.*

Let's face it. Variety is more interesting.

Picture an enormous Plinko board — *the size of a football field* — with hundreds of slots at the bottom. Every peg, every bump, is carefully positioned. Drop a puck from a specific spot, and in theory, its path is predictable.

But in the real world, predictability breaks down. The pegs aren’t perfect. Wind blows. Micro-vibrations shift the path. You can calculate the odds, but never the exact outcome — like Vegas odds.

Now simulate that same Plinko board in a computer. Suddenly, all those tiny variables vanish. Drop the puck from the same spot, and it follows the exact same path every time.

In *Angry Birds*, you pick your bird, pull back the slingshot at a precise angle and strength. The game’s physics engine can predict everything: the arc, the impact, the damage. No guessing — just simulation. That’s **determinism**.

It's also LLMs. They simulate likely next steps with precision. You give it an input (“drop the puck”), and it calculates the probability of every possible next word (“slot”). The model given the same input, yields the same output.

The variation comes not from the model. It's introduced after sampling its probabilities. That’s ChatGPT introducing randomness to make its responses feel more natural or surprising. They don’t always pick the highest-probability word. Instead, they control the sampling algorithm to give you variety.

What if the GPS didn't always choose the fastest route home. Instead, it finds six good ones and rolls a die. Wouldn't that be more interesting? Determinism with a dose of randomness thrown in.

In situations where consistency matters, turning off that randomness is valuable. Some apps expose these settings, some don't. ChatGPT, to brand its UX, has chosen to keep them behind the curtain.
