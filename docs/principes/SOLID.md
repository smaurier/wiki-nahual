SOLID est un ensemble de 5 principes pour la conception orientée objet (OOP). Ces principes permettent de créer des systèmes robustes et faciles à maintenir.

---

### **S : Single Responsibility Principle (SRP)**
Une classe ou une fonction doit avoir **une seule responsabilité** ou raison de changer.

#### Mauvais exemple
```javascript
class UserManager {
    createUser(userData) {
        // Logic to create a user
    }
    
    sendWelcomeEmail(userEmail) {
        // Logic to send an email
    }
}
```
**Problème** : Cette classe gère à la fois la création de l'utilisateur et l'envoi d'emails. Ces deux responsabilités devraient être séparées.

#### Bon exemple
```javascript
class UserManager {
    createUser(userData) {
        // Logic to create a user
    }
}

class EmailService {
    sendWelcomeEmail(userEmail) {
        // Logic to send an email
    }
}
```
**Avantage** : Chaque classe a une seule responsabilité, facilitant la maintenance.

---

### **O : Open/Closed Principle (OCP)**
Une classe ou une fonction doit être ouverte à **l'extension** mais fermée à la modification.

#### Mauvais exemple
```javascript
class Payment {
    process(type) {
        if (type === 'creditCard') {
            console.log('Processing credit card payment...');
        } else if (type === 'paypal') {
            console.log('Processing PayPal payment...');
        }
    }
}
```
**Problème** : Chaque fois qu'un nouveau type de paiement est ajouté, il faut modifier la méthode `process`.

#### Bon exemple
```javascript
class Payment {
    process() {
        throw new Error('Method not implemented');
    }
}

class CreditCardPayment extends Payment {
    process() {
        console.log('Processing credit card payment...');
    }
}

class PayPalPayment extends Payment {
    process() {
        console.log('Processing PayPal payment...');
    }
}

// Usage
const payments = [new CreditCardPayment(), new PayPalPayment()];
payments.forEach(payment => payment.process());
```
**Avantage** : On peut ajouter un nouveau type de paiement sans modifier les classes existantes.

---

### **L : Liskov Substitution Principle (LSP)**

Une classe dérivée doit pouvoir être utilisée à la place de sa classe parente sans modifier le comportement.

#### Mauvais exemple
```javascript
class Payment {
    process(type) {
        if (type === 'creditCard') {
            console.log('Processing credit card payment...');
        } else if (type === 'paypal') {
            console.log('Processing PayPal payment...');
        }
    }
}
```
**Problème** : Si une méthode plus complexe utilisait un Rectangle, mais passe un Square, cela pourrait provoquer des comportements inattendus.

#### Bon exemple
Utiliser des classes séparées sans briser leur comportement attendu.

---

### **I : Interface Segregation Principle (ISP)**
Une classe ne doit pas être forcée d'implémenter des interfaces dont elle n'a pas besoin.

#### Mauvais exemple
```javascript
class Worker {
    work() {}
    eat() {}
}

class Robot extends Worker {
    eat() {
        throw new Error('Robots do not eat');
    }
}
```

#### Bon exemple
```javascript
class Worker {
    work() {}
}

class Eater {
    eat() {}
}

class Human extends Worker {
    eat() {
        console.log('Eating...');
    }
}

class Robot extends Worker {}
```

---

### **D : Dependency Inversion Principle (DIP)**
Les modules de haut niveau ne doivent pas dépendre des modules de bas niveau. Les deux doivent dépendre d'abstractions.

#### Mauvais exemple
```javascript
class MySQLDatabase {
    connect() {
        console.log('Connected to MySQL');
    }
}

class App {
    constructor() {
        this.db = new MySQLDatabase();
    }
    start() {
        this.db.connect();
    }
}
```
**Problème** : `App` dépend directement de `MySQLDatabase`.

#### Bon exemple
```javascript
class Database {
    connect() {}
}

class MySQLDatabase extends Database {
    connect() {
        console.log('Connected to MySQL');
    }
}

class App {
    constructor(db) {
        this.db = db;
    }
    start() {
        this.db.connect();
    }
}

// Usage
const app = new App(new MySQLDatabase());
app.start();
```
---

### **📌 Résumé**
> - **SOLID** : Conception évolutive avec 5 principes.
