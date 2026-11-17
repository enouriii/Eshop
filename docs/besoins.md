# Acteurs et besoins fonctionnels

Projet **eShop** : solution web responsive de vente et d'achat en ligne (sujet S01).
Module Développement Web 1, iTeam University, année universitaire 2026/2027.
Stack : Angular (frontend), Spring Boot (backend), PostgreSQL.

---

## 1. Acteurs

| Acteur | Description | Actions principales |
|---|---|---|
| **Visiteur** | Personne non connectée, sans compte | Consulter le catalogue, rechercher des produits, remplir un panier, s'inscrire, se connecter |
| **Client** | Utilisateur inscrit et connecté | Tout ce que fait le visiteur, et en plus : passer commande, payer, suivre ses commandes et sa livraison, gérer ses adresses et ses favoris |
| **Administrateur** | Gérant de la boutique | Gérer les produits, catégories, stocks, commandes, clients et livreurs, consulter les statistiques |
| **Livreur** | Employé chargé de la livraison | Consulter les commandes à livrer, les prendre en charge, mettre à jour leur statut |

**Rôles techniques (Spring Security) :** `CLIENT`, `ADMIN`, `LIVREUR`.
Le visiteur n'a pas de compte : c'est un utilisateur sans jeton d'authentification.

---

## 2. Besoins fonctionnels

### Comptes
| Code | Besoin | Acteur | Priorité |
|---|---|---|---|
| BF01 | S'inscrire avec nom, e-mail et mot de passe | Visiteur | Obligatoire |
| BF02 | Se connecter et se déconnecter | Tous les comptes | Obligatoire |
| BF03 | Modifier son profil | Client | Obligatoire |

### Catalogue
| Code | Besoin | Acteur | Priorité |
|---|---|---|---|
| BF04 | Consulter la liste des produits | Visiteur, client | Obligatoire |
| BF05 | Consulter la fiche détaillée d'un produit | Visiteur, client | Obligatoire |
| BF06 | Filtrer les produits par catégorie | Visiteur, client | Obligatoire |
| BF07 | Rechercher un produit par mot-clé | Visiteur, client | Obligatoire |
| BF08 | Filtrer par prix et trier les résultats | Visiteur, client | Obligatoire |

### Panier
| Code | Besoin | Acteur | Priorité |
|---|---|---|---|
| BF09 | Ajouter un produit au panier | Visiteur, client | Obligatoire |
| BF10 | Modifier la quantité ou retirer un produit du panier | Visiteur, client | Obligatoire |
| BF11 | Afficher le total du panier | Visiteur, client | Obligatoire |

### Commande et paiement
| Code | Besoin | Acteur | Priorité |
|---|---|---|---|
| BF12 | Valider une commande avec une adresse de livraison | Client | Obligatoire |
| BF13 | Payer la commande (paiement simulé) | Client | Obligatoire |
| BF14 | Consulter l'historique de ses commandes | Client | Obligatoire |
| BF15 | Annuler une commande non expédiée | Client | Obligatoire |

### Espace client
| Code | Besoin | Acteur | Priorité |
|---|---|---|---|
| BF16 | Gérer ses adresses de livraison | Client | Obligatoire |
| BF17 | Gérer ses produits favoris | Client | Obligatoire |

### Livraison
| Code | Besoin | Acteur | Priorité |
|---|---|---|---|
| BF18 | Suivre le statut de sa livraison | Client | Obligatoire |
| BF19 | Consulter les commandes à livrer | Livreur | Obligatoire |
| BF20 | Mettre à jour le statut d'une livraison | Livreur | Obligatoire |

### Back-office
| Code | Besoin | Acteur | Priorité |
|---|---|---|---|
| BF21 | Gérer les produits (ajout, modification, suppression) | Administrateur | Obligatoire |
| BF22 | Gérer les catégories | Administrateur | Obligatoire |
| BF23 | Gérer les stocks | Administrateur | Obligatoire |
| BF24 | Gérer les commandes et affecter un livreur | Administrateur | Obligatoire |
| BF25 | Gérer les clients et les comptes livreurs | Administrateur | Obligatoire |
| BF26 | Consulter le tableau de bord des statistiques de vente | Administrateur | Obligatoire |

### Réservations
| Code | Besoin | Acteur | Priorité |
|---|---|---|---|
| BF27 | Réserver un produit en rupture de stock (version simple) | Client | Obligatoire, réalisé en dernier |

### Extensions (bonus)
À réaliser uniquement si tous les besoins obligatoires sont terminés.

| Code | Besoin | Acteur | Priorité |
|---|---|---|---|
| BF28 | Appliquer un code promo à une commande | Client | Bonus |
| BF29 | Laisser un avis et une note sur un produit | Client | Bonus |
| BF30 | Télécharger la facture au format PDF | Client | Bonus |
| BF31 | Recevoir des e-mails (confirmation de commande, changement de statut) | Client | Bonus |

---

## 3. Besoins non fonctionnels

| Code | Besoin |
|---|---|
| BNF01 | Interface responsive, conçue d'abord pour le mobile, utilisable sur smartphone, tablette et ordinateur |
| BNF02 | Mots de passe hachés (BCrypt) et authentification par jeton JWT |
| BNF03 | Requêtes préparées (JPA), protection contre les failles XSS, CORS restreint |
| BNF04 | Validation des formulaires côté client (Angular) et côté serveur (Spring Boot) |
| BNF05 | Messages d'erreur clairs et temps de chargement raisonnable |
| BNF06 | Code versionné avec Git, secrets stockés dans des variables d'environnement |

---

## 4. Synthèse

| | Nombre |
|---|---|
| Acteurs | 4 (3 rôles techniques) |
| Besoins fonctionnels obligatoires | 27 (BF01 à BF27) |
| Besoins fonctionnels bonus | 4 (BF28 à BF31) |
| Besoins non fonctionnels | 6 |
