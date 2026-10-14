![PrerenderX – Instant Page & Speculation Preloader](assets/banner-772x250.png)

# PrerenderX – Instant Page & Speculation Preloader ⚡

> Next-generation browser preloading and W3C Speculation Rules control suite with granular administrative settings, Save-Data awareness, and zero external JavaScript overhead.

[![WordPress Plugin](https://img.shields.io/badge/WordPress.org-prerenderx--instant--preloader-blue.svg)](https://wordpress.org/plugins/prerenderx-instant-preloader/)
[![WordPress Tested](https://img.shields.io/badge/WordPress-5.7%2B-blue.svg)](https://wordpress.org/)
[![PHP Version](https://img.shields.io/badge/PHP-7.4%2B-purple.svg)](https://php.net/)
[![License: GPL v2+](https://img.shields.io/badge/License-GPLv2%2B-green.svg)](https://www.gnu.org/licenses/gpl-2.0.html)

---

## 🚀 Overview

**PrerenderX** accelerates WordPress page navigation to near-zero latency by leveraging Chromium's native [Speculation Rules API](https://developer.mozilla.org/en-US/docs/Web/API/Speculation_Rules_API).

Instead of injecting heavy third-party JavaScript libraries that strain the main thread, **PrerenderX** communicates directly with the browser's native rendering engine to prerender or prefetch target pages in the background before the user even finishes clicking.

## ✨ Key Features

- **⚙️ Dedicated Admin Dashboard:** Configure all preloading behaviors visually under **Settings > PrerenderX** without touching code.
- **🔄 Dual Delivery Modes:**
  - **Prerender:** Renders full HTML & DOM in the background for instantaneous (near 0ms) transitions.
  - **Prefetch:** Bandwidth-safe mode that pre-downloads HTML only without rendering.
- **🎯 Configurable Eagerness:** Choose between `Moderate` (hover intent / 200ms hold), `Conservative` (pointer down / click start), or `Eager` (viewport detection).
- **📶 Save-Data & Network Awareness:** Automatically inspects the client `Save-Data` HTTP header and suspends background preloading for mobile visitors on metered connections.
- **🛡️ User Session Protection:** Option to disable preloading for logged-in administrators and users.
- **🚫 Visual Exclusions Manager:** Define custom wildcard (`*`) URL paths and CSS selectors directly from the WordPress dashboard.
- **🛒 WooCommerce Compatible:** Automatically detects and excludes WooCommerce Cart, Checkout, and My Account endpoints.
- **⚡ Zero Runtime JS:** 100% native browser implementation with no external JavaScript or CSS files loaded.

## 🛠️ How It Works

PrerenderX outputs a native specification block in the document footer:

```html
<script type="speculationrules" id="prerenderx-speculation-rules">
{
  "prerender": [
    {
      "source": "document",
      "where": {
        "and": [
          { "href_matches": "/*" },
          { "not": { "href_matches": [...] } },
          { "not": { "selector_matches": "..." } }
        ]
      },
      "eagerness": "moderate"
    }
  ]
}
</script>
```

Supporting browsers (Chrome, Edge, Brave, Opera) parse the rules natively, while other browsers safely ignore the tag with zero errors.

🔌 Developer Hooks
Programmatically customize excluded URL paths using the prerenderx_exclude_paths filter:
```
add_filter('prerenderx_exclude_paths', function( array $exclude_paths ): array {
    $exclude_paths[] = '/my-custom-portal/*';
    $exclude_paths[] = '/private-downloads/*';
    return $exclude_paths;
});
```
To exclude specific links in your HTML markup, add rel="nofollow" or the .no-prerender class:

```
<a href="/special-page" class="no-prerender">Special Link</a>
```
📦 Installation
From WordPress.org (Recommended):
In your WordPress Admin, go to Plugins > Add New.

Search for PrerenderX.

Click Install Now and Activate.

Configure settings under Settings > PrerenderX.

Via Git:
```
git clone [https://github.com/saeedtx/PrerenderX.git](https://github.com/saeedtx/PrerenderX.git) wp-content/plugins/prerenderx-instant-preloader
```
👤 Author
Saeed Tosifyan

Website: medseo.ir

LinkedIn: linkedin.com/in/saeedtx

WordPress.org: @saeedtx

📄 License
This project is open-source software licensed under the GNU General Public License v2.0 or later.
