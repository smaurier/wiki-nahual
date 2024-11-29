KISS (Keep It Simple, Stupid)

Gardez votre code simple et clair.

#### Mauvais exemple
```javascript
function isEven(num) {
    if (num % 2 === 0) {
        return true;
    } else {
        return false;
    }
}
```
#### Bon exemple
```javascript
function isEven(num) {
    return num % 2 === 0;
}
```
**Avantage** : Un code plus simple est plus facile à lire et à maintenir.

---

### **📌 Résumé**
> - **KISS** : Garder le code simple.