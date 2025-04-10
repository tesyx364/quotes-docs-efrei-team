# Fonctions principales de l'application

## load_quotes(filepath)

Charge les citations depuis un fichier JSON.

- **Paramètre** : `filepath` (chemin vers le fichier JSON)
- **Retour** : liste de citations (chaînes de caractères)

---

## random_quote(quotes)

Renvoie une citation aléatoire parmi la liste.

- **Paramètre** : `quotes` (liste de citations)
- **Retour** : une citation (chaîne de caractères)

---

## print_quote(quote)

Affiche une citation dans le terminal.

- **Paramètre** : `quote` (la citation à afficher)
- **Effet** : affiche la citation formatée

---

## main()

Fonction principale qui orchestre le programme :

1. Charge les citations.
2. Sélectionne une citation aléatoire.
3. L’affiche.
