 📈 Modèle de Heston – Simulation & Pricing

## 🔍 Description
Ce projet implémente le **modèle de Heston (1993)**, un modèle de volatilité stochastique largement utilisé en finance quantitative.  
Contrairement au modèle de Black–Scholes, la volatilité n’est pas supposée constante mais suit un processus stochastique (CIR).  

L’objectif du projet est de :
- Simuler les trajectoires du couple $(S_t, v_t)$ (prix et variance).
- Estimer le prix d’une option européenne via Monte Carlo.
- (Bonus) **Calibrer** les paramètres du modèle à partir de données réelles avec `scipy.optimize`.

---

## 📚 Rappels théoriques

Le modèle est défini par le système d’équations différentielles stochastiques :

\[
dS_t = \mu S_t \, dt + \sqrt{v_t}\, S_t \, dW_t^{(1)}, 
\]
\[
dv_t = \kappa (\theta - v_t)\, dt + \sigma \sqrt{v_t}\, dW_t^{(2)},
\]

où :
- $S_t$ : prix de l’actif  
- $v_t$ : variance instantanée  
- $\mu$ : rendement attendu  
- $\kappa$ : vitesse de rappel vers $\theta$  
- $\theta$ : variance de long terme  
- $\sigma$ : volatilité de la variance (vol-of-vol)  
- $\rho$ : corrélation entre les chocs sur $S_t$ et $v_t$

---

## 🛠️ Contenu du repo

- `Heston_Model.ipynb` → Notebook Python contenant :
  - Simulation de trajectoires $(S_t, v_t)$
  - Pricing d’options européennes via Monte Carlo
  - Calibration optionnelle des paramètres
- `rapport.pdf` → Explication mathématique détaillée du modèle et du projet
- `README.md` → Ce fichier :)

---

## ▶️ Utilisation

### 1. Cloner le repo
```bash
git clone https://github.com/tonpseudo/Heston_Model.git
cd Heston_Model

2. Installer les dépendances

pip install numpy scipy matplotlib

3. Lancer le notebook

Ouvrir dans Jupyter ou Google Colab :

jupyter notebook Heston_Model.ipynb

📊 Résultats attendus

    Visualisation des trajectoires du prix $S_t$ et de la variance $v_t$

    Estimation du prix d’une option européenne par simulation Monte Carlo

    (Bonus) Paramètres calibrés sur données de marché
