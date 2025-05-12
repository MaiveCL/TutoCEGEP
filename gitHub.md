## 🔄 Travailler avec Git dans la VM
# Préparation
LA PREMIERE FOIS :

## 🔑 Première connexion à GitHub depuis la VM (une seule fois par VM)

Configurer ton identité Git :
```bash
git config --global user.name "Ton Nom"
git config --global user.email "ton@email.com"
```
Assure-toi d'être dans le dossier de ton projet
```bash
cd /var/www/dossierDuProjet
```
copie l'url épuré du projet (à la racine, mais sans le trea/main à la fin)
- *Le dossier de destination doit être vide !*
```bash
git clone url_du_dépôt_git
```

### 📍 1. Se placer dans le dossier de travail
```bash
cd /var/www/dossierDeTravail/
```

### 🌱 2. S'assurer d'être sur `main` et le mettre à jour
```bash
git checkout main
git pull origin main
```

### 🌿 3. Créer une nouvelle branche de travail
*C'est le -b qui fabrique la branche*
```bash
git checkout -b nom-de-ta-branche
```

# ✍️ 4. Travailler sur ton projet

## Assure-toi d'être sur la bonne branche
*Sans le -b tu basculeras vers cette branche*
```bash
git checkout nom-de-ta-branche
```
Modifier tes fichiers `.phtml`, `.php`, `.css`, `.js`, etc.

### 🔎 5. Vérifier les changements
```bash
git status
```

### ➕ 6. Ajouter les fichiers modifiés
```bash
git add .
```

### 🧹 7. Vérifier à nouveau avant de commit
```bash
git status
```

### ✅ 8. Faire un commit clair
```bash
git commit -m "Message clair sur ce que tu as modifié"
```
---
### 🚀 9. Pousser ta branche sur GitHub la première fois
  ```bash
  git push --set-upstream origin nom-de-ta-branche
  ```
## 9. a les fois suivantes 
```bash
git push
```
---

### 🔄 10. Fusionner ta branche dans main (quand ton travail est prêt)
Tester ton projet en local. Si tout est correct :
```bash
git checkout main
git pull origin main
git merge nom-de-ta-branche
git push origin main
```
Optionnel (supprimer la branche si tu ne l'utilisera plus) :
```bash
git branch -d nom-de-ta-branche
```

### ⚡ 11. Se tenir à jour avec main pour continuer à travailler
Avant de commencer une nouvelle tâche ou pour continuer sur la même branche (selon ce qui est plus pertinent) :

- **Option A : Créer une nouvelle branche :**
  ```bash
  git checkout main
  git pull origin main
  git checkout -b nouvelle-branche
  ```

- **Option B : Continuer sur la même branche :**
  ```bash
  git checkout nom-de-ta-branche
  git merge main
  ```

---
