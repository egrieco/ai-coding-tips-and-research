# AI Coding Tips and Research

A repo to collect various tips, resources and other research about using AI (currently mostly LLMs) to write code that doesn't suck.

## Tools

I prefer tools that limit the reach of the LLMs used for several reasons:

- LLMs are probabilistic, hence unreliable. Will it delete all of my stuff? *Probably* not, but you can never be sure.
- In addition to their probabilistic nature and [Simon Willison’s lethal trifecta for AI agents: private data, untrusted content, and external communication](https://simonwillison.net/2025/Jun/16/the-lethal-trifecta/), most LLM tooling has terrible or zero security hardening or consideration in its design.

My preferred tools by category are:

### Basic Questions and Research

When asking questions, looking up references/docs, or requesting snippets of example code:

- For Linux: [aichat](https://github.com/sigoden/aichat): All-in-one LLM CLI tool featuring Shell Assistant, Chat-REPL, RAG, AI Tools & Agents, with access to OpenAI, Claude, Gemini, Ollama, Groq, and more.
- For Android: [oxproxion](https://github.com/stardomains3/oxproxion) (on [f-droid](https://f-droid.org/en/packages/io.github.stardomains3.oxproxion/))
: oxproxion is a versatile and user-centric Android chat application designed to interact with various Large Language Models (LLMs). It provides a seamless interface for managing conversations, customizing bot personas, and saving chat histories.

### More Complete Coding Assistance

For having the LLM generate larger amounts of code, asking more difficult questions about existing code, or making changes to an existing codebase, [Aider](https://aider.chat/) ([source](https://github.com/Aider-AI/aider)) is currently my favorite "AI Pair Programming in Your Terminal" type tool.

There are some good suggestions on how to start with Aider in [Vibe Coding With Aider: Tips And Tricks by  Mitchell A. Gordon](https://mitchgordon.me/tools/2025/02/26/aider.html).
