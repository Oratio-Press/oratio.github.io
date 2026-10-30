# oratioprayer.com

The website for the Oratio prayer app, by Oratio Press LLC. GitHub Pages builds
it with Jekyll from `main` and serves it at https://oratioprayer.com (`CNAME`):
a push to `main` publishes it, with no build step to run.

## How it is put together

| Path | What |
|---|---|
| `_config.yml` | The site's name, the header's navigation, and the email address the launch-list and contact links use. |
| `_layouts/default.html` | The one layout: header, the burgundy hero card, footer. A page's front matter sets its `title`, `description`, and `hero` (kicker, title, lead, buttons; `logo: true` adds the logo, as Home does). |
| `_includes/launch-list.html` | The closing invitation at the end of most pages. |
| `index.html`, `about.html`, … | The pages: front matter, then their content. |
| `privacy.html` | The privacy policy the app stores link to. Keep it in step with what the app collects. |
| `assets/css/site.css` | All the styling. Its colors, type, radii, and shadows are the app's design tokens (`app/lib/theme/tokens.dart` in Oratio-Prayer-App), with the app's night theme in dark mode. |
| `assets/img/` | The client's logo files, from Oratio-Prayer-App's `design/brand/` (never edited by hand), the favicon and touch icon from the app's web icons, and the link-preview image (Play's feature graphic). |
| `assets/fonts/` | Crimson Pro and Inter, the app's fonts, subset to Latin as WOFF2 (SIL Open Font License, `OFL.txt`). Served from the site, so a page loads nothing from anyone else. |

## Working on it

```sh
gem install jekyll -v 3.10.0 webrick   # GitHub Pages' Jekyll version
jekyll serve                           # http://localhost:4000
```

The launch-list and contact buttons open an email to oratiopress@gmail.com
until a real mailing list exists; change `email` and `launch_list` in
`_config.yml` to move them.
