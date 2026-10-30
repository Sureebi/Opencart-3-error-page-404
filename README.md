# POS-inspired 404 template for OpenCart 3

A single-file, responsive Twig template with a POS terminal illustration, Bulgarian and English copy, and an orange accent shape.

## Files

- `not_found.twig` — the complete template, including CSS and the embedded PNG illustration. No additional asset uploads or build tools are required.

## Installation

1. Back up your existing `catalog/view/theme/default/template/error/not_found.twig` outside the public website directory.
2. Upload this repository's `not_found.twig` to that location.
3. If your active theme has its own `template/error/not_found.twig`, check which template OpenCart actually uses before replacing anything.
4. Check **Design → Theme Editor** for a database override of `error/not_found`.
5. Open a nonexistent page. If the old design remains, refresh **Dashboard → Developer Settings → Theme cache**, then hard-refresh your browser.

No controller, language file, or database changes are needed. The existing OpenCart controller remains responsible for the HTTP 404 status.

## Personalization before publishing

Adapted from the POS-HUB version with the store's phone number and email removed. No contact details are included in the template.

Edit the Bulgarian and English strings directly in the Twig file. The `ph404_en` variable selects English when the supplied OpenCart language `code` is `en`; other values currently select Bulgarian. Add conditions/translations for other languages if needed.

The home button uses OpenCart's `continue` URL. The categories button opens the existing sitemap route, `index.php?route=information/sitemap`; it is not a custom categories page.

The illustration is embedded as a PNG data URI. Replace the image's `src` to use another illustration. A Content Security Policy must allow `data:` images for the embedded image to display.

The decorative shape is controlled by `.ph404-art::before`; the orange accent colors and other layout rules are in the inline `<style>` block.

## Compatibility and scope

Developed and visually checked on a local OpenCart 3 store with the OPC100227_1 theme. Other themes may need spacing or typography adjustments; universal theme compatibility has not been tested.

Preserves header, footer, breadcrumbs, both sidebar slots, `content_top`, `content_bottom`, and OpenCart's content-column sizing. The title uses `role="heading"` and `aria-level="1"` because the original theme moves native h1/h2 headings outside the content area.

No JavaScript, third-party scripts, remote image services, credentials, or store configuration files are included. The header/footer and their existing scripts still come from the destination store.
