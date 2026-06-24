# ftrading

Futu trading network rules for Surge and Clash.

## Files

- `surge/futu.list`: Surge rule set.
- `clash/futu.yaml`: Clash provider payload.

## Surge

Use `surge/futu.list` as a remote rule set, then route the rule set to your target policy in Surge.

```ini
RULE-SET,https://github.com/aliantech/ftrading/raw/refs/heads/main/surge/futu.list,DIRECT
```

## Clash

Use `clash/futu.yaml` as a classical rule provider:

```yaml
rule-providers:
  futu:
    type: http
    behavior: classical
    url: https://github.com/aliantech/ftrading/raw/refs/heads/main/clash/futu.yaml
    path: ./ruleset/futu.yaml
    interval: 86400

rules:
  - RULE-SET,futu,DIRECT
```

## Validate

```bash
node scripts/validate-rules.mjs
```
