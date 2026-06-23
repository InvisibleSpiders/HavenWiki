# ClaimsBridge Admin

ClaimsBridge connects HavenNecessities systems to a claims plugin. The current native provider is GriefPrevention. It is configured in `modules/claimsbridge.yml` and disabled by default.

## GriefPrevention Support

When enabled with GriefPrevention present, ClaimsBridge can:

- Prevent new claims that touch the frontier.
- Require claimed land for Haven spawner placement.
- Require build trust or ownership for spawner placement.
- Require trust for spawner upgrades.
- Require trust for spawner altar use.
- Mark orphaned Haven spawners inactive when claims are unclaimed or resized away.

Bypass permissions are intentionally separate for frontier claim blocking and spawner placement checks.

## Claim Storage

Claim storage is a shared storage area owned by the claim. Players can access it through `/storage claim` or the Claim Storage button in `/storage` while standing in a claim they can access.

Capacity can scale from claim size and activity. Access levels are based on owner and trust relationships.

## Teleport Safety

ClaimsBridge can help teleport features avoid protected land. The current RTP integration can prevent random teleporting players into claimed land.

## Admin Commands

ClaimsBridge diagnostics:

```text
/admin claimsbridge status
/admin claimsbridge inspect
/admin claimsbridge scan
/admin claimsbridge reactivate
```

Claim storage administration:

```text
/admin claimstorage inspect [claimId]
/admin claimstorage setslots <claimId> <slots>
/admin claimstorage lock <claimId> [reason]
/admin claimstorage unlock <claimId>
/admin claimstorage purge <claimId> confirm
/admin claimstorage transfer <fromClaimId> <toClaimId>
```

## Permissions

- `havennecessities.admin.claimsbridge`
- `havennecessities.admin.claimstorage`
- `havennecessities.claimsbridge.bypass.frontier-claims`
- `havennecessities.claimsbridge.bypass.spawner-placement`

