# WordPress Embedding Instructions

## Quick Setup (2 Minutes)

There are two methods to embed your Fraud Prevention Assessment tool in WordPress:

---

## Method 1: Direct HTML Embed (Recommended)

This method embeds the entire assessment directly into a WordPress page.

### Steps:

1. **Log in to WordPress Admin**
   - Go to your WordPress dashboard

2. **Create a New Page**
   - Navigate to `Pages > Add New`
   - Give it a title (e.g., "Fraud Prevention Assessment")

3. **Switch to HTML/Code Editor**
   - Click the three dots (⋮) in the top right
   - Select "Code editor" (or use Ctrl+Shift+Alt+M)

4. **Paste the HTML**
   - Copy the entire contents of `fraud-assessment-tool.html`
   - Paste it into the code editor

5. **Publish**
   - Click "Publish" in the top right
   - View your page!

### Pros:
- ✅ Fully integrated into your site
- ✅ No external hosting needed
- ✅ Matches your WordPress theme's container
- ✅ Works with most WordPress themes

### Cons:
- ⚠️ Some WordPress themes may have CSS conflicts
- ⚠️ Page editor might be slow with large HTML

---

## Method 2: iFrame Embed (Alternative)

This method embeds the tool as an iframe from an external file.

### Steps:

1. **Upload the HTML file**
   - Upload `fraud-assessment-tool.html` to your web hosting
   - Note the full URL (e.g., `https://yourdomain.com/fraud-assessment-tool.html`)

2. **Create a New Page in WordPress**
   - Navigate to `Pages > Add New`
   - Give it a title

3. **Add Custom HTML Block**
   - Click the `+` button to add a new block
   - Search for "Custom HTML" and select it

4. **Insert iFrame Code**
   ```html
   <iframe
     src="https://yourdomain.com/fraud-assessment-tool.html"
     width="100%"
     height="1200"
     frameborder="0"
     style="border: none; min-height: 1200px;">
   </iframe>
   ```
   - Replace the `src` URL with your actual file URL

5. **Adjust Height (Optional)**
   - If content is cut off, increase the `height` value
   - Or add this JavaScript to auto-resize:
   ```html
   <script>
   window.addEventListener('message', function(e) {
     var iframe = document.querySelector('iframe');
     if (e.data.height && iframe) {
       iframe.style.height = e.data.height + 'px';
     }
   });
   </script>
   ```

6. **Publish**
   - Click "Publish"

### Pros:
- ✅ Complete CSS isolation (no theme conflicts)
- ✅ Easy to update (just replace the HTML file)
- ✅ Can be embedded on multiple pages

### Cons:
- ⚠️ Requires external hosting
- ⚠️ Might have fixed height issues
- ⚠️ Can feel less integrated

---

## Method 3: Using a Plugin (Easiest for Non-Technical Users)

### Recommended Plugin: **Insert Headers and Footers** or **Code Snippets**

1. **Install Plugin**
   - Go to `Plugins > Add New`
   - Search for "Insert Headers and Footers"
   - Install and activate

2. **Create a Shortcode**
   - Go to `Settings > Insert Headers and Footers`
   - Create a new snippet with your HTML
   - Generate a shortcode

3. **Use the Shortcode**
   - In any page, add the shortcode block
   - Insert your custom shortcode
   - Publish

---

## Customization Tips

### Adjusting Colors to Match Your Brand

Edit the CSS variables in the `<style>` section:

```css
:root {
  --pia-teal: #00404a;        /* Change to your primary color */
  --pia-teal-light: #0f9c91;  /* Lighter version of primary */
  --pia-orange: #e84e0f;      /* Change to your accent color */
  --bg-light: #f5f7f8;        /* Background color */
  --text-main: #222;          /* Main text color */
  --text-muted: #555;         /* Secondary text color */
  --border-soft: #dde2e6;     /* Border colors */
}
```

### Changing Text and Questions

All text content is in plain HTML. Simply find and replace:
- Section titles: Look for `<div class="fp-section-title">`
- Questions: Look for `<div class="fp-question-text">`
- Intro text: Find `<div class="fp-intro">`

### Adding Your Logo

Add this HTML right after the opening `<div class="fp-header">`:

```html
<img src="https://yourdomain.com/logo.png" alt="Logo" style="max-width: 200px; margin-bottom: 10px;">
```

---

## Troubleshooting

### Issue: Assessment looks broken or unstyled
**Solution**: Make sure you're copying the ENTIRE HTML file, including the `<style>` tags.

### Issue: Buttons don't work
**Solution**: Ensure the `<script>` tags at the bottom are included. Check browser console for errors.

### Issue: Chart doesn't appear
**Solution**: Make sure your site allows loading external scripts from CDN:
- `https://cdn.jsdelivr.net/npm/chart.js`
- `https://cdnjs.cloudflare.com/ajax/libs/jspdf`

### Issue: PDF download doesn't work
**Solution**: Some WordPress security plugins block external scripts. Try allowing the jsPDF CDN in your security plugin settings.

### Issue: Assessment is too wide/narrow
**Solution**: The assessment has a max-width of 900px. You can change this in the CSS:
```css
.fp-wrapper {
  max-width: 1200px;  /* Change this value */
}
```

---

## Advanced: Making it Dynamic with WordPress

If you want the assessment results to be saved in WordPress (not just browser localStorage), you'll need:

1. A custom WordPress plugin to handle form submissions
2. A database table to store results
3. PHP backend code to process and store data

This requires WordPress development knowledge. Consider hiring a WordPress developer if you need this functionality.

---

## Testing Checklist

Before making your assessment live, test:

- [ ] All questions can be selected
- [ ] Navigation (Previous/Next) works
- [ ] Progress bar updates correctly
- [ ] Results page displays with chart
- [ ] PDF download works
- [ ] "Start New Assessment" clears data
- [ ] Mobile responsive (test on phone)
- [ ] Works in different browsers (Chrome, Firefox, Safari, Edge)

---

## Need Help?

If you encounter issues:
1. Check the browser console for JavaScript errors (F12 > Console)
2. Verify all CDN scripts are loading
3. Try Method 2 (iframe) if Method 1 has CSS conflicts
4. Test in a different WordPress theme to isolate theme conflicts

For custom development or advanced features, consider consulting a WordPress developer.
