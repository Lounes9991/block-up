# Empile (application Android)

Le jeu est une page HTML/JavaScript (`app/src/main/assets/index.html`) affichée en plein écran
dans une WebView. Tout fonctionne hors ligne : la musique est générée par le téléphone,
les scores sont gardés sur l'appareil.

## Obtenir l'APK

### Option 1 : Android Studio (la plus simple)
1. Installe Android Studio (https://developer.android.com/studio).
2. Ouvre le dossier `empile-android`. Laisse la synchronisation Gradle se terminer.
3. Branche ton téléphone (débogage USB activé) puis clique sur Run, ou choisis
   Build > Build Bundle(s) / APK(s) > Build APK(s).
4. L'APK est dans `app/build/outputs/apk/debug/app-debug.apk`.
   Copie-le sur ton téléphone et ouvre-le (autorise l'installation d'applications inconnues).

### Option 2 : sans rien installer (GitHub)
1. Crée un dépôt GitHub et envoie-y le contenu de ce dossier.
2. Onglet Actions > Build APK > Run workflow.
3. Quand c'est terminé, télécharge `empile-apk` dans les artefacts de l'exécution.

## Modifier le jeu
Le jeu se trouve dans `app/src/main/assets/index.html`. Réglages utiles en haut du code :
- `REGAIN` : largeur récupérée à chaque perfect (2 % du premier bloc).
- `THRESH` : tolérance pour un perfect.
- `speed()` : vitesse du bloc.

## Publier sur le Play Store
Il faut un APK/AAB signé en mode release et un compte développeur Google Play.
Change aussi `applicationId` dans `app/build.gradle` (par exemple `com.tonnom.empile`).
