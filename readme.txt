=== PrerenderX – Instant Page & Speculation Preloader ===
Contributors: saeedtx
Tags: prerender, speculation rules, instant page, prefetch, speed
Requires at least: 5.7
Tested up to: 7.1
Stable tag: 1.1.0
Requires PHP: 7.4
License: GPLv2 or later
License URI: https://www.gnu.org/licenses/gpl-2.0.html

Next-generation browser preloading and speculation rules control suite with zero external JavaScript overhead.

== Description ==
PrerenderX accelerates page navigation to near-zero latency by leveraging Chromium's native Speculation Rules engine. Instead of running heavy JavaScript preloading scripts, PrerenderX activates native browser-level background rendering with granular administrative controls.

= Key Features =
* **Dual Delivery Modes:** Choose between instantaneous Prerender (DOM background render) or lightweight Prefetch (HTML cache only).
* **Configurable Eagerness:** Trigger preloads via Moderate hover intent (200ms hold), Conservative click initiation, or Eager viewport loading.
* **Save-Data Awareness:** Automatically halts background fetching when mobile visitors have Data Saver mode turned on.
* **Granular Exclusions:** Visual exclusion managers for custom wildcard URL paths and CSS selectors directly from the dashboard.
* **User Session Protection:** Optionally disable preloading for logged-in administrators and editors.
* **WooCommerce Compatible:** Automatically excludes cart, checkout, and customer account endpoints.
* **Zero Runtime JS:** 100% native browser implementation with no external render-blocking assets.

== Installation ==
1. Upload the `prerenderx-instant-preloader` folder to your `/wp-content/plugins/` directory.
2. Activate the plugin via the 'Plugins' menu in WordPress.
3. Configure your preferences under **Settings > PrerenderX**.

== Changelog ==
= 1.1.0 =
* Initial release of PrerenderX suite.
* Administrative control dashboard under Settings > PrerenderX.
* Support for Prerender and Prefetch modes with granular eagerness levels.
* Integrated mobile Save-Data header detection.
* Built-in visual wildcard URL and CSS selector exclusions.
