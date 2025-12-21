# 🌳 GENEALOGY - GUIDE D'UTILISATION

## 📁 Fichiers Nécessaires

Vous avez besoin de **2 fichiers** dans le même dossier:

1. **genealogy.html** ← Le fichier principal
2. **family-data.json** ← Les données familiales

## 🚀 Comment Utiliser

### Sur votre ordinateur:
```
1. Télécharger les 2 fichiers
2. Les mettre dans le MÊME dossier
3. Double-cliquer sur genealogy.html
4. ✓ Ça ouvre dans le navigateur et fonctionne!
```

### Sur GitHub:
```
1. Créer un dossier genealogy/ dans votre repo
2. Uploader genealogy.html
3. Uploader family-data.json
4. Accéder via: https://username.github.io/repo/genealogy/genealogy.html
5. ✓ Fonctionne!
```

## ✅ Comment Vérifier que ça Marche

1. **Ouvrez genealogy.html** dans le navigateur
2. **Appuyez sur F12** (ouvrir la console)
3. Vous devriez voir:
   ```
   Script démarré
   Chargement du fichier family-data.json...
   ✓ Données chargées: {...}
   renderAll() appelé
   renderOverview()
   renderGenerations()
   renderPeople()
   renderLocations()
   ```
4. **Testez chaque onglet:**
   - 📋 **Aperçu**: 3 cartes des personnes principales
   - 🌳 **Générations**: Arbre avec tous les noms, 6 niveaux
   - 👥 **Personnes**: Tous les 5 membres de la famille
   - 📍 **Localités**: 3 localités principales

5. **Testez un clic:**
   - Cliquez sur un NOM dans l'arbre (Générations)
   - Une MODAL doit s'ouvrir avec les détails
   - ✓ Si ça marche, c'est bon!

## 🎯 Fonctionnalités

### Navigation
- Cliquer sur les onglets change de section
- Barre de recherche filtre les cartes

### Cliquer sur les Personnes
- Cliquer sur n'importe quel nom → Ouvre une MODAL
- La modal affiche TOUS les détails:
  - Dates, génération, lieu
  - Épouses et enfants
  - Profession et titres
  - Distinctions et notes

### Fermer la Modal
- Appuyez sur **Escape**
- OU cliquez le bouton **×**
- OU cliquez en dehors de la modal

## 🌳 Données Actuelles

### Personnes (5):
1. **Ta'a Fieu Tagni Tinang Joseph** - Patriarche (1898-2001)
2. **Poueme Emmanuel** - Héritier (1950)
3. **Megni Ngongang Rebecca** - 1ère épouse (1906-1998)
4. **Ngoughou Théodore** - Fils (1947-2017)
5. **Langue Samuel** - Fils (1968-2017)

### Générations:
- Gen 1: Wetio Kouamou (~1770s)
- Gen 2: Magni Kouabou, Cha Neyou, Wajiamou (~1800s)
- Gen 3: Ngnoumegni (~1868)
- Gen 4: **Patriarche Tinang Joseph** (1898)
- Gen 5: **Héritier Poueme Emmanuel** + 4 autres (1950)
- Gen 6: 20+ petits-enfants (1975+)

### Localités (3):
- **Batchingou** - Foyer principal
- **Foumbot** - Centre commercial
- **Balengou** - Ancêtres

## 🔴 Si ça ne fonctionne pas

### Erreur: "family-data.json not found"
```
→ Les 2 fichiers ne sont pas dans le MÊME dossier
→ Vérifiez qu'ils sont côte à côte
```

### Les noms ne s'affichent pas
```
→ Attendez 2 secondes que le JSON charge
→ Rafraîchissez la page (F5)
→ Videz le cache (Ctrl+Shift+Suppr)
```

### Les clics sur les noms ne fonctionnent pas
```
→ Ouvrez F12 → Console
→ Vérifiez qu'il n'y a pas d'erreur rouge
→ Testez un clic et regardez la console
```

### Tout est blanc
```
→ Attendez que le JSON charge (3-5 secondes)
→ Ouvrez F12 pour voir les erreurs
→ Testez dans Firefox si Chrome ne marche pas
```

## 📝 Ajouter Plus de Personnes

Éditez **family-data.json**:

```json
{
  "families": [
    {
      "id": "ma-personne",
      "name": "Prénom Nom",
      "dates": "YYYY - YYYY",
      "generation": "Génération X",
      "role": "Rôle",
      "birthPlace": "Lieu",
      "children": 2,
      "occupation": "Profession",
      "notes": "Contexte historique"
    }
  ]
}
```

Puis:
1. Sauvegardez le fichier JSON
2. Rafraîchissez la page (F5)
3. Nouvelle personne apparaît!

## 🎨 Personnaliser les Couleurs

Éditez **genealogy.html**, cherchez les couleurs:
```css
#2d5016  = Vert principal
#d97706  = Or (accent)
#059669  = Vert clair
```

Remplacez par vos couleurs préférées.

## 📊 Architecture Fichiers

```
mon-dossier/
├── genealogy.html          (Le site)
└── family-data.json        (Les données)
```

C'est tout! Simple et efficace.

## ✨ Points Clés

✓ 2 fichiers seulement  
✓ Pas de serveur nécessaire  
✓ Fonctionne offline après chargement initial  
✓ JSON facile à éditer  
✓ Responsive (mobile/desktop)  
✓ Données complètes pour chaque personne  

## 📞 Dépannage

**Si vous avez toujours des problèmes:**

1. Ouvrez F12 (Console)
2. Regardez les messages (ils racontent ce qui se passe)
3. Vérifiez que family-data.json est au bon endroit
4. Testez sur un autre navigateur
5. Essayez un serveur local si besoin

---

**Status:** ✅ FONCTIONNEL

