# Security policy

## Reporting a vulnerability

Please report security issues privately, not in a public issue.

- Email **siamak@spritesai.com** (the privacy and security contact listed in the Sprites privacy policy), or
- use GitHub's **Report a vulnerability** button on this repository's Security tab.

Include what you found, how to reproduce it, and the client you used. Do not include access tokens,
passwords or customer data. We acknowledge reports and keep you updated until the issue is resolved.

## Scope

- The hosted MCP server at `https://mcp.sprites.ai/mcp` and its OAuth sign-in.
- The documentation and configuration files in this repository.

Out of scope: the ad platforms' own APIs and the MCP clients themselves; report those to their owners.

## How access works

- Your MCP client holds a Sprites OAuth token bound to `https://mcp.sprites.ai/mcp`, never an ad platform credential.
- Platform connections (Google, Meta, LinkedIn and the rest) are made inside Sprites and stay there.
- Every change to an ad account or a site is proposed first and applied only after a person approves it.
- Grants can be revoked from your client or from Sprites at any time; the next call fails closed.
