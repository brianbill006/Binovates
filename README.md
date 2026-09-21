# Binovate

Real-time digit trading platform. Node.js backend, single-file frontend, Postgres persistence, Telegram bot for withdrawal approvals.

## Deploy

1. Free Postgres at https://neon.tech → connection string must end with `?sslmode=require`
2. Push this repo to GitHub
3. Render → New Web Service → connect repo
   - Environment: Node
   - Build: npm install
   - Start: node server.js
   - Free tier
4. Add env vars (see table)
5. Open /healthz — must show storage: postgres, telegram: yes

## Telegram

1. @BotFather → /newbot → get token
2. Send any message to bot
3. Visit api.telegram.org/bot<TOKEN>/getUpdates → copy chat id
4. Add TELEGRAM_BOT_TOKEN + TELEGRAM_CHAT_ID to Render env
5. Redeploy — webhook auto-registers

## Features

- Real-time digit trading (Even/Odd, Match/Differ, Over/Under)
- 7 volatility indices (10, 25, 50, 75, 100, 150, 250)
- Auto-trading with TP/SL/Multiplier
- Smart Recovery mode (multiplier staircase)
- Telegram withdrawal approval (✅ / ❌)
- Referral system (15% commission)
- Responsible Trading limits
- Account settings (password / email change)
- Light & dark theme (Binance palette)
- PWA install
- M-Pesa + USDT deposits
- Password reset via email
