# Ethone DevTools

Une boîte à outils développeur rapide, responsive et pensée pour la confidentialité. Les entrées sont traitées dans le navigateur et ne sont envoyées à aucun backend.

## Développement local

```bash
npm install
npm run dev
```

## Production

```bash
npm run build
npm run preview
```

Le site statique généré se trouve dans `dist/`.

## Déploiement Cloudflare

### Cloudflare Workers

Dans **Workers & Pages → votre Worker → Settings → Builds**, définissez la commande de déploiement sur `npm run deploy`. Le script construit d’abord `dist/`, puis lance Wrangler. Aucun build command séparé n’est nécessaire avec ce réglage.

Pour déployer depuis un terminal local :

```bash
npm run deploy
```

Le `wrangler.toml` configure le Worker et ses assets statiques.

### Cloudflare Pages

1. Connectez le dépôt Git dans **Workers & Pages → Create → Pages**.
2. Choisissez `npm run build` comme commande de build et `dist` comme répertoire de sortie.
3. Aucune variable d’environnement n’est requise.

Déploiement Pages avec Wrangler :

```bash
npm run build
npx wrangler pages deploy dist --project-name ethone-devtools
```

## Outils disponibles

Formateur/validateur JSON, Base64, UUID v4, hash SHA-256/384/512 (Web Crypto), mots de passe cryptographiquement aléatoires, timestamp Unix, conversion HEX/RGB/HSL, QR code, diff textuel, test Regex, encodeur URL et conversion de casse. Les outils s’exécutent dans le navigateur ; aucun backend ne reçoit vos données.
