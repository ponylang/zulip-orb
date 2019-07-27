# Zulip Orb

Easily send [CircleCI](https://circleci.com/ "CircleCI") status updates to [Zulip](https://zulipchat.com/ "Zulip").

Learn more about [Orbs](https://circleci.com/docs/2.0/using-orbs/ "Using Orbs").

## Requirements

- Requires usage of the CircleCI 2.1 configuration format. Earlier versions will not work.
- Bash shell
- curl

## Usage

Example config:

```yaml
version: 2.1

orbs:
  zulip: ponylang/zulip@1

jobs:
  build:
    docker:
      - image: <docker image>
    steps:
      - zulip/status:
          webhook: https://ponylang.zulipchat.com/api/v1/messages
          user: circleci-bot@ponylang.zulipchat.com:57HRshi7NNNNNNSX123
          stream: notifications
          topic: CircleCI Activity
```

