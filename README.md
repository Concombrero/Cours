# 📚 Mes Cours

Ce dépôt contient l'ensemble de mes cours organisés par matière. Chaque matière est un repo Git indépendant (submodule) permettant de synchroniser facilement entre différentes machines.

## 📁 Structure

```
Cours/
├── .gitmodules
├── README.md
└── variational-methods/    ← Submodule
    ├── notes/
    ├── exercises/
    ├── exams/
    └── resources/
```

## 📖 Matières

| Matière | Description | Lien |
|---------|-------------|------|
| `variational-methods` | Méthodes variationnelles | [GitHub](https://github.com/Concombrero/variational-methods) |

## 🚀 Cloner ce repo (avec tous les cours)

```bash
git clone --recurse-submodules https://github.com/Concombrero/Cours.git
```

Si vous avez déjà cloné sans les submodules :
```bash
git submodule update --init --recursive
```

## 🔄 Mettre à jour tous les cours

```bash
git submodule update --remote --merge
```

## 📝 Ajouter une nouvelle matière

```bash
# 1. Créer le repo sur GitHub (github.com/new)

# 2. Créer le dossier local et initialiser
mkdir nom-matiere && cd nom-matiere
git init
# Ajouter vos fichiers...
git add . && git commit -m "Initial commit"

# 3. Lier à GitHub et pousser
git remote add origin https://github.com/Concombrero/nom-matiere.git
git push -u origin master

# 4. Revenir au repo Cours et ajouter comme submodule
cd ..
rm -rf nom-matiere
git submodule add https://github.com/Concombrero/nom-matiere.git nom-matiere
git commit -m "Add nom-matiere submodule"
git push
```

## 💡 Commandes utiles

| Action | Commande |
|--------|----------|
| Voir le statut des submodules | `git submodule status` |
| Mettre à jour un submodule | `cd submodule && git pull` |
| Commit dans un submodule | `cd submodule && git add . && git commit -m "msg" && git push` |
| Enregistrer la mise à jour dans Cours | `git add submodule && git commit -m "Update submodule"` |
