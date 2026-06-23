# Events

Events let the server run vote-driven or scheduled activities when the events module is enabled. Events are disabled by default until staff configure them.

## Player Commands

| Command | Description |
| --- | --- |
| `/event` | View the active event or open the event status dialog. |
| `/event status` | Show the active event state. |
| `/event vote yes` | Vote yes on the active vote. |
| `/event vote no` | Vote no on the active vote. |
| `/event reroll` | Vote to reject the current randomly selected event and roll another eligible event. |

## How Voting Works

- Only one active vote runs at a time.
- Votes can require a minimum number of votes and a pass ratio.
- Reroll voting has its own threshold, usually matching the main vote threshold.
- Server-bank-funded events withdraw funds only after the vote passes.
- Unfunded world events do not use server-bank funds.
- Successful events can grant configured rewards to eligible voters.
- Event lifecycle notifications can be mirrored to Discord when the Discord bridge and event notifications are enabled.

## Example

```text
/event status
/event vote yes
/event vote no
/event reroll
```

Common event types include worldborder expansion, frontier surges, announcements, command rewards, server-bank-funded commands, and timed broadcasts.

## Permissions

- `havennecessities.events.vote`
