# Instagram Feed Integration Guide

## How to Get Instagram Post IDs and Embed Codes

### Method 1: Get the Post ID from URL
1. Go to your Instagram profile: https://www.instagram.com/benco.renovation.construction/
2. Click on any post you want to embed
3. Look at the URL in your browser, it will look like:
   ```
   https://www.instagram.com/p/ABC123XYZ456/
   ```
4. The part after `/p/` is your POST_ID (e.g., `ABC123XYZ456`)

### Method 2: Get the Complete Embed Code (Recommended)
1. Go to the Instagram post in your browser
2. Click the three dots (...) on the top right of the post
3. Select "Embed"
4. Copy the entire embed code that Instagram provides
5. Replace the placeholder `<blockquote>` tags in `index-2.html`

### Where to Update in the Code

Open `source/index-2.html` and find the Instagram Feed Section (around line 127).

Replace these placeholder URLs:
- `YOUR_POST_ID_1` with your first post ID
- `YOUR_POST_ID_2` with your second post ID  
- `YOUR_POST_ID_3` with your third post ID

### Example:
```html
<!-- Before -->
<blockquote class="instagram-media" data-instgrm-permalink="https://www.instagram.com/p/YOUR_POST_ID_1/" ...>

<!-- After -->
<blockquote class="instagram-media" data-instgrm-permalink="https://www.instagram.com/p/ABC123XYZ456/" ...>
```

### Testing
1. After updating the post IDs, run: `./node_modules/.bin/gulp`
2. Open your browser to: http://localhost:3006/index-2.html
3. The Instagram posts should load directly from Instagram with live data

### Important Notes
- The Instagram embed script is already included at the bottom of the section
- Posts will show with Instagram's official styling and branding
- The posts are live - any updates you make on Instagram will reflect automatically
- Users can interact with posts (like, comment) directly from your website

### Alternative: Using Instagram's Official Embed Code
For better compatibility, you can also:
1. Get the embed code from Instagram (as described in Method 2)
2. Replace the entire `<blockquote>` section for each post
3. This ensures you have the most up-to-date embed format

## Current Implementation
- Location: `source/index-2.html`
- Section ID: `instagram-feed`
- Number of posts: 3 (customizable - add more `<div class="col-lg-4">` blocks)
- Instagram account: @benco.renovation.construction
