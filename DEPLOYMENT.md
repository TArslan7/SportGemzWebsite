# Deployment Instructies voor SportGemz Website

## Optie 1: GitHub Pages (Gratis)

### Stappen:

1. **Push de deploy branch naar GitHub:**
   ```bash
   git push origin deploy
   ```

2. **Activeer GitHub Pages in GitHub:**
   - Ga naar je repository op GitHub: https://github.com/TArslan7/SportGemzWebsite
   - Klik op **Settings** (Instellingen)
   - Scroll naar **Pages** in het linker menu
   - Bij **Source**, selecteer **GitHub Actions**
   - De workflow zal automatisch draaien en je website deployen

3. **Je website is beschikbaar op:**
   - `https://tarslan7.github.io/SportGemzWebsite/`

**Let op:** Het kan 1-2 minuten duren voordat de website live gaat na de eerste deployment.

---

## Optie 2: Netlify (Gratis, Sneller Setup)

### Via Netlify Drop (Drag & Drop):
1. Ga naar https://app.netlify.com/drop
2. Sleep de map met je website bestanden (index.html, styles.css, script.js) naar de pagina
3. Je website is direct live!

### Via Git Integration:
1. Ga naar https://app.netlify.com
2. Klik op **Add new site** > **Import an existing project**
3. Kies **GitHub** en autoriseer Netlify
4. Selecteer je repository: `TArslan7/SportGemzWebsite`
5. Bij **Branch to deploy**, selecteer `deploy` of `main`
6. Bij **Publish directory**, laat leeg (root directory)
7. Klik op **Deploy site**

Je website krijgt automatisch een URL zoals: `https://sportgemz-xxxxx.netlify.app`

---

## Optie 3: Vercel (Gratis, Zeer Snel)

1. Ga naar https://vercel.com
2. Klik op **Add New Project**
3. Importeer je GitHub repository
4. Bij **Framework Preset**, selecteer **Other**
5. Klik op **Deploy**

Je website krijgt automatisch een URL zoals: `https://sportgemz-website.vercel.app`

---

## Aanbeveling

Voor de snelste setup: **Netlify Drop** (optie 2, drag & drop)
Voor automatische deployments: **GitHub Pages** (optie 1) of **Netlify Git Integration** (optie 2)

