# Redbox X → Telegram

Forwards new public posts from [@REDBOXINDIA](https://x.com/REDBOXINDIA) to a Telegram chat using GitHub Actions.

## Schedule

Runs every hour from 08:00 through 23:00 India time (Asia/Kolkata). Posts published overnight are picked up by the 08:00 run. The workflow also supports manual runs.

## Required GitHub Actions secrets

Add these under **Settings → Secrets and variables → Actions → New repository secret**:

- `X_BEARER_TOKEN`: X Developer Portal app Bearer Token with access to the user-posts endpoint.
- `TELEGRAM_BOT_TOKEN`: token created with @BotFather.
- `TELEGRAM_CHAT_ID`: your personal chat ID or target group ID.

Never commit tokens to the repository.

## Notes

- The account's numeric X user ID is configured as `1092883822473924608`.
- The last delivered post ID is stored in `state.json` and committed by the workflow.
- GitHub scheduled workflows can start late occasionally. They are not guaranteed to run at the exact minute.
- X API access is required. If the selected X API plan does not allow the user-posts endpoint, the workflow will report the API error in its Actions log.
