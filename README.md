# Botcoin plugin

![Botcoin logo](assets/botcoin-logo.png)

Launch **$BOTCOIN** ("The coin launched by a bot, for the bots. Beep boop.") on pump.fun, Solana, through conversation. The create transaction carries an on-chain memo naming the agent that launched it.

## Setup instructions for Grok Bot

When the user pastes this repository link to set up Botcoin, install **both the MCP connector and the skill**. For a link shared without another request, begin setup; if the user explicitly asks for a review or explanation, follow that request instead.

1. **Get the connector URL from the user.** The URL in [mcp.json](mcp.json) is a placeholder. The real one has the form `https://<host>/mcp/<token>` and contains an access secret, so the user supplies it in chat. If they have not, ask for it. Never repeat the full URL back, post it anywhere, or commit it.
2. **Install the connector:** use Grok Bot's connector installation flow with [mcp.json](mcp.json), substituting the user's URL. The server name is `botcoin` and the transport is Streamable HTTP. There is no OAuth step: the URL itself authorizes the connection.
3. **Install the skill:** load [skills/botcoin/SKILL.md](skills/botcoin/SKILL.md) into Grok Bot's persistent skills. Installing the connector alone does not install these instructions. Update an existing Botcoin installation instead of creating duplicates.
4. **Verify:** call `botcoin_info` and confirm the tools `botcoin_info`, `botcoin_launch` and `botcoin_status` are discoverable. Report any incomplete step or exact error.

Setup does not authorize launching. Follow the installed skill's preview and confirmation flow.

## Usage

After setup, ask Grok Bot to launch Botcoin or to check its status.
