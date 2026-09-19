# AllSolos MCP Server

Remote, read-only [Model Context Protocol](https://modelcontextprotocol.io) server for the [AllSolos](https://www.allsolos.com) jazz solo database. Connect it to any MCP-compatible host (Claude, ChatGPT, etc.) to search and explore thousands of cataloged jazz solos.

## Endpoint

- **URL:** `https://mcp.allsolos.com`
- **Transport:** Streamable HTTP
- **Auth:** none — public, read-only

## Tools

| Tool | Description |
| ---- | ----------- |
| `search_allsolos` | Search the catalog for soloists, tunes, albums, recordings, and solos. Input: `query` (string). |
| `get_solo` | Retrieve one solo by AllSolos ID, or a random solo when no ID is given. Includes an embedded YouTube player cued to the solo via an MCP Apps widget. |
| `get_album` | Retrieve one album by AllSolos ID, or a random album. |
| `get_recording` | Retrieve one recording by AllSolos ID, or a random recording. |
| `get_insight` | Retrieve a music insight from the AllSolos catalog. |

All tools are annotated `readOnlyHint: true` — the server never modifies data. Results include links back to entity pages on allsolos.com (tagged `utm_campaign=allsolos_mcp`).

## Data source

The server is a thin wrapper over the public AllSolos API (`https://api.allsolos.com`), which backs [allsolos.com](https://www.allsolos.com) — a searchable catalog of the world's musical solos with YouTube players cued to cataloged timestamps.

## Connecting

Point your MCP client at `https://mcp.allsolos.com` using Streamable HTTP transport. No API key or OAuth required.
