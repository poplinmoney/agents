# Poplin for AI assistants

[Poplin](https://poplinmoney.com) is an account for getting paid from abroad and paying bank
accounts abroad. Poplin’s two MCP servers let an AI assistant, such as Claude, ChatGPT or GitHub
Copilot, answer questions from Poplin’s own published figures, and read your own Poplin account if
you choose to connect it.

This repository is documentation only. Both servers are hosted by Poplin and there is nothing to
install or run.

| Server | Address | Sign-in |
|---|---|---|
| `com.poplinmoney/public` | `https://agents.poplinmoney.com/public` | None |
| `com.poplinmoney/account` | `https://agents.poplinmoney.com/account` | Your Poplin account (OAuth, approved with your passkey) |

Check the address before you add it. Poplin’s servers answer only at `agents.poplinmoney.com`.

## The public server

No account or sign-in needed. Ask your assistant:

- What a payment to a bank account abroad costs, and how much arrives
- How many US dollars arrive when a client pays into a Poplin receiving account in EUR, GBP or another currency
- Which currencies you can get a receiving account in, and whether you can open one where you live
- Which payout methods reach a country, what each costs and how long it takes
- Whether a particular bank can be reached
- What a business needs to sign up in its country
- How a currency’s mid-market rate has moved
- Where to find Poplin’s terms, privacy policy and other legal documents

Every quote is an estimate at standard pricing for a new account; the final terms are shown in the
Poplin app before you confirm anything. Rate history shows the mid-market rate before fees and isn’t
a forecast. Through this server the assistant can’t see anyone’s account or move money.

## The account server

If you have a personal Poplin account, you can let an assistant read it and ask things like “Has my
payment arrived?”, “Which payments came in this month, and from whom?” or “Match this month’s
payments to my invoices.”

- **Read-only.** It can see your balance, your payments and other activity, whether Poplin needs
  anything more to verify you, and your notifications. It can’t send money or change anything, and
  it’s never given full account numbers, passwords, passkeys, recovery codes or identity documents.
- **Personal accounts only.** A business account can’t be connected.
- **Connect on a computer**, in a web browser or the assistant’s desktop app. Signing in from an
  assistant’s phone app may not work.
- **You stay in control.** Poplin notifies you each time an assistant is connected. Disconnect one at
  any time under Connected assistants in the Poplin app; a connection also ends one year after you
  approve it.

## Configuration

**Claude:** add a custom connector with the server’s address, or
[open the form with the public server filled in](https://claude.ai/customize/connectors?modal=add-custom-connector&connectorName=Poplin&connectorUrl=https%3A%2F%2Fagents.poplinmoney.com%2Fpublic).

**VS Code (GitHub Copilot):** install it from the MCP gallery, or add it to `.vscode/mcp.json`:

```json
{
  "servers": {
    "poplin": {
      "type": "http",
      "url": "https://agents.poplinmoney.com/public"
    },
    "poplin-account": {
      "type": "http",
      "url": "https://agents.poplinmoney.com/account"
    }
  }
}
```

**Any other assistant** that adds a remote MCP server by its address: use the address from the table
above. Both servers speak streamable HTTP.

## More

- How to use it, with the same answers kept current: <https://poplinmoney.com/ai-assistants/>
- What Poplin receives and keeps: section 3.4 of the [Privacy Policy](https://poplinmoney.com/legal/privacy-policy/)
- Questions: [support@poplinmoney.com](mailto:support@poplinmoney.com)
