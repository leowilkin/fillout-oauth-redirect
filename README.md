# Fillout Campfire Forms Redirect

A simple service that redirects users to Fillout forms with their Airtable record ID appended.

## How it works

1. User visits `yoursite.com/{fillout_form_id}` (e.g., `/hVKvAVGBf8us`)
2. User enters their email address
3. Service looks up the email in the Airtable `poc_email` field
4. If found, redirects to `https://forms.hackclub.com/t/{form_id}?id={record_id}`

## Environment Variables

| Variable | Description | Example |
|----------|-------------|---------|
| `AIRTABLE_API_KEY` | Airtable Personal Access Token | `pat...` |
| `AIRTABLE_BASE_ID` | Airtable Base ID | `appNV5AaqOvyDryyQ` |
| `AIRTABLE_TABLE_NAME` | Table name (optional, defaults to `Event`) | `Event` |
| `PORT` | Server port (optional, defaults to `3000`) | `3000` |

## Deploy on Coolify

1. Connect this repo in Coolify
2. Set the environment variables above
3. Deploy using the included Dockerfile

## Local Development

```bash
npm install
AIRTABLE_API_KEY=xxx AIRTABLE_BASE_ID=xxx npm start
```
