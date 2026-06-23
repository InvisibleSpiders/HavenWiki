# Rewards Admin

Rewards provide reusable reward packs for events and future systems. The rewards module is disabled by default.

## Reward Pack Pieces

Reward packs can combine:

- console commands with placeholders;
- balance deposits when the balance module is active;
- loot pools with weighted entries, per-entry chance, and amount ranges.

## Example

```yaml
packs:
  frontier_vote_bonus:
    enabled: true
    grant-mode: yes-voters-online
    commands:
      - "say <player> helped fund <event>."
    economy:
      amount: "250.00"
    loot-pools:
      frontier_supplies:
        rolls: 2
        entries:
          diamonds:
            material: DIAMOND
            chance: 0.25
            min-amount: 1
            max-amount: 3
            weight: 3
```

Each loot-pool roll chooses a weighted entry, then applies that entry's chance. Invalid loot entries are skipped so one bad material or amount range does not disable the entire pack.
