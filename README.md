# InvoicifyAI for Claude

InvoicifyAI is business software for trades and service businesses: invoicing, estimates,
CRM, service requests and appointments, expenses, an AI Receptionist for incoming calls, and
Call for Me outbound AI calls. This plugin connects Claude to the InvoicifyAI company you
authorize and adds three skills that show Claude how to use it well.

## What you can do

- Review saved AI Receptionist and outbound AI call summaries, transcripts and analysis, then
  create a manual CRM follow-up task from a call.
- Find customers and leads, and prepare unsent invoice drafts for existing customers and
  estimate drafts for customers or leads.
- Check receivables and revenue by currency, plus expenses, appointments, service requests,
  CRM notes and activities, and your CRM pipeline.
- Search company and customer files in Document Hub and read their extracted text. Files
  marked restricted are visible only to Owners.
- Ask Claude to have Call for Me call a vendor or supplier on your behalf, for example to
  confirm a delivery, check availability or arrange a service. Before the request is placed,
  you confirm the recipient, phone number, purpose, timing, maximum call length and whether
  you want to join the call. The AI agent cannot accept prices, make purchases or promise
  payment. Calls use your company's calling minutes.

With your permission, other supported tools can create and update records such as customers,
leads, expenses, CRM opportunities and tasks, service offerings and service requests; convert
accepted estimates to invoice drafts; email invoices, estimates and receipts to the customer's
saved email address, issuing a draft first when you ask; and record a payment you already
received.

## What is in this plugin

| Component | Purpose |
| --- | --- |
| `.mcp.json` | Connects to the InvoicifyAI MCP server at `https://mcp.invoicifyai.com/mcp`. |
| `skills/business-brief` | Summarizes receivables, draft sales documents, CRM and recent calls for a period. Read-only. |
| `skills/invoice-draft` | Prepares and verifies one unsent invoice draft for an existing customer. |
| `skills/call-follow-up` | Reviews a saved call and, only when you ask, saves a manual CRM task. |

The plugin contains no code, hooks, commands, local servers or scripts. It runs nothing on
your computer.

## Requirements

- An InvoicifyAI account with an active subscription or trial, and membership in the company
  you connect.
- A Member or Owner role for writes. Viewers can read.
- Tools follow your company's plan and feature access, your role, and the permissions you grant
  at sign-in.

## How it connects and what it sends

When you connect, Claude opens InvoicifyAI's sign-in and consent page at
`app.invoicifyai.com`. The page names the company you are signed in to and lists each read and
write permission requested; your role limits what can be granted. You can revoke access at any
time in InvoicifyAI under Settings, Integrations. Revoking access does not cancel Call for Me
calls already scheduled, so cancel those first.

Each tool call sends the tool's arguments, such as a customer name or invoice line items, to
`https://mcp.invoicifyai.com/mcp`. The plugin sends nothing anywhere else. The server returns
records from your company only, and those records, including document text and call
transcripts, become part of your Claude conversation under your Claude data settings. Some tools reach people outside InvoicifyAI when you ask: the
email tools send a document to the customer's saved address, and Call for Me speaks your
objective to the person it calls. Arguments you ask Claude to save, such as invoice notes or a Call for Me
objective, become records in your company. InvoicifyAI does not receive your conversation with
Claude beyond those arguments. See the
[privacy policy](https://www.invoicifyai.com/privacy).

## Limits

- It cannot charge cards, move money, send text messages or create payment links. Recording a
  payment logs money you already collected.
- Appointment booking, rescheduling and cancellation, CRM note writes and invoice draft editing
  are not available through this connection.
- The tools and skills tell Claude to treat record content such as notes, documents and call
  transcripts as data, not instructions.

## Documentation and support

- Setup and tool reference: <https://www.invoicifyai.com/integrations/mcp/docs>
- Support: <https://www.invoicifyai.com/contact> or support@invoicifyai.com
- Terms: <https://www.invoicifyai.com/terms-and-conditions>

## License

The files in this plugin are released under the MIT License. See `LICENSE`. The InvoicifyAI
service and MCP server are not part of this license.
