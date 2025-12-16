# DNS Configuratie voor sportgemz.nl

## ⚠️ BELANGRIJK: Voor Webapp Deployment

Voor een **webapp** gebruik je **Vercel** of **Netlify** in plaats van GitHub Pages!
Zie `DEPLOYMENT_WEBAPP.md` voor volledige instructies.

---

## GitHub Pages met Eigen Domein (Alleen voor statische websites)

### Stap 1: GitHub Pages Instellingen

1. Push de deploy branch naar GitHub:
   ```bash
   git push origin deploy
   ```

2. Activeer GitHub Pages:
   - Ga naar: https://github.com/TArslan7/SportGemzWebsite/settings/pages
   - Bij **Source**, selecteer **GitHub Actions**
   - Bij **Custom domain**, voer in: `sportgemz.nl`
   - Vink **Enforce HTTPS** aan (na DNS configuratie)

### Stap 2: DNS Records Configureren

Je moet DNS records toevoegen bij je domeinregistrar (waar je sportgemz.nl hebt geregistreerd).

#### Optie A: Apex Domain (sportgemz.nl zonder www)

Voeg deze A records toe bij je DNS provider:

```
Type: A
Name: @ (of leeg, of sportgemz.nl)
Value: 185.199.108.153

Type: A
Name: @
Value: 185.199.109.153

Type: A
Name: @
Value: 185.199.110.153

Type: A
Name: @
Value: 185.199.111.153
```

#### Optie B: www Subdomain (www.sportgemz.nl)

Voeg deze CNAME record toe:

```
Type: CNAME
Name: www
Value: tarslan7.github.io
```

#### Optie C: Beide (Aanbevolen)

Doe beide bovenstaande opties om zowel sportgemz.nl als www.sportgemz.nl te laten werken.

### Stap 3: Wachten op DNS Propagatie

- DNS wijzigingen kunnen 24-48 uur duren om wereldwijd te propageren
- Meestal werkt het binnen enkele minuten tot uren
- Je kunt de status checken via: https://dnschecker.org

### Stap 4: HTTPS Certificaat

- GitHub Pages genereert automatisch een SSL certificaat
- Dit kan enkele minuten tot uren duren nadat DNS correct is geconfigureerd
- Check de status in GitHub Pages settings

---

## Vercel (Aanbevolen voor Webapps)

### DNS Records voor sportgemz.nl op Vercel:

**Voor apex domain (sportgemz.nl):**
```
Type: A
Name: @ (of leeg)
Value: 76.76.21.21
```

**Voor www subdomain:**
```
Type: CNAME
Name: www
Value: cname.vercel-dns.com
```

### Stappen:
1. Deploy op Vercel (zie DEPLOYMENT_WEBAPP.md)
2. Ga naar Project Settings > Domains
3. Voeg `sportgemz.nl` en `www.sportgemz.nl` toe
4. Vercel geeft je exacte DNS instructies
5. Voeg bovenstaande records toe bij je DNS provider
6. Wacht op DNS propagatie (1-24 uur)

---

## Netlify (Alternatief voor Webapps)

Als je liever Netlify gebruikt voor betere DNS ondersteuning:

1. Ga naar https://app.netlify.com
2. Deploy je website (via drag & drop of Git)
3. Ga naar **Domain settings** > **Add custom domain**
4. Voer `sportgemz.nl` in
5. Netlify geeft je DNS instructies (meestal eenvoudiger)

Voor Netlify zijn de DNS records meestal:

```
Type: A
Name: @
Value: [IP die Netlify geeft]

Type: CNAME
Name: www
Value: [Netlify URL]
```

---

## Veelgestelde Vragen

**Q: Welke DNS provider gebruik ik?**
A: Dit is waar je sportgemz.nl hebt geregistreerd (bijv. TransIP, Hostnet, Mijndomein, etc.)

**Q: Werkt het direct?**
A: Nee, DNS wijzigingen hebben tijd nodig om te propageren (meestal 1-24 uur)

**Q: Kan ik testen of DNS werkt?**
A: Ja, gebruik: `dig sportgemz.nl` of check via https://dnschecker.org

