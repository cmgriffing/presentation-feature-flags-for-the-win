# Options

## Proprietary (SaaS only)

- LaunchDarkly
- Split.io
- AWS AppConfig
- Firebase RemoteConfig
- DevCycle

## Open Source (Docker-based or SaaS)

- Unleash
- GrowthBook
- Flagsmith
- Flipt
- FeatureHub

## Client Based (Just Remote JSON):

Vexilla (mine) also Open Source (MIT)

Very simple

- Toggles
- Gradual rollout

## Vexilla (Clients)

Clients in many languages (hand-written):

- JS/TS
- Elixir
- PHP
- Python
- C#
- Go
- Rust
- Ruby
- lua
- Dart

## Vexilla (Cons)

- does not currently consider value based flags (pricing, etc). only cares about boolean "should"
- no realtime listening (polling is typically fine if its just a json file)
- ugly config UI (its on the TODO board)
- Very Unopinionated
