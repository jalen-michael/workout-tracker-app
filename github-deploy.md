# Deploying Your Workout Tracker App to GitHub Pages

This guide will walk you through the process of deploying your workout tracker app to GitHub Pages, making it available as a Progressive Web App (PWA) on iOS devices.

## Step 1: Update package.json

Make sure your package.json file has:
- The gh-pages dependency in devDependencies
- The homepage set to your GitHub Pages URL
- The predeploy and deploy scripts

It should look like this (replace YOUR-USERNAME with your actual GitHub username):
```json
{
  "homepage": "https://YOUR-USERNAME.github.io/workout-tracker-app",
  "scripts": {
    "predeploy": "npm run build",
    "deploy": "gh-pages -d build"
  },
  "devDependencies": {
    "gh-pages": "^5.0.0"
  }
}
```

## Step 2: Install dependencies

```bash
npm install
```

This will install all dependencies including gh-pages.

## Step 3: Deploy to GitHub Pages

```bash
npm run deploy
```

This command will:
1. Build your app for production (creating the build folder)
2. Deploy the contents of the build folder to a branch called gh-pages
3. Configure GitHub Pages to serve your app from this branch

## Step 4: Configure GitHub Pages in repository settings

1. Go to your GitHub repository
2. Click on "Settings"
3. Scroll down to the "GitHub Pages" section
4. Make sure the source is set to the "gh-pages" branch
5. The site will be published at: https://YOUR-USERNAME.github.io/workout-tracker-app

## Step 5: Access your app on iOS

1. Open Safari on your iOS device
2. Navigate to https://YOUR-USERNAME.github.io/workout-tracker-app
3. Wait for the app to fully load
4. Tap the Share button (square with up arrow)
5. Scroll down and tap "Add to Home Screen"
6. Give it a name and tap "Add"
7. Find and tap the app icon on your home screen

Your app should now launch in full-screen mode and work offline!

## Troubleshooting

- If your app doesn't appear after deployment, check the GitHub Actions tab to see if there were any deployment errors
- Make sure your repository is public for GitHub Pages to work on the free plan
- If the app doesn't work properly as a PWA, verify that your manifest.json and service worker are correctly set up
