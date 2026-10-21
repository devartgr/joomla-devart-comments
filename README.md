# DevArt Comments for Joomla

Modern comments for Joomla 6 articles (and multi-context hosts), designed for
production sites that need guest email OTP, registered commenting, moderation,
cache-safe write endpoints, and Cloudflare-friendly frontend behaviour.

![Joomla](https://img.shields.io/badge/Joomla-6.x-blue)
![PHP](https://img.shields.io/badge/PHP-8.3%2B-green)
![Release](https://img.shields.io/badge/Version-1.1.0-orange)
![License](https://img.shields.io/badge/License-GPLv2%2B-red)

---

## Overview

DevArt Comments is a Joomla 6 package with:

- `com_devartcomments` — administrator component + site JSON APIs
- `plg_content_devartcomments` — article panel / badge (UI gated by `enable_articles`)
- `plg_user_devartcomments` — user delete cleanup
- `plg_privacy_devartcomments` — Privacy export / remove
- `plg_extension_devartcomments` — Options ↔ Settings params merge
- `plg_task_devartcomments` — scheduled OTP / session cleanup + job queue
- `mod_devartcomments_latest` — latest comments module (context source selector)

Comments are keyed by `context` + `item_id` so articles ship first and Video /
Business / Events (and later Shop) can attach without schema forks. Host
products stay thin: Comments owns ACL, OTP, storage, and markup.

The extension targets Joomla 6, PHP 8.3+, Full Page Cache, and Cloudflare.

---

## Version 1.1.0

DevArt Comments **1.1.0** is the first **public** release.

### Highlights

- Article comments with SSR first page, guest email OTP sessions, replies,
  likes, reports, and reply subscriptions
- Bot protection: PoW / reCAPTCHA v2 / Turnstile
- Admin moderation, bans, per-item overrides, privacy tools, job queue
- Multi-context policies for Video / Business / Events (`enable_*` default Off)
- Denylist exclusions + Latest Comments module source selector
- 15 language packs (`en-GB`, `el-GR`, `fr-FR`, `de-DE`, `es-ES`, `it-IT`,
  `pt-BR`, `cs-CZ`, `nl-NL`, `pl-PL`, `ru-RU`, `uk-UA`, `ja-JP`, `tr-TR`,
  `zh-CN`)

### Requirements

- Joomla 6.0+
- PHP 8.3+

### Safe update

First public release. Safe install on a new site, or update from late `1.0.x`
development builds using the full `pkg_devartcomments` package only.

---

## Requirements

- Joomla 6.0+
- PHP 8.3.0+
- MySQL / MariaDB with utf8mb4

No Joomla 3/4/5 or PHP 8.2-and-below compatibility.

---

## Installation

1. Download:

   `pkg_devartcomments_v1.1.0.zip`

2. Open Joomla administrator.

3. Go to:

   `System → Install → Extensions`

4. Upload and install the package.

5. Open:

   `Components → DevArt Comments → Settings`

6. Enable articles (`enable_articles`) and configure guest OTP / bot protection
   as needed.

7. Optionally place **DevArt Latest Comments** in a module position.

---

## Updating

DevArt Comments uses the standard Joomla update system.

Before updating a production website:

- Create a complete backup
- Test on staging
- Verify comment post, guest OTP, moderation, and (if used) Cloudflare purge
- Clear page cache / CDN cache when necessary

Install or update using the full `pkg_devartcomments` package only. Do not
install individual package members by hand.

Cloudflare URL purge (if used) is configured in **DevArt Utils**, not in the
Comments “Clear Joomla page cache” switch.

Keep `enable_video` / `enable_business` / `enable_events` Off until the matching
host thin plugin is installed and pair-QA passes.

---

## Download

Latest release:

`pkg_devartcomments_v1.1.0.zip`

GitHub releases:

https://github.com/devartgr/joomla-devart-comments/releases

Direct download:

https://github.com/devartgr/joomla-devart-comments/releases/download/v1.1.0/pkg_devartcomments_v1.1.0.zip

SHA-256:

`79d0bcb675e47d066c995ea300651a38d73484e74a52ec96fd10446b563e4790`

---

## Support

Project repository:

https://github.com/devartgr/joomla-devart-comments

Website:

https://devart.gr

Before reporting an issue, include:

- Joomla version
- PHP version
- Database type and version
- DevArt Comments version
- Registered or guest path
- Bot protection mode
- Relevant error message
- Steps to reproduce

Do not include passwords, private keys, access tokens, or other sensitive information.

---

## License

DevArt Comments is released under the GNU General Public License version 2 or later.

See the included license files for complete licensing information.

---

## Author

**Kostas Stathopoulos — DevArt**

Website: https://devart.gr
