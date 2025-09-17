# Content Discovery – TryHackMe

## Overview
Content Discovery in web applications focuses on identifying hidden or forgotten files, directories, and endpoints that could expose sensitive information or functionality.

## Methods

### Manual
- **robots.txt** → reveals restricted areas not meant for indexing.
- **sitemap.xml** → lists intended indexed pages, sometimes includes forgotten ones.
- **Favicons** → identify frameworks/CMS via OWASP favicon database.
- **Page Source & Comments** → check for hidden links, credits, or clues.
- **HTTP Headers** → reveal server info (e.g., NGINX, PHP versions).

### Automated
- Use tools like:
  - Gobuster  
  - Dirb  
  - Feroxbuster  
- Example:
  ```bash
  gobuster dir -u http://target-site.com -w wordlist.txt
