## Intro

## What

- popular sites and apps that use feature flagging a lot

  - Web Browsers (chrome://flags)
  - Twitch
  - Github (Experimental) and https://github.blog/2021-04-27-ship-code-faster-safer-feature-flags/
  - Twitter
  - Facebook
  - YouTube

- examples of feature flags.
  - UI Changes (layout)
  - Payment Providers
  - Gradual Rollouts
  - Single source of truth for pricing changes

## Why Remote? (why not compile based)

- Time
  Deployment to production often takes a long time
  - even for continual release. Projects can take upwards of 20 to 30 minutes to build and test. (not uncommon)
  - Now remember that you have to build for each environment
    - dev: PR review and merging
    - staging: QA
    - production
  - 60 to 90 minutes for a release
  - Worst Case: Mobile apps and the AppStore (up to a week)

## Options

- Proprietary:

  - LaunchDarkly
  - Split.io
  - AWS AppConfig
  - Firebase RemoteConfig
  - DevCycle

- Open Source (Docker-Based and cloud options):

  - Unleash
  - GrowthBook
  - Flagsmith
  - Flipt
  - FeatureHub

- Client Based (just json):

  - Vexilla (mine)
    - Very simple
      - Toggles
      - Gradual rollout
    - cons:
      - does not currently consider value based flags (pricing, etc). only cares about boolean "should"
      - no realtime listening (polling is typically fine if its just a json file)

- Thoughts
  - prefer not mine (trying to stay objective)
  - if mine, we could use it on UI-only trial period at very little cost (hosting or maintenance for self-hosted)
    - refactoring to another service is simple
      - if (vexilla.should("someCoolNewFeature")) --> if (launchDarkly.variation("flag-key-123abc", false))
