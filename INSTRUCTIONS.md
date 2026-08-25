# Générer l'APK - Scan Codes

## Prérequis
- Node.js installé (https://nodejs.org)
- Android Studio installé (https://developer.android.com/studio)

## Étapes

1. Ouvre un terminal dans ce dossier `scan-codes-capacitor`

2. Installe les dépendances :
   npm install

3. Ajoute la plateforme Android :
   npx cap add android

4. IMPORTANT - Ajoute les permissions caméra :
   Ouvre android/app/src/main/AndroidManifest.xml
   Ajoute les lignes du fichier ANDROID_PERMISSIONS_A_AJOUTER.txt
   (juste avant la balise <application>)

5. Synchronise :
   npx cap sync android

6. Ouvre le projet dans Android Studio :
   npx cap open android

7. Dans Android Studio :
   Build > Build Bundle(s) / APK(s) > Build APK(s)
   L'APK sera dans : android/app/build/outputs/apk/debug/app-debug.apk

8. Transfère ce fichier .apk sur ton téléphone et installe-le
   (active "Sources inconnues" dans les paramètres Android si demandé)

## Note sur la caméra
Une fois installée en APK avec les permissions ajoutées à l'étape 4,
Android affichera une demande d'autorisation caméra au premier lancement.
Accepte-la pour que le scan fonctionne.
