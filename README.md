# AI Coding Tips and Research

A repo to collect various tips, resources and other research about using AI (currently mostly LLMs) to write code that doesn't suck.

## Tools

I prefer tools that limit the reach of the LLMs used for several reasons:

- LLMs are probabilistic, hence unreliable. Will it delete all of my stuff? *Probably* not, but you can never be sure.
- In addition to their probabilistic nature and [Simon Willison’s lethal trifecta for AI agents: private data, untrusted content, and external communication](https://simonwillison.net/2025/Jun/16/the-lethal-trifecta/), most LLM tooling has terrible or zero security hardening or consideration in its design.

Further, I prefer to be able to switch between any arbitrary model at a moment's notice. This can be helpful if a model gets stuck, but is even more important to prevent lock-in with one provider. It also reduces the cost as API calls to LLMs are dramatically cheaper than standard subscriptions. Finally, it eases the transition to running models locally, which should dramatically improve confidentially, security, and cost in the next few years.

### Tools for Basic Questions and Research

When asking questions, looking up references/docs, or requesting snippets of example code:

- For Linux: [aichat](https://github.com/sigoden/aichat): All-in-one LLM CLI tool featuring Shell Assistant, Chat-REPL, RAG, AI Tools & Agents, with access to OpenAI, Claude, Gemini, Ollama, Groq, and more.
- For Android: [oxproxion](https://github.com/stardomains3/oxproxion) (on [f-droid](https://f-droid.org/en/packages/io.github.stardomains3.oxproxion/))
: oxproxion is a versatile and user-centric Android chat application designed to interact with various Large Language Models (LLMs). It provides a seamless interface for managing conversations, customizing bot personas, and saving chat histories.

### AI Coding Tools

For having the LLM generate larger amounts of code, asking more difficult questions about existing code, or making changes to an existing codebase, [Aider](https://aider.chat/) ([source](https://github.com/Aider-AI/aider)) is currently my favorite "AI Pair Programming in Your Terminal" type tool.

There are some good suggestions on how to start with Aider in [Vibe Coding With Aider: Tips And Tricks by  Mitchell A. Gordon](https://mitchgordon.me/tools/2025/02/26/aider.html).

### Agentic Coding Tools

Currently, I am not using any agentic tools due to:

- The pervasive data breach and data loss risks.
- The potential for excessive token usage. Agents have been known to get stuck in loops and burn through tokens without making progress. There seems to be some amount of progress in preventing this, but it's still an issue as of now.
- I like to stay pretty firmly in the loop given how bad LLMs are at architecting software. They can pump out code, but it tends to be very WET and poorly structured.
- Other assorted issues with agentic coding discussed in [The imminent risk of vibe coding by Matt Basta](https://basta.substack.com/p/the-imminent-risk-of-vibe-coding).
- And the jury is still out on whether these issues can be solved in LLMs. It seems like we are finally past the "just throw more data at the LLM and it'll keep getting exponentially better" idiocy that was common the last few years. [This is NOT the worst LLM you'll ever use by Ibrahim Diallo](https://idiallo.com/blog/not-the-worst-llm-you-will-ever-use) covers the basics but doesn't go deep into the reasons that these flaws are likely intrinsic to LLMs as code generators.

That said, here are the tools and techniques I'm keeping an eye on:

- [Coding Agent VMs on NixOS with microvm.nix by Michael Stapelberg](https://michael.stapelberg.ch/posts/2026-02-01-coding-agent-microvm-nix/) has some good guidance on how to isolate agentic systems from the rest of your data and system.
- [claude-code](https://github.com/anthropics/claude-code): Claude Code is an agentic coding tool that lives in your terminal, understands your codebase, and helps you code faster by executing routine tasks, explaining complex code, and handling git workflows - all through natural language commands.
- [goose](https://github.com/block/goose/): an open source, extensible AI agent that goes beyond code suggestions - install, execute, edit, and test with any LLM
