# 📟 Projet ESPHome - Afficheur e-Paper 480x800

Ce projet permet d’afficher diverses informations issues de **Home Assistant** sur un écran **e-Paper Waveshare 7.5" (résolution 480x800)**, connecté via **ESPHome**.
![Aperçu du projet](https://i.imgur.com/fGrRHZi.png)

## 🚀 Fonctionnalités

- Affichage de la **date complète** (personnalisable en français : jour, date, heure).
- Informations issues de Home Assistant :
  - Compteurs (ex. litres, vidage de cave).
  - Dernières mises à jour.
  - Textes dynamiques (plat du jour, événements, etc.).
- Icônes **Material Design Icons (MDI)** intégrées directement en Unicode.
- Lignes et séparateurs personnalisables avec `filled_rectangle`.
- Mise en page optimisée pour la résolution **480x800**.

## 🖼️ Matériel nécessaire

- Un écran **e-Paper Waveshare 7.5" (HD) - Résolution 480x800**  (ESP inclu)
👉 [Lien d’achat officiel](https://www.waveshare.com/product/displays/e-paper/epaper-7.5.htm)
- Connexion réseau Wi-Fi.

## ⚙️ Détails techniques

- **Résolution écran :** 480x800 px (pratique pour calculer facilement les positions `x, y` dans le code).
- **Technologie :** e-Paper (consomme très peu d’énergie, parfait pour affichage statique).
- **Pilotage :** via bibliothèque ESPHome (`display:`).
- **Langage :** YAML avec `lambda` C++ pour personnaliser l’affichage.

## 📂 Structure du code

Quelques éléments principaux utilisés dans le projet :

- `it.printf(x, y, font, align, "Texte : %s", id(mon_text_sensor).state.c_str());`  
  → Pour afficher du texte dynamique (string).

- `it.printf(x, y, font, align, "Valeur : %d", (int)id(mon_capteur).state);`  
  → Pour afficher une valeur numérique.

- `it.filled_rectangle(x, y, width, height);`  
  → Pour tracer des lignes ou zones de séparation.

- `strftime` intégré pour la gestion de la date et de l’heure.

## 🔧 Installation

1. Installer **ESPHome** dans Home Assistant.
2. Récupérer ce projet et copier le fichier YAML dans `/config/esphome/`.
3. Adapter les `id` des entités Home Assistant selon votre configuration.
4. Compiler et flasher l’ESP32.
5. Profiter de l’affichage sur votre écran e-Paper.

## 📌 Notes utiles

- Les dates peuvent être formatées avec `strftime` pour afficher jour/mois/année.
- Les icônes sont intégrées en **Unicode** (MDI). Vérifiez la compatibilité avec la police utilisée.
- Pensez à bien choisir vos polices (`id(bold35)`, `id(book20)`, etc.) pour une lisibilité optimale.
- La mise en page dépend des coordonnées : **(0,0)** correspond au **coin supérieur gauche**.

---

✍️ Projet en cours d’amélioration, n’hésitez pas à forker et adapter selon vos besoins !
