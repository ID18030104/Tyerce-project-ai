# ⚖️ Tyerce — IA de résolution de litiges entre particuliers

Bienvenue sur **Tyerce** !

Tyerce est une application que j’ai imaginée pour répondre à un vrai problème : les litiges lors de transactions entre particuliers (un vélo non livré, un objet cassé, une caution non rendue, etc.).

L’idée : **placer une IA comme tiers de confiance**.
👉 Quand il y a conflit, les deux parties déposent leurs échanges (discussion JSON), le contrat signé (PDF), et leurs preuves (photos).
Ensuite, **Tyerce IA lit tout, applique la loi française (Code civil, Code de la consommation, Code du commerce…) et rend une décision justifiée** : qui a raison et pourquoi.

---

## 🚀 Le notebook principal

Tout le cœur du projet se trouve dans ce notebook :
🔗 [Tyerce\_IA\_V1\_3\_VF.ipynb](https://github.com/ID18030104/Tyerce-project-ai/blob/main/Tyerce_IA_V1_4_VF.ipynb)

Ce notebook montre comment :

* Importer et traiter une discussion JSON.
* Lire et analyser un contrat PDF.
* Interpréter des preuves images.
* Utiliser un **RAG (base de lois françaises en XML)**.
* Charger et exécuter **mon modèle Qwen LoRA fine-tuné sur des litiges**.
* Générer un verdict clair et argumenté.

---

## 📂 Données fournies

Pour tester Tyerce, deux fichiers utiles sont inclus :

1. **Base RAG légale**

   * 📄 `Tyerce-data-legalV2XML.xml`
   * Contient des articles du Code civil, du Code de la consommation et du Code du commerce.
   * L’IA les utilise pour justifier ses décisions.

2. **Exemple de litige**

   * 📄 `litige-velo-livraison.json`
   * Une conversation réaliste autour d’un vélo jamais livré.
   * Permet de tester la chaîne complète.

Ces fichiers doivent être placés dans ton dossier de travail au même niveau que le notebook.

---

## 🎨 Interface Streamlit

J’ai déjà construit une **interface Streamlit complète** pour Tyerce :

* Un **design premium** avec affichage de la discussion comme sur un vrai téléphone.
* Import direct des fichiers (JSON, PDF, images).
* Gestion de la base RAG et du modèle Qwen fine-tuné.
* Génération d’un **verdict instantané** affiché de manière élégante.

Pour la lancer :

```bash
streamlit run app.py
```

---

## ⚙️ Installation et exécution en local

### 1. Cloner le projet

```bash
git clone https://github.com/ID18030104/Tyerce-project-ai.git
cd Tyerce-project-ai
```

  ### Google Collab

Si vous utilisez un notebook Google collab (conseillé), après avoir cloné le projet (avec la commande: !git clone https://github.com/ID18030104/Tyerce-project-ai.git dans une cellule), les fichiers apparaitront sur votre gauche, il faudra les télécharger (les 3). Pour le notebook Tyerce-data-legalV2XML, après l'avoir téléchargé, il faut aller dans la barre de tâce, fichier>Ouvrir le notebook, puis selectionner le notebook Tyerce-data-legalV2XML. 

### 2. Créer un environnement virtuel

```bash
python -m venv tyerce-venv
source tyerce-venv/bin/activate  # Linux / Mac
tyerce-venv\Scripts\activate     # Windows
```

### 3. Installer les dépendances principales

```bash
pip install torch transformers accelerate bitsandbytes sentencepiece pdfplumber pytesseract lxml streamlit
```

### 4. Lancer le notebook ou Streamlit

Notebook :

```bash
jupyter notebook Tyerce_IA_V1_3_VF.ipynb
```

Ou directement l’interface :

```bash
streamlit run app.py
```

---

## 💻 Ressources nécessaires

* ✅ **GPU recommandé** : au moins 8 Go VRAM (RTX 3060 ou supérieur). Fonctionne bien sur Google collab avec une A100.
* ⚠️ Sur CPU, ça fonctionne pour tester, mais ce sera lent.
* 📦 Le modèle est **Qwen-2.5 LoRA fine-tuné** : spécialisé sur des litiges et le droit français.

---

## 🧠 Fonctionnement

1. Importer une **discussion JSON**.
2. Ajouter un **contrat PDF** si disponible.
3. Joindre des **preuves images**.
4. L’IA analyse tout ça + consulte le **RAG légal**.
5. Elle rend un **verdict clair** du type :

```
"A la vue de l’article L.216-2 du Code de la consommation et de la clause de remboursement du contrat, l’acheteur est en droit d’obtenir un remboursement complet."
```

---

## 🌍 Vision

Tyerce est plus qu’un POC technique :

* C’est une **solution d’escrow intelligente**.
* Elle automatise la **médiation entre particuliers**.
* L’objectif final : une **application mobile**, où l’argent est bloqué, et libéré automatiquement selon la décision de l’IA.

---

✍️ **Auteur :** Projet développé par [Isaac Derhy](https://github.com/ID18030104)
📌 Repo : [Tyerce-project-ai](https://github.com/ID18030104/Tyerce-project-ai)


