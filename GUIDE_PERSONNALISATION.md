# Guide de personnalisation - Version Wiki Style

Ce guide vous aide à personnaliser la page biographique au format Wikipedia.

## 📸 Ajouter une photo dans l'infobox

### Étape 1 : Préparer la photo
- Format recommandé : JPG ou PNG
- Dimensions idéales : 300x400 pixels (portrait)
- Nommez le fichier : `photo.jpg`

### Étape 2 : Téléverser la photo
- Dans votre repository GitHub, cliquez sur "Add file" > "Upload files"
- Glissez-déposez `photo.jpg`
- Cliquez sur "Commit changes"

### Étape 3 : Modifier le code HTML
Dans le fichier `index-wiki-style.html`, trouvez cette section (ligne ~166) :

```html
<div class="infobox-image">
    <!-- Pour ajouter une vraie photo, remplacez par: <img src="photo.jpg" alt="Emmanuel Poueme"> -->
    <div class="infobox-image-placeholder">EP</div>
</div>
```

Remplacez par :

```html
<div class="infobox-image">
    <img src="photo.jpg" alt="Emmanuel Poueme">
</div>
```

## ✏️ Modifier l'infobox

L'infobox commence à la ligne ~158. Voici comment modifier chaque section :

### Changer le titre de l'infobox
```html
<div class="infobox-title">Emmanuel Poueme</div>
```

### Modifier les informations biographiques

Trouvez les blocs `infobox-row` et modifiez le contenu dans `infobox-data` :

```html
<div class="infobox-row">
    <div class="infobox-label">Naissance</div>
    <div class="infobox-data">1955<br>Foumbot (quartier Company), Cameroun</div>
</div>
```

### Ajouter une nouvelle ligne d'information

Pour ajouter une nouvelle information (par exemple, "Conjoint"), ajoutez ce code après une ligne existante :

```html
<div class="infobox-row">
    <div class="infobox-label">Conjoint</div>
    <div class="infobox-data">Nom du conjoint</div>
</div>
```

### Modifier les distinctions

```html
<div class="infobox-row">
    <div class="infobox-label">Décorations</div>
    <div class="infobox-data">
        • Commandeur de l'Ordre de la Valeur<br>
        • Médaille d'Or du Travail<br>
        • Ajoutez d'autres distinctions ici
    </div>
</div>
```

## 📝 Modifier le contenu de l'article

### Ajouter une nouvelle section

Copiez ce modèle et insérez-le où vous voulez :

```html
<h2 id="nouvelle-section"><span class="mw-headline">Titre de la section</span></h2>

<p>Votre texte ici...</p>
```

N'oubliez pas d'ajouter la section dans la table des matières :

```html
<li>X <a href="#nouvelle-section">Titre de la section</a></li>
```

### Ajouter une référence

1. Dans le texte, ajoutez :
```html
<a href="#refX" class="reference">[X]</a>
```
(Remplacez X par le numéro de référence suivant)

2. Dans la section "Notes et références", ajoutez :
```html
<li id="refX">↑ <a href="URL" target="_blank">Titre de la source</a>, Date</li>
```

### Ajouter un lien interne

Les liens internes (vers d'autres sections) utilisent des ancres :

```html
<a href="#nom-de-section">Texte du lien</a>
```

### Ajouter un lien externe

```html
<a href="https://example.com" target="_blank">Texte du lien</a>
```

## 🎨 Personnaliser les couleurs

Les couleurs Wikipedia sont standardisées, mais vous pouvez les modifier :

Dans la section `<style>` (lignes 1-500), cherchez ces valeurs :

### Couleur des liens
```css
a {
    color: #0645ad;  /* Bleu des liens */
}

a:visited {
    color: #0b0080;  /* Violet des liens visités */
}
```

### Couleur de l'infobox
```css
.infobox-title {
    background-color: #d3d3d3;  /* Titre de l'infobox */
}

.infobox {
    background-color: #f8f9fa;  /* Fond de l'infobox */
}
```

### Couleur des bordures
```css
border: 1px solid #a2a9b1;  /* Gris des bordures */
```

## 📚 Ajouter un tableau

Pour ajouter un tableau style Wikipedia :

```html
<table class="wikitable">
    <tr>
        <th>En-tête 1</th>
        <th>En-tête 2</th>
    </tr>
    <tr>
        <td>Données 1</td>
        <td>Données 2</td>
    </tr>
</table>
```

## 🏷️ Modifier les catégories

En bas de page, trouvez la section "Catégories" et ajoutez ou retirez des liens :

```html
<a href="#" class="category-link">Nouvelle catégorie</a> •
```

## 🔗 Ajouter des portails

Modifiez la section portails :

```html
<div class="navbox">
    <div class="navbox-title">Portails</div>
    <div style="text-align: center;">
        🇨🇲 Cameroun • 💼 Politique • ⚡ Énergie • 🆕 Nouveau portail
    </div>
</div>
```

## 💾 Sauvegarder vos modifications

Après chaque modification dans GitHub :

1. Cliquez sur l'icône crayon (Edit)
2. Faites vos changements
3. Scrollez en bas
4. Ajoutez un message de commit (ex: "Ajout photo")
5. Cliquez sur "Commit changes"

Attendez 1-2 minutes, puis rafraîchissez votre page GitHub Pages pour voir les changements.

## 🆘 Problèmes courants

### La photo ne s'affiche pas
- Vérifiez que le nom du fichier est exactement `photo.jpg`
- Vérifiez que la photo est bien dans le même dossier que index.html
- Le nom du fichier est sensible à la casse (Photo.jpg ≠ photo.jpg)

### L'infobox est décalée
- Assurez-vous de ne pas avoir supprimé les balises `<div>` de fermeture
- Chaque `<div>` doit avoir son `</div>` correspondant

### Les liens ne fonctionnent pas
- Les ancres doivent correspondre exactement : `id="section"` et `href="#section"`
- N'oubliez pas le `#` dans les liens d'ancre

### La page est cassée après modification
- Vérifiez que vous n'avez pas supprimé accidentellement des balises
- Dans GitHub, cliquez sur "History" pour revenir à une version antérieure

## 📱 Responsive Design

La page s'adapte automatiquement aux mobiles. Sur petit écran :
- L'infobox passe au-dessus du texte
- La navigation s'adapte
- Les tableaux deviennent scrollables

Pas de modification nécessaire !

## ✅ Checklist avant publication

- [ ] Photo ajoutée et affichée correctement
- [ ] Toutes les informations de l'infobox sont à jour
- [ ] Les références sont complètes avec leurs liens
- [ ] La table des matières correspond aux sections
- [ ] Tous les liens fonctionnent
- [ ] Aucune faute d'orthographe
- [ ] Les catégories sont pertinentes
- [ ] La page s'affiche bien sur mobile

---

**Besoin d'aide ?** Consultez la documentation GitHub Pages : https://docs.github.com/pages
