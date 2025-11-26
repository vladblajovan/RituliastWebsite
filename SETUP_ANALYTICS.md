# Google Analytics 4 Setup Guide

This guide will help you set up Google Analytics 4 (GA4) for your Ritualist website - completely free with unlimited traffic.

## Step 1: Create a Google Analytics Account

1. Go to [Google Analytics](https://analytics.google.com/)
2. Click **"Start measuring"** (or sign in if you have an account)
3. Fill in your **Account name** (e.g., "Ritualist")
4. Configure data sharing settings (recommended: keep all checked)
5. Click **"Next"**

## Step 2: Create a Property

1. **Property name**: `Ritualist Website`
2. **Reporting time zone**: Select your timezone
3. **Currency**: Select your currency
4. Click **"Next"**

## Step 3: Set Up Data Stream

1. Select **"Web"** as your platform
2. **Website URL**: `https://ritualist.app` (or your domain)
3. **Stream name**: `Ritualist Web`
4. Click **"Create stream"**

## Step 4: Get Your Measurement ID

After creating the stream, you'll see a **Measurement ID** like `G-XXXXXXXXXX`

Copy this ID!

## Step 5: Add Measurement ID to Your Website

1. Create a `.env.local` file in your project root (if it doesn't exist)
2. Add this line:
   ```
   NEXT_PUBLIC_GA_ID=G-XXXXXXXXXX
   ```
   (Replace `G-XXXXXXXXXX` with your actual Measurement ID)

3. **Important**: The `.env.local` file is already in `.gitignore` so it won't be committed to GitHub

## Step 6: Deploy and Verify

1. Restart your dev server (`npm run dev`)
2. Visit your website
3. In Google Analytics, go to **Reports** → **Realtime**
4. You should see your visit appear within 30 seconds!

## What Gets Tracked (Automatically)

Google Analytics will automatically track:
- ✅ Page views
- ✅ User sessions
- ✅ Geographic location (country/city)
- ✅ Device type (mobile/desktop/tablet)
- ✅ Browser and OS
- ✅ Traffic sources (direct, social, search, referral)
- ✅ User flow through your site

## Custom Events You Can Add Later

To track specific actions (optional):

```typescript
// Example: Track TestFlight button clicks
onClick={() => {
  // Send event to GA4
  gtag('event', 'testflight_click', {
    'event_category': 'engagement',
    'event_label': 'hero_cta'
  });
}}
```

Common events to track:
- TestFlight button clicks
- Waitlist form submissions
- Navigation clicks
- Scroll depth
- Time on page

## Privacy & GDPR Compliance

Google Analytics 4 is designed to be privacy-friendly:
- ✅ Cookieless tracking available
- ✅ IP anonymization built-in
- ✅ Data retention settings (default: 14 months)
- ✅ GDPR compliant when configured correctly

**Recommendation**: Add a cookie consent banner if you target EU users (free options: cookie-consent, react-cookie-consent)

## Viewing Your Analytics

1. **Real-time**: See current visitors live
2. **Acquisition**: Where users come from
3. **Engagement**: What pages they visit
4. **Retention**: How often users return
5. **Demographics**: Age, gender, interests

## Free Tier Limits

Google Analytics 4 is **completely free** with:
- ✅ Unlimited traffic/events
- ✅ Unlimited properties
- ✅ 14 months of data retention
- ✅ All standard reports
- ✅ Custom reports and dashboards

No paid tier needed for most websites!

## Troubleshooting

**Not seeing data?**
1. Check that `NEXT_PUBLIC_GA_ID` is set in `.env.local`
2. Restart your dev server after adding the env variable
3. Clear your browser cache
4. Make sure you're not blocking analytics with an ad blocker
5. Check the browser console for errors

**Data showing in Realtime but not in Reports?**
- Standard reports can take 24-48 hours to populate
- Realtime is instant, reports are delayed

## Next Steps

Once you have data flowing:
1. Set up **Goals** (e.g., TestFlight clicks, waitlist signups)
2. Create **Conversion Events** for important actions
3. Set up **Audience segments** (e.g., mobile vs desktop users)
4. Configure **Data retention** settings
5. Add **Google Search Console** integration for SEO data

---

Need help? Check the [Google Analytics Help Center](https://support.google.com/analytics)
