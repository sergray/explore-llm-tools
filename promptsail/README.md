# [Prompt Sail](https://github.com/PromptSail/prompt_sail)

> Open Source LLM proxy that transparently captures and logs all interactions with LLM API

## Quickstart

Fetched `wget https://raw.githubusercontent.com/PromptSail/prompt_sail/main/docker-compose.yml`.

Then it started as simple as:

```shell
docker-compose up
```

Create `.env` file with `OPENAI_API_KEY` and the run:

```shell
dotenv run python test.py
```

## Impressesion

- Doesn't require provider keys and seems to be passing them through
- Has built-in logging, but doesn't have prompt management
- Seems to be less feature full compared to [litellm](../litellm/README.md)
