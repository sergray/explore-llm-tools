# [LiteLLM](https://docs.litellm.ai/docs/)

Run LiteLLM locally to explore its functionality.

## Quickstart

Create environment files and fill in secret keys and DB passwords:

```shell
cat <<EOF >> .env_app
DATABASE_URL=postgresql://litellm:FILL_ME@postgres:5432/litellm
LITELLM_MASTER_KEY=FILL_ME
OPENAI_API_KEY=FILL_ME
STORE_MODEL_IN_DB='True'
LANGFUSE_HOST="http://host.docker.internal:3000"
EOF

cat <<EOF >> .env_db
POSTGRES_DB=litellm
POSTGRES_USER=litellm
POSTGRES_PASSWORD=FILL_ME
EOF
```

Run
```shell
docker-compose up
```

Then open: http://localhost:4000/ui

## Configuration
- [Config docs](https://docs.litellm.ai/docs/proxy/configs)
- [Deploy docs](https://docs.litellm.ai/docs/proxy/deploy)
- [Logging]()
    - Start Langfuse for logging traces from Litellm:
      ```shell
      cd ../langfuse
      docker-compose up
      ```
    - Save secret and public keys and add Langfuse logging callback in Litellm UI (can be also provided in YAML config).

## Impressions

- Easy to configure
    - YAML config supporting env var substitutions
- Supports various providers, internal users and virtual keys
- Has different routing mechanism, including usage based
- No logging enabled out of the box, but it is easy to set up with [Langfuse](https://docs.litellm.ai/docs/proxy/logging)

## Features to explore

- Add redis and check usage based routing
