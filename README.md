## Obsidian Auto Link Title
![Auto linking example](auto-link-title.gif)

### Automatically Title New Links
This plugin automatically fetches the webpage to extract link titles when they're pasted, creating a markdown link with the correct title set.

#### For example:

When pasting `https://github.com/zolrath/obsidian-auto-link-title` the plugin fetches the page and retrieves the title, resulting in a paste of: `[zolrath/obsidian-auto-link-title: Automatically fetch the titles of pasted links](https://github.com/zolrath/obsidian-auto-link-title)`

### Add Titles To Existing Raw URLs
Additionally, using `ctrl-shift-e` (Windows) or `cmd-shift-e` (OS X) you can enhance an existing raw link to a markdown formatted link with the proper title.

If your text cursor is within the url `https://github.com/zolrath/obsidian-auto-link-title` pressing `ctrl-shift-e` or `cmd-shift-e` converts the text to `[zolrath/obsidian-auto-link-title: Automatically fetch the titles of pasted links](https://github.com/zolrath/obsidian-auto-link-title)`

### Overwrite Titles Of Existing Markdown Links
Additionally, using `ctrl-shift-e` (Windows) or `cmd-shift-e` (OS X) you can overwrite an existing title of a markdown link with the fetched title from the url.

If your text cursor is within `[some plugin](https://github.com/zolrath/obsidian-auto-link-title)` pressing `ctrl+shift+e` fetches the sites title and replaces it, resulting in `[zolrath/obsidian-auto-link-title: Automatically fetch the titles of pasted links](https://github.com/zolrath/obsidian-auto-link-title)`

### Mobile Pasting
In order to paste the URL ensure you perform the `Tap and Hold -> Paste` action to paste the URL into your document.

#### Gboard
Google's [Gboard](https://play.google.com/store/apps/details?id=com.google.android.inputmethod.latin&hl=en_US&gl=US) keyboard has a Clipboard helper shortcut above the keyboard to quickly paste.
Due to the implementation of that feature, it does not trigger the `paste` event, preventing this plugin from interacting with the text.

### DeArrow Integration
This plugin now supports fetching de-branded titles for YouTube videos using the DeArrow API. DeArrow removes sponsorships, branding, and other non-essential elements from YouTube video titles, providing cleaner, more informative link text.

#### How it works:
- When pasting a YouTube URL (e.g., `https://www.youtube.com/watch?v=VIDEO_ID` or `https://youtu.be/VIDEO_ID`), the plugin checks if the "Use DeArrow" setting is enabled.
- If enabled, it queries the DeArrow API for alternative titles and selects the most trusted one (based on community votes or locked status).
- If no trusted title is available or the API fails, it falls back to the standard title fetching methods (Link Preview or scraper).
- The fetched DeArrow title is cleaned (removes special markers like `>`) and used as the link text.

#### Enabling DeArrow:
1. Open the plugin settings in Obsidian.
2. Toggle "Use DeArrow" to **on**.
3. Paste a YouTube link to test – the title should now be de-branded if available.

#### Notes:
- This feature only applies to YouTube URLs.
- Requires an internet connection, like other fetching methods.
- DeArrow API is free and community-driven; see [DeArrow Docs](https://wiki.sponsor.ajay.app/w/API_Docs/DeArrow) for more details.
- If you encounter issues, ensure your Obsidian instance can make external API requests (no network blocks).

For installation and other details, see the [Obsidian plugin page](https://obsidian.md/plugins?id=auto-link-title).
