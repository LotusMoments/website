## Lotus Moments website

Jekyll-website voor de holistische massagepraktijk Lotus Moments. De site bevat:

- `index.md` – homepage met behandelingen, reviews en Calendly embed.
- `over-mij.md` – persoonlijke introductiepagina.

### Lokale ontwikkeling

```bash
bundle install
bundle exec jekyll serve
```

Surf vervolgens naar `http://localhost:4000`.

### Deploy naar GitHub Pages

1. Push de main branch naar GitHub.
2. Activeer GitHub Pages voor de repository en kies “GitHub Actions” of de `main` branch (`/` root).
3. Voeg optioneel een custom domein toe via de Pages-instellingen.
