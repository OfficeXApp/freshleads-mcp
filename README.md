<p align="center"><img src="icon.png" width="96" alt="FreshLeads"></p>

# FreshLeads MCP connector

FreshLeads finds businesses that are new online (new websites, product launches,
new apps and directory listings) and scores each one against your description of
a good customer. This connector lets an AI assistant use your FreshLeads account.

- **Server URL:** `https://freshleads.cloud/mcp`
- **Transport:** Streamable HTTP
- **Sign-in:** OAuth 2.1 (dynamic client registration, client ID metadata documents, PKCE S256). You choose Full access or Read only when you sign in.
- **Docs:** https://freshleads.cloud/connectors/

This repository holds the public listing files only (registry metadata, plugin
manifests, icon). The server is hosted; there is no server code here.

## Connect

In an assistant that supports remote MCP servers (Claude, ChatGPT, Cursor,
VS Code, Grok, Le Chat, Manus and others), add a custom connector with the URL
`https://freshleads.cloud/mcp`, then sign in to FreshLeads in the window that opens.

```json
{
  "mcpServers": {
    "freshleads": { "url": "https://freshleads.cloud/mcp" }
  }
}
```

## Tools

| Tool | Type | What it does |
|---|---|---|
| `search_leads` | Read | Search the business leads that match your filters, by words, place, category or registration day. |
| `get_lead` | Read | One business: name, website, description, business contact details, location and tags. |
| `list_filters` | Read | Your filters and their match counts. |
| `get_filter` | Read | The rules of one filter. |
| `list_contacts` | Read | The contacts you saved, by tag. |
| `list_tags` | Read | The tags on your leads and contacts, with counts. |
| `get_usage` | Read | Your plan and how much of it you used this month. |
| `save_draft_filter` | Write | Save a new filter or a change as a draft. You apply it in the app. |
| `save_contact` | Write | Save a lead to your contacts with tags. |
| `update_contact_note` | Write | Add or change your private note on a contact. |

The connector does not send email, buy plans or credits, or delete data.

## Data

- Business contacts only: no personal webmail addresses, no personal social profiles, no street addresses.
- Leads from websites show only when the website's robots.txt allows our crawler ([FreshLeadsBot](https://freshleads.cloud/bot/)).
- Privacy: https://freshleads.cloud/privacy/ · Terms: https://freshleads.cloud/terms/ · Remove a business: https://freshleads.cloud/remove/

## Support

https://freshleads.cloud/support/ · operator@zoom-gtm.com
