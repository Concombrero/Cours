# Mes Cours

Ce dépôt contient l'ensemble de mes cours organisés par matière. Chaque matière est un repo Git indépendant (submodule) permettant de synchroniser facilement entre différentes machines.

## Matières

| Matière |  Lien |
|---------|------|
| `variational-methods` | [GitHub](https://github.com/Concombrero/variational-methods) |
| `Numerical-Optimization` | [GitHub](https://github.com/Concombrero/Numerical-Optimization) |
| `Statistical-Learning` | [GitHub](https://github.com/Concombrero/Statistical-Learning) |

## Cloner ce repo (avec tous les cours)

```bash
git clone --recurse-submodules https://github.com/Concombrero/Cours.git
```

Si vous avez déjà cloné sans les submodules :
```bash
git submodule update --init --recursive
```

## Mettre à jour tous les cours

```bash
git submodule update --remote --merge
```

## Ajouter une nouvelle matière

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

## Ajouter un repo existant (fork) comme submodule

```bash
# 1. Fork le repo sur GitHub (bouton "Fork" sur le repo original)

# 2. Ajouter le fork comme submodule
cd /chemin/vers/Cours
git submodule add https://github.com/Concombrero/nom-du-fork.git nom-du-fork
git commit -m "Add nom-du-fork submodule"
git push
```

## Synchroniser un fork avec le repo original (upstream)

Quand le prof met à jour le repo original, voici comment récupérer ses modifications :

```bash
# 1. Aller dans le dossier du submodule (le fork)
cd nom-du-fork

# 2. Ajouter le repo original comme "upstream" (une seule fois)
git remote add upstream https://github.com/PROF/repo-original.git

# 3. Récupérer les modifications du prof
git fetch upstream

# 4. Fusionner les modifications dans votre branche
git merge upstream/main
# ou si la branche principale s'appelle "master" :
git merge upstream/master

# 5. Pousser les modifications vers votre fork
git push origin main  # ou master

# 6. Revenir au repo Cours et enregistrer la mise à jour
cd ..
git add nom-du-fork
git commit -m "Update nom-du-fork from upstream"
git push
```

### En cas de conflit

Si vous avez modifié les mêmes fichiers que le prof :
```bash
# Après le merge, résoudre les conflits dans les fichiers marqués
# Puis :
git add .
git commit -m "Resolve merge conflicts"
git push
```

### Vérifier les remotes configurés

```bash
git remote -v
# Devrait afficher :
# origin    https://github.com/Concombrero/nom-du-fork.git (fetch/push)
# upstream  https://github.com/PROF/repo-original.git (fetch/push)
```

## Commandes utiles

| Action | Commande |
|--------|----------|
| Voir le statut des submodules | `git submodule status` |
| Mettre à jour un submodule | `cd submodule && git pull` |
| Commit dans un submodule | `cd submodule && git add . && git commit -m "msg" && git push` |
| Enregistrer la mise à jour dans Cours | `git add submodule && git commit -m "Update submodule"` |
