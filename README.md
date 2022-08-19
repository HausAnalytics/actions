Post to Slack using Google Secret

Create a label in your repo to assign to stuck pull requests. The default label this action uses is stuck, but you can use any label.

Inputs
❗ = Required

CHANNEL_ID ❗
Id of the recipient channel or user e.g. "@test_user", "#test_channel"

TEXT ❗
Text you want to send to the channel

BLOCKS
Encoded JSON string similar to what is outlined here https://api.slack.com/reference/block-kit/blocks

Secrets

These secrets must be exist in the calling repo

GOOGLE_CREDENTIALS_FOR_SLACK_TOKEN ❗
Credentials in JSON format

GOOGLE_SECRET_KEY_FOR_SLACK_TOKEN ❗
Secret Key Id in the format of [gcp_project_id]/[secret_name]

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
