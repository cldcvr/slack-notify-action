# Simple Slack notification action ![visitors](https://visitor-badge.laobi.icu/badge?page_id=vishal-kapse.slack-notify-action)

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

##

Send GitHub Actions workflow status notifications to Slack.
A very simple and light javascript action uses POST request to slack webhook.

## Features

- Simple, light and easy to use
- Customize the Slack notification message
- Dynamic color of slack message based on the status of job. Green if success and red on failure


## Example workflows

Minimal workflow

```bash
  - name: "Workflow Status Slack Notification"
    if: failure()
    uses: ollionorg/slack-notify-action@v1.0
    with:
      SLACK_WEBHOOK_URL: ${{ secrets.SLACK_WEBHOOK_URL }} # required
      status: ${{ job.status }}
     
```

Custom message

```bash
  - uses: ollionorg/slack-notify-action@v1.0
    if: always()
    with:
      SLACK_WEBHOOK_URL: ${{ secrets.SLACK_WEBHOOK_URL }} # required
      status: ${{ job.status }}
      message: "Github workflow run has status ${{ job.status }}"
```

Note: If `status` is not passed it will take the default value as `failure`

