# MY FINN — gestion de mes finances personnelles (Flutter)

App Android / iPhone pour suivre toutes mes finances, sur le modèle de mes fichiers de trésorerie mensuels (FCFA, séparateur de milliers = point).

## Fonctionnalités

- **Comptes** : Compte Coris, Nita, Visa Nita, Amana, Cash, Bons d'essence (hors disponible). Ajout, modification, archivage.
- **Opérations** : dépenses, entrées, transferts (avec frais de retrait). Champ **Pour qui ?** : Moi, Chez moi, ou une personne (dépense pour elle, donation, cadeau).
- **Catégories** personnalisables avec icône, couleur et budget mensuel.
- **Prêts & dettes** : on me doit / je dois, remboursements partiels, échéances, retards.
- **Bilan du mois** : graphique en anneau, répartition pour qui, par personne, prêts du mois, entrées par source, tendance 6 mois, postes.
- **Modernes** : mode sombre, masquer les montants, code PIN + empreinte, saisie rapide des opérations fréquentes, catégorie devinée depuis le libellé, opérations récurrentes (salaire, tontine…), alertes (échéances, budgets), rapport du mois au format Trésorerie à partager, sauvegarde / restauration.
- **Import de septembre 2026** (Réglages) : retombe exactement sur les soldes du 30/09 (disponible 1.479.050).
- **Hors ligne** : données stockées sur le téléphone (fichier `myfinn.json`).

## Lancer / fabriquer

```bash
flutter pub get
flutter run              # sur un téléphone branché ou un émulateur Android Studio
flutter test             # tests des calculs
flutter build apk        # APK dans build/app/outputs/flutter-apk/app-release.apk
flutter build web        # aperçu navigateur (démo préremplie au 30/09/2026)
```

Sur GitHub, `.github/workflows/android-apk.yml` fabrique l'APK automatiquement et le publie dans **Releases**.

## Organisation du code

- `lib/models.dart` : comptes, catégories, opérations, prêts, remboursements, récurrences
- `lib/store.dart` : données, calculs (soldes, bilans, prêts), import, sauvegarde, rapport
- `lib/screens/` : écrans ; `lib/widgets/` : composants visuels ; `lib/theme.dart` : couleurs clair / sombre
- `tool/build_seed.py` : convertit un fichier `Tresorerie_*.md` en données d'import
