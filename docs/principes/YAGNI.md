(You Aren't Gonna Need It)

N'implémentez pas des fonctionnalités qui ne sont pas nécessaires immédiatement.

#### Mauvais exemple
```javascript
function fetchData() {
    // Add caching logic (unnecessary now)
    console.log('Fetching data...');
}
```
#### Bon exemple
```javascript
function fetchData() {
    console.log('Fetching data...');
    // Plus tard, ajoutez le cache seulement si nécessaire.
}
```
**Avantage** : Moins de code inutile à maintenir.

---

### **📌 Résumé**
> - **YAGNI** : Éviter les fonctionnalités inutiles.