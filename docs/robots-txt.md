## robots.txt

The `robots.txt` file is a web standard used to communicate with web crawlers and search engine bots. It specifies which areas of the website should or should not be crawled and indexed.

### Purpose

- **Control crawler access** to specific directories and pages
- **Prevent duplicate content** issues by blocking parameter-based URLs
- **Protect sensitive areas** like admin panels and user data
- **Manage server load** by controlling crawl frequency
- **Guide search engines** to important content via sitemap references

### Location

The file must be placed at the root of your domain:

```
https://yourdomain.com/robots.txt
```

### Important Notes

- `robots.txt` is a **directive, not a security measure**. It requests that bots respect the rules but doesn't enforce them.
- Sensitive content should be protected with proper authentication, not just robots.txt.
- Changes take effect once search engines re-crawl the file (timing varies by bot).
- Always test your robots.txt using tools like [Google Search Console](https://search.google.com/search-console).

### Syntax Reference

- `User-agent:` - Specifies which crawler the rules apply to
- `Allow:` - Permits access to specific paths
- `Disallow:` - Blocks access to specific paths
- `Sitemap:` - Points to XML sitemap location
- `*` - Wildcard matching any sequence of characters
- `$` - End of URL marker

### Recommendations

- Always update the sitemap URLs with your actual domain
- Test your robots.txt file before deploying using Google Search Console's robots.txt tester
- Remember that robots.txt is advisory - use proper authentication for truly sensitive content
- Monitor your crawl budget in the search console to adjust the configuration if needed

### Resources

- [Google's robots.txt specifications](https://developers.google.com/search/docs/crawling-indexing/robots/intro)
- [robots.txt tester tools](https://support.google.com/webmasters/answer/6062598)
