# Projet E5 - DevSecOps Docker - ESTIAM Paris

## Auteur : Celaire OKA

## 📄 Description
Ce projet a été réalisé dans le cadre du module DevSecOps à l'ESTIAM Paris. Il consiste à déployer une stack multi-applications via Docker Compose, en respectant les consignes suivantes :

- Déployer 4 applications (dont 1 statique HTML)
- Mettre en place un reverse proxy (Nginx) pour 3 d'entre elles
- Laisser une application exposée directement (pour pentest)
- Utiliser un seul fichier `docker-compose.yml`
- Optimiser les Dockerfiles
- Publier les images sur Docker Hub

## 📆 Arborescence du projet
```
Deployed_app/
├── appli1-simpleco/             # HTML statique
├── appli2-arise/                # React + Vite
├── appli3-estiprojback/         # Node.js API
├── appli4-estiamrh-front/       # React Js
├── appli5-ecoresp/              # Vite + React (exposée directement)
├── reverse-proxy/
│   └── nginx.conf
├── docker-compose.yml
└── README.md
```

## 🌐 Accès aux applications

---------------------------------------------------------------------------------------------------
| URL                            | Application               | Description                        |
|--------------------------------|---------------------------|------------------------------------|
| `http://localhost/ecogame/`    | Simple_Ecoresp            | Site HTML statique                 |
| `http://localhost/arise/`      | Arise_app                 | App React/Vite                     |
| `http://localhost/api/employes`| Estiprojback              | API Node.js                        |
| `http://localhost/front/`      | Estiamrh Front            | Frontend React                     |
| `http://localhost:5173/`       | Ecoresp_v2                | Exposée directement (pour pentest) |
---------------------------------------------------------------------------------------------------

## 🛠️ Services et reverse proxy
Un reverse proxy Nginx redirige les flux HTTP vers les bonnes applications. 
Une application est volontairement laissée en accès direct pour simuler un scénario de test de sécurité whitebox.

## 🚀 Lancement du projet

### 1. Cloner les repositories dans un meme dossier. Ici, nous l'avons nomme "Deployed_app"
```bash
git clone https://github.com/celaireo/Simple_Ecoresp.git appli1-simpleco
git clone https://github.com/celaireo/Arise_app.git appli2-arise
git clone https://github.com/celaireo/estiprojback.git appli3-estiprojback
git clone https://github.com/celaireo/estiamrh-front.git appli4-estiamrh-front
git clone https://github.com/celaireo/Ecoresp_v2.git appli5-ecoresp
```

### 2. Lancer la stack Docker
```bash
cd Deployed_app
docker compose up --build -d
```

### 3. Tester dans le navigateur
- http://localhost/ecogame/
- http://localhost/arise/
- http://localhost/api/employes
- http://localhost/front/
- http://localhost:5173/

## 🔧 Commandes utiles
```bash
# Voir les conteneurs en cours
docker ps

# Voir les logs
docker logs app3

# Arrêter la stack
docker compose down
```

## 📅 Checklist de vérification
- [x] Tous les conteneurs démarrent sans erreur
- [x] Les ports sont correctement exposés
- [x] Le reverse proxy redirige vers les bonnes apps
- [x] Une application est bien en accès direct
- [x] Toutes les apps sont accessibles via navigateur

## 🌍 Liens GitHub des apps
- https://github.com/celaireo/Simple_Ecoresp.git
- https://github.com/celaireo/Arise_app.git
- https://github.com/celaireo/estiprojback.git
- https://github.com/celaireo/estiamrh-front.git
- https://github.com/celaireo/Ecoresp_v2.git

## 📖 Auteur
**Celaire OKA**  
Projet réalisé dans le cadre du module E5 DevSecOps - ESTIAM Paris

