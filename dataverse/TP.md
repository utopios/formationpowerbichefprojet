## **TP Dataverse – Gestion des Formations Interne**

### **Objectif du TP :**  
Modéliser un système de gestion des sessions de formation interne pour une entreprise, uniquement avec **Dataverse** (sans passer par Power Apps ni Power Automate).  
Les stagiaires devront manipuler les **tables, colonnes, relations, vues, formulaires, graphiques et règles métier**.



### **Contexte métier :**  
L’entreprise propose des **formations internes** pour ses employés. Elle souhaite centraliser les informations suivantes :
- Les **formations proposées** (titre, durée, formateur, niveau)
- Les **sessions de formation** (date, lieu, nombre de places, statut)
- Les **employés inscrits** à chaque session


#### 1. **Modélisation des données**
- Créer une table personnalisée `Formation`
- Créer une table `Session de formation` liée à `Formation` (relation 1:N)
- Créer une table `Inscription` liée à `Session de formation` et à `Employé` (table standard)
- Ajouter les colonnes nécessaires dans chaque table :
  - `Formation` : titre, durée (en jours), niveau (débutant/intermédiaire/avancé), formateur
  - `Session de formation` : date de début, lieu, nombre de places, statut (ouverte, complète, annulée)
  - `Inscription` : date d’inscription, statut (confirmée, en attente, annulée)

#### 2. **Vues personnalisées**
- Créer une vue `Formations avancées`
- Créer une vue `Sessions ouvertes`
- Créer une vue `Inscriptions en attente`

#### 3. **Formulaires**
- Modifier le formulaire principal de `Session de formation` :
  - Regrouper les champs en sections (informations générales, logistique)
  - Masquer le champ `lieu` tant que le `statut` n’est pas "ouverte"

#### 4. **Règles métier**
- Ajouter une règle : si le nombre de places est < 5 → afficher un message d’alerte
- Ajouter une règle : si le statut de la session est "annulée", rendre tous les champs en lecture seule

#### 5. **Graphiques**
- Créer un graphique `Nombre de sessions par niveau`
- Créer un graphique `Répartition des inscriptions par statut`
