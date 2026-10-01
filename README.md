# Desk Prep

**Démo :** https://pierre-polifeb.github.io/desk-prep/ · [Français](#français) · [English](#english)

---

## Français

### Ce que c'est
Une application web statique pour préparer les entretiens Sales & Trading / Global Markets : environ 1 700 cartes
(options, taux / change / crédit, marchés, structuration, quant, finance d'entreprise, énigmes, questions de motivation et
de CV), répétition espacée, plan du jour, énigmes avec indices et un entraînement au calcul mental.
Interface et cartes en français (`fr/`) et en anglais (`en/`). Projet personnel, construit pour ma propre préparation.

### Technique
- Une seule page HTML par langue, JavaScript sans framework, sans étape de build côté navigateur.
- Les cartes sont dans `fr/cards.json` et `en/cards.json`, chargées avec `fetch()`.
- Bibliothèques chargées depuis cdnjs, versions figées et vérifiées par SRI : marked (Markdown), DOMPurify (nettoyage HTML),
  MathJax (formules, liste fermée d'extensions TeX).
- Politique de sécurité (CSP) stricte dans chaque page : scripts autorisés uniquement par empreinte sha256 ou depuis les
  3 chemins cdnjs, aucune connexion sortante hors du site, aucun formulaire.
- Hébergement : GitHub Pages (fichiers statiques).

Lancer en local :

    python3 -m http.server 8000
    # puis ouvrir http://localhost:8000/

### Confidentialité
- Pas de compte, pas de serveur applicatif : **votre progression reste dans votre navigateur** (localStorage).
  Effacer les données du site la remet à zéro. Rien n'est envoyé ailleurs.
- Aucun traceur, aucun cookie, aucune statistique de visite.
- Les pages de l'application chargent les polices depuis Google Fonts et les bibliothèques depuis cdnjs (Cloudflare) :
  ces services voient donc l'adresse IP du visiteur, comme pour tout site qui les utilise. La page d'accueil et la page 404
  n'appellent aucun service tiers.
- L'entretien simulé par IA de la version privée est désactivé dans cette démo.

### Contenu et crédits
- Les réponses et explications ont été rédigées pour ce projet. Beaucoup de questions sont des classiques qui circulent
  largement ; chaque carte indique dans ses sources les pages où la question (ou une variante) a été signalée.
- Une mention « Signalée en ligne chez <établissement> » veut seulement dire qu'une page publique (forum, site carrières,
  témoignage de candidat) a rapporté la question pour cet établissement. Ce n'est pas vérifié. **Ce projet n'est affilié à
  aucune banque ni aucun établissement cité, et n'est approuvé par aucun d'eux.** Les noms sont cités à titre informatif.
- Les chiffres de marché sont datés dans les cartes et vieillissent vite. Rien ici n'est un conseil en investissement.
- Une partie du contenu s'appuie sur Stack Exchange, sous licence CC BY-SA 4.0 : la liste des cartes concernées et des
  messages d'origine est dans [SOURCES.md](SOURCES.md) (attribution obligatoire, à conserver). Ces cartes (et seulement
  elles) sont partagées sous la même licence. SOURCES.md liste aussi les dépôts GitHub utilisés comme sources de questions
  (licence MIT ou CC0, droits à leurs auteurs) et les licences des bibliothèques.

---

## English

### What it is
A static web app to prepare Sales & Trading / Global Markets interviews: about 1,700 flashcards (options, rates / FX /
credit, markets, structuring, quant, corporate finance, brainteasers, fit and CV questions), spaced repetition, a daily
plan, puzzles with hints and a mental-maths drill. French (`fr/`) and English (`en/`) interface and cards.
A personal project, built for my own preparation.

### Tech
- One HTML page per language, framework-free JavaScript, no client-side build step.
- Cards live in `fr/cards.json` and `en/cards.json`, loaded with `fetch()`.
- Libraries from cdnjs, pinned versions with SRI: marked (Markdown), DOMPurify (HTML sanitising), MathJax (formulas,
  closed list of TeX extensions).
- Strict Content Security Policy in every page: scripts allowed only by sha256 hash or from the 3 cdnjs paths, no outgoing
  connection outside the site, no forms.
- Hosting: GitHub Pages (static files).

Run locally:

    python3 -m http.server 8000
    # then open http://localhost:8000/

### Privacy
- No account, no application server: **your progress stays in your browser** (localStorage). Clearing site data resets
  it. Nothing is sent anywhere else.
- No trackers, no cookies, no analytics.
- The app pages load fonts from Google Fonts and libraries from cdnjs (Cloudflare), so those services see the visitor's IP
  address, as on any site that uses them. The home page and the 404 page call no third-party service.
- The AI mock interview of the private version is disabled in this demo.

### Content and credits
- The answers and explanations were written for this project. Many questions are classic interview questions that
  circulate widely; each card lists in its sources the pages where the question (or a close variant) was reported.
- A "Reported online at <firm>" label only means that a public page (forum, career site, candidate write-up) reported the
  question for that firm. It is not verified. **This project is not affiliated with, or endorsed by, any bank or firm
  named.** Names are given for information only.
- Market figures are dated inside the cards and age quickly. Nothing here is investment advice.
- Part of the content draws on Stack Exchange, under CC BY-SA 4.0: the list of the cards concerned and of the original
  posts is in [SOURCES.md](SOURCES.md) (required attribution, keep it). Those cards (and only those) are shared under the
  same licence. SOURCES.md also lists the GitHub repositories used as question sources (MIT or CC0, copyright their
  authors) and the library licences.
