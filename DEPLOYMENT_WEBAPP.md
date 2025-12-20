# Webapp Deployment voor sportgemz.nl

## Aanbevolen: Vercel (Gratis, Perfect voor Webapps)

Vercel is ideaal voor moderne webapps en ondersteunt:
- ✅ React, Next.js, Vue, Nuxt, Svelte
- ✅ Serverless Functions (Node.js, Python, Go)
- ✅ Automatische HTTPS
- ✅ Custom domain support (sportgemz.nl)
- ✅ Edge Functions
- ✅ Gratis tier is zeer genereus

### Stappen:

1. **Maak account op Vercel:**
   - Ga naar https://vercel.com
   - Login met GitHub account

2. **Import Project:**
   - Klik op **Add New Project**
   - Selecteer repository: `TArslan7/SportGemzWebsite`
   - Branch: `deploy` of `main`
   - Framework Preset: **Other** (of kies je framework als je React/Vue/etc. gebruikt)

3. **Configureer Project:**
   - Root Directory: `./` (laat leeg)
   - Build Command: (leeg als je geen build hebt, anders bv. `npm run build`)
   - Output Directory: (leeg voor statische files, of `dist`/`build` als je een build hebt)
   - Install Command: (leeg als je geen dependencies hebt, anders `npm install`)

4. **Add Custom Domain:**
   - Ga naar Project Settings > Domains
   - Voeg `sportgemz.nl` toe
   - Voeg ook `www.sportgemz.nl` toe (optioneel)

5. **DNS Configuratie:**
   
   Voeg bij je domeinregistrar deze records toe:
   
   Voor apex domain (sportgemz.nl):
   ```
   Type: A
   Name: @
   Value: 76.76.21.21
   ```
   
   Voor www:
   ```
   Type: CNAME
   Name: www
   Value: cname.vercel-dns.com
   ```

6. **Deploy:**
   - Klik op **Deploy**
   - Elke push naar de deploy branch wordt automatisch gedeployed!

---

## Alternatief: Netlify (Ook Gratis)

### Stappen:

1. **Ga naar Netlify:**
   - https://app.netlify.com
   - Login met GitHub

2. **Import Project:**
   - **Add new site** > **Import an existing project**
   - Kies **GitHub**
   - Selecteer `TArslan7/SportGemzWebsite`
   - Branch: `deploy`

3. **Build Settings:**
   - Build command: (leeg als geen build nodig)
   - Publish directory: `.` (of `dist`/`build` als je een build hebt)

4. **Add Custom Domain:**
   - Domain settings > Add custom domain
   - Voeg `sportgemz.nl` toe

5. **DNS Configuratie:**
   
   Netlify geeft je specifieke DNS records. Meestal:
   ```
   Type: A
   Name: @
   Value: [Netlify IP - krijg je van Netlify]
   
   Type: CNAME
   Name: www
   Value: [jouw-site].netlify.app
   ```

---

## Railway (Voor Backend Webapps)

Als je later een backend nodig hebt (Node.js, Python, etc.):

1. **Ga naar Railway:**
   - https://railway.app
   - Login met GitHub

2. **New Project:**
   - Kies **Deploy from GitHub repo**
   - Selecteer `TArslan7/SportGemzWebsite`

3. **Configure:**
   - Railway detecteert automatisch je stack
   - Voor Node.js: voeg `package.json` toe
   - Voor Python: voeg `requirements.txt` toe

4. **Add Domain:**
   - Settings > Networking > Custom Domain
   - Voeg `sportgemz.nl` toe
   - Volg DNS instructies van Railway

---

## Render (Voor Backend Webapps)

1. **Ga naar Render:**
   - https://render.com
   - Login met GitHub

2. **New Web Service:**
   - Connect repository: `TArslan7/SportGemzWebsite`
   - Branch: `deploy`

3. **Configure:**
   - Build Command: (afhankelijk van je stack)
   - Start Command: (afhankelijk van je stack)

4. **Custom Domain:**
   - Settings > Custom Domain
   - Voeg `sportgemz.nl` toe

---

## DNS Algemeen

### Apex Domain (sportgemz.nl zonder www)

**Vercel:**
- A record: `@ → 76.76.21.21`

**Netlify:**
- A record: `@ → [IP van Netlify]`

**Andere platforms:**
- Check hun documentatie voor specifieke IP addresses

### WWW Subdomain

**Meeste platforms:**
- CNAME: `www → [jouw-platform-url]`

---

## Voor Backend/Database

Als je later een backend of database nodig hebt:

### Database Opties:
- **Supabase** (Gratis PostgreSQL)
- **PlanetScale** (Gratis MySQL)
- **MongoDB Atlas** (Gratis MongoDB)
- **Railway Database** (Betaald)

### Backend Opties:
- **Vercel Serverless Functions** (Gratis, Node.js/Python/Go)
- **Netlify Functions** (Gratis, Node.js/Go)
- **Railway** (Betaald, volledige controle)
- **Render** (Gratis tier, volledige controle)

---

## Aanbeveling

**Voor nu (statische/frontend webapp):**
→ **Vercel** (snelste, makkelijkste, gratis)

**Later (met backend):**
→ **Vercel + Supabase** (serverless functions + database)
→ Of **Railway** (volledige controle, betaald)

