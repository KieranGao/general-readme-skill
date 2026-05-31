<!--
  Example: Library README
  Tone: Energetic
  Badge style: Flat
  Project type: npm package (typed-fetch)
  Sections: Hero, Features, Quick Start, Usage, API, Contributing, License
  This example demonstrates how to write a benefit-oriented README for a published library.
-->

<h1 align="center">typed-fetch</h1>
<p align="center">
  <strong>Type-safe fetch wrapper with automatic response parsing and error handling</strong>
  <br />
  <em>Zero Overhead · Full TypeScript Inference · Tree-Shakeable</em>
</p>

<p align="center">
  <a href="#quick-start"><img src="https://img.shields.io/badge/Quick_Start-4CAF50?style=for-the-badge" alt="Quick Start" /></a>
  <a href="LICENSE"><img src="https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge" alt="License" /></a>
</p>

<p align="center">
  <a href="https://docs.anthropic.com/en/docs/claude-code"><img src="https://img.shields.io/badge/Claude_Code-D97757?style=flat&logo=claude&logoColor=white" alt="Claude Code" /></a>
  <a href="https://github.com/features/copilot"><img src="https://img.shields.io/badge/GitHub_Copilot-000000?style=flat&logo=github&logoColor=white" alt="GitHub Copilot" /></a>
  <a href="https://cursor.sh"><img src="https://img.shields.io/badge/Cursor-000000?style=flat&logo=cursor&logoColor=white" alt="Cursor" /></a>
</p>

<p align="center">
  <a href="README.md">English</a> · <a href="README-zh.md">中文</a>
</p>

---

<p align="center">
  <img src="https://img.shields.io/github/actions/workflow/status/user/typed-fetch/ci.yml" alt="Build" />
  <img src="https://img.shields.io/npm/v/typed-fetch" alt="Version" />
  <img src="https://img.shields.io/badge/TypeScript-3178C6?style=flat&logo=typescript&logoColor=white" alt="TypeScript" />
  <img src="https://img.shields.io/badge/Node.js-339933?style=flat&logo=node.js&logoColor=white" alt="Node.js" />
</p>

## Features

- ⚡ **Zero overhead** — Built on native `fetch`, no extra dependencies
- 🔒 **Type-safe responses** — Full TypeScript inference from endpoint to response
- 🎯 **Automatic parsing** — JSON, text, blob — handled based on Content-Type
- 🛡️ **Error handling** — Typed errors with status codes and response bodies
- 🔄 **Interceptors** — Request/response middleware for auth, logging, retries
- 📦 **Tree-shakeable** — Import only what you use

## Quick Start

```bash
npm install typed-fetch
```

```typescript
import { createClient } from 'typed-fetch'

const api = createClient({
  baseUrl: 'https://api.example.com',
  headers: { Authorization: 'Bearer xxx' }
})

const user = await api.get('/users/123')
// user is fully typed based on your schema
```

## Usage

### Typed Responses

```typescript
import { createClient, type InferResponse } from 'typed-fetch'

const api = createClient({ baseUrl: 'https://api.example.com' })

// Define your API schema
type UserResponse = { id: string; name: string; email: string }

// Response is automatically typed
const user = await api.get<UserResponse>('/users/123')
console.log(user.name) // TypeScript knows this is a string
```

### Error Handling

```typescript
import { createClient, HttpError } from 'typed-fetch'

const api = createClient({ baseUrl: 'https://api.example.com' })

try {
  await api.get('/users/999')
} catch (error) {
  if (error instanceof HttpError) {
    console.log(error.status)    // 404
    console.log(error.body)      // { error: 'User not found' }
  }
}
```

### Interceptors

```typescript
import { createClient } from 'typed-fetch'

const api = createClient({ baseUrl: 'https://api.example.com' })

// Add auth token to every request
api.interceptors.request.use((config) => {
  config.headers.Authorization = `Bearer ${getToken()}`
  return config
})

// Log all responses
api.interceptors.response.use((response) => {
  console.log(`${response.status} ${response.url}`)
  return response
})
```

## API

### `createClient(options)`

Creates a typed fetch client instance.

| Option | Type | Default | Description |
|---|---|---|---|
| `baseUrl` | `string` | — | Base URL for all requests |
| `headers` | `Record<string, string>` | `{}` | Default headers |
| `timeout` | `number` | `30000` | Request timeout in ms |

### `client.get<T>(path, options?)`

GET request. Returns `Promise<T>`.

### `client.post<T>(path, body, options?)`

POST request. Returns `Promise<T>`.

### `client.put<T>(path, body, options?)`

PUT request. Returns `Promise<T>`.

### `client.delete<T>(path, options?)`

DELETE request. Returns `Promise<T>`.

### `client.interceptors.request.use(fn)`

Add a request interceptor.

### `client.interceptors.response.use(fn)`

Add a response interceptor.

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing`)
3. Commit your changes (`git commit -m 'feat: add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing`)
5. Open a Pull Request

## License

[MIT](LICENSE)
