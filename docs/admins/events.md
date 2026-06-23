# Events Admin

Events can be admin-started, fixed schedule, or hidden weighted-random launches. The module is disabled by default until configured.

## Admin Commands

| Command | Description |
| --- | --- |
| `/havenadmin event start <event-id>` | Start a configured event vote or event action. |
| `/havenadmin event cancel` | Cancel the active event. |
| `/havenadmin event status` | Inspect the active event. |

## Funding Modes

- `funding.mode: none` runs world events without server-bank funds.
- `funding.mode: server-bank` charges the shared server bank only after a vote passes.
- Costs can be fixed or generated from configured ranges.

## Voting And Rerolls

Votes use configured duration, pass ratio, and minimum vote count. Reroll voting has its own threshold, usually matching the main vote threshold.

Only one event vote is active at a time in the current design. If no event is active, status can show the next scheduled event time while hidden random rolls stay a surprise.

## Launch Modes

An event can support more than one launch mode:

- Admin start through `/havenadmin` or `/admin`.
- Fixed schedule at a configured interval.
- Weighted random schedule.

Random scheduling can roll eligible events on a cadence such as every 600 seconds, using each event's weight and cooldown.

## Example Event Shape

```yaml
events:
  frontier-surge:
    enabled: true
    type: frontier-surge
    display-name: "Frontier Surge"
    vote-required: true
    funding:
      mode: none
    world: world
    surge-profile: "ominous_frontier"
    launches:
      admin:
        enabled: true
      random:
        enabled: true
        weight: 8
```

## Supported Action Types

- `worldborder-expand`
- `announcement`
- `command-reward`
- `server-bank-command`
- `timed-broadcast`
- `frontier-surge`

Event lifecycle notifications can be mirrored to Discord when the Discord bridge and event notifications are enabled.

## Permissions

- `havennecessities.admin.events`
- `havennecessities.events.vote` for player voting
