# Detailed Tools Documentation

Full documentation moved from TOOLS.md to reduce context window.

## Microsoft Graph Full Setup
- Credentials: `~/.clawdbot/credentials/microsoft-graph.json`, `microsoft-tokens.json`
- API examples:
```bash
~/.clawdbot/scripts/msgraph.sh call "/me/messages?\$top=10"
~/.clawdbot/scripts/msgraph.sh call "/me/calendarview?startDateTime=2026-01-30T00:00:00Z&endDateTime=2026-01-31T00:00:00Z"
```
- Full setup: `memory/microsoft-graph-setup.md`

## Asana Detailed Config
- User: Derick Dahl (derickd@sonance.com)
- Key Projects:
  | Project | GID |
  |---------|-----|
  | Derick - Private | 1202127678978097 |
  | Dashboard - Technology & Innovation | 1211377592740891 |
  | ACTIVE BMT PROJECTS | 1205827966484333 |
  | HUB | 1211762584253887 |
- Full config: `memory/asana-config.md`

## ElevenLabs Voice Details
- API Key: `~/.clawdbot/credentials/elevenlabs-api-key`
- Tier: Creator (110k chars/month)
- Emotion tags: `[sarcastic]`, `[excited]`, `[whispers]`, `[laughs]`, `[curious]`
- Full command:
```bash
export ELEVENLABS_API_KEY=$(cat ~/.clawdbot/credentials/elevenlabs-api-key)
sag --api-key "$ELEVENLABS_API_KEY" -v pFZP5JQG7iQjIQuC4Bku --speed 1.35 -o /tmp/voice.mp3 "[excited] Your text here"
```

## GoDaddy Full API Usage
```bash
GODADDY_KEY=$(cat ~/.clawdbot/credentials/godaddy-key)
GODADDY_SECRET=$(cat ~/.clawdbot/credentials/godaddy-secret)
curl -s "https://api.godaddy.com/v1/domains" \
  -H "Authorization: sso-key ${GODADDY_KEY}:${GODADDY_SECRET}" | jq '.[].domain'
```
- 22 domains available: optamistic.ai, logolist.app, storygrove.app, etc.

## Salsify Product API
```bash
SALSIFY_KEY=$(cat ~/.clawdbot/credentials/salsify-api-key)
curl -s "https://app.salsify.com/api/v1/products?access_token=$SALSIFY_KEY"
```
- Available Data: SKUs, pricing, descriptions, dimensions, digital assets
- Key Fields: `sku`, `msrp`, `dealer_price`, `hero_product_image_*`, `description_long`

## Auto-Order Full Details

### Wowpoki Poke Bowl
- Large Bowl, Salad base
- Proteins: Tuna/Spicy Tuna x2/Albacore/Yellow Tail  
- Medium spice, Crab + Extra Crab
- Toppings: Masago/Seaweed/Green Onion/Ginger
- Payment: Amex ...6003
- Address: 1001 Calle Amanecer (work)

### Thai Palace Tom Ka Soup
- Item: Chicken Tom Kar, Large — $19.90
- Payment: Amex ...6003
- Address: 1001 Calle Amanecer (work)
- DoorDash store: thai-palace-san-clemente-13306
- Use "Order It Again" → Chicken Tom Kar for fastest checkout

## Other Available Integrations
- GitHub: Token exists, need `gh auth login`
- Slack: Via Clawdbot channel integration
- Supabase: `supabase-token`, `supabase-token-personal`
- Vercel: `vercel-token-business/personal`, `vercel-team-id`

*Moved from TOOLS.md on 2026-02-07 to reduce context window*