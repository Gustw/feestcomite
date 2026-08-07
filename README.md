# Feestcomité Sint-Denijs - Website

Officiële website van het Feestcomité Sint-Denijs, gebouwd met [Hugo](https://gohugo.io/) en gehost op GitHub Pages.

## 🚀 Technologie

- **Static Site Generator**: [Hugo](https://gohugo.io/) (Extended)
- **CMS**: [Decap CMS](https://decapcms.org/) (voorheen Netlify CMS)
- **Hosting**: GitHub Pages
- **CI/CD**: GitHub Actions

## 📁 Structuur

```
site-feestcomite/
├── content/              # Alle inhoud (Markdown bestanden)
│   ├── _index.md         # Homepage
│   ├── over-ons/         # Over ons pagina
│   ├── evenementen/      # Evenementen (komend + archief)
│   └── archief/          # Archief overzichtspagina
├── static/
│   ├── admin/            # Decap CMS configuratie
│   └── images/           # Uploads en afbeeldingen
├── themes/
│   └── feestcomite-theme/  # Custom thema
├── .github/workflows/    # GitHub Actions (auto-deploy)
└── hugo.toml             # Hugo configuratie
```

## ✏️ Content Beheren

### Via het CMS (aanbevolen)

1. Ga naar `https://jouw-site.github.io/site-feestcomite/admin/`
2. Log in met je GitHub account
3. Bewerk pagina's, voeg evenementen toe, upload foto's
4. Klik op "Publiceren" — de site wordt automatisch bijgewerkt

### Via bestanden (geavanceerd)

1. Bewerk Markdown bestanden in de `content/` map
2. Commit en push naar `main`
3. GitHub Actions bouwt en deployt automatisch

## 🎨 Evenementen beheren

### Nieuw evenement toevoegen
- Ga naar CMS → Evenementen → Nieuw
- Vul de details in (titel, datum, type, programma, etc.)
- Zet status op "Komend"

### Evenement archiveren
- Open het evenement in het CMS
- Verander status van "Komend" naar "Voorbij (archief)"
- Voeg eventueel foto's toe als terugblik
- Publiceer

## 🏗️ Lokaal ontwikkelen

```bash
# Hugo installeren (https://gohugo.io/installation/)
# Dan:
hugo server -D
```

De site draait dan op `http://localhost:1313/`

## 🔧 GitHub Pages instellen

1. Maak een GitHub repository aan
2. Pas `hugo.toml` aan:
   - `baseURL` → je GitHub Pages URL
3. Pas `static/admin/config.yml` aan:
   - `repo` → je GitHub username/repo
4. Push alle bestanden naar de `main` branch
5. Ga naar Repository Settings → Pages → Source: "GitHub Actions"
6. De site wordt automatisch gedeployd

## 📋 CMS Authenticatie instellen

Om het CMS te laten werken met GitHub:

1. Ga naar [GitHub OAuth Apps](https://github.com/settings/developers)
2. Of gebruik de ingebouwde GitHub backend (aanbevolen voor kleine teams)
3. Meer info: [Decap CMS Authentication](https://decapcms.org/docs/authentication-backends/)

## 📄 Licentie

MIT License - Vrij te gebruiken en aan te passen.

