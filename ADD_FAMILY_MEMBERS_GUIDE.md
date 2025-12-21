# Quick Reference: Adding More Family Members to the Genealogy Database

## How to Add a New Family Member

### Step 1: Locate the Family Database
Open `genealogy_enhanced.html` in a text editor and find this section (around line 1938):

```javascript
const familyDatabase = {
```

### Step 2: Add Your Entry
Insert a new entry following this template:

```javascript
'member-id': {
    name: 'Full Name As Written',
    ndap: 'Traditional/Praise Name (optional)',
    dates: '1920 - 1990',          // Birth - Death year
    lifespan: '70 ans',            // Age calculation
    generation: 'Génération 4',
    birthPlace: 'Village Name',
    residence: 'Current/Last Known Location',
    spouse: 'Spouse Name',          // If one spouse
    spouses: [                      // If multiple spouses
        { 
            name: 'First Spouse Name',
            dates: '1925-2000',
            place: 'Origin',
            children: ['Child 1', 'Child 2']
        }
    ],
    children: 3,                    // Total number
    childrenList: [                 // Detailed list
        { name: 'Child Name', dates: '1945', place: 'Location' }
    ],
    occupation: 'Primary profession',
    workPlace: 'Where they worked',
    activities: [
        'Activity 1',
        'Activity 2'
    ],
    titles: [
        'Title or Position 1',
        'Title or Position 2'
    ],
    awards: [
        'Award or Honor'
    ],
    notes: 'Historical significance or personal details'
}
```

## Quick Copy-Paste Templates

### For Children of Main Patriarch
```javascript
'daughter-name': {
    name: 'Ngnoumegni [FirstName]',
    generation: 'Génération 5 - Fille',
    birthPlace: 'Foumbot',
    residence: '[Marriage Location]',
    spouse: '[Husband Name]',
    spousePlace: '[Village]',
    children: 3,
    childrenList: [
        { name: '[Child Name]', place: '[Location]' }
    ],
    parents: 'Patriarche et Megni Rachel',
    notes: 'Fille du Patriarche, établie à [Village]'
}
```

### For Spouses
```javascript
'spouse-name': {
    name: '[Full Name]',
    dates: '1906 - 1998',
    generation: 'Génération 4 - Épouse',
    birthPlace: '[Village]',
    spouse: '[Patriarch Name]',
    children: 2,
    childrenList: [
        { name: '[Child]', dates: '[Years]' }
    ],
    activities: ['Activity 1', 'Activity 2'],
    notes: '[Personality and significance]'
}
```

### For Heirs/Successors
```javascript
'heir-name': {
    name: '[Full Name]',
    ndap: '[Traditional Name]',
    born: 1950,
    generation: 'Génération 5 - Héritier',
    birthPlace: '[Village]',
    residence: '[Current Location]',
    spouse: '[Spouse Name] ([Origin])',
    children: 4,
    succession: '[Year Became Heir]',
    title: '[Inherited Title]',
    notes: '[Role and significance]'
}
```

## Data from PDF to Add

### From Chapter 2 (Batchingou Development):
- [ ] **Tchassep Ta'a Tchiendjo** (1862) - Parents of Tinang Joseph
- [ ] **Ngnoumegni Tchakouyap** - Mother
- [ ] **Nougue Pauline** - Sibling
- [ ] **Nagouo Gaston** - Sibling
- [ ] **Ngoko Monique** - Sibling
- [ ] **Kouakep Catherine** - Sibling
- [ ] **Ngomegni Benoit** - Sibling

### From Chapter 3 (Batchingou Family):
- [ ] **Ndomou Juliette (Maman Souhé)** - Aunt
- [ ] **Tagni Meyuka** - Uncle
- [ ] **Ngoko André** - Related family
- [ ] **Wemba Mbiendu Sadrack** - Balengou patriarch

### From Chapter 5 (Balengou Development):
- [ ] **Ouafeu Ngantchou Étienne (Papa Tayou)** - Extended family
- [ ] **Tagni Nguenang Martin** - Makénéné patriarch

---

## Important Field Notes

### dates
- Format: `'YYYY - YYYY'` for birth-death
- Example: `'1898 - 2001'`
- For still-living: just the birth year or `'born: 1950'`

### ndap
- Traditional Bamiléké naming system
- Shows family lineage connection
- Example: "Ta'a Fieu" means "Father of the Chief"

