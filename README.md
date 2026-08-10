# Feestcomité Sint-Denijs - Website

Officiële website van het Feestcomité Sint-Denijs, gebouwd met [Hugo](https://gohugo.io/) en gehost op GitHub Pages.

**Live site**: https://www.feestcomitesintdenijs.be  
**CMS**: https://www.feestcomitesintdenijs.be/admin/  
**Handleiding**: zie `HANDLEIDING.md`

## 🚀 Technologie

- **Static Site Generator**: [Hugo](https://gohugo.io/) (Extended)
- **CMS**: [Sveltia CMS](https://github.com/sveltia/sveltia-cms) (open source, drop-in Decap CMS vervanging)
- **Hosting**: GitHub Pages
- **CI/CD**: GitHub Actions
- **Authenticatie**: [Sveltia CMS Auth](https://github.com/sveltia/sveltia-cms-auth) (Cloudflare Worker)
- **Domein**: www.feestcomitesintdenijs.be

## 📁 Structuur

```
site-feestcomite/
├── content/                # Alle inhoud (Markdown bestanden)
│   ├── _index.md           # Homepage
│   ├── over-ons/           # Over ons pagina
│   ├── evenementen/        # Alle evenementen (komend + archief, automatisch)
│   └── archief/            # Archief overzichtspagina (_index.md)
├── static/
│   ├── admin/              # CMS configuratie (config.yml + index.html)
│   ├── images/uploads/     # Geüploade afbeeldingen
│   └── CNAME               # Custom domain configuratie
├── themes/
│   └── feestcomite-theme/  # Custom thema (layouts, CSS, fonts, logo)
├── .github/workflows/      # GitHub Actions (auto-deploy bij push)
├── hugo.toml               # Hugo configuratie
├── HANDLEIDING.md          # Gebruikershandleiding (Nederlands)
└── README.md               # Dit bestand
```

## ✏️ Content Beheren

### Via het CMS (aanbevolen)

1. Ga naar https://www.feestcomitesintdenijs.be/admin/
2. Log in met het GitHub-account dat toegang heeft
3. Bewerk pagina's, voeg evenementen toe, upload foto's
4. Klik op "Publiceren" — de site wordt automatisch bijgewerkt (±2 min)

### Via bestanden (geavanceerd)

1. Bewerk Markdown bestanden in de `content/` map
2. Commit en push naar `master`
3. GitHub Actions bouwt en deployt automatisch

## 🎨 Evenementen beheren

### Nieuw evenement toevoegen
- Ga naar CMS → Evenementen → Nieuw
- Vul de details in (titel, startdatum, einddatum, type, programma, etc.)
- Publiceer

### Automatisch archiveren
- Evenementen verhuizen **automatisch** naar het archief zodra de (eind)datum voorbij is
- Je hoeft niets handmatig te doen

### Meerdaags evenement
- Vul zowel **Startdatum** als **Einddatum** in
- Het programma kan per dag gegroepeerd worden via het "Dag" veld

## 🏗️ Lokaal ontwikkelen

```bash
# Hugo installeren (https://gohugo.io/installation/)
hugo server -D --buildFuture
```

De site draait dan op `http://localhost:1313/`

## 🔧 Configuratie

### GitHub Pages
- Repository Settings → Pages → Source: "GitHub Actions"
- Custom domain: `www.feestcomitesintdenijs.be`
- Enforce HTTPS: aan

### CMS Authenticatie (Cloudflare Worker)
- Worker: `sveltia-cms-auth.gust-wittevrongel.workers.dev`
- Environment variables:
  - `GITHUB_CLIENT_ID`: OAuth App Client ID
  - `GITHUB_CLIENT_SECRET`: OAuth App Client Secret
  - `ALLOWED_DOMAINS`: `www.feestcomitesintdenijs.be,feestcomitesintdenijs.be,gustw.github.io`

### GitHub OAuth App
- Authorization callback URL: `https://sveltia-cms-auth.gust-wittevrongel.workers.dev/callback`

### DNS (Theory7)
- 4x A-record `@` → GitHub Pages IPs (185.199.108-111.153)
- CNAME `www` → `gustw.github.io`

## 📄 Licentie

MIT License - Vrij te gebruiken en aan te passen.
