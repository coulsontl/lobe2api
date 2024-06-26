## lobe2api
Welcome to the lobe2api, offering free self-hosted API access to lobe-chat with OpenAI's familiar structure, so no code changes are needed.

## Features

- **Streaming Response**: The API supports streaming response, so you can get the response as soon as it's available.
- **API Endpoint Compatibility**: Full alignment with official OpenAI API endpoints, ensuring hassle-free integration with existing OpenAI libraries.
- **Complimentary Access**: No charges for API usage, making advanced AI accessible to everyone even **without an API key**.

## Installing/Self-Hosting Guide

### Using docker

1. Ensure Docker is installed by referring to the [Docker Installation Docs](https://docs.docker.com/engine/install/).

2. Clone repository
   ```bash
   git clone https://github.com/k0baya/lobe2api.git && cd lobe2api
   ```

3. Edit the `.env` file.

4. Run the following command:
   ```bash
   docker compose up -d
   ```

5. Done! You can now connect to your local server's API at:
   ```
   http://localhost:3000/v1/chat/completions
   ```
   Note that the base URL is `http://localhost:PORT/v1`.

### From source code

1. Edit the `.env` file, add variables such as `PORT` 、 `BASE_URL` 、 `AUTH_TOKEN` .

   |Key|Default Value|Note|
   |-|-|-|
   |`PORT`|`3000`|Port that lobe2api listens on|
   |`BASE_URL`|`http://localhost:1234`|That lobe-chat url that you need to reverse|
   |`AUTH_TOKEN`||Authentication for your lobe2api|
   |`ACCESS_CODE`||The access code for the lobe-chat url that you need to reverse|

2. Run the following command:
   ```bash
   npm install
   npm run start
   ```

3. Done! You can now connect to your local server's API at:
   ```
   http://localhost:PORT/v1/chat/completions
   ```
   Note that the base URL is `http://localhost:PORT/v1`.

## Usage Examples

Leverage the same integration code as OpenAI's official libraries by simply adjusting the API key and base URL in your requests. For self-hosted setups, ensure to switch the base URL to your local server's address as mentioned above.

### Example Usage with curl

```bash
curl --location 'http(s)://localhost:PORT/v1/chat/completions' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer AUTH_TOKEN' \
--data '{
  "model": "gpt-3.5-turbo",
  "stream": true,
  "messages": [{"role": "user", "content": "Tell me a story about socialism."}]
}'
```
## License

This repository is under the AGPL-3.0 License. Refer to the [LICENSE](LICENSE) file for detailed information.