# ✨ Résumé des Principes SOLID en Développement

Les principes SOLID sont des bonnes pratiques de conception logicielle qui rendent le code **plus maintenable, modulaire et extensible**. Voici un résumé de chaque principe :

---

## **1. SRP - Single Responsibility Principle (Responsabilité Unique)**
> **"Une classe ne doit avoir qu'une seule raison de changer."**

**Idée principale :** Chaque classe ou module doit avoir une seule responsabilité, c'est-à-dire qu'il doit être responsable d'une seule fonctionnalité du système.

✅ **Bon exemple :**
- `ShoppingCart` gère uniquement les articles.
- `PaymentProcessor` gère le paiement.
- `Notifier` gère les notifications.

❌ **Mauvais exemple :** Une classe `ShoppingCart` qui gère à la fois les articles, le paiement et les notifications.

---

## **2. OCP - Open/Closed Principle (Ouvert/Fermé)**
> **"Une classe doit être ouverte à l'extension, mais fermée à la modification."**

**Idée principale :** Le code existant ne doit pas être modifié pour ajouter de nouvelles fonctionnalités. Il doit être extensible via des abstractions (ex. interfaces, héritage, polymorphisme).

✅ **Bon exemple :**
- Une interface `PaymentMethod` permet d'ajouter **PayPal**, **Stripe** ou **Google Pay** sans modifier `ShoppingCart`.

❌ **Mauvais exemple :** Modifier `ShoppingCart` à chaque ajout d'un nouveau mode de paiement.

---

## **3. LSP - Liskov Substitution Principle (Substitution de Liskov)**
> **"Une classe dérivée doit pouvoir être utilisée partout où sa classe mère est attendue, sans modifier le comportement du programme."**

**Idée principale :** Une sous-classe ne doit pas casser les attentes liées à sa classe mère. Elle doit pouvoir remplacer sa classe parente sans erreur.

✅ **Bon exemple :**
- `PayPalPayment` et `StripePayment` implémentent la même interface `PaymentMethod` et peuvent être interchangés sans modifier `ShoppingCart`.

❌ **Mauvais exemple :** Une classe `Bird` avec `fly()`, mais `Penguin` hérite de `Bird` et ne peut pas voler. Solution : Créer une interface `FlyingBird` séparée.

---

## **4. ISP - Interface Segregation Principle (Ségrégation des Interfaces)**
> **"Une classe ne doit pas être forcée d'implémenter des méthodes qu'elle n'utilise pas."**

**Idée principale :** Plutôt que d'avoir une seule interface massive avec trop de méthodes, il vaut mieux créer plusieurs interfaces plus petites et spécifiques.

✅ **Bon exemple :**
- `Workable` (avec `work()`) et `Eatable` (avec `eat()`) permettent de distinguer les robots (qui travaillent mais ne mangent pas) des humains (qui font les deux).

❌ **Mauvais exemple :** Une interface `Worker` avec `work()` et `eat()`, obligeant un `Robot` à implémenter `eat()` alors qu'il n'en a pas besoin.

---

## **5. DIP - Dependency Inversion Principle (Inversion des Dépendances)**
> **"Les modules de haut niveau ne doivent pas dépendre des modules de bas niveau. Tous deux doivent dépendre d'abstractions."**

**Idée principale :** Ne dépendre que d'abstractions (ex. interfaces) et non de classes concrètes pour rendre le code flexible et testable.

✅ **Bon exemple :**
- `ShoppingCart` ne dépend pas directement de `PayPalPayment` mais de `PaymentMethod`. Ainsi, on peut facilement changer de moyen de paiement.

❌ **Mauvais exemple :** `ShoppingCart` instancie directement `PayPalPayment`, ce qui rend difficile l'ajout d'autres moyens de paiement.

---

## **🎯 Pourquoi utiliser SOLID ?**
✅ Code plus **lisible et maintenable** 📖  
✅ Moins de **couplage**, plus de **flexibilité** 🔄  
✅ Facilite **les tests unitaires** 🧪  
✅ Permet d'éviter les **effets de bord** 🎯  
✅ Favorise **l'extensibilité** sans modifier le code existant 🚀  

---

## **📌 Résumé des Principes SOLID en une phrase**
- **S**RP : Une classe = Une seule responsabilité.
- **O**CP : On peut **ajouter** des fonctionnalités sans **modifier** le code existant.
- **L**SP : Une sous-classe doit pouvoir **remplacer** sa classe mère sans problème.
- **I**SP : Mieux vaut plusieurs **petites interfaces** qu'une grosse.
- **D**IP : Ne dépendre que **d'abstractions**, pas d'implémentations concrètes.

---