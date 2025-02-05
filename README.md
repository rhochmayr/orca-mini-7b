# >> [Complete Setup](../../issues/new?template=complete_setup.yml)

# Ollama %%MODEL_NAME%% (%%MODEL_TAG%%)

This README provides instructions for building and running the Ollama %%MODEL%% model Docker container and using Lilypad CLI for running on the Lilypad network.

## Prerequisites

- Docker installed on your system
- GPU
- Lilypad CLI installed (for Lilypad network runs)

## Building and Running with Docker

1. Open a terminal and navigate to the directory containing the Dockerfile.

2. Build the Docker image:
   ```
   docker build -t %%REPO_NAME%% .
   ```

3. Run the container:

   Basic run with GPU support:
   ```
   docker run --gpus all %%REPO_NAME%% "your prompt here"
   ```

## Running on Lilypad Network

### Using Lilypad LocalNet

To run on the local development network:

```
go run . run --network dev github.com/%%REPOSITORY_OWNER%%/%%REPO_NAME%%:%%VERSION%% --web3-private-key <private-key> -i Prompt="your prompt here"
```

Replace `<admin_key>` with the admin key found in `hardhat/utils/accounts.ts`.

Example:
```
go run . run --network dev github.com/%%REPOSITORY_OWNER%%/%%REPO_NAME%%:%%VERSION%% --web3-private-key <private-key> -i Prompt="A haiku about Lilypad, a decentralized GPU network."
```

### Using Lilypad Main Network

To run on the main Lilypad network:

```
lilypad run github.com/%%REPOSITORY_OWNER%%/%%REPO_NAME%%:%%VERSION%% -i Prompt="your prompt here"
```

Example:
```
lilypad run github.com/%%REPOSITORY_OWNER%%/%%REPO_NAME%%:%%VERSION%% -i Prompt="A haiku about Lilypad, a decentralized GPU network."
```

## Notes

- Ensure you have the necessary permissions and resources to run Docker containers with GPU support.
- The module version (`%%VERSION%%`) may be updated. Check for the latest version before running.

## Dependencies and Credits

- [Ollama](https://ollama.com/)
- [%%MODEL_NAME%%](%%MODEL_URL%%)