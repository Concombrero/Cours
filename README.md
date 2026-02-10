# 📚 Mes Cours

Ce dépôt contient l'ensemble de mes cours organisés par matière.

## 📁 Structure

Chaque matière est un sous-module Git indépendant :

| Matière | Description |
|---------|-------------|
| (à compléter) | (à compléter) |

## 🚀 Cloner ce repo avec les sous-modules

```bash
git clone --recurse-submodules <url-du-repo>
```

## 📝 Ajouter une nouvelle matière

```bash
# Créer le dossier de la matière
mkdir NomMatiere
cd NomMatiere
git init
# Ajouter vos fichiers...
git add .
git commit -m "Initial commit"
cd ..

# Ajouter comme sous-module local
git submodule add ./NomMatiere NomMatiere
```
