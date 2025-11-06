<p align="center">
  <img src="https://raw.githubusercontent.com/MonolitDigital-Products/.github/main/profile/monolit-shield-banner.png" alt="Monolit Shield – Hardened WordPress MU Plugin" width="720">
</p>

<h1 align="center">Monolit Shield (Hardened) — MU Plugin</h1>

<p align="center">
  <strong>Zero-configuration WordPress hardening for developers.</strong><br>
  Secure defaults without dashboards or toggles.
</p>

<p align="center">
  <a href="https://img.shields.io/badge/WordPress-6.8%20tested-0073aa?logo=wordpress&logoColor=white"><img src="https://img.shields.io/badge/WordPress-6.8%20tested-0073aa?logo=wordpress&logoColor=white" alt="Tested WP 6.8"></a>
  <a href="https://img.shields.io/badge/PHP-7.4%20–%208.3-777bb4?logo=php&logoColor=white"><img src="https://img.shields.io/badge/PHP-7.4%20–%208.3-777bb4?logo=php&logoColor=white" alt="PHP 7.4–8.3"></a>
  <a href="LICENSE"><img src="https://img.shields.io/badge/license-MIT-green" alt="MIT License"></a>
</p>

---

> 🇪🇸 Read this in Spanish: <a href="./README.es.md">README.es.md</a>

---

## 🔐 Overview
Monolit Shield applies WordPress security hardening automatically: admin aliasing, user-enum protection, HTML/JSON-LD sanitization, and modern security headers. It ships as a **MU-plugin** intended for developers and CI/CD pipelines.

## 🚀 Features
- **Admin aliasing** — access `/admin-portal` instead of `/wp-admin` (customizable)
- **User enumeration protection** — blocks `?author=1` and REST `/wp-json/wp/v2/users`
- **Disables XML-RPC, feeds and pingbacks**
- **Head cleanup** — removes `generator`, oEmbed and discovery meta
- **Email cloaking** (HTML + JSON-LD)
- **Security headers**: X-Content-Type-Options, X-Frame-Options, Referrer-Policy, Permissions-Policy, CSP *(Report-Only)*
- Elementor / WPML safe
- Zero-config, deterministic behavior

## 🧭 Install (MU)
Copy the contents of `mu-plugins/` to your site’s `wp-content/mu-plugins/`.

Recommended: apply server templates in `server/` (Apache/Nginx).

### Customize the alias
In `wp-config.php`:
```php
define( 'MSHIELD_ADMIN_SLUG', 'your-custom-admin-slug' );
```
Then visit: `https://yourdomain.com/your-custom-admin-slug/`

## 🔍 Quick checks
```bash
curl -I https://yourdomain.com/wp-admin/             # → 403 (anonymous)
curl -I https://yourdomain.com/admin-portal/         # → login
curl -I https://yourdomain.com/wp-json/wp/v2/users   # → 403
curl -I https://yourdomain.com/xmlrpc.php            # → 403
```

## 🧱 Compatibility
- WordPress 5.8 → 6.8+
- PHP 7.4 → 8.3+
- Works with caches/CDNs/managed hosts
- Does **not** auto-edit `.htaccess` (templates included)

## 🛠️ Development
- License: MIT
- No telemetry, no UI
- PRs welcome — see <a href="./CONTRIBUTING.md">CONTRIBUTING.md</a>

## 🧾 Changelog
See <a href="./CHANGELOG.md">CHANGELOG.md</a>

---

© 2025 Monolit Digital — https://monolit.digital
