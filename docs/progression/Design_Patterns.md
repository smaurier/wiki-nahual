# Les Design Patterns en JavaScript

## 1. Singleton

**C'est quoi ?**  
T'imagines une cafetière unique dans toute la maison. Tout le monde doit utiliser cette seule cafetière, pas une de plus.

**À quoi ça sert ?**  
Quand tu veux un truc qui n'a besoin d'exister qu'UNE SEULE FOIS (par exemple, une config d'application).

```javascript
const Singleton = (function () {
  let instance;

  function createInstance() {
    return { message: "Je suis unique" };
  }

  return {
    getInstance: function () {
      if (!instance) {
        instance = createInstance();
      }
      return instance;
    },
  };
})();

const obj1 = Singleton.getInstance();
const obj2 = Singleton.getInstance();
console.log(obj1 === obj2); // true (même objet)
```

---

## 2. Factory

**C'est quoi ?**  
Imagine un **magasin de pizzas**. Tu commandes une pizza (margherita, pepperoni...), et ils te la font. Mais toi, tu sais pas comment ils la fabriquent exactement.

**À quoi ça sert ?**  
Créer des objets sans te soucier de **comment** ils sont faits.

```javascript
function PizzaFactory(type) {
  if (type === "margherita") {
    return { type: "Margherita", ingredients: ["tomate", "mozza"] };
  } else if (type === "pepperoni") {
    return { type: "Pepperoni", ingredients: ["tomate", "mozza", "pepperoni"] };
  }
}

const pizza1 = PizzaFactory("margherita");
const pizza2 = PizzaFactory("pepperoni");
console.log(pizza1, pizza2);
```

---

## 3. Observer

**C'est quoi ?**  
Imagine t'es dans une salle de classe. Dès que le prof écrit au tableau, tout le monde (les élèves) regarde et réagit.

**À quoi ça sert ?**  
Quand tu veux que des trucs soient **au courant automatiquement** d'un changement.

```javascript
class Prof {
  constructor() {
    this.eleves = [];
  }

  ajouterEleve(eleve) {
    this.eleves.push(eleve);
  }

  ecrire(message) {
    console.log("Prof : " + message);
    this.eleves.forEach((eleve) => eleve.reagir(message));
  }
}

class Eleve {
  reagir(message) {
    console.log("Élève : Je réagis au message - " + message);
  }
}

const prof = new Prof();
const eleve1 = new Eleve();
const eleve2 = new Eleve();

prof.ajouterEleve(eleve1);
prof.ajouterEleve(eleve2);

prof.ecrire("Interro surprise !");
```

---

## 4. Module

**C'est quoi ?**  
C'est comme une boîte à outils. Tout est bien rangé dedans, et tu peux prendre que ce dont t'as besoin.

**À quoi ça sert ?**  
Organiser ton code pour qu'il soit plus clair.

```javascript
const Outils = (function () {
  function marteau() {
    console.log("BANG !");
  }

  function tournevis() {
    console.log("SCRATCH !");
  }

  return {
    marteau: marteau,
    tournevis: tournevis,
  };
})();

Outils.marteau(); // BANG !
Outils.tournevis(); // SCRATCH !
```

---

## 5. Prototype

**C'est quoi ?**  
Imagine que t'as un **moule** pour faire des gâteaux. À partir du même moule, tu peux faire plein de gâteaux identiques.

**À quoi ça sert ?**  
Créer des objets rapidement en réutilisant un modèle.

```javascript
const gateauPrototype = {
  ingredients: [],
  ajouterIngredient(ingredient) {
    this.ingredients.push(ingredient);
  },
};

const gateau1 = Object.create(gateauPrototype);
gateau1.ajouterIngredient("chocolat");
console.log(gateau1.ingredients); // ["chocolat"]

const gateau2 = Object.create(gateauPrototype);
gateau2.ajouterIngredient("vanille");
console.log(gateau2.ingredients); // ["vanille"]
```

---

## 6. Decorator

**C'est quoi ?**  
Tu prends une pizza nature et tu ajoutes des toppings dessus (champignons, fromage, jambon). Ça reste une pizza, mais elle est **customisée**.

**À quoi ça sert ?**  
Ajouter des trucs en plus à un objet **sans le modifier directement**.

```javascript
function pizzaDeBase() {
  return "Pizza nature";
}

function ajouterFromage(pizza) {
  return pizza + " + fromage";
}

function ajouterChampignons(pizza) {
  return pizza + " + champignons";
}

let maPizza = pizzaDeBase();
maPizza = ajouterFromage(maPizza);
maPizza = ajouterChampignons(maPizza);

console.log(maPizza); // Pizza nature + fromage + champignons
```

---

## TL;DR : Les design patterns en version ultra simple

- **Singleton** : Une cafetière unique pour tout le monde.
- **Factory** : Un resto qui fait des pizzas sans te montrer la recette.
- **Observer** : Les élèves qui écoutent le prof.
- **Module** : Une boîte à outils bien rangée.
- **Prototype** : Un moule à gâteaux pour en faire plein pareil.
- **Decorator** : Une pizza nature qu’on customise avec des toppings.
