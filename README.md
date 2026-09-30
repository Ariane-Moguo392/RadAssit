RadAssist — Assistant radiologue virtuel

 Présentation et instructions de Lancement

RadAssist est un prototype pédagogique réalisé dans le cadre d’un projet collectif à l’EFREI. Il permet d’expérimenter une chaîne d’intelligence artificielle autour de radiographies thoraciques, avec une interface de démonstration, une API et des outils d’évaluation.

Contributrice : Ariane Emmanuelle MOGUO. 
Le projet initial a été créé par Badr Tajini avec l’équipe mentionnée dans le README du dossier RadAssist.

À quoi sert ce projet ?

Le projet permet de :
- charger une image de radiographie thoracique ;
- produire un résultat expérimental : normal, opacité suspectée ou incertain ;
- présenter une justification et les limites du résultat ;
- enregistrer les résultats et évaluer les performances sur des cas synthétiques.

Il met en pratique Python, Streamlit, FastAPI, SQLite et les méthodes d’évaluation en intelligence artificielle.

> Ce prototype est destiné à l’apprentissage et à la démonstration. Il n’est pas un dispositif médical et ne doit pas être utilisé pour établir un diagnostic.

Organisation

Le code se trouve dans le dossier `RadAssist/` :
- `app/` : interface utilisateur ;
- `api/` : API FastAPI ;
- `src/` : traitement, inférence et garde-fous ;
- `data/` : données de démonstration ;
- `eval/` : évaluation des résultats ;
- `docs/` : documentation ;
- `tests/` : vérifications du projet.

 Installation et lancement sous Windows

Installer Python et Git, puis ouvrir un terminal et exécuter :

*bash
git clone https://github.com/Ariane-Moguo392/RadAssit.git
cd RadAssit/RadAssist
python -m venv .venv
```

Activer l’environnement dans l’invite de commandes Windows :

```bat
.venv\Scripts\activate
```

Installer les dépendances et lancer l’interface :

*bash
python -m pip install -r requirements.txt
python -m streamlit run app/streamlit_app.py


Ouvrir ensuite l’adresse affichée dans le terminal, généralement :
http://localhost:8501

Lancement de l’API

Dans un deuxième terminal, depuis le dossier `RadAssist`, activer le même environnement puis exécuter :

*bash
python -m uvicorn api.main:app --reload
```

La documentation interactive de l’API est accessible à :
http://127.0.0.1:8000/docs

 Évaluation de démonstration

```bash
python eval/run_evaluation.py --mode toy
```

Ces commandes lancent le projet sur l’ordinateur. Sa publication sur GitHub partage le code ; elle ne met pas automatiquement l’application en ligne.

 Licence

Le code est distribué sous licence MIT. Les crédits de l’équipe initiale et la licence sont conservés dans le dossier RadAssist.
