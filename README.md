# Binovate

Real-time digit trading platform. Deriv-style flat stakes with a multiplier on payout only.

## Features

- Even/Odd, Matches/Differs, Over/Under
- 7 volatility indices
- Flat stake (Deriv style) — no martingale
- Multiplier ×1 to ×5 applies to payout only
- Stop Loss + Target Profit
- Telegram withdrawal approval (✅ / ❌)
- Referral system (15% commission)
- Responsible Trading limits
- Account settings (password / email)
- Light & dark theme (Binance palette)
- PWA install
- M-Pesa + USDT deposits
- Password reset via email

## Deploy

1. Free Postgres at https://neon.tech — copy connection string ending with `?sslmode=require`
2. Push this repo to GitHub
3. Render → New Web Service → Node → Free
4. Build: `npm install` · Start: `node server.js`
5. Add env vars from the deploy table
6. Open `/healthz` — should show `storage: postgres`, `telegram: yes`

## Telegram setup

1. @BotFather → `/newbot` → get token
2. Send any message to the bot
3. Visit `api.telegram.org/bot<TOKEN>/getUpdates` → copy chat id
4. Add `TELEGRAM_BOT_TOKEN` and `TELEGRAM_CHAT_ID` in Render
5. Redeploy — webhook auto-registers
