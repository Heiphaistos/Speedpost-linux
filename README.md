# SpeedPost — Linux

Application Linux de **SpeedPost** : envoyez des fichiers par un simple lien chiffré, sans compte.
Serveur, site et application web : [SpeedPost-Web](https://github.com/Heiphaistos/SpeedPost-Web) · Windows : [SpeedPost-Windows](https://github.com/Heiphaistos/SpeedPost-Windows).

## Fonctionnalités

- Glisser-déposer dans la fenêtre, ou **clic droit sur un fichier → Ouvrir avec → SpeedPost** (paquet .deb)
- Envoi par morceaux avec **reprise automatique**, bouton Annuler
- **Lien copié automatiquement** à la fin de l'envoi + notification du bureau
- Options : titre, message, expiration, mot de passe, e-mail du destinataire (facultatif)
- **Mes envois** : recopier un lien, l'ouvrir, supprimer le transfert du serveur
- Icône dans la zone de notification, une seule instance
- Chiffrement AES-256 : la clé est générée sur votre machine et n'existe que dans le lien

## Installation

Téléchargez dans les **Releases** (ou sur la page *Applications* de votre site SpeedPost) :
- **Debian / Ubuntu / Mint** : `sudo apt install ./SpeedPost-x.y.z-amd64.deb` (ajoute SpeedPost au menu et à *Ouvrir avec*) ;
- **Toutes distributions** : `chmod +x SpeedPost-x.y.z-x86_64.AppImage` puis lancez-le (pour *Ouvrir avec*, utilisez AppImageLauncher ou Gear Lever).

Au premier lancement, indiquez l'adresse de votre serveur dans **Réglages** (et le mot de passe d'envoi s'il est privé).

## Compiler

Les paquets sont générés par GitHub Actions à chaque push ; un tag `v*` crée une release avec l'AppImage et le .deb.

```bash
npm install
npm start                         # SPEEDPOST_SERVER=http://localhost:3080 pour un serveur local
npm run dist                      # dist/SpeedPost-*.AppImage et dist/SpeedPost-*.deb
SPEEDPOST_WEB_DIR=../SpeedPost-Web npm test   # compatibilité avec le serveur
```

## Licence

MIT
