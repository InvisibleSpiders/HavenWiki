# Events

Events let the server run vote-driven or scheduled activities when the events module is enabled. Events are disabled by default until staff configure them.

## Player Commands

| Command | Description |
| --- | --- |
| `/event` | View the active event or open the event status dialog. |
| `/event status` | Show the active event state. |
| `/event vote yes` | Vote yes on the active vote. |
| `/event vote no` | Vote no on the active vote. |

## How Voting Works

- Only one active vote runs at a time.
- Votes can require a minimum number of votes and a pass ratio.
- Server-bank-funded events withdraw funds only after the vote passes.
- Unfunded world events do not use server-bank funds.
- Successful events can grant configured rewards to eligible voters.

## Example

```text
/event status
/event vote yes
/event vote no
```

Common event types include worldborder expansion, command rewards, timed broadcasts, and frontier surges.

## Permissions

- `havennecessities.events.vote`
