# Compiler l'APK avec GitHub (depuis le téléphone, sans PC)

## 1. Créer le dépôt
1. Ouvre github.com (ou l'appli GitHub) sur ton téléphone, connecte-toi (crée un compte gratuit si besoin)
2. Crée un nouveau dépôt (bouton "+") → nomme-le par exemple `scan-codes-app` → Public ou Privé, peu importe → Create repository

## 2. Envoyer les fichiers
Depuis la page du dépôt vide, utilise "uploading an existing file" (ou "Add file" > "Upload files") et envoie TOUS les fichiers/dossiers de ce paquet, en respectant la même structure de dossiers :
- package.json
- capacitor.config.json
- www/index.html
- .github/workflows/build-apk.yml

Astuce sur mobile : GitHub (site ou appli) permet de glisser/sélectionner plusieurs fichiers à la fois, mais recrée bien les dossiers `www/` et `.github/workflows/` exactement à ces emplacements (tu peux taper le chemin complet dans le nom de fichier lors de l'upload, ex: `www/index.html`).

## 3. Lancer la compilation
1. Une fois les fichiers envoyés (commit), va dans l'onglet **Actions** du dépôt
2. Le workflow "Build APK" se lance automatiquement après le push. Sinon clique dessus puis "Run workflow"
3. Attends 5-10 minutes que le build se termine (cercle vert = succès)

## 4. Télécharger l'APK
1. Clique sur le run terminé (coche verte)
2. En bas, dans "Artifacts", télécharge **scan-codes-app-apk** (fichier .zip contenant l'APK)
3. Décompresse, tu obtiens `app-debug.apk`
4. Transfère-le sur ton téléphone et installe-le (autorise "Sources inconnues" si demandé)

C'est tout — tout se passe sur les serveurs de GitHub, aucun logiciel à installer sur ton téléphone.

## Fonctionnement hors connexion
Le workflow télécharge les bibliothèques nécessaires (scanner + export Excel) et les intègre DANS l'APK au moment du build. Résultat : une fois l'application installée sur le téléphone, elle fonctionne **sans connexion internet** pour scanner et exporter. Il faut juste une connexion internet le jour du build (sur les serveurs GitHub, pas sur ton téléphone) et lors de l'installation de l'APK.
