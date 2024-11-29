(Don't Repeat Yourself)

Ne dupliquez pas du code. Placez la logique réutilisable dans une fonction ou un module.

#### Mauvais exemple
```javascript
function calculateDiscount(price) {
    return price * 0.9;
}

function calculateTax(price) {
    return price * 1.2;
}
```
#### Bon exemple
```javascript
function applyRate(price, rate) {
    return price * rate;
}

const discount = applyRate(100, 0.9);
const tax = applyRate(100, 1.2);
```
**Avantage** : Moins de duplication, plus facile à modifier.

---

### **📌 Résumé**
> - **DRY** : Réduire les duplications.