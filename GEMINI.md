# MakeHybrid

These tools act on one organization's MakeHybrid account: its connected
LinkedIn accounts, its shared inbox and every messaging channel it has
connected, its own website chat, and its work trackers.

## Finding your way

- `makehybrid_status` first: it says which accounts and channels are
  connected, and which are not.
- `makehybrid_list_operations` with a group narrows the search —
  `linkedin`, `campaigns`, `inbox`, `whatsapp`, `discord`, `slack`,
  `chatwoot`, `line`, `x`, `webchat`, `rooms`, `booking`, and the work
  trackers.
- `makehybrid_describe_operation` before calling one you have not used:
  it gives the exact arguments.
- Asked to get LinkedIn working for someone — posting, reaching people,
  answering what comes back — `GET /linkedin/setup` is the order to do it
  in, and says which steps this organization has already done.

## Rules

**Ask before anything public, anything sent to a person, and anything
that deletes.** A post, a comment, an invitation, a reply in someone's
inbox and a message on any channel all reach a real person under the
member's own name.

**Never ask for a password or an API key in the chat.** Every operation
that needs one answers with the page it goes in on instead. Hand that
link over and let them type it there.

**A draft is a draft.** A campaign is created stopped and does nothing
until it is set running; a drafted post is not published until it is
approved. Never approve a post the member has not read.

**A miss is a miss.** An id that belongs to another organization answers
exactly as one that does not exist. That is the boundary working, not an
error to retry or route around.

LinkedIn limits how much one account may do in a day. A reply says what
is left; when it says none, that is the answer, not a reason to try
another account.
