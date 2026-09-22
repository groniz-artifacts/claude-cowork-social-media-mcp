# How to Publish to Social Media From Claude Cowork With MCP

To publish from Claude Cowork, add Groniz as a remote custom connector, connect it for the member who will operate it, and enable it in the specific conversation. Use `https://mcp.groniz.com/mcp` and prefer OAuth when the connector flow offers it. Keep a human approval immediately before the social write. In Team and Enterprise organizations, an owner adds the connector before members connect.

Cowork connects from Anthropic cloud. It does not use a local Groniz CLI or inherit a local Claude Desktop configuration. Give it an approved post or media packet, let it inspect the destination's live requirements, and upload approved media before the write. A person then reviews the exact payload, account, disclosure, and time. Submit once, capture the post ID, and verify the accepted result. Reconcile an unknown outcome before retrying.

## Account for Cowork's remote environment

The connection runs in Anthropic's cloud. A Groniz executable or configuration on your computer is therefore unavailable to Cowork. Follow Anthropic's [official remote custom connector guide](https://support.claude.com/en/articles/11175166-get-started-with-custom-connectors-using-remote-mcp) and configure the documented remote route.

A local Claude Desktop MCP recipe cannot configure Cowork. Both products can support remote custom connectors, though their execution boundaries and organization controls differ. For a map of the client-specific routes, use the [AI agent publishing setup guide](https://groniz.com/blog/ai-agent-social-media-publishing-setup). For the protocol and publishing-layer distinction, read the [social media MCP server guide](https://groniz.com/blog/social-media-mcp-servers).

## Prepare the approved asset before connecting it to a write

Use a stable asset Cowork can refer to without deciding what is true or cleared for public use. Suitable inputs include a reviewed announcement, an approved adaptation brief, or a rights-cleared media package. Record the version instead of relying on "the latest file."

```markdown
Source asset and version:
Owner:
Facts and links verified by:
Rights and consent verified by:
Disclosure decision:
Approved destination or allowed destination set:
Approved copy or adaptation boundaries:
Approved media:
Timing constraint:
```

Research, creation, recording, editing, approval, and rights or disclosure checks for this content stay outside Groniz. Cowork can organize the packet and form a destination-specific proposal, but a person remains responsible for those decisions and the final payload.

Cross-channel reuse needs the same restraint. A reviewed factual core is not an identical payload for every provider. Use the [cross-posting breakpoints](https://groniz.com/blog/where-cross-posting-breaks) to identify decisions that must be revisited per destination.

## Separate owner, member, and conversation gates

For Team and Enterprise organizations, Anthropic’s documented pattern separates organization administration from individual use:

1. An organization owner adds the remote custom connector.
2. A member connects to the approved connector with their own allowed access.
3. The user enables the connector for the conversation that will use it.
4. A person separately approves the exact publishing write.

Each gate answers a different question. Owner setup decides which remote service the organization may offer. Member connection decides who can use it. Conversation enablement gives the current Cowork session access to its tools. None of these steps approves a particular message for a public account.

Use this owner/member connector gate as the first original asset for the run:

| Gate | Responsible person | Evidence | What it does not approve |
| --- | --- | --- | --- |
| Remote connector added | Organization owner where required | Connector name and verified endpoint | A member’s credentials or a social post |
| Member connected | Individual operator | Connected state for that member | Use in every conversation |
| Conversation enabled | Conversation operator | Connector enabled in the intended Cowork task | The destination, payload, media, or time |
| Final write approved | Account owner or designated reviewer | Approval bound to an exact delivery packet | Later edits or another destination |

If your organization does not use the owner/member model, preserve the same boundaries between connector authorization, individual connection, conversation access, and write approval.

## Add the Groniz remote connector

Use the remote MCP endpoint:

```text
https://mcp.groniz.com/mcp
```

Follow the current connector-creation steps in Anthropic's official guide instead of relying on a screenshot or remembered label. Prefer OAuth 2.0 when the remote connector supports it. Groniz MCP also supports a Bearer header or a key embedded in the endpoint URL. Either fallback is a secret and needs appropriate handling in the cloud connector environment.

If an API key is required for the supported setup, the issuance location is [Groniz Connectors API keys](https://groniz.com/console/connectors/api-keys). Do not paste a real key into a Cowork prompt, article, shared runbook, screenshot, or delivery log. A URL containing a key is itself sensitive.

Once connected, enable the connector only in the conversation intended for this delivery. Ask Cowork to discover the tools and use read operations first. A working server connection proves only that Cowork can reach it. The operator must still confirm that the intended social integration exists and that the right account is selected.

## Inspect the live connection and settings

Have Cowork follow a read-first sequence:

```text
discover connector tools
→ list available integrations
→ resolve the exact profile, Page, channel, or community
→ retrieve or inspect its current settings
→ prepare the destination payload
```

Groniz is a connector core that handles provider OAuth, per-platform formatting, and delivery to 32+ networks. The capabilities are not identical across providers. Required fields, media options, analytics, and scheduling can differ, so the live integration settings are authoritative. Do not ask Cowork to invent a missing field or assume a payload from another network will fit.

Put both the stable integration reference and a human-readable account label in the packet. The reviewer then has something recognizable, and the agent does not have to guess from names such as "main" or "brand." If more than one plausible destination is connected, ask a person to select one.

For media, confirm rights and suitability first, then upload the asset before the post is created or scheduled. Record the supported returned media reference and keep it with the correct destination. The final approval should show media order and any live settings that affect how it is delivered.

## Assemble the first-delivery packet

Use this second original asset for the first delivery. Cowork should fill it from the approved source and read-only integration results, with unresolved items left visible.

```markdown
### Claude Cowork first delivery

Source asset and version:
Connector added by:
Connected member:
Conversation purpose:
Exact network and account label:
Integration reference:
Live required settings:
Final text and links:
Rights and disclosure confirmation:
Uploaded media references and order:
Publish now or schedule:
Local time and named timezone:
Exact timestamp with offset:
Reviewer:
Decision: approve / revise / reject
Approval reference:
```

The person reviewing this packet owns the facts, rights, disclosures, destination, final payload, and time. If Cowork changes the text, link, integration, media, settings, or timestamp after approval, the packet returns to review. Enabling the connector for the conversation is not a substitute for this decision.

For a more detailed risk policy, use [human approval for AI social posts](https://groniz.com/blog/human-approval-ai-social-posts). Ask the reviewer a concrete question: may this exact payload, with these assets, go to this account at this time?

## Submit once and distinguish states

After approval, let Cowork invoke the discovered write operation once. Capture:

- submission timestamp;
- selected integration;
- approved packet version;
- response state;
- returned post or scheduled-record ID;
- requested delivery time and timezone; and
- the evidence used for verification.

An accepted result shows that the publishing layer received the request. A scheduled record shows that it recorded work for a future time. Neither is automatically a verified public post. For immediate delivery, check the supported state and public destination when a public reference is available. For a schedule, confirm that the stored account, content, and timestamp match the approval packet.

If Cowork loses the response, a second call is unsafe until the first outcome has been reconciled. Search the available delivery records and intended destination for the original submission. Keep the state as unknown if the evidence remains ambiguous and hand it to an operator. Retry only after non-delivery is established, correcting the cause and obtaining new approval for any material change.

Keep the approval packet with the response evidence. Together they document a reviewed delivery path, not a guarantee of reach, engagement, leads, sales, or revenue. Provider differences still apply after a successful connection.

Once the approved source and owner/member first-delivery packet are ready, [connect Claude Cowork’s reviewed delivery path in Groniz Connectors](https://groniz.com/console/connectors).
