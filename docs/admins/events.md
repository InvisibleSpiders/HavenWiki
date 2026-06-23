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
- `command-reward`
- `server-bank-command`
- `timed-broadcast`
- `frontier-surge`

## Permissions

- `havennecessities.admin.events`
- `havennecessities.events.vote` for player voting
