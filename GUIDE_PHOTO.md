# 📸 Guide : Télécharger et ajouter la photo au repository

## Méthode 1 : Télécharger depuis Wikimedia Commons (Recommandé)

### Étape 1 : Télécharger l'image

1. **Allez sur la page Wikimedia Commons :**
   https://commons.wikimedia.org/wiki/File:Emmanuel_Poueme.jpg

2. **Cliquez sur l'image** pour l'agrandir

3. **Clic droit sur l'image** et sélectionnez "Enregistrer l'image sous..."

4. **Nommez le fichier exactement :** `photo.jpg`
   ⚠️ Important : Le nom doit être exactement "photo.jpg" (en minuscules)

5. **Enregistrez** dans un dossier facile à retrouver (ex: Bureau, Téléchargements)

### Étape 2 : Ajouter l'image à votre repository GitHub

**Option A : Via l'interface web GitHub (plus simple)**

1. Allez sur votre repository GitHub dans votre navigateur
2. Cliquez sur **"Add file"** > **"Upload files"**
3. Glissez-déposez le fichier `photo.jpg` ou cliquez sur "choose your files"
4. Sélectionnez `photo.jpg` depuis votre ordinateur
5. Dans le message de commit, écrivez : "Ajout photo Emmanuel Poueme"
6. Cliquez sur **"Commit changes"**

**Option B : Via ligne de commande Git (pour utilisateurs avancés)**

```bash
# Dans le dossier de votre repository local
git add photo.jpg
git commit -m "Ajout photo Emmanuel Poueme"
git push origin main
```

### Étape 3 : Vérifier que ça fonctionne

1. Attendez 1-2 minutes que GitHub Pages se mette à jour
2. Allez sur votre page : `https://votre-nom.github.io/nom-du-repo/`
3. La photo devrait s'afficher automatiquement

Si la photo ne s'affiche pas :
- Videz le cache du navigateur (Ctrl+F5 ou Cmd+Shift+R)
- Vérifiez que le fichier s'appelle exactement `photo.jpg` (minuscules)
- Vérifiez que le fichier est à la racine du repository (même niveau que index.html)

---

## Méthode 2 : Si vous avez déjà la photo sur votre ordinateur

Si vous avez déjà une photo d'Emmanuel Poueme :

1. **Renommez votre fichier photo en :** `photo.jpg`
2. **Suivez l'Étape 2** ci-dessus pour l'ajouter au repository
3. Assurez-vous que la photo est au format JPG ou PNG

---

## 📋 Structure du repository après ajout

Votre repository devrait ressembler à ceci :

```
votre-repository/
├── index.html                    (version moderne)
├── index-wiki-style.html        (version Wikipedia)
├── photo.jpg                    ← VOTRE PHOTO ICI
├── README.md
└── autres fichiers...
```

⚠️ **Important :** Le fichier `photo.jpg` doit être au même niveau que les fichiers HTML, **PAS** dans un sous-dossier.

---

## 🔧 Résolution des problèmes

### La photo ne s'affiche pas

**Problème 1 : Mauvais nom de fichier**
- Solution : Le fichier doit s'appeler exactement `photo.jpg` (minuscules)
- ❌ Mauvais : `Photo.jpg`, `photo.JPG`, `emmanuel.jpg`, `image.jpg`
- ✅ Bon : `photo.jpg`

**Problème 2 : Mauvais emplacement**
- Solution : Le fichier doit être à la racine (même dossier que index.html)
- ❌ Mauvais : `images/photo.jpg`, `photos/photo.jpg`
- ✅ Bon : `photo.jpg` (à la racine)

**Problème 3 : Cache du navigateur**
- Solution : Videz le cache avec Ctrl+F5 (Windows) ou Cmd+Shift+R (Mac)

**Problème 4 : GitHub Pages n'a pas mis à jour**
- Solution : Attendez 2-3 minutes et rafraîchissez la page

### L'image est trop grande ou trop petite

Si l'image ne s'affiche pas bien, vous pouvez la redimensionner avant de l'ajouter :

**Dimensions recommandées :**
- Largeur : 300-400 pixels
- Hauteur : 400-500 pixels
- Format : Portrait (vertical)

Utilisez un éditeur d'image gratuit comme :
- Windows : Paint, Photos
- Mac : Aperçu (Preview)
- En ligne : https://www.iloveimg.com/resize-image

---

## 🎯 Vérification rapide

Avant de penser que ça ne marche pas, vérifiez :

✅ Le fichier s'appelle exactement `photo.jpg` (minuscules)
✅ Le fichier est à la racine du repository
✅ Le fichier est au format JPG ou PNG
✅ Vous avez attendu 2-3 minutes après le commit
✅ Vous avez vidé le cache du navigateur

---

## 📱 Format d'image optimal

Pour un meilleur rendu :
- **Format** : JPG (recommandé) ou PNG
- **Taille du fichier** : Moins de 500 Ko
- **Dimensions** : 300x400 pixels minimum
- **Qualité** : Haute résolution
- **Orientation** : Portrait (photo verticale)
- **Arrière-plan** : Uni de préférence

---

## ✅ Checklist finale

Avant de fermer ce guide, assurez-vous :

- [ ] Vous avez téléchargé l'image depuis Wikimedia Commons
- [ ] Le fichier s'appelle exactement `photo.jpg`
- [ ] Vous avez téléversé le fichier sur GitHub
- [ ] Le fichier est à la racine du repository
- [ ] Vous avez attendu quelques minutes
- [ ] La photo s'affiche correctement sur votre page

---

**Besoin d'aide ?**

Si vous rencontrez des difficultés, vérifiez :
1. La documentation GitHub Pages : https://docs.github.com/pages
2. Que votre repository est bien public
3. Que GitHub Pages est activé dans Settings > Pages

---

**🎉 Une fois la photo ajoutée, votre page biographique sera complète !**
