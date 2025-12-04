# 📘 **Compte rendu détaillé de l’analyse du dataset Churn**

## **1. Présentation générale du dataset**

Le dataset contient **667 observations** et décrit des clients d’un opérateur télécom.
L’objectif de l’analyse est de **prédire le churn**, c’est-à-dire si un client quitte l’entreprise (*Churn = True*) ou reste (*Churn = False*).

Le dataset comporte des informations sur :

* l’usage téléphonique (minutes, appels, charges),
* les abonnements (international plan, voicemail plan),
* les interactions avec le service client,
* la localisation (État, code régional),
* et la variable cible *Churn*.

---

## **2. Aperçu des variables**

Les principales variables présentes sont :

### 🔹 **Variables catégorielles**

* **State** : État du client (50 états représentés).
* **Area code** : Code régional (408, 415, 510).
* **International plan** : Oui / Non.
* **Voice mail plan** : Oui / Non.
* **Churn** : Variable cible (True = client quitté).

### 🔹 **Variables numériques**

* **Account length** : Ancienneté du client.
* **Usage journalier, soir, nuit, international** :

  * minutes,
  * calls,
  * charge.
* **Number vmail messages** : Nombre de messages vocaux.
* **Customer service calls** : Nombre d’appels au service client.

---

## **3. Qualité et distribution des données**

* Le dataset ne présente **pas de valeurs manquantes**, ce qui facilite l’analyse.
* Les variables numériques présentent des valeurs cohérentes (pas d’anomalies extrêmes).
* Le churn est **fortement déséquilibré** :

  * **572 clients non churners**
  * **95 churners**
    → Le modèle devra tenir compte de cet imbalance.

---

## **4. Points clés observés dans les données**

### 🔸 **1. Les clients qui partent appellent bien plus le service client**

La variable **Customer service calls** varie de 0 à 8.
Les clients churners sont généralement ceux qui :

* ont appelé plusieurs fois,
* ont eu des problèmes récurrents.

→ C’est un indicateur fort du churn.

---

### 🔸 **2. Le plan international influence le churn**

Les clients ayant **International Plan = Yes** sont plus susceptibles de quitter :

* coût élevé,
* insatisfaction potentielle,
* un des facteurs les plus étudiés dans ce dataset.

---

### 🔸 **3. Usage téléphonique : les clients churners consomment plus**

Notamment pour :

* **Total day minutes**,
* **Total day charge**.

Cela suggère que des clients à forte utilisation peuvent être plus exigeants et donc plus sensibles aux frustrations.

---

## **5. Analyse statistique générale**

Les principales mesures :

* **Account length** (ancienneté) :
  Moyenne ≈ 101 jours → pas de grande différence entre churners et non churners.

* **Total day minutes** :
  Minimum : 0 – Maximum : 351 minutes
  Forte variabilité → important pour l’explication du churn.

* **Total intl charge** :
  Moyenne ≈ 2.76 → correspond à environ 10 minutes en appel international.

* **Customer service calls** :
  Quartiles montrent que 75 % des clients contactent moins de deux fois le service client.

---

## **6. La variable cible : Churn**

* **Churn False : 572 (≈ 86%)**
* **Churn True : 95 (≈ 14%)**

Ce **déséquilibre fort** implique :

* Utilisation de métriques adaptées : ROC, recall, f1-score.
* Éventuellement une technique de rééquilibrage (oversampling, SMOTE, pondération).

---

## **7. Conclusion générale**

Cette base de données est parfaitement adaptée pour un examen de data science, car elle permet d’aborder :

* **Classification binaire**
* **Préparation de données**
* **Analyse exploratoire**
* **Importance des variables**
* **Interprétation business**

Les variables les plus déterminantes dans le churn sont généralement :

* **International plan**
* **Customer service calls**
* **Total day minutes / charge**


Souhaites-tu la version longue, académique et bien rédigée ?

