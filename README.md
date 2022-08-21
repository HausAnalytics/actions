Post to Slack using Google Secret

Inputs
❗ = Required

CHANNEL_ID ❗
Id of the recipient channel or user e.g. "@test_user", "#test_channel"

TEXT ❗
Text you want to send to the channel

WORKLOAD_IDENTITY_PROVIDER ❗

SERVICE_ACCOUNT ❗
Google service account, which must have secret manager viewer access to the secret for the slack bot

GOOGLE_SECRET_KEY_FOR_SLACK_TOKEN ❗
Secret Key Id in the format of [gcp_project_id]/[secret_name]

BLOCKS
Encoded JSON string similar to what is outlined here https://api.slack.com/reference/block-kit/blocks


Usage
```
name: Test post to slack with token from google secrets

on:
  push

jobs:
  test_post_to_slack:
    uses: HausAnalytics/actions/.github/workflows/post_to_slack_google_secret.yml@f-slack
    secrets: inherit
    with:
      CHANNEL_ID: "#test_channel"
      TEXT: "Test Text"
