# Aider Setup and Tips

[Aider](https://aider.chat/) is an open source, CLI based, non-agentic AI coding tool that integrates with [Git](https://git-scm.com/).

Using an open source tool like this has some advantages:

- No risk of lock-in from the provider.
- Use multiple providers and models. Switch them on a whim to compare performance.
- Using APIs directly can be much cheaper than using web interfaces for language models (unless you get unlimited tokens on a subscription).
- Git integration reduces risk and allows easy review of changes, reversal of unwanted changes via `/undo`, and experimentation via Git branches.

The [Aider Documentation](https://aider.chat/docs/) is quite good, but some specific tips and tricks follow.

## API Keys

To use Aider, you'll need [API Keys](https://aider.chat/docs/config/api-keys.html) for one or more providers:

- You can sign up directly with one of the [General Purpose LLMs](https://github.com/kostja94/awesome-ai-tools?tab=readme-ov-file#large-language-models-llms) such as [Claude Developer Platform](https://platform.claude.com/).
- Or you can use an [AI Aggregation Platform](https://github.com/kostja94/awesome-ai-tools?tab=readme-ov-file#ai-aggregation-platforms) such as [OpenRouter](https://openrouter.ai/) to allow rapidly switching between models for a small additional fee (currently [5.5% on OpenRouter](https://openrouter.ai/docs/faq#pricing-and-fees)).

More resources can be found in [awesome-ai-tools](https://github.com/kostja94/awesome-ai-tools).

## Config File

Once you have your API Keys, they need to be made available to Aider.

You'll need to put the keys in [Aider's config file](https://aider.chat/docs/config/aider_conf.html). A [sample config file](https://aider.chat/docs/config/aider_conf.html#sample-yaml-config-file) can be downloaded to `~/.aider.conf.yml` and then modified.

### Aider Config

Some specific config options you may wish to change:

```yaml
# This is the main model that is in charge of making coding changes. It can also be changed at runtime.
model: anthropic/claude-opus-4-5
# See all available models for Anthropic with: aider --list-models anthropic/

# API Keys
openai-api-key: ""
anthropic-api-key: ""
api-key:
  # Specify the OpenRouter API key
  - openrouter=""

# Set other models
weak-model: anthropic/claude-3-5-haiku-20241022
editor-model: anthropic/claude-sonnet-4-5

# Other misc settings
show-diffs: false # these don't actually work that well, better to just diff in another terminal or tab
gitignore: false # we'll set a global ignore
attribute-committer: true
attribute-co-authored-by: true
analytics-disable: true
```

### Git Config

Instead of having Aider modify the local `.gitignore` in each git repository, we can modify the global Git ignore file `~/.config/git/ignore` and add the following lines:

```gitignore
.aider.chat.history.md
.aider.input.history
.aider.tags.cache.v4/
```

Or simply:

```gitignore
.aider.*
```

## Usage Tips

There are some good suggestions on how to start with Aider in [Vibe Coding With Aider: Tips And Tricks by  Mitchell A. Gordon](https://mitchgordon.me/tools/2025/02/26/aider.html).
