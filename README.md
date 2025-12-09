# LeapNest Legal Documents - GitHub Pages Setup

This directory contains the legal documents for LeapNest, designed to be hosted on GitHub Pages.

## What's Included

- `index.html` - Landing page with links to all legal documents
- `privacy-policy.html` - Privacy Policy
- `terms-of-service.html` - Terms of Service

## Setup Instructions

### Option 1: Host in Main Project Repository

If you want to host these pages from your main LeapNest repository:

1. **Commit the docs folder**:
   ```bash
   git add docs/
   git commit -m "Add legal documents for GitHub Pages"
   git push origin main
   ```

2. **Enable GitHub Pages**:
   - Go to your repository on GitHub
   - Click **Settings** > **Pages**
   - Under "Source", select **Deploy from a branch**
   - Under "Branch", select **main** and **/docs** folder
   - Click **Save**

3. **Wait for deployment** (1-2 minutes)
   - Your site will be available at: `https://YOUR-USERNAME.github.io/YOUR-REPO-NAME/`

4. **Update App Store URLs**:
   - Privacy Policy: `https://YOUR-USERNAME.github.io/YOUR-REPO-NAME/privacy-policy.html`
   - Terms of Service: `https://YOUR-USERNAME.github.io/YOUR-REPO-NAME/terms-of-service.html`

### Option 2: Create Separate Repository (Recommended)

For a cleaner URL structure, create a dedicated repository:

1. **Create a new repository on GitHub**:
   - Name it: `leapnest-legal` (or any name you prefer)
   - Make it public (required for GitHub Pages)
   - Don't initialize with README

2. **Copy files to new repository**:
   ```bash
   # Create new directory
   mkdir leapnest-legal
   cd leapnest-legal

   # Copy docs contents
   cp ../leapnest/docs/* .

   # Initialize git
   git init
   git add .
   git commit -m "Initial commit: Add legal documents"

   # Add remote and push
   git remote add origin https://github.com/YOUR-USERNAME/leapnest-legal.git
   git branch -M main
   git push -u origin main
   ```

3. **Enable GitHub Pages**:
   - Go to repository Settings > Pages
   - Select **main** branch and **/ (root)** folder
   - Click Save

4. **Access your site**:
   - URL: `https://YOUR-USERNAME.github.io/leapnest-legal/`
   - Privacy Policy: `https://YOUR-USERNAME.github.io/leapnest-legal/privacy-policy.html`
   - Terms of Service: `https://YOUR-USERNAME.github.io/leapnest-legal/terms-of-service.html`

### Option 3: Custom Domain (Optional)

If you own a domain (e.g., leapnest.com):

1. **Add custom domain in GitHub Pages settings**:
   - Go to Settings > Pages
   - Under "Custom domain", enter: `legal.leapnest.com` (or similar)
   - Click Save

2. **Configure DNS**:
   - Add a CNAME record in your domain provider:
     - Name: `legal` (or your subdomain)
     - Value: `YOUR-USERNAME.github.io`

3. **Enable HTTPS** (recommended):
   - In GitHub Pages settings, check "Enforce HTTPS"

4. **Your URLs will be**:
   - Privacy Policy: `https://legal.leapnest.com/privacy-policy.html`
   - Terms of Service: `https://legal.leapnest.com/terms-of-service.html`

## Updating Legal Documents

### Before Updating

Apple and Google require advance notice before changing legal documents. Best practices:

1. Update "Last Updated" date
2. Notify users of material changes (via app or email)
3. Wait 30 days before enforcing new terms (if changes are significant)

### How to Update

1. **Edit the HTML files** in the `docs/` folder
2. **Commit and push changes**:
   ```bash
   git add docs/
   git commit -m "Update privacy policy"
   git push origin main
   ```
3. **Changes go live automatically** (within 1-2 minutes)

## Using URLs in Your App

Once deployed, update these locations:

### In App Store Connect (iOS)
- App Information > Privacy Policy URL
- App Information > Terms of Service URL (if requested)

### In Google Play Console (Android)
- Store Presence > Store Listing > Privacy Policy

### In app.json (Optional)
Add a privacy field to link directly to your policy:

```json
{
  "expo": {
    "privacy": "public",
    "privacyPolicy": "https://YOUR-USERNAME.github.io/YOUR-REPO/privacy-policy.html"
  }
}
```

### In Your Code (Optional)
Update the placeholder URLs in your components if you want to link to external pages:

```typescript
// src/components/PrivacyPolicyContent.tsx or similar
const PRIVACY_POLICY_URL = "https://YOUR-USERNAME.github.io/YOUR-REPO/privacy-policy.html";
const TERMS_URL = "https://YOUR-USERNAME.github.io/YOUR-REPO/terms-of-service.html";
```

## Verification

After setup, verify:

1. ✅ All pages load correctly
2. ✅ Links work between pages
3. ✅ Pages are mobile-responsive
4. ✅ HTTPS is enabled (lock icon in browser)
5. ✅ Content is readable and formatted correctly
6. ✅ URLs are accessible from incognito/private browser

## Benefits of GitHub Pages

- ✅ **Free hosting** (no cost)
- ✅ **Automatic HTTPS** (secure)
- ✅ **Fast CDN** (global)
- ✅ **Version control** (track changes)
- ✅ **Easy updates** (just commit and push)
- ✅ **99.9% uptime** (reliable)
- ✅ **Accepted by App Store & Play Store**

## Alternative Hosting Options

If you prefer not to use GitHub Pages:

1. **Netlify** (free, easy drag-and-drop)
2. **Vercel** (free, good for Next.js/React sites)
3. **Cloudflare Pages** (free, fast)
4. **Firebase Hosting** (free tier available)
5. **Your own domain/hosting** (if you already have one)

## Need Help?

- [GitHub Pages Documentation](https://docs.github.com/en/pages)
- [GitHub Pages Troubleshooting](https://docs.github.com/en/pages/getting-started-with-github-pages/troubleshooting-404-errors-for-github-pages-sites)

## Important Notes

⚠️ **Repository must be public** for free GitHub Pages hosting

⚠️ **Update contact emails** in the HTML files:
- Replace `privacy@leapnest.com` with your real email
- Replace `support@leapnest.com` with your real email

⚠️ **Test thoroughly** before submitting to App Stores:
- Check URLs load correctly
- Verify mobile display
- Test all links
