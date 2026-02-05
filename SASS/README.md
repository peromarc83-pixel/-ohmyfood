# Architecture Sass - OhMyFood



---

##  Structure des dossiers

```
sass/
│
├── utils/                    # Outils et helpers
│   ├── _variables.scss       # Variables (couleurs, polices, espacements)
│   ├── _mixins.scss          # Mixins réutilisables
│   └── _animations.scss      # Animations (@keyframes)
│
├── base/                     # Styles de base
│   ├── _base.scss            # Reset et styles globaux
│   └── _typography.scss      # Typographie (h1, h2, p, a)
│
├── layout/                   # Structure de la page
│   ├── _header.scss          # Header page d'accueil
│   ├── _header-menu.scss     # Header page menu
│   ├── _navigation.scss      # Navigation et informations
│   └── _footer.scss          # Pied de page
│
├── components/               # Composants réutilisables
│   ├── _buttons.scss         # Tous les boutons
│   ├── _cards.scss           # Cartes restaurants
│
├── pages/                    # Styles par page
│   ├── _home.scss            # Page d'accueil
│   └── _menu.scss            # Page menu restaurant
│
└── main.scss                 # FICHIER PRINCIPAL
```

---

##  Compilation

### Commande de base
```bash
sass sass/main.scss css/style.css
```

### Mode watch (développement)
```bash
sass --watch sass/main.scss:css/style.css
```

Le mode watch surveille automatiquement les modifications et recompile.

---

##  Intégration HTML

### Page 1 : index.html (Accueil)
```html
<!DOCTYPE html>
<html lang="fr">
<head>
    <link rel="stylesheet" href="css/style.css">
</head>
<body>
    <div class="main-conteneur">
        <header class="header-top">
            <!-- Header avec logo -->
        </header>
        <div class="header-bottom">
            <!-- Barre de localisation -->
        </div>
        <nav class="informations">
            <!-- Titre et CTA -->
        </nav>
        <main>
            <section class="fonctionnement">
                <!-- Boutons fonctionnement -->
            </section>
            <section class="restaurants">
                <!-- Cartes restaurants -->
            </section>
        </main>
        <footer>
            <!-- Footer -->
        </footer>
    </div>
</body>
</html>
```

### Page 2 : menu.html (Menu Restaurant)
```html
<!DOCTYPE html>
<html lang="fr">
<head>
    <link rel="stylesheet" href="css/style.css">
</head>
<body>
    <div class="main-conteneur">
        <header class="header">
            <div class="menu-back">
                <a href="index.html"><i class="fa-solid fa-arrow-left"></i></a>
            </div>
            <div class="logo">
                <img src="images/logo/ohmyfood.png" alt="Logo">
            </div>
        </header>
        <div class="photo-plat">
            <img src="images/restaurant.jpg" alt="Restaurant">
        </div>
        <main class="menu">
            <div class="titre principal">
                <h1>La palette du goût</h1>
                <div class="heart">♥</div>
            </div>
            <section class="entrées">
                <h3>Entrées</h3>
                <!-- Cartes entrées -->
            </section>
            <section class="plats">
                <h3>Plats</h3>
                <!-- Cartes plats -->
            </section>
            <section class="desserts">
                <h3>Desserts</h3>
                <!-- Cartes desserts -->
            </section>
            <div class="btn-commander">
                <button class="btn">Commander</button>
            </div>
        </main>
        <footer>
            <!-- Footer -->
        </footer>
    </div>
</body>
</html>

```

##  Organisation du code

1. utils/ - Variables, mixins, animations

- **_variables.scss** : Toutes les variables du projet
  - Couleurs (primaire, secondaire, tertiaire, backgrounds)
  - Polices (Roboto, Shrikhand)
  - Tailles de police
  - Espacements
  - Border radius
  - Transitions

- **_mixins.scss** : Mixins réutilisables
  - Flexbox (flex-center, flex-column-center, flex-between)
  - Box shadows (light, medium, dark, hover)
  - Gradients
  - Effets hover

- **_animations.scss** : Animations keyframes
  - Apparition progressive des sections menu

2. base/ - Styles de base

- **_base.scss** : Reset et styles globaux (body, conteneurs)
- **_typography.scss** : Typographie (h1, h2, h3, p, a)

 3. layout/ - Structure

- **_header.scss** : Header page d'accueil avec logo et localisation
- **_header-menu.scss** : Header page menu avec bouton retour
- **_navigation.scss** : Section d'informations et titre
- **_footer.scss** : Pied de page avec liens

  4. components/ - Composants réutilisables

- **_buttons.scss** : 
  - Bouton CTA principal
  - Bouton commander
  - Boutons fonctionnement
  - **_cards.scss** : 
  - Cartes restaurants
  - Badge "Nouveau"
  - Animation du cœur
  - **_menu-cards.scss** : 
  - Cartes de plats (entrées, plats, desserts)
  - Titre, description, prix

5. pages/ - Pages spécifiques

- **_home.scss** : 
  - Structure page d'accueil
  - Section fonctionnement
  - Section restaurants
  - **_menu.scss** : 
  - Photo du restaurant
  - Titre et cœur
  - Sections menu (entrées, plats, desserts)
  - Animations d'apparition

---

## Système de design

### Couleurs
```scss
$primary-color: #9356DC    // Violet
$secondary-color: #FF79DA  // Rose
$tertiary-color: #99E2D0   // Vert menthe
```

### Typographie
```scss
$font-main: "Roboto"       // Police principale
$font-logo: "Shrikhand"    // Logo et titres
```

### Espacements
```scss
$spacing-xs: 10px
$spacing-md: 20px
$spacing-xl: 40px
$spacing-xxl: 50px

```
 
##  Ajouter une nouvelle page

1. Créer le fichier Sass : `sass/pages/_nouvelle-page.scss`
2. Ajouter l'import dans `main.scss` : `@import 'pages/nouvelle-page';`
3. Sass recompile automatiquement
4. Créer le HTML et lier `style.css`