### generation
- Format: `'Génération # - [Role]'`
- Examples:
  - 'Génération 4 - Patriarche'
  - 'Génération 5 - Fils'
  - 'Génération 5 - Héritier'
  - 'Génération 6 - Petits-enfants'

### spouses vs spouse
- **spouse**: Use when there's only ONE spouse
- **spouses**: Use as ARRAY when there are MULTIPLE spouses
  ```javascript
  spouses: [
      { name: 'First', dates: 'X-Y', children: ['A', 'B'] },
      { name: 'Second', dates: 'X-Y', children: [] }
  ]
  ```

### activities
- All professional and community roles
- Example values from PDF:
  - 'Commerce ambulant'
  - 'Plantations de café'
  - 'Chrétienne évangélique'
  - 'Groupe Tambour'
  - 'Garagiste dieseliste'

### titles
- Formal positions and honors
- Example values:
  - 'Ta\'a fieu (Père du chef)'
  - 'Chef de la communauté'
  - 'Notable de la cour royale'
  - 'Assesseur à la Mairie'

---

## ID Naming Convention

Use lowercase, no spaces, with hyphens:
```javascript
'person-full-name'           // Simple names
'ngouzou-theodore'           // First name lowercase
'maman-souhé'                // With accents
'tagni-meyuka'               // Multiple names
'ouafeu-ngantchou-etienne'   // Long names with hyphens
```

## Validation Checklist

Before adding a new person, verify:

- [ ] Name spelling matches PDF exactly
- [ ] Dates are in correct format
- [ ] Location names are consistent with PDF
- [ ] Generation number is correct (count up from Patriarch)
- [ ] Spouse relationships are clear
- [ ] Children list matches parent information
- [ ] No special characters except accents and apostrophes
- [ ] Comma placement is correct (proper JSON format)
- [ ] No missing closing braces `}`

---

## Quick Test

After adding a person, test by:

1. Save the file
2. Open in web browser
3. Go to "People" tab
4. Click on newly added person
5. Verify modal displays all information correctly
6. Check for any console errors (F12 > Console tab)

---

## Common Mistakes to Avoid

❌ **Wrong**: `dates: 1898 - 2001` (missing quotes)
✓ **Right**: `dates: '1898 - 2001'`

❌ **Wrong**: `childrenList: 'Ngoughou, Poueme'` (string instead of array)
✓ **Right**: `childrenList: [{ name: 'Ngoughou' }, { name: 'Poueme' }]`

❌ **Wrong**: Missing comma between entries
```javascript
'person1': { ... }  // Missing comma!
'person2': { ... }
```

✓ **Right**:
```javascript
'person1': { ... },  // Comma present
'person2': { ... }
```

❌ **Wrong**: `occupation: "Commerçant"` (double quotes with French accents)
✓ **Right**: `occupation: 'Commerçant'` (single quotes)

---

## PDF Reference Pages

| Person | Location | PDF Chapter |
|--------|----------|------------|
| Tinang Joseph | Batchingou | Ch. 2, Pages 21-50 |
| Megni Rebecca | Batchingou/Foumbot | Ch. 2, Pages 27-28 |
| Poueme Emmanuel | Batchingou/Foumbot | Ch. 2, Pages 40-41 |
| Family Tree | Batchingou | Ch. 3, Pages 56-62 |
| Balengou Family | Balengou | Ch. 5, Pages 68-77 |
| Bamena Family | Bamena | Ch. 4, Page 63 |

---

## Advanced: Adding Multiple Generations

When adding a whole family line, follow this structure:

```javascript
// Generation 4 - Parents
'grandparent': {
    // ... parent info
    children: 2,
    childrenList: [
        { name: 'Parent1', dates: '1920' },
        { name: 'Parent2', dates: '1925' }
    ]
},

// Generation 5 - Children
'parent-one': {
    // ... child info
    children: 3,
    childrenList: [
        { name: 'Grandchild1', dates: '1950' },
        { name: 'Grandchild2', dates: '1955' },
        { name: 'Grandchild3', dates: '1960' }
    ]
},

// Generation 6 - Grandchildren
'grandchild-one': {
    // ... grandchild info
}
```

---

## Questions?

Refer back to existing entries in the database for examples:
- Look at `'tinang-joseph'` for patriarch template
- Look at `'megni-rebecca'` for spouse template
- Look at `'poueme-emmanuel'` for heir template

