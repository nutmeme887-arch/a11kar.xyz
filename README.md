# 1Kar website

Responsive English and Burmese landing and download pages using the supplied app logo, screenshots, and APKs. No runtime CDN or JavaScript framework is required. Download links also work without JavaScript.

Run `npm run serve`, then open http://localhost:8080. Run `npm run build` after editing `assets/input.css` to regenerate `assets/styles.css`. The generated CSS is included.

Publish `index.html`, `download.html`, `assets/`, and `src/` together. The hosting service must support APK files up to 54 MiB. The APK paths are relative, so the site also works in a subdirectory.

The download page defaults to Universal. On Android, browser Client Hints may suggest ARM64, ARMv7, or x86_64 when architecture and bitness are available. Missing hints and other platforms retain Universal. Users can always download Universal or a specific build directly. Device hints do not guarantee app compatibility.

Release 1.0.0 includes Universal (53.6 MiB), ARM64 (19.7 MiB), ARMv7 (17.3 MiB), and x86_64 (21.1 MiB). Sizes were calculated from the supplied files; their bundled native architectures were verified. Minimum Android version was not supplied and is not claimed on the site.

For a new release, update links and release labels in both HTML files and the package definitions in `assets/app.js`. Translations are in the `words` dictionary in `assets/app.js`; English is included in the HTML as a fallback. Burmese is the default, regardless of browser language or saved preferences. Add `?e` to either page for English. The language switcher updates the URL and internal navigation preserves the selection. A native speaker should review Burmese copy before publication.

## SEO

Both pages include Burmese HTML content, page titles, descriptions, Open Graph and Twitter metadata, language alternates, canonical links, and SoftwareApplication structured data. JavaScript updates metadata for `?e`. `robots.txt` permits crawling. Before publishing, replace relative canonical, alternate, Open Graph URL and social image URLs in the HTML with the final HTTPS domain and add a sitemap using that domain. Social crawlers commonly do not execute JavaScript; English-specific share previews require server rendering or prerendering the `?e` variant.
