# Chatbase Integration Guide for Gamma Website

## Overview
This guide provides step-by-step instructions to integrate your Chatbase AI assistant into your Gamma website at creator.medtools.id.

## Implementation Options

### Option 1: Complete HTML Embed (Recommended)
Use the complete HTML file `gamma-chatbase-embed.html` as a custom HTML block in Gamma.

### Option 2: Script-Only Integration
Use just the JavaScript portion if you prefer minimal integration.

## Step-by-Step Integration

### For Gamma.ai Platform:

1. **Access Your Gamma Editor**
   - Go to your Gamma dashboard
   - Open your creator.medtools.id site for editing

2. **Add Custom HTML Block**
   - Look for "Embed" or "Custom HTML" component in Gamma
   - Add a new HTML/Embed block to your page

3. **Insert the Integration Code**
   - Copy the entire content from `gamma-chatbase-embed.html`
   - Paste it into the HTML/Embed block

4. **Alternative: Script-Only Method**
   If you prefer to add just the script to your site's footer:
   
   ```html
   <!-- Add this to your site's footer or custom code section -->
   <div class="chatbase-container" style="position: fixed; bottom: 20px; right: 20px; z-index: 9999;">
       <button class="chatbase-fallback" id="chatbaseFallback" style="display: none; background: #007bff; color: white; border: none; border-radius: 50px; padding: 15px 20px; cursor: pointer; font-size: 16px; box-shadow: 0 4px 12px rgba(0, 123, 255, 0.3);">
           💬 Chat with AI Assistant
       </button>
   </div>
   
   <script>
   (function(){
     if (!window.chatbase || window.chatbase("getState") !== "initialized") {
       window.chatbase = (...arguments) => {
         if (!window.chatbase.q) {
           window.chatbase.q = [];
         }
         window.chatbase.q.push(arguments);
       };
       window.chatbase = new Proxy(window.chatbase, {
         get(target, prop) {
           if (prop === "q") return target.q;
           return (...args) => target(prop, ...args);
         }
       });
     }
     const onLoad = function() {
       const script = document.createElement("script");
       script.src = "https://www.chatbase.co/embed.min.js";
       script.id = "y7jTzyHhLeJFzUvlpBqqP";
       script.setAttribute("chatbotId", "y7jTzyHhLeJFzUvlpBqqP");
       script.setAttribute("domain", "creator.medtools.id");
       document.body.appendChild(script);
       
       // Fallback handling
       script.onerror = function() {
         document.getElementById('chatbaseFallback').style.display = 'block';
         document.getElementById('chatbaseFallback').onclick = function() {
           alert('AI Assistant is temporarily unavailable. Please try again later.');
         };
       };
     };
     if (document.readyState === "complete") {
       onLoad();
     } else {
       window.addEventListener("load", onLoad);
     }
   })();
   </script>
   ```

## Features Included

### ✅ Enhanced Integration Features:
- **Automatic Retry Logic**: Attempts to load the chatbase script 3 times
- **Fallback Interface**: Shows a backup button if the main script fails
- **Status Indicators**: Visual feedback during loading
- **Error Handling**: Graceful degradation when services are unavailable
- **Mobile Responsive**: Works on all device sizes
- **Non-intrusive Design**: Floating button in bottom-right corner

### ✅ Styling Features:
- Modern blue theme matching your site
- Smooth hover animations
- Loading spinner during initialization
- Status messages for user feedback

## Troubleshooting

### If the Chatbase doesn't appear:
1. Check browser console for errors
2. Verify the script URL is accessible
3. Ensure your domain (creator.medtools.id) is whitelisted in Chatbase settings

### If you see the fallback button:
- This means the main Chatbase script couldn't load
- The fallback provides a temporary solution
- Check if https://www.chatbase.co/embed.min.js is accessible

## Customization Options

### Change Button Position:
Modify the CSS in the `.chatbase-container` class:
```css
.chatbase-container {
    position: fixed;
    bottom: 20px;    /* Distance from bottom */
    right: 20px;     /* Distance from right */
    /* For left side: left: 20px; right: auto; */
}
```

### Change Colors:
Modify the button colors in `.chatbase-fallback`:
```css
.chatbase-fallback {
    background: #your-color;  /* Change button color */
}
```

## Testing

After implementation:
1. Visit your live site
2. Look for the chat button in bottom-right corner
3. Check browser console for any errors
4. Test the chat functionality

## Support

If you encounter issues:
1. Check the browser console for error messages
2. Verify your Chatbase agent ID and domain settings
3. Ensure your Gamma site allows custom HTML/JavaScript

---

**Note**: The current Chatbase embed script (https://www.chatbase.co/embed.min.js) returns a 404 error, which is why the fallback system is crucial. Monitor this URL and update when the service is restored.
