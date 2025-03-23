# 📚 Dictionnaire des concepts clés

Voici une liste de définitions pour certains concepts importants en développement logiciel.

---

## **Singleton**

Un **Singleton** est un **pattern de conception** qui garantit qu'une classe n'ait qu'une seule instance et fournit un point d'accès global à cette instance.

### **Caractéristiques** :
- **Instance unique** : Il n'existe qu'une seule instance de la classe.
- **Accès global** : La classe fournit un point d'accès global pour obtenir l'instance unique.
- **Contrôle de la création d'instance** : Le Singleton empêche la création d'une nouvelle instance de la classe en dehors de la classe elle-même.

### **Exemple** :

```typescript
class Singleton {
    private static instance: Singleton;

    private constructor() {}

    public static getInstance(): Singleton {
        if (!Singleton.instance) {
            Singleton.instance = new Singleton();
        }
        return Singleton.instance;
    }

    public showMessage(): void {
        console.log("Je suis un singleton !");
    }
}
```

---

## **Injection de Dépendances**

L'Injection de dépendances (DI) est un pattern de conception qui permet de fournir les dépendances d'une classe de l'extérieur, plutôt que de laisser la classe les créer elle-même. Cela permet de réduire le couplage entre les classes et de faciliter les tests unitaires.

### **Types d'injection** :
- **Injection par constructeur** : Les dépendances sont passées dans le constructeur.
- **Injection par méthode (setter)** : Les dépendances sont injectées via des méthodes après la création de l'objet.
- **Injection par interface** : Les dépendances sont fournies via une interface.

### **Exemple** :

```typescript
interface PaymentService {
    pay(amount: number): void;
}

class PayPalService implements PaymentService {
    pay(amount: number): void {
        console.log(`Paiement de ${amount}€ via PayPal.`);
    }
}

class ShoppingCart {
    private paymentService: PaymentService;

    constructor(paymentService: PaymentService) {
        this.paymentService = paymentService;
    }

    checkout(amount: number): void {
        this.paymentService.pay(amount);
    }
}
```

---

## **SOLID**

Le terme SOLID représente un ensemble de 5 principes de conception pour écrire un code plus propre et maintenable. Ces principes sont les suivants :

- S - Single Responsibility Principle (SRP)
- O - Open/Closed Principle (OCP)
- L - Liskov Substitution Principle (LSP)
- I - Interface Segregation Principle (ISP)
- D - Dependency Inversion Principle (DIP)

[Voir le markdown complet a ce sujet](./SOLID.md)